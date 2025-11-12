---
solution: Journey Optimizer
product: journey optimizer
title: ライブアクティビティチャネルの設定
description: Adobe Experience Platform Mobile SDK統合を設定する方法について説明します
feature: Channel Configuration
role: Admin
level: Intermediate
hide: true
hidefromtoc: true
source-git-commit: ce6bfca78d097588b5958c10c721b29b7013b3e2
workflow-type: tm+mt
source-wordcount: '465'
ht-degree: 1%

---


# Adobe Experience Platform Mobile SDKとライブアクティビティの統合 {#mobile-live-config-sdk}

>[!BEGINSHADEBOX]

* [ライブアクティビティの基本を学ぶ](get-started-mobile-live.md)
* [ライブアクティビティ設定](mobile-live-configuration.md)
* **[Adobe Experience Platform Mobile SDKとライブアクティビティの統合](mobile-live-configuration-sdk.md)**
* [ライブアクティビティの作成](create-mobile-live.md)
* [よくある質問](mobile-live-faq.md)
* [ライブアクティビティキャンペーンレポート](../reports/campaign-global-report-cja-activity.md)


>[!ENDSHADEBOX]

Adobe Experience Platform Mobile SDKは、Appleのライブアクティビティに対する組み込みのサポートを提供します。 これにより、アプリを開かなくても、アプリでリアルタイムの動的な更新をロック画面と動的な島に直接表示できます。

1. [必要なモジュールの読み込み](#import)

   **[!DNL AEPMessaging]**、**[!DNL AEPMessagingLiveActivity]**、**[!DNL ActivityKit]** のモジュールを読み込みます。

1. [&#x200B; 属性の定義 &#x200B;](#attributes)

   `LiveActivityAttributes` に準拠し、`LiveActivityData` 属性と `ContentState` 属性を含めます。

1. [ライブアクティビティの登録](#register)

   SDKの初期化後に `Messaging.registerLiveActivity()` を使用します。

1. [ウィジェット設定の作成](#widget)

   ロック画面と Dynamic Island インターフェイスの両方に `ActivityConfiguration` を実装します。

1. [ライブアクティビティをローカルで開始（オプション）](#local)

   ライブアクティビティは、Journey Optimizerからリモートで開始することも、アプリケーションコード内でローカルに開始することもできます。

1. [デバッグサポートの追加（オプション）](#debug)

   Assuranceに `LiveActivityAssuranceDebuggable` を実装します。

正しい設定と互換性を確保するために、次の最小バージョンがインストールされていることを確認します。

>[!BEGINSHADEBOX]

**前提条件：**

* **iOS:**
   * **iOS16.1 以降**：基本的なライブアクティビティ機能
   * **iOS 17.2 以降**: プッシュツースタートのサポート
   * **iOS 18 以降**: ブロードキャストチャンネルのサポート
* **Xcode:** 14.0 以降
* **Swift:** 5.7 以降
* **依存関係：** AEPCore、AEPMessaging、AEPMessagingLiveActivity、ActivityKit

>[!ENDSHADEBOX]

## 手順 1：必要なモジュールのインポート {#import}

開始するには、まず **[!DNL AEPMessaging]**、**[!DNL AEPMessagingLiveActivity]**、**[!DNL ActivityKit]** モジュールを読み込む必要があります。

```swift
import AEPMessaging
import AEPMessagingLiveActivity
import ActivityKit
```

## 手順 2：ライブアクティビティ属性の定義 {#attributes}

`LiveActivityAttributes` プロトコルに準拠する構造体を作成します。 ライブアクティビティの静的データと動的コンテンツの状態の両方を定義します。

主なコンポーネントは次のとおりです。

* Adobe Experience Platform固有のデータを含む **`liveActivityData`** （必須）。
   * 個々のユーザーの場合：`LiveActivityData(liveActivityID: "unique-id")` を使用します
   * ブロードキャストの場合：`LiveActivityData(channelID: "channel-id")` を使用します

* 静的属性、ユースケースに固有のカスタムプロパティ（`restaurantName` など）。

* ライブアクティビティのライフサイクル中に更新できる動的データを定義する **`ContentState`**。 それは `Codable` と `Hashable` に従わなければなりません。

* 定義済みリスト `LiveActivityOrigin`、アクティビティがアプリケーション内でローカルに開始されたか、iOS 17.2 以降でサポートされているプッシュトゥスタート通知を使用してリモートに開始されたかを示します。 この値を使用すると、SDKで、データ収集中のローカルで開始されたライブアクティビティとリモートでトリガーされたライブアクティビティを区別できます。

**例**

```swift
@available(iOS 16.1, *)
struct FoodDeliveryLiveActivityAttributes: LiveActivityAttributes {
    // Mandatory: AEP Integration Data
    var liveActivityData: LiveActivityData
    
    // Static Attributes: Custom properties that do not change
    var restaurantName: String
    
    // Dynamic Content State: Data that can be updated
    struct ContentState: Codable, Hashable {
        var orderStatus: String
    }
}
```

```swift
@available(iOS 16.1, *)
public struct LiveActivityData: Codable {
    /// Unique identifier for broadcast Live activity channels
    public let channelID: String?
     
    /// Unique identifier for individual Live activities
    public let liveActivityID: String?
     
    /// Indicates local vs remote creation
    public let origin: LiveActivityOrigin?
     
    // Initializers
    public init(channelID: String)        // For broadcast Live activities
    public init(liveActivityID: String)   // For individual Live activities
}
```

また、アプリに複数のライブアクティビティタイプを登録できます。

```swift
if #available(iOS 16.1, *) {
    Messaging.registerLiveActivity(AirplaneTrackingAttributes.self)
    Messaging.registerLiveActivity(FoodDeliveryLiveActivityAttributes.self)
    Messaging.registerLiveActivity(GameScoreLiveActivityAttributes.self)
}
```

## 手順 3：ライブアクティビティの登録 {#register}

SDKの初期化後、ライブ アクティビティ タイプを `AppDelegate` に登録します。これにより、次のことが可能になります。

* 自動プッシュトゥスタートトークンコレクションを有効にする（iOS 17.2 以降）
* ライブアクティビティ更新トークンを自動的に収集します
* ライフサイクル管理とイベント追跡を可能にする

**食品配信ライブアクティビティの例：**

```swift
if #available(iOS 16.1, *) {
    Messaging.registerLiveActivity(FoodDeliveryLiveActivityAttributes.self)
}
```

## 手順 4：ライブアクティビティ ウィジェットの作成 {#widgets}

ライブアクティビティはウィジェットを通じて表示されます。ウィジェットバンドルと設定を作成する必要があります。

**食品配信ライブアクティビティの例：**

```swift
@main
struct FoodDeliveryWidgetBundle: WidgetBundle {
    var body: some Widget {
        FoodDeliveryLiveActivityWidget()
    }
}

@available(iOS 16.1, *)
struct FoodDeliveryLiveActivityWidget: Widget {
    var body: some WidgetConfiguration {
        ActivityConfiguration(for: FoodDeliveryLiveActivityAttributes.self) { context in
            // Lock Screen UI
            VStack {
                Text("Order from \(context.attributes.restaurantName)")
                Text("Status: \(context.state.orderStatus)") // possible status may include "Ordered", "Order accepted", "Preparing", "On the Way","Delivered"
            }
        } dynamicIsland: { context in
            // Dynamic Island UI
            DynamicIsland {
                // Expanded UI
            } compactLeading: {
                // Compact leading UI
            } compactTrailing: {
                // Compact trailing UI
            } minimal: {
                // Minimal UI
            }
        }
    }
}
```

## 手順 5：ライブアクティビティのローカルでの開始（オプション） {#local}

Journey Optimizerではライブ アクティビティをリモートから開始できますが、ローカルで開始することもできます。

**食品配信ライブアクティビティの例：**

```swift
let attributes = FoodDeliveryLiveActivityAttributes(
    liveActivityData: LiveActivityData(liveActivityID: "order123"),
    restaurantName: "Pizza Palace"
)

let contentState = FoodDeliveryLiveActivityAttributes.ContentState(
    orderStatus: "Ordered"
)

let activity = try Activity<FoodDeliveryLiveActivityAttributes>.request(
    attributes: attributes,
    contentState: contentState,
    pushType: .token
)
```

## 手順 6：デバッグサポートの追加（オプション） {#debug}

必要に応じて、Adobe Assuranceでライブアクティビティスキーマをデバッグできます。

**食品配信ライブアクティビティの例：**

```swift
@available(iOS 16.1, *)
extension FoodDeliveryLiveActivityAttributes: LiveActivityAssuranceDebuggable {
    static func getDebugInfo() -> (attributes: FoodDeliveryLiveActivityAttributes, state: ContentState) {
        return (
            FoodDeliveryLiveActivityAttributes(
                liveActivityData: LiveActivityData(liveActivityID: "debug-order-123"),
                restaurantName: "Debug Restaurant"
            ),
            ContentState(orderStatus: "Ordered")
        )
    }
}
```


