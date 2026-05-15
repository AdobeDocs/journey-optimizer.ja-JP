---
solution: Journey Optimizer
product: journey optimizer
title: ' [!DNL Journey Optimizer]  チャネル設定の基本を学ぶ'
description: ' [!DNL Journey Optimizer]  チャネル設定について説明します'
role: Admin, Developer
level: Intermediate, Experienced
exl-id: 0964a484-f957-4aae-a571-61b2a1615026
feature: Application Settings
topic: Administration
keywords: 設定,メッセージ,チャネル,サンドボックス,Optimizer
TQID: https://experienceleague.adobe.com/zHp3C6KVKfRsQbi4B710ACFuMQhGuVxjaNIrXkxwhMc
product_v2: id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2: id: bb359667-ec7d-4d4b-8663-5850fc219d32id: d556b755-390a-43f0-be32-a08cf6236126id: fe338112-e2ce-4876-8989-fc4d497613f1
subfeature_v2: id: b3a93754-a8b8-46eb-9421-7eccaeeb3dffid: c343082f-e963-4f57-a96b-b64d27f8118eid: cf64c7f6-7428-4ae5-b158-8df9771f38f4id: e23d48b5-7858-4d45-9c56-9e2b4be8500eid: e30b0a1a-b594-47b8-af94-1e3a2be6df11id: e5329d1b-e590-4e24-a3fb-ef3fe0f2c721id: efb19423-4da4-4fd1-88d8-5ee8c71ae766
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2: id: d3cdead0-685a-4489-9250-4bb709942f66id: e9001ce2-5245-4a8e-8601-dd958009072fid: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: f9b8e1590f14cdcd00432295c653769f753b9b40
workflow-type: tm+mt
source-wordcount: 471
ht-degree: 88%

---

# チャネル設定の基本を学ぶ {#start-optimizer-configuration}

>[!CONTEXTUALHELP]
>id="ajo_channels_rate_controls"
>title="チャネルのレートコントロール"
>abstract="チャネルのレートコントロール"

[!DNL Journey Optimizer] に初めてアクセスすると、実稼動サンドボックスがプロビジョニングされ、契約に応じて一定数の IP が割り当てられます。

メッセージを送信するには、次の設定手順を実行する必要があります。

1. [Adobe Journey Optimizer システム管理者](../start/path/administrator.md)として、チャネル固有の設定を定義します。 これらの設定を行う方法について詳しくは、次のページを参照してください。

   <table style="table-layout:fixed"><tr style="border: 0;">
    <td><a href="../email/get-started-email-config.md"><img alt="メール" src="../channels/assets/do-not-localize/email.png"></a>
    <div align="center"><a href="../email/get-started-email-config.md"><strong>メール</strong></a></div></td>
    <td><a href="../sms/sms-configuration.md"><img alt="SMS" src="../channels/assets/do-not-localize/sms.png"></a>
    <div align="center"><a href="../sms/sms-configuration.md"><strong>SMS</strong></a></div></td>
    <td><a href="../push/push-configuration.md"><img alt="プッシュ" src="../channels/assets/do-not-localize/push.png"></a>
    <div align="center"><a href="../push/push-configuration.md"><strong>プッシュ通知</strong></a></div></td>
    <td><a href="../direct-mail/direct-mail-configuration.md"><img alt="ダイレクトメール" src="../channels/assets/do-not-localize/direct-mail.jpg"></a>
    <div align="center"><a href="../direct-mail/direct-mail-configuration.md"><strong>ダイレクトメール</strong></a></div></td>
    </tr></table>

   <table style="table-layout:fixed"><tr style="border: 0;">
    <td><a href="../in-app/inapp-configuration.md"><img alt="アプリ内" src="../channels/assets/do-not-localize/inapp.jpg"></a>
    <div align="center"><a href="../in-app/inapp-configuration.md"><strong>アプリ内</strong></a></div></td>
    <td><a href="../web/web-configuration.md"><img alt="Web" src="../channels/assets/do-not-localize/web.jpg"></a>
    <div align="center"><a href="../web/web-configuration.md"><strong>Web</strong></a></div></td>
    <td><a href="../code-based/code-based-configuration.md"><img alt="コードベースのエクスペリエンス" src="../channels/assets/do-not-localize/code.png"></a>
    <div align="center"><a href="../code-based/code-based-configuration.md"><strong>コードベースのエクスペリエンス</strong></a></div></td>
    <td><a href="../content-card/content-card-configuration-prereq.md"><img alt="コンテンツカード" src="../channels/assets/do-not-localize/cards.png"></a>
    <div align="center"><a href="../content-card/content-card-configuration-prereq.md"><strong>コンテンツカード</strong></a></div></td>
    </tr></table>

   その他のチャネルについては、[iOS ライブ アクティビティ ](../mobile-live/mobile-live-configuration.md)、[WhatsApp](../whatsapp/whatsapp-configuration.md)、[LINE](../line/line-configuration.md)を参照してください。

   >[!NOTE]
   >
   >モバイルチャネルの場合、[ガイド付きチャネル設定](set-mobile-config.md)によってマーケティングチャネルを迅速に設定できるようになり、Experience Platform、Journey Optimizer およびデータ収集内で必要なすべてのリソースがすぐに使用できるようになります。 これにより、マーケティングチームはキャンペーンとジャーニーの作成を開始できます。

1. 完了したら、**チャネル設定**&#x200B;を作成して、メッセージの配信に必要なすべての技術パラメーターを設定する必要があります。 [詳しくは、チャネル設定を参照してください](channel-surfaces.md)

1. 使用しているチャネル、環境、ニーズに応じて、次の手順も実行する必要があります。

   * [メール](about-subdomain-delegation.md)、[SMS](../sms/sms-subdomains.md)、[ランディングページ](../landing-pages/lp-subdomains.md)、[web エクスペリエンス](../web/web-delegated-subdomains.md)などのチャネルのサブドメイン設定とデリゲーション。

   * 最適な配信品質を実現するために、IP ウォームアッププランを設定します。 [詳細情報](ip-warmup-gs.md)

   * メール送信用の許可リストを定義します。 [詳細情報](allow-list.md)

   * 抑制リストにメールアドレスを送信する前に再試行が実行される日数を管理します。 [詳細情報](manage-suppression-list.md)

   * **「BCC メール」オプション**&#x200B;を有効にして、個人に送信されたメッセージのコピーを保持します。 [詳細情報](archiving-support.md#enable-bcc)

   * **ビジネスルール**&#x200B;を設定して、受信者を過度に勧誘しないようにします。 [詳細情報](../conflict-prioritization/rule-sets.md)

   * Adobe Experience Platform で使用可能なメールアドレス／電話番号が複数ある場合、受信者に優先して使用するメールアドレス／電話番号を決定します。 [詳細情報](primary-email-addresses.md)

## その他のリソース

* **[チャネルサーフェスの設定](channel-surfaces.md)** - メール、プッシュ、SMS、その他のチャネルのチャネルサーフェスを設定および管理する方法について説明します。
* **[サブドメインデリゲーション](delegate-subdomain.md)** - メールの配信品質とブランディングのためにサブドメインをアドビにデリゲートする方法について説明します。
* **[IP ウォームアップ](ip-warmup-gs.md)** - メールの配信品質と送信者の評判を向上させるための IP アドレスウォームアップのベストプラクティスについて説明します。
* **[抑制リストの管理](manage-suppression-list.md)** - バウンスを処理し、リストハイジーンを維持するために抑制リストを管理する方法について説明します。
* **[モバイルアプリの設定](set-mobile-config.md)** - プッシュ通知とアプリ内メッセージ用のモバイルアプリ設定を指定します。
* **[iOSのライブアクティビティを設定](../mobile-live/mobile-live-configuration.md)** - iPhoneのロック画面とDynamic Islandにライブアクティビティを送信する環境を設定します。
* **[WhatsAppの設定](../whatsapp/whatsapp-configuration.md)** - キャンペーンとジャーニーに対して、Meta Cloud APIを介してWhatsApp メッセージを設定します。
* **[LINEを設定](../line/line-configuration.md)** - キャンペーンとジャーニーにLINE メッセージを設定します。
* **[設定チュートリアル](https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/configure-channels){target="_blank"}** - チャネル設定とベストプラクティスに関するステップバイステップのビデオチュートリアルを参照してください。
