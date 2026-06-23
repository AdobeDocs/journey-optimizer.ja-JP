---
solution: Journey Optimizer
product: journey optimizer
title: 高度な式エディターの使用
description: 高度な式の作成方法について説明します
feature: Journeys
role: Developer
level: Experienced
hide: true
keywords: 式, 条件, ユースケース, イベント
exl-id: 753ef9f4-b39d-4de3-98ca-e69a1766a78b
version: Journey Orchestration
TQID: https://experienceleague.adobe.com/UUeCcATC7MFHsLuI8TPoVHqwVe9GOXUq3U3RoAG-a1o
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2:
  - id: d998adac-2f81-400b-a669-d07bb196e4eb
  - id: df64005d-8f9a-422e-ba4d-c6f6dc3454b4
subfeature_v2:
  - id: fa683eda-48de-4558-af32-2673edcd44fe
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: bf5866b0e7437f93936f573fd83ada8526fe004d
workflow-type: tm+mt
source-wordcount: 1103
ht-degree: 51%

---

# 高度な式の例{#advanced-expression-examples}

高度な式エディターを使用すると、ジャーニーでユーザーをフィルタリングできる条件を作成できます。 これらの条件を使用すると、時刻、日付、場所、期間に基づいてユーザーをターゲットに設定して、ジャーニーで再ターゲット化できるようになります。

>[!CAUTION]
>
>ジャーニーの式／条件でのエクスペリエンスイベントの使用はサポートされていません。 ユースケースでエクスペリエンスイベントを使用する必要がある場合は、別の方法を考慮します。 [詳細情報](../exp-event-lookup.md)


## エクスペリエンスイベントに関する条件の作成


>[!CAUTION]
>
>ジャーニーの式／条件でのエクスペリエンスイベントの使用はサポートされていません。 ユースケースでエクスペリエンスイベントを使用する必要がある場合は、別の方法を考慮します。 [詳細情報](../exp-event-lookup.md)
>



高度な式エディターは、購入のリストやメッセージに対する過去のクリックなどの時系列に対してクエリを実行する場合に必須です。 このようなクエリは、単純なエディターでは実行できません。

>[!NOTE]
>
>イベントは @ で始まり、データソースは # で始まります。

エクスペリエンスイベントは、Adobe Experience Platform からコレクションとして新しい順に取得されます。したがって、次のようになります。

* first 関数は最新のイベントを返します
* last 関数は最も古いイベントを返します

例えば、過去 7 日間に買い物かごを放棄した顧客をターゲットにして、顧客が店に近づいたときに、過去に顧客が希望した商品のうち店頭にあるものに関するオファーをメッセージで送信するとします。

**次の条件を作成する必要があります。**

まず、過去 7 日間にオンラインストアを閲覧したものの、最終的に注文をしていない顧客をターゲットにします。

**この式は、文字列値で指定された値を検索します。**

`In ("addToCart", #{field reference from experience event})`

**この式は、過去 7 日間に指定された、このユーザーのすべてのイベントを検索します。**

次に、completePurchase に変換されなかったすべての買い物かごに追加イベントを選択します。

>[!NOTE]
>
>式に手早くフィールドを挿入するには、エディターの左パネルにあるフィールドをダブルクリックします。

指定したタイムスタンプは日時の値として機能し、2 番目は日数です。

```json
        in( "addToCart", #{ExperiencePlatformDataSource
                        .ExperienceEventFieldGroup
                        .experienceevent
                        .all(
                        inLastDays(currentDataPackField.timestamp, 7 ))
                        .productData
                        .productInteraction})
        and
        not(in( "completePurchase", #{ExperiencePlatformDataSource
                        .ExperienceEventFieldGroup
                        .experienceevent
                        .all(
                        inLastDays(currentDataPackField.timestamp, 7 ))
                        .productData
                        .productInteraction}))
```

この式はブール値を返します。

**次に、商品の在庫があるかどうかを確認する式を作成します**

* Inventory で、この式は製品の数量フィールドを検索し、その値が 0 より大きいことを指定します。

`#{Inventory.fieldgroup3.quantity} > 0`

* 必要な値は適宜指定されます。ここでは、ストアの場所を取得する必要があります。これは、イベント「ArriveLumaStudio」の location からマッピングされています。

`#{ArriveLumaStudio._acpevangelists1.location.location}`

* そして、SKU を指定し、`first` 関数を使用して、最新の「addToCart」インタラクションを取得します。

  ```json
      #{ExperiencePlatformDataSource
                      .ExperienceEventFieldGroup
                      .experienceevent
                      .first(
                      currentDataPackField
                      .productData
                      .productInteraction == "addToCart"
                      )
                      .SKU}
  ```

そこから、商品がストアにない場合のために別のパスをジャーニーに追加し、エンゲージメントオファーの通知を送信することができます。 メッセージを適切に設定し、パーソナライゼーションデータを使用してメッセージのターゲットを強化します。

## エクスプレッションでのタイムスタンプフィルタリング

複数のカートアクティビティイベントを参照する場合は、履歴データを取得しないように、開始と終了の両方のタイムスタンプウィンドウを指定します。 以下に例を示します。

```json
toDateTimeOnly(currentDataPackField.timestamp) >= toDateTimeOnly(@event{poc_UDXCartAddSavedCheckOutEv.timestamp})
AND
toDateTimeOnly(currentDataPackField.timestamp) < toDateTimeOnly(nowWithDelta(4, "hours"))
```

## 高度な式エディターを使用した文字列操作の例

**条件内**

次の条件は、「Arlington」でトリガーされたジオフェンスイベントのみを取得します。

```json
        @event{GeofenceEntry
                    .placeContext
                    .POIinteraction
                    .POIDetail
                    .name} == "Arlington"
```

説明：これは厳密な文字列比較（大文字と小文字を区別）で、`Is sensitive` をオンにして `equal to` を使用するシンプルモードのクエリと同等です。

同じクエリでも `Is sensitive` をオフにすると、詳細設定モードで次の式が生成されます。

```json
        equalIgnoreCase(@event{GeofenceEntry
                        .placeContext
                        .POIinteraction
                        .POIDetail
                        .name}, "Arlington")
```

**アクション内**

次の式を使用すると、アクションパーソナライゼーションフィールドで CRM ID を定義できます。

```json
substr(
   @event{MobileAppLaunch
   ._myorganization
   .identification
   .crmid},
   1, 
   lastIndexOf(
     @event{MobileAppLaunch
     ._myorganization
     .identification
     .crmid},
     '}'
   )
)
```

説明：この例では、`substr` および `lastIndexOf` 関数を使用して、モバイルアプリ起動イベントで渡される CRM ID を囲む中括弧を削除しています。


高度な式エディターの使用方法について詳しくは、 [このビデオ](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-journeys/introduction-to-building-a-journey.html?lang=ja)をご覧ください。

+++ AI ナレッジリファレンス

このセクションには、このトピックに関連する解釈、検索、質問への回答をサポートすることを目的とした構造化された知識が含まれています。

理解を深めるには、この情報をこのページのドキュメントと組み合わせる必要があります。 どちらのソースも単独で使用することを意図していません。このページでは、機能について説明しますが、この節では、用語、意図、適用可能性、および制約の曖昧さを解消するのに役立つ追加のコンテキストを提供します。

* **TL;DR:**&#x200B;このページでは、高度な式エディターを使用して、カートのアクティビティ、在庫状況、ジオフェンス イベント、文字列操作、タイムスタンプウィンドウでユーザーをフィルタリングするジャーニー条件を構築する実用的な例を紹介します。

**インテント：**

* `in()`と`inLastDays()`を使用してカート放棄条件を作成し、アイテムを追加したが7日以内に購入を完了しなかったユーザーをターゲットにします
* タイムスタンプウィンドウでエクスペリエンスイベントのコレクションをフィルタリングし、過去のデータを取得しないようにします
* ジオフェンスのイベントフィールドに大文字と小文字を区別する文字列比較を適用する
* `substr`と`lastIndexOf`を使用して、モバイルアプリ起動イベントからCRM IDを抽出して操作します
* 数量フィールドと閾値を比較して、製品の在庫状況を確認します
* ジャーニー条件で`and` / `not` ロジックを使用して複数のブール式を組み合わせる

**用語集：**

* **高度な式エディター**：関数、演算子、フィールド参照を使用して、複雑なコードレベルの式を記述するためのJourney Optimizer インターフェイス *（product-specific）*
* **currentDataPackField**: `all()`、`first()`または`last()`関数&#x200B;*（製品固有）*&#x200B;内のデータソースコレクションを繰り返し処理する際に使用されるループ変数
* **inLastDays （timestamp, N）**：指定されたタイムスタンプが過去N日以内に含まれる場合にtrueを返す日付関数&#x200B;*（製品固有）*
* **エクスペリエンスイベント**:Adobe Experience Platformに保存されている時系列行動データレコードが、逆時系列で取得されました&#x200B;*（製品固有）*

**ガードレール：**

* ジャーニー式/条件でエクスペリエンスイベントを直接使用することはサポートされていません。代わりに、計算属性やオーディエンスセグメントなどの代替メソッドを使用する必要があります
* 購入やクリックのコレクションなどの時系列データのクエリには、高度な式エディター（単純なエディターではなく）を使用する必要があります
* 左側のパネルでフィールドをダブルクリックすると、そのフィールドがエクスプレッションにすばやく挿入されます。エラーを軽減するために、フィールドパスを手動で入力しないでください
* エクスプレッション エクスペリエンスイベントのクエリはブール値を返します。ダウンストリームロジックでブール値タイプが想定されていることを確認します

**用語：**

* 正規表現の名前：詳細式エディター – Acronym: none — バリアント：式エディター、詳細エディター
* 同義語：「addToCart」 = 「カートに追加インタラクション」;「completePurchase」 = 「購入完了イベント」
* 混同しないでください：イベント （先頭に`@`）≠ データソース （先頭に`#`）

**FAQ:**

* **Q: カート放棄クエリの単純なエディターの代わりに高度なエディターを使用する必要があるのはなぜですか？** — シンプル エディターは時系列コレクションでクエリを実行できません。`all()`、`first()`および`last()` コレクション関数には高度なエディターが必要です。
* **Q：式の最新の「addToCart」イベントを参照する方法を教えてください。** — イベントは逆時系列で返されるため、`productInteraction == "addToCart"`でフィルタリングされたエクスペリエンスイベント コレクションで`first()`関数を使用します。
* **Q：高度なエディターで文字列比較を大文字と小文字を区別しないようにする方法を教えてください。** — `==`演算子の代わりに`equalIgnoreCase()`関数を使用します。
* **Q: カートイベントのクエリ時にタイムスタンプウィンドウを追加する目的は何ですか？**  – 開始と終了の両方のタイムスタンプを指定すると、目的のアクティビティウィンドウ外に入る履歴データを取得できなくなります。
* **Q: イベントで渡されたCRM ID文字列から中括弧を削除する方法を教えてください。** — `substr()`を`lastIndexOf()`と組み合わせて使用し、括弧の間のコンテンツを抽出します。

+++
