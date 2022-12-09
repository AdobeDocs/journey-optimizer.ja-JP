---
solution: Journey Optimizer
product: journey optimizer
title: コレクション管理関数
description: コレクション管理関数のデータ型について説明します。
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 09b38179-9ace-4921-985b-ddd17eb64681
source-git-commit: d17e64e03d093a8a459caef2fb0197a5710dfb7d
workflow-type: tm+mt
source-wordcount: '603'
ht-degree: 0%

---

# コレクション管理関数 {#collection-management-functions}

また、エクスプレッション言語では、コレクションにクエリを実行する関数のセットが導入されています。

これらの関数について以下に説明します。 次の例では、コレクションを含むイベントペイロードを使用してみます。

```json
                { 
   "_experience":{ 
      "campaign":{ 
         "message":{ 
            "profile":{ 
               "pushNotificationTokens":[ 
                  { 
                     "token":"token_1",
                     "application":{ 
                        "_id":"APP1",
                        "name":"MarltonMobileApp",
                        "version":"1.0"
                     }
                  },
                  { 
                     "token":"token_2",
                     "application":{ 
                        "_id":"APP2",
                        "name":"MarketplaceApp",
                        "version":"1.0"
                     }
                  },
                  { 
                     "token":"token_3",
                     "application":{ 
                        "_id":"APP3",
                        "name":"VendorApp",
                        "version":"2.0"
                     }
                  }
               ]
            }
         }
      }
   },
   "timestamp":"1536160728"
}
```

**この関数は、「all ( `<condition>` )」となります。**

**[!UICONTROL all]**&#x200B;この関数を使用すると、ブール式を使用して、特定のコレクションに対するフィルターの定義を有効にすることができます。

```json
<listExpression>.all(<condition>)
```

例えば、すべてのアプリケーションユーザーは、IOS 13 (「使用するアプリケーション = = IOS 13」) を使用してアプリケーションユーザーを取得することができます。 この関数の結果は、ブール式 (例: アプリケーションユーザー1、アプリケーションユーザー34、アプリユーザー 432) と一致する項目を含む、フィルター処理されたリストです。

データソースの条件アクティビティーでは、 **[!UICONTROL all]** 関数の結果が null かどうかを確認できます。 この **[!UICONTROL all]** 関数は、など **[!UICONTROL count]** 、他の関数と組み合わせることもできます。 詳しくは、データソースの条件アクティビティー ](../condition-activity.md#data_source_condition) を参照してください [ 。

**例 1:**

特定のバージョンのアプリケーションがユーザーによってインストールされているかどうかを確認する必要があります。 このため、バージョンが1.0 であるモバイルアプリケーションに関連付けられたすべてのプッシュ通知トークンを取得します。次に、関数を使用 **[!UICONTROL count]** して、返されたトークンのリストに1つ以上のエレメントが含まれていることを確認するための条件を実行します。

```json
count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all(currentEventField.application.version == "1.0").token}) > 0
```

結果は true になります。

**例 2:**

ここでは、 **[!UICONTROL count]** この関数を使用して、コレクション内にプッシュ通知トークンがあるかどうかをチェックします。

```json
count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all().token}) > 0
```

結果は true になります。

<!--Alternatively, you can check if there is no token in the collection:

   ```json
   count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all().token}) == 0
   ```

The result will be false.

Here we use the count function in a condition to count the number of push notification tokens in the event.

`count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all().token})`

The result is true.

Note that when the condition in the **all()** function is empty, the filter will return all the elements in the list. Hence, the expression above is equivalent to:

`count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.application.name})`

In both cases, the result of the expression is **3**.

A query of experience events recorded on the Adobe Experience Platform may or may not include the current event that triggered the current Journey. This will depend on the relative processing time with which [!DNL Journey Orchestration] sees an event and started evaluating conditions, versus the time it takes for that event to be ingested into the Adobe Experience Platform. For example, when using the .all() syntax to query experience events from the Adobe Experience Platform, we recommend enforcing the exclusion of the current event (by requiring an
earlier timestamp) in order to only consider prior events.-->

>[!NOTE]
>
>All () **関数のフィルター条件** が空の場合、フィルターはリスト内のすべてのエレメントを返します。**ただし、1つのコレクションのエレメント数を数えるには、all 関数は必要ありません。**


```json
count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.token})
```

式の結果は 3 **に** なります。

**例 3:**

ここでは、過去24時間以内に通信がまったく受信されなかったかどうかを確認します。 ExperiencePlatform データソースから取得された経験イベントのコレクションにフィルターを適用して、2つの式がコレクションの2つの要素に基づいています。 特に、イベントのタイムスタンプは、この関数によって **[!UICONTROL nowWithDelta]** 返される dateTime と比較されます。

```json
count(#{ExperiencePlatform.MarltonExperience.experienceevent.all(
   currentDataPackField.directMarketing.sends.value > 0 and
   currentDataPackField.timestamp > nowWithDelta(-1, "days")).timestamp}) == 0
```

この2つの条件に一致するエクスペリエンスイベントがない場合は、結果が true になります。

**例 4:**

次の例では、各ユーザーが前にリリースされた7日間に、少なくとも1回はアプリケーションで起動されているかどうかをチェックしています。これにより、インスタンスに対して、チュートリアルの開始を要請するプッシュ通知がトリガーされます。

```json
count(
 #{ExperiencePlatform.AnalyticsData.experienceevent.all(
 nowWithDelta(-7,"days") <= currentDataPackField.timestamp
 and currentDataPackField.application.firstLaunches.value > 0
)._id}) > 0
```

<!--**"All + Count" example 4:** here we use the count function in a boolean expression to see if there is push notification tokens in the collection.

`count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all().application.name}) > 0`

The result will be:

`true`

Alternatively, you can check if there is NO token in the collection:

`count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all().application.name}) =0`

The result will be:

`false`-->

>[!NOTE]
>
>**[!UICONTROL currentEventField]** イベントコレクションおよび **currentDataPackField を操作する場合にのみ使用できます。**
>データソースコレクションを操作する場合。 でコレクション **[!UICONTROL all]** を **[!UICONTROL first]** **[!UICONTROL last]** 処理する場合、
>コレクションの各エレメントを1つずつループします。 **[!UICONTROL currentEventField]****currentDataPackField**
>ループの対象となるエレメントに対応しています。

**関数「first ( `<condition>` )」と「last」 ( `<condition>` )**

および関数を使用すると **[!UICONTROL last]** 、コレクション上のフィルターの定義も可能になります。また、 **[!UICONTROL first]** リストの先頭または最後にある、フィルターに一致するエレメントが返されます。

_`<listExpression>.first(<condition>)`_

_`<listExpression>.last(<condition>)`_

**例 1:**

この式は、バージョンが1.0 であるモバイルアプリケーションに関連付けられた最初のプッシュ通知トークンを返します。

```json
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.first(currentEventField.application.version == "1.0").token
```

結果は &quot;token_1&quot; になります。

**例 2:**

この式は、バージョンが1.0 のモバイルアプリケーションに関連付けられた、最後のプッシュ通知トークンを返します。

```json
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.last(currentEventField.application.version == "1.0").token}
```

結果は &quot;token_2&quot; になります。

>[!NOTE]
>
>経験イベントは、Adobe エクスペリエンスプラットフォームから日付順にコレクションとして取得されます。
>
>* **[!UICONTROL first]** 関数は最新のイベントを返します。
>* **[!UICONTROL last]** 関数は、最も古いものを返します。


**例 3:**

DMA ID に0以外の値が設定されている最初の Adobe アナリティクスイベントの値が602であるかどうかを確認します。

```json
#{ExperiencePlatform.AnalyticsProd_EvarsProps.experienceevent.first(
currentDataPackField.placeContext.geo.dmaID > 0).placeContext.geo.dmaID} == 602
```

**関数 &quot;at ( `<index>` )&quot;**

**[!UICONTROL at]**&#x200B;この関数を使用して、コレクション内の特定のエレメントをインデックスに基づいて参照することができます。インデックス0がコレクションの最初のインデックスになります。

_`<listExpression>`ます。 at ( `<index>` )_

**一**

この式は、リストの2番目のプッシュ通知トークンを返します。

```json
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.at(1).token}
```

結果は &quot;token_2&quot; になります。

**その他の例**

```json
#{ExperiencePlatform.ExperienceEventFieldGroup.experienceevent. all(currentDataPackField._aepgdcdevenablement2.purchase_event.receipt_nbr == "10-337-4016"). 
_aepgdcdevenablement2.purchase_event.productListItems. all(currentDataPackField.SKU == "AB17 1234 1775 19DT B4DR 8HDK 762").name}
```

```json
 #{ExperiencePlatform.ExperienceEventFieldGroup.experienceevent.last(
currentDataPackField.eventType == "commerce.productListAdds").productListItems.last(currentDataPackField.priceTotal >= 150).name}
```
