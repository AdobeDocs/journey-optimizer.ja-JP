---
solution: Journey Optimizer
product: journey optimizer
title: API トリガーキャンペーンコンテンツの編集
description: API トリガーキャンペーンコンテンツの編集方法について説明します。
feature: Campaigns, API
topic: Content Management
role: Developer
level: Experienced
keywords: キャンペーン, API トリガー, REST, Optimizer, メッセージ
exl-id: b7f12c65-c1af-4c49-b126-c13a51940a43
TQID: https://experienceleague.adobe.com/bGwpeOAxkX8JWh2c-CNrq7-L1YphGT0aoQvUJBia4IE
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2:
  - id: d556b755-390a-43f0-be32-a08cf6236126
  - id: a653cc2e-bc85-4353-a306-399e5b247978
subfeature_v2:
  - id: f7479fa1-474b-479d-8c98-f6cee5865a38
  - id: ee67bd4a-25ee-4cdd-9eab-0d7549fde0c6
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: a4e4f5ca5c3eb9dbfb5691cb5de420009ed7e5a5
workflow-type: tm+mt
source-wordcount: 450
ht-degree: 88%

---

# API トリガーキャンペーンコンテンツの編集 {#api-content}

メッセージコンテンツを設定するには、「**[!UICONTROL コンテンツ]**」タブに移動するか、「**[!UICONTROL コンテンツを編集]**」ボタンをクリックします。

![](assets/campaign-content.png)

## コンテンツのデザイン {#design}

コンテンツの作成プロセスは、選択したチャネルによって異なります。 メッセージコンテンツを作成する詳細な手順については、次のページを参照してください。

<table style="table-layout:fixed"><tr style="border: 0;">
<td><a href="../email/create-email.md"><img alt="メール" src="../channels/assets/do-not-localize/email.png"></a>
<div align="center"><a href="../email/create-email.md"><strong>メール</strong></a></div></td>
<td><a href="../mobile/create-mobile-message.md"><img alt="SMS" src="../channels/assets/do-not-localize/sms.png"></a>
<div align="center"><a href="../mobile/create-mobile-message.md"><strong>SMS</strong></a></div></td>
<td><a href="../push/create-push.md"><img alt="プッシュ" src="../channels/assets/do-not-localize/push.png"></a>
<div align="center"><a href="../push/create-push.md"><strong>プッシュ通知</strong></a></div></td>
</tr></table>

>[!IMPORTANT]
>
>[高スループットキャンペーン](../campaigns/api-triggered-high-throughput.md)はアドビのプロファイルに依存しません。すべてのパーソナライゼーションは、以下に説明するように、コンテキストデータとして API ペイロードに含める必要があります。 このモードは、メールチャネルと米国地域でのみ使用できます。

## コンテキストデータを使用したコンテンツのパーソナライズ {#contextual}

メッセージをパーソナライズするのに活用できる追加データを API ペイロードに渡すことができます。

この例では、パスワードのリセットを希望する顧客に、サードパーティツールで生成されるパスワードリセット URL を送信するとします。 API トリガーキャンペーンを使用すると、生成されたこの URL を API ペイロードに渡し、キャンペーンに活用してメッセージに追加できます。

それには、これらのデータを API ペイロードに渡し、パーソナライゼーションエディターを使用してメッセージに追加する必要があります。 `{{context.<contextualAttribute>}}` 構文を使用します。ここで、`<contextualAttribute>` は、渡すデータを含んだ API ペイロード内の変数の名前と一致する必要があります。

なお、現時点では、左側のパネルメニューで使用できるコンテキスト属性はありません。 属性はパーソナライゼーション式に直接入力する必要がありますが、[!DNL Journey Optimizer] によるチェックは行われません。

![](assets/api-triggered-context.png)

**必読**

* リクエストに渡すコンテキスト属性は 200 KB を超えることはできず、常に文字列タイプと見なされます。
* `context.system` 構文はアドビ内部での使用のみに制限されているので、コンテキスト属性を渡すには使用しないでください。
* プロファイル対応のイベントとは異なり、REST API で渡されるコンテキストデータは、1 回限りの通信に使用され、プロファイルに対しては保存されません。 プロファイルが見つからなかった場合、名前空間の詳細を最大限に使用してプロファイルが作成されます。
* コンテンツで多数または大量のコンテキストデータを使用すると、パフォーマンスに影響を与える可能性があります。

## コンテンツのテストとチェック

コンテンツを定義したら、「**[!UICONTROL コンテンツをシミュレート]**」ボタンを使用して、コンテンツをプレビューおよびテストします。 どちらのシミュレーションメソッドも使用できます。

* 「**[!UICONTROL コンテンツをシミュレート]**」をクリックして、サンプル入力データまたはAI自動生成を使用してコンテンツのバリエーションをテストします。
* 「**[!UICONTROL コンテンツをシミュレート]**」をクリックし、ドロップダウンから「**[!UICONTROL コンテンツをシミュレート（AEP プロファイル）]**」を選択して、テストプロファイルでプレビューします。

[詳しくは、コンテンツのプレビューとテストの方法を参照してください](../content-management/preview-test.md)。 キャンペーン作成画面に戻るには、左向き矢印をクリックします。

![](assets/create-campaign-design.png)

## 次の手順 {#next}

キャンペーンの設定とコンテンツの準備が整ったら、キャンペーンオーディエンスを定義できます。 [詳細情報](api-triggered-campaign-audience.md)
