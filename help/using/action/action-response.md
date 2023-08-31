---
solution: Journey Optimizer
product: journey optimizer
title: カスタムアクションの機能強化
description: カスタムアクションの最新の機能強化について説明します
feature: Actions
topic: Administration
role: Admin
level: Experienced
badge: label="Beta" type="Informative"
keywords: アクション, サードパーティ, カスタム, ジャーニー, API
source-git-commit: 494e51d5e44796047e237e6ad692fc6fd4c4e31d
workflow-type: tm+mt
source-wordcount: '666'
ht-degree: 100%

---

# カスタムアクションの機能強化 {#custom-action-enhancements}

カスタムアクションで API 呼び出し応答を活用し、これらの応答に基づいてジャーニーを調整できるようになりました。

この機能は、以前はデータソースを使用する場合にのみ使用可能でした。これで、カスタムアクションでも使用できるようになりました。

>[!AVAILABILITY]
>
>この機能は現在、Private Beta として使用可能です。

>[!WARNING]
>
>カスタムアクションは、プライベートまたは内部のエンドポイントでのみ使用し、適切なキャッピングまたはスロットリング制限を付ける必要があります。[このページ](../configuration/external-systems.md)を参照してください。

## カスタムアクションを定義 {#define-custom-action}

カスタムアクションを定義する際、GET メソッドの追加と新しいペイロード応答フィールドという 2 つの機能強化が使用可能になりました。その他のオプションとパラメーターには変更はありません。[このページ](../action/about-custom-action-configuration.md)を参照してください。

### エンドポイントの設定 {#endpoint-configuration}

「**URL 設定**」セクションの名前が、**エンドポイントの設定**&#x200B;に変更されました。

**メソッド**&#x200B;ドロップダウンで、「**GET**」を選択できるようになりました。

![](assets/action-response1.png){width="70%" align="left"}

### ペイロード {#payloads-new}

「**アクションパラメーター**」セクションの名前が、**ペイロード**&#x200B;に変更されました。次の 2 つのフィールドを使用できます。

* 「**リクエスト**」フィールド：このフィールドは、POST および PUT 呼び出しメソッドでのみ使用できます。
* 「**応答**」フィールド：これは新しい機能です。このフィールドは、すべての呼び出しメソッドで使用できます。

>[!NOTE]
> 
>これらのフィールドは、どちらもオプションです。

![](assets/action-response2.png){width="70%" align="left"}

1. 「**応答**」フィールド内でクリックします。

   ![](assets/action-response3.png){width="80%" align="left"}

1. 呼び出しで返されたペイロードの例をペーストします。フィールドのタイプが正しい（文字列、整数など）ことを確認します。次に、呼び出し中にキャプチャされた応答ペイロードの例を示します。ローカルエンドポイントは、ロイヤルティポイントの数と、プロファイルのステータスを送信します。

   ```
   {
   "customerID" : "xY12hye",    
   "status":"gold",
   "points": 1290 }
   ```

   ![](assets/action-response4.png){width="80%" align="left"}

   API が呼び出されるたびに、ペイロードの例に含まれるすべてのフィールドが取得されます。

1. では、クエリパラメーターとして customerID も追加してみましょう。

   ![](assets/action-response9.png){width="80%" align="left"}

1. 「**保存**」をクリックします。

## ジャーニーで応答を活用 {#response-in-journey}

カスタムアクションをジャーニーに追加するだけです。その後、条件、その他のアクションおよびメッセージのパーソナライゼーションで応答ペイロードフィールドを活用できます。

例えば、ロイヤルティポイント数を確認する条件を追加できます。ユーザーがレストランに入ると、ローカルエンドポイントは、プロファイルのロイヤルティ情報が入った呼び出しを送信します。プロファイルがゴールド顧客の場合は、プッシュを送信できます。また、呼び出しでエラーが検出された場合は、カスタムアクションを送信して、システム管理者に通知します。

![](assets/action-response5.png)

1. イベントと、先ほど作成した「ロイヤルティ」カスタムアクションを追加します。

1. 「ロイヤルティ」カスタムアクションで、プロファイル ID を使用して顧客 ID クエリパラメーターをマッピングします。「**タイムアウトまたはエラーの場合に代替パスを追加**」オプションをオンにします。

   ![](assets/action-response10.png)

1. 1 つ目の分岐で、条件を追加し、高度なエディターを使用して、「**コンテキスト**」ノードの下にあるアクション応答フィールドを活用します。

   ![](assets/action-response6.png)

1. 次に、プッシュを追加し、応答フィールドを使用してメッセージをパーソナライズします。この例では、ロイヤルティポイント数と顧客ステータスを使用してコンテンツをパーソナライズします。アクション応答フィールドは、**コンテキスト属性**／**Journey Orchestration**／**アクション**&#x200B;で使用できます。

   ![](assets/action-response8.png)

   >[!NOTE]
   >
   >各プロファイルがカスタムアクションに入ると、呼び出しをトリガーします。応答が常に同じであっても、ジャーニーはプロファイルごとに 1 回の呼び出しを実行します。

1. タイムアウトとエラーの分岐で、条件を追加し、組み込みの **jo_status_code** フィールドを活用します。この例では、
   **http_400** エラータイプを使用しています。[この節](#error-status)を参照してください。

   ```
   @action{ActionLoyalty.jo_status_code} == "http_400"
   ```

   ![](assets/action-response7.png)

1. 組織に送信するカスタムアクションを追加します。

   ![](assets/action-response11.png)

## エラーステータス {#error-status}

**jo_status_code** フィールドは、応答ペイロードが定義されていない場合でも常に使用できます。

このフィールドに指定できる値は次のとおりです。

* http ステータスコード：http_`<HTTP API call returned code>`、例えば、http_200 や http_400
* タイムアウトエラー：**timedout**
* キャッピングエラー：**capped**
* 内部エラー：**internalError**

返された http コードが 2xx より大きい場合やエラーが発生した場合、アクション呼び出しはエラーと見なされます。この場合、ジャーニーは専用のタイムアウトまたはエラー分岐に進みます。

>[!WARNING]
>
>新しく作成したカスタムアクションにのみ、**jo_status_code** フィールドが標準で含まれます。既存のカスタムアクションで使用する場合は、アクションを更新する必要があります。例えば、説明を更新して保存できます。

## 式の構文 {#exp-syntax}

構文は次のとおりです。

```json
#@action{myAction.myField} 
```

以下に、いくつかの例を示します。

```json
 // action response field
 @action{<action name>.<path to the field>}
 @action{ActionLoyalty.status}
```

```json
 // action response field
 @action{<action name>.<path to the field>, defaultValue: <default value expression>}
 @action{ActionLoyalty.points, defaultValue: 0}
 @action{ActionLoyalty.points, defaultValue: @{myEvent.newPoints}}
```

フィールド参照について詳しくは、[この節](../building-journeys/expression/field-references.md)を参照してください。

