---
solution: Journey Optimizer
product: journey optimizer
title: ライブアクティビティチャネルの設定
description: Adobe Experience Platform Mobile SDK 統合を設定する方法について説明します
feature: Channel Configuration
role: Admin
level: Intermediate
hide: true
hidefromtoc: true
source-git-commit: ce6bfca78d097588b5958c10c721b29b7013b3e2
workflow-type: ht
source-wordcount: '465'
ht-degree: 100%

---


# Adobe Experience Platform Mobile SDK とのライブアクティビティ統合 {#mobile-live-config-sdk}

>[!BEGINSHADEBOX]

* [ライブアクティビティの基本を学ぶ](get-started-mobile-live.md)
* [ライブアクティビティの設定](mobile-live-configuration.md)
* **[Adobe Experience Platform Mobile SDK とのライブアクティビティ統合](mobile-live-configuration-sdk.md)**
* [ライブアクティビティの作成](create-mobile-live.md)
* [よくある質問](mobile-live-faq.md)
* [ライブアクティビティキャンペーンレポート](../reports/campaign-global-report-cja-activity.md)


>[!ENDSHADEBOX]

Adobe Experience Platform Mobile SDK は、Apple のライブアクティビティのビルトインのサポートを提供します。 これにより、アプリを開かなくても、ロック画面と Dynamic Island でリアルタイムの動的な更新を直接表示できます。

1. [必要なモジュールをインポート](#import)

   **[!DNL AEPMessaging]**、**[!DNL AEPMessagingLiveActivity]**、**[!DNL ActivityKit]** のモジュールを読み込みます。

1. [属性の定義](#attributes)

   `LiveActivityAttributes` に準拠し、`LiveActivityData` 属性と `ContentState` 属性を含めます。

1. [ライブアクティビティを登録](#register)

   SDK の初期化後に `Messaging.registerLiveActivity()` を使用します。

1. [ウィジェット設定を作成](#widget)

   ロック画面と Dynamic Island インターフェイスの両方に `ActivityConfiguration` を実装します。

1. [ローカルでライブアクティビティを開始（オプション）](#local)

   ライブアクティビティは、Journey Optimizer を通じてリモートで開始することも、アプリケーションコード内でローカルで開始することもできます。

1. [デバッグサポートを追加（オプション）](#debug)

   Assuranceに `LiveActivityAssuranceDebuggable` を実装します。

正しい設定と互換性を確保するために、次の最小バージョンがインストールされていることを確認します。

>[!BEGINSHADEBOX]

**前提条件：**

* **iOS：**
   * **iOS 16.1 以降**：基本的なライブアクティビティ機能
   * **iOS 17.2 以降**：プッシュトゥスタートのサポート
   * **iOS 18 以降**：ブロードキャストチャネルのサポート
* **Xcode：** 14.0 以降
* **Swift：** 5.7 以降
* **依存関係：** AEPCore、AEPMessaging、AEPMessagingLiveActivity、ActivityKit

>[!ENDSHADEBOX]

## 手順 1：必要なモジュールをインポート {#import}

開始するには、まず **[!DNL AEPMessaging]**、**[!DNL AEPMessagingLiveActivity]**、**[!DNL ActivityKit]** モジュールを読み込む必要があります。

```swift
import AEPMessaging
import AEPMessagingLiveActivity
import ActivityKit
```

## 手順 2：ライブアクティビティ属性を定義 {#attributes}

`LiveActivityAttributes` プロトコルに準拠する構造体を作成します。これにより、ライブアクティビティの静的データと動的コンテンツの状態の両方が定義されます。

主なコンポーネントは次のとおりです。

* Adobe Experience Platform 固有のデータを含む **`liveActivityData`**（必須）。
   * 個々のユーザーの場合：`LiveActivityData(liveActivityID: "unique-id")` を使用します
   * ブロードキャストの場合：`LiveActivityData(channelID: "channel-id")` を使用します

* 静的属性、ユースケースに固有のカスタムプロパティ（例：`restaurantName`）。

* ライブアクティビティライフサイクル中に更新できる動的データを定義する **`ContentState`**。これは、`Codable` と `Hashable` に準拠する必要があります。

* `LiveActivityOrigin` 定義済みリストは、アクティビティがアプリ内でローカルで開始されたか、iOS 17.2 以降でサポートされているプッシュトゥスタート通知を通じてリモートで開始されたかを指定します。この値により、SDK で、データ収集中にローカルで開始されたライブアクティビティとリモートでトリガーされたライブアクティビティを区別できます。

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

また、アプリに複数のライブアクティビティタイプを登録することもできます。

```swift
if #available(iOS 16.1, *) {
    Messaging.registerLiveActivity(AirplaneTrackingAttributes.self)
    Messaging.registerLiveActivity(FoodDeliveryLiveActivityAttributes.self)
    Messaging.registerLiveActivity(GameScoreLiveActivityAttributes.self)
}
```

## 手順 3：ライブアクティビティを登録 {#register}

SDK の初期化後に `AppDelegate` にライブアクティビティタイプを登録すると、次の操作を実行できます。

* 自動プッシュトゥスタートトークン収集を有効にする（iOS 17.2 以降）
* ライブアクティビティ更新トークンを自動的に収集
* ライフサイクル管理とイベントトラッキングを有効にする

**食品配送ライブアクティビティの例：**

```swift
if #available(iOS 16.1, *) {
    Messaging.registerLiveActivity(FoodDeliveryLiveActivityAttributes.self)
}
```

## 手順 4：ライブアクティビティウィジェットを作成 {#widgets}

ライブアクティビティはウィジェットを通じて表示されます。ウィジェットバンドルと設定を作成する必要があります。

**食品配送ライブアクティビティの例：**

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

## 手順 5：ローカルでライブアクティビティを開始（オプション） {#local}

Journey Optimizer ではライブアクティビティをリモートで開始できますが、ローカルで開始することもできます。

**食品配送ライブアクティビティの例：**

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

## 手順 6：デバッグサポートを追加（オプション） {#debug}

必要に応じて、Adobe Assurance でライブアクティビティスキーマをデバッグできます。

**食品配送ライブアクティビティの例：**

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


