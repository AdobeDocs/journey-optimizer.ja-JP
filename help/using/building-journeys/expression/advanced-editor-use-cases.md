---
solution: Journey Optimizer
product: journey optimizer
title: 高度な式エディターの使用
description: 高度な式を作成する方法について説明します。
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 753ef9f4-b39d-4de3-98ca-e69a1766a78b
source-git-commit: d17e64e03d093a8a459caef2fb0197a5710dfb7d
workflow-type: tm+mt
source-wordcount: '489'
ht-degree: 0%

---

# 高度な式の例{#advanced-expression-examples}

高度な式エディターを使用すると、journeys でユーザーをフィルター処理するための条件を作成できます。 このような条件によって、あるユーザーにとって時間、日付、場所、デュレーション、またはその他の操作を行うことができます。これにより、abandonment またはその他の操作を行うことができます。

>[!NOTE]
>
>イベントは、@、# を含むデータソースで始まります。

## エクスペリエンスイベントに関する作成条件

購入のリストやメッセージの過去のクリックなどのように、タイムシリーズでクエリーを実行する場合は、高度な条件式エディターが必須です。 このようなクエリーは、単純なエディターでは実行できません。

経験イベントは、Adobe エクスペリエンスプラットフォームから日付順にコレクションとして取得されます。

* 最初の関数は最新のイベントを返します。
* 最後の関数は、最も古いものを返します。

例えば、abandonment を使用して、顧客が店舗に近づいたときに、ストアに格納されている品目に対する申し出が記載されている場合に、それを電子メールで送信する必要があるとします。

**次のような条件を作成する必要があります。**

第1に、オンラインストアを参照していても、過去7日間に注文を完了していない対象となるお客様が対象となります。

<!--**This expression looks for a specified value in a string value:**

`In (“addToCart”, #{field reference from experience event})`-->

**この式は、過去7日間に指定された、このユーザーのすべてのイベントを検索します。**

次に、「completePurchase」に変換されていないすべての addtocart イベントを選択します。

>[!NOTE]
>
>式にフィールドを挿入するときは、そのフィールドをエディターの左側のパネルでダブルクリックします。

指定されたタイムスタンプは日時の値として機能します。2番目の日付は日数です。

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

**ここで、製品の在庫があるかどうかをチェックする式を作成してみましょう。**

* 在庫には、製品の数量フィールドが検索され、0より大きい値が指定されていることを示します。

`#{Inventory.fieldgroup3.quantity} > 0`

* 適切な値を指定する必要がありますが、ここでは、イベント &quot;ArriveLumaStudio&quot; の位置からマップされているストアの場所を取得する必要があります。

`#{ArriveLumaStudio._acpevangelists1.location.location}`

* 最新の &quot;addToCart&quot; インタラクションを取得するために、この関数 `first` を使用して SKU を指定します。

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

ここから、製品が保管されていないときには別のパスを追加し、engagement の通知を送信することができます。 メッセージを適切に設定し、カスタマイズされたデータを使用してメッセージターゲットを強化します。

## 高度な式エディターを使用したストリング操作の例

**条件**

この状態で取得されるのは、「Arlington」で発生した geofence イベントのみです。

```json
        @{GeofenceEntry
                    .placeContext
                    .POIinteraction
                    .POIDetail
                    .name} == "Arlington"
```

説明: これは、大文字と小文字が区別されます。これは、checked と共 `Is sensitive` に使用 `equal to` される簡易モードのクエリーに相当します。

オフにした場合と `Is sensitive` 同じクエリーにより、アドバンスモードで次のエクスプレッションが生成されます。

```json
        equalIgnoreCase(@{GeofenceEntry
                        .placeContext
                        .POIinteraction
                        .POIDetail
                        .name}, "Arlington")
```

**アクションで**

次の式を使用すると、アクションのパーソナライズされたフィールドに CRM ID を定義することができます。

```json
substr(
   @{MobileAppLaunch
   ._myorganization
   .identification
   .crmid},
   1, 
   lastIndexOf(
     @{MobileAppLaunch
     ._myorganization
     .identification
     .crmid},
     '}'
   )
)
```

説明: この例では、および関数を使用 `substr` して、 `lastIndexOf` モバイルアプリの起動イベントに渡される CRM ID を囲む中括弧を削除します。

高度な式エディターを使用する方法について詳しくは、このビデオ ](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-journeys/introduction-to-building-a-journey.html) を [ 参照してください。
