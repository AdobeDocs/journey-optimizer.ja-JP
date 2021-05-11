---
title: オプトアウトの管理
description: オプトアウトとプライバシーを管理する方法について説明します。
translation-type: tm+mt
source-git-commit: 55b9e5d8ed259ec6ed7746e835691d7d6261a8a4
workflow-type: tm+mt
source-wordcount: '613'
ht-degree: 3%

---

# オプトアウトの管理{#consent}

![](assets/do-not-localize/badge.png)

[!DNL Journey Optimizer]を使用して、受信者のコミュニケーションに対する同意を追跡し、自分の好みや購読を管理して自社ブランドとどのように関わりたいかを理解します。<!--Their preferences and subscriptions are handled through Consent management.-->

GDPRなどの規制では、データ・サブジェクトからの情報を使用する前に、特定の要件を満たす必要があると規定されています。 また、データサブジェクトは、いつでも同意を変更できる必要があります。

**なぜ重要なのか？**

* これらの規制に準拠できないと、ブランドに関する規制上のリスクが生じます。
* この機能を使用すると、迷惑メールとしてメッセージをマークしたり、評判を害したりする可能性のある、迷惑メールを受信者に送信しないようにできます。

プライバシーの管理と適用される規則について詳しくは、[Experience Platformドキュメント](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=ja)を参照してください。

<!--* Recipients should be able to opt-in/opt-out from receiving electronic communication through one or more channel
* Recipients expect the brand to offer preference centre capability that controls how brand should engage with them (example: channel of communication, invasive and non-invasive tracking etc). This helps to fulfil regulatory obligations and also facilitates quality engagement with recipient. 
* The third category is the capability to offer subscription to recipients (newsletter, etc)-->

## オプトアウト管理{#opt-out-management}

受信者がブランドからの通信を受信しないようにする機能を提供することは、法的要件です。 該当する法律について詳しくは、[Experience Platformドキュメント](https://experienceleague.adobe.com/docs/experience-platform/privacy/regulations/overview.html?lang=en#regulations)を参照してください。

したがって、受信者に送信されるすべての電子メールに、**登録解除リンク**&#x200B;を必ず含める必要があります。
* このリンクをクリックすると、受信者に、オプトアウトを確認するボタンを含むランディングページが表示されます。
* オプトアウトボタンをクリックすると、Adobe I/Oコールが実行され、プロファイルデータがこの情報で更新されます。 [詳しくは](#consent-service-api)、

登録解除リンクを追加するには、次の手順に従います。

1. 購読解除ランディングページを作成します。
1. ランディングページを任意のサードパーティ製システムでホストします。
1. [メッセージを作成](../../help/using/create-message.md) し [!DNL Journey Optimizer]ます。

   <!--The link to your landing page should contain a static URL and the profile ID.-->

1. コンテンツ内のテキストを選択し、コンテキストツールバーを使用してリンクを挿入します。

   ![](assets/opt-out-insert-link.png)

1. **[!UICONTROL リンクタイプ]**&#x200B;ドロップダウンリストから&#x200B;**[!UICONTROL 購読解除リンク]**&#x200B;を選択します。

   ![](assets/opt-out-link-type.png)

1. **[!UICONTROL 購読解除ページのURL]**&#x200B;フレームで、リンクをランディングページにコピーします。

   ![](assets/opt-out-link-url.png)

1. 「**[!UICONTROL 保存]**」をクリックします。

1. コンテンツを保存し、[メッセージ](../../help/using/publish-manage-message.md)を公開します。

   >[!NOTE]
   >
   >サードパーティランディングページのURLには、プロファイル呼び出しを通じてAdobe I/Oの環境設定を更新するために使用される3つのパラメーターが含まれ&#x200B;ます。 [詳しくは、この節](#consent-service-api)を参照してください。

1. [ジャーニー](building-journeys/journey.md)を通じて、ランディングページへのリンクを含むメッセージを送信します。

1. メッセージを受け取ると、受信者が登録解除リンクをクリックすると、ランディングページが表示されます。

   ![](assets/opt-out-lp-example.png)

1. 受信者がランディングページ内のオプトアウトボタン（ここでは「**購読解除**」ボタン）をクリックすると、[Adobe I/Oコール](#opt-out-api)によってプロファイルデータが更新されます。

   その後、オプトアウト受信者は、オプトアウトが成功したことを示す確認メッセージ画面にリダイレクトされます。

   ![](assets/opt-out-confirmation-example.png)

   その結果、このユーザーは再度登録しない限り、ブランドからの連絡を受けることはありません。

対応するプロファイルの選択が更新されたことを確認するには、「Experience Platform」に移動し、ID名前空間と対応するID値を選択してプロファイルにアクセスします。 詳しくは、[Experience Platformドキュメント](https://experienceleague.adobe.com/docs/experience-platform/profile/ui/user-guide.html?lang=en#getting-started)を参照してください。

![](assets/opt-out-profile-choice.png)

「**[!UICONTROL 属性]**」タブで、**[!UICONTROL choice]**&#x200B;の値が&#x200B;**[!UICONTROL no]**&#x200B;に変更されたことを確認できます。

<!--The opt-out URL is resolved upon each recipient receiving the message. It is then personalized with the relevant encrypted parameters (profile ID, profile name, journey ID, sandbox ID, and message execution ID).-->

## オプトアウトAPI呼び出し{#opt-out-api}

受信者が登録解除リンクをクリックしてオプトアウトすると、Adobe I/OAPI <!--Consent service API to capture the encrypted data and-->が呼び出され、対応するプロファイルの環境設定が更新されます。

このAdobe I/OPOST呼び出しは次のとおりです。

エンドポイント：cjm.adobe.io/imp/consent/preferences

クエリパラメーター:
* **params**:暗号化されたペイロードを含む
* **sig**:signature  <!--which signature?-->
* **pid**:暗号化されたプロファイルID

これらのパラメーターは、受信者に送信される登録解除リンク(特定の受信者のサードパーティランディングページを開くURLなど)から利用できます。

![](assets/opt-out-parameters.png)

<!--QUESTION: How do you get the URL built for each recipient? Do you have to wait until each targeted recipient receives the unsubscribe link or can you deduce it in advance? Is it done automatically upon the API call or do you have to do something manually for each profile? In other words will the LP automatically include the 3 parameters or do you have to insert something manually? Still not completely clear-->

ヘッダー要件：
* x-api-key
* x-gw-ims-org-id
* x-sandbox-name
* 認証（テクニカルアカウントからのユーザートークン） <!--How do you find this information? And other header elements?-->

リクエスト本文:

```
{
   "marketing": [
       {
            "type": "email",           
            "choice": "no",          
            "scope": "channel"       
        }
    ],
 
}
```

<!--The Consent service /-->Adobe Customer Management will <!--decrypt and-->use these parameters to update the corresponding profile's choice. <!--and provide an answer back to the landing page.-->

## プッシュオプトアウト管理{#push-opt-out-management}

プッシュ受信者は、自分のデバイスを通じて登録を取り消すことができます。

例えば、アプリのダウンロード時や使用時に、通知の停止を選択できます。 同様に、モバイルオペレーティングシステムを使用して通知設定を変更できます。
