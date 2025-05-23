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
source-git-commit: b2446c6a243d6d95b6f695b9c7007e62c51d8fa3
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# チャネル設定の基本を学ぶ {#start-optimizer-configuration}

[!DNL Journey Optimizer] に初めてアクセスすると、実稼動サンドボックスがプロビジョニングされ、契約に応じて一定数の IP が割り当てられます。


メッセージを送信するには、次の設定手順を実行する必要があります。

1. [Adobe Journey Optimizer システム管理者](../start/path/administrator.md)として、チャネル設定を定義します。これらの設定を行う方法について詳しくは、次のページを参照してください。

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

>[!NOTE]
>
>モバイルチャネルの場合、[ガイド付きチャネル設定](set-mobile-config.md)によってマーケティングチャネルを迅速に設定できるようになり、Experience Platform、Journey Optimizer およびデータ収集内で必要なすべてのリソースがすぐに使用できるようになります。これにより、マーケティングチームはキャンペーンとジャーニーの作成を開始できます。

1. 完了したら、**チャネル設定**&#x200B;を作成して、メッセージの配信に必要なすべての技術パラメーターを設定する必要があります。[詳しくは、チャネル設定を参照してください](channel-surfaces.md)

1. 以下を行うこともできます。

   * 抑制リストにメールアドレスを送信する前に再試行が実行される日数を管理します。[詳細](manage-suppression-list.md)

   * **メールの BCC オプション**&#x200B;を有効にして、個人に送信されたメッセージのコピーを保持します。[詳細情報](archiving-support.md#enable-bcc)

   * **ビジネスルール**&#x200B;を設定して、受信者を過度に勧誘しないようにします。[詳細情報](../configuration/rule-sets.md)

   * Adobe Experience Platform で使用可能なメールアドレス／電話番号が複数ある場合、受信者に優先して使用するメールアドレス／電話番号を決定します。[詳細情報](primary-email-addresses.md)
