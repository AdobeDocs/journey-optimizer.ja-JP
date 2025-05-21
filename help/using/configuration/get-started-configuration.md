---
solution: Journey Optimizer
product: journey optimizer
title: チャネル設定  [!DNL Journey Optimizer]  基本を学ぶ
description: チャネル設定  [!DNL Journey Optimizer]  詳細情報
role: Admin, Developer
level: Intermediate, Experienced
exl-id: 0964a484-f957-4aae-a571-61b2a1615026
feature: Application Settings
topic: Administration
keywords: 設定,メッセージ,チャネル,サンドボックス,Optimizer
source-git-commit: 528e1a54dd64503e5de716e63013c4fc41fd98db
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 64%

---


# チャネル設定の基本を学ぶ {#start-optimizer-configuration}

[!DNL Journey Optimizer] に初めてアクセスするときは、実稼動用サンドボックスがプロビジョニングされ、契約に応じて一定数の IP が割り当てられます。


メッセージを送信するには、次の設定手順を実行する必要があります。

1. [Adobe Journey Optimizer システム管理者 ](../start/path/administrator.md) として、チャネル設定を定義します。 これらの設定を行う方法については、次のページを参照してください。

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
>モバイルチャネルの場合、[ ガイド付きチャネルの設定 ](set-mobile-config.md) を使用すると、マーケティングチャネルを迅速に設定でき、必要なすべてのリソースをExperience Platform、Journey Optimizerおよび Data Collection 内ですぐに使用できるようになります。 これにより、マーケティングチームはキャンペーンとジャーニーの作成を開始できます。

1. 完了したら、**チャネル設定**&#x200B;を作成して、メッセージの配信に必要なすべての技術的パラメーターを設定する必要があります。[ チャネル設定の詳細情報 ](channel-surfaces.md)

1. 以下を行うこともできます。

   * 抑制リストにメールアドレスを送信する前に再試行が実行される日数を管理します。[詳細](manage-suppression-list.md)

   * **メールの BCC オプション**&#x200B;を有効にして、個人に送信されたメッセージのコピーを保持します。[詳細情報](archiving-support.md#enable-bcc)

   * **ビジネスルール**&#x200B;を設定して、受信者を過度に勧誘しないようにします。[詳細情報](../conflict-prioritization/rule-sets.md)

   * Adobe Experience Platform で使用可能なメールアドレス／電話番号が複数ある場合、受信者に優先して使用するメールアドレス／電話番号を決定します。[詳細情報](primary-email-addresses.md)
