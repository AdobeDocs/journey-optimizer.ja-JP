---
title: オプトアウトの管理
description: オプトアウトとプライバシーを管理する方法について説明します。
feature: Journeys
topic: Content Management
role: User
level: Intermediate
exl-id: c5bae757-a109-45f8-bf8d-182044a73cca
source-git-commit: 06a7abc2ada930356cbaf45ce01eed5e3156f2e3
workflow-type: tm+mt
source-wordcount: '833'
ht-degree: 98%

---

# オプトアウトの管理 {#consent}

[!DNL Journey Optimizer]を使用すると、通信に対する受信者の同意を追跡でき、受信者の好みや購読を管理して受信者がブランドとどのように関わりたいと思っているかを理解できます。

GDPR などの規制では、データサブジェクトからの情報を使用するには、特定の要件を満たす必要があると規定されています。また、データサブジェクトは、いつでも同意を変更できる必要があります。

**なぜそれが重要なのでしょうか？**

* これらの規制に準拠できないと、ブランドに法規制上のリスクが生じます。
* この機能を使用すると、未承諾の通信を受信者に送信して、メッセージがスパムと見なされたり、ブランドの評判が損なわれたりする危険性を避けることができます。

プライバシーの管理と適用される法規制について詳しくは、[Experience Platform のドキュメント](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=ja){target=&quot;_blank&quot;}を参照してください。

## オプトアウト管理 {#opt-out-management}

ブランドからの連絡を購読解除する機能を受信者に提供することは、法的要件です。適用される法律について詳しくは、[Experience Platform のドキュメント](https://experienceleague.adobe.com/docs/experience-platform/privacy/regulations/overview.html?lang=ja#regulations){target=&quot;_blank&quot;}を参照してください。

したがって、受信者に送信されるすべての メールに、**登録解除リンク**&#x200B;を必ず含める必要があります。

* 受信者がこのリンクをクリックすると、オプトアウトを確認するボタンを含んだランディングページが表示されます。
* オプトアウトボタンをクリックすると、Adobe I/O が呼び出され、プロファイルデータにこの情報が反映されます。[この詳細を説明します](#consent-service-api)。

### 購読解除リンクの追加 {#add-unsubscribe-link}

登録解除リンクを追加するには、次の手順に従います。

1. 登録解除ランディングページを作成します。

1. 任意のサードパーティ製システムでホストします。

1. [!DNL Journey Optimizer] で[メッセージを作成](create-message.md)します。

1. コンテンツ内のテキストを選択し、コンテキストツールバーを使用してリンクを挿入します。

   ![](assets/opt-out-insert-link.png)

1. **[!UICONTROL リンクタイプ]**&#x200B;ドロップダウンリストから「**[!UICONTROL 登録解除リンク]**」を選択します。

   ![](assets/opt-out-link-type.png)

1. 「**[!UICONTROL リンク]**」フィールドに、ランディングページへのリンクを貼り付けます。

   ![](assets/opt-out-link-url.png)

1. 「**[!UICONTROL 保存]**」をクリックします。

1. コンテンツを保存し、[メッセージを公開](publish-manage-message.md)します。

   >[!NOTE]
   >
   >サードパーティランディングページの URL には、Adobe I/O を呼び出してプロファイルの環境設定を更新するための 3 つのパラメーターが含まれています。詳しくは、[この節](#consent-service-api)を参照してください。

1. [ジャーニー](../building-journeys/journey.md)を通じて、ランディングページへのリンクを含んだメッセージを送信します。

1. メッセージを受け取った受信者が登録解除リンクをクリックすると、ランディングページが表示されます。

   ![](assets/opt-out-lp-example.png)

1. 受信者がランディングページ内のオプトアウトボタン（ここでは「**登録解除**」ボタン）をクリックすると、[Adobe I/O 呼び出し](#opt-out-api)を通じてプロファイルデータが更新されます。

   その後、オプトアウトした受信者は、オプトアウトが成功したことを示す確認メッセージ画面にリダイレクトされます。

   ![](assets/opt-out-confirmation-example.png)

   その結果、購読を再度登録しない限り、このユーザーはブランドから連絡を受けることはありません。

対応するプロファイルの選択が更新されたことを確認するには、Experience Platform に移動し、ID 名前空間と対応する ID 値を選択してプロファイルにアクセスします。詳しくは、[Experience Platform のドキュメント](https://experienceleague.adobe.com/docs/experience-platform/profile/ui/user-guide.html?lang=ja#getting-started){target=&quot;_blank&quot;}を参照してください。

![](assets/opt-out-profile-choice.png)

「**[!UICONTROL 属性]**」タブで、**[!UICONTROL choice]** の値が **[!UICONTROL no]** に変更されたことを確認できます。

### オプトアウト API 呼び出し {#opt-out-api}

受信者が登録解除リンクをクリックしてオプトアウトすると、Adobe I/O API が呼び出され、対応するプロファイルの環境設定が更新されます。

Adobe I/O のこの POST 呼び出しは次のとおりです。

エンドポイント：platform.adobe.io/journey/imp/consent/preferences

クエリパラメーター：

* **params**：暗号化されたペイロードが格納されています
* **sig**：署名
* **pid**：暗号化されたプロファイル ID

これらのパラメーターは、受信者に送信される登録解除リンク（特定の受信者のサードパーティランディングページを開く URL など）から入手できます。

![](assets/opt-out-parameters.png)

ヘッダー要件：

* x-api-key
* x-gw-ims-org-id
* x-sandbox-name
* 認証（技術アカウントからのユーザートークン） 

リクエスト本文：

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

[!DNL Journey Optimizer] は、これらのパラメーターを使用して、対応するプロファイルの選択を更新します。

## ワンクリックオプトアウト {#one-click-opt-out}

購読解除をするためのより簡単なプロセスを求めているお客様が多いので、ワンクリックオプトアウトリンクをメールコンテンツに追加することもできます。このリンクにより、受信者は、オプトアウトの確認が必要なランディングページにリダイレクトされることなく、コミュニケーションをすばやく購読解除できます。

メッセージコンテンツにオプトアウトリンクを追加する方法については、[この節](message-tracking.md#one-click-opt-out-link)を参照してください。

メッセージが[ジャーニー](../building-journeys/journey.md)から送信された後、受信者がオプトアウトリンクをクリックすると、受信者のプロファイルは直ちにオプトアウトされます。

## ヘッダーの購読解除リンク {#unsubscribe-email}

受信者の E メールクライアントがメールヘッダーに購読解除リンクを表示することをサポートしている場合、[!DNL Journey Optimizer] と共に送信されるメールには自動的にこのリンクが含まれます。

例えば、購読解除リンクは Gmail では次のように表示されます。

![](assets/unsubscribe-email.png)

E メールクライアントに応じて、ヘッダーから購読解除リンクをクリックすると、次のいずれかの影響を受けます。

* 対応するプロファイルはすぐにオプトアウトされ、この選択は Experience Platform で更新されます。詳しくは、[Experience Platform のドキュメント](https://experienceleague.adobe.com/docs/experience-platform/profile/ui/user-guide.html#getting-started){target=&quot;_blank&quot;}を参照してください。

* これは、メールコンテンツから購読解除リンクをクリックするのと同じ効果があります。受信者は、オプトアウトを確認するボタンを含むランディングページにリダイレクトされます。オプトアウト管理の詳細については、[この節](#opt-out-management)を参照してください。

## プッシュのオプトアウト管理 {#push-opt-out-management}

プッシュの受信者は、自分のデバイスから登録を解除できます。

例えば、アプリのダウンロード時や使用時に、通知の停止を選択できます。同様に、モバイルオペレーティングシステムから通知設定を変更することもできます。
