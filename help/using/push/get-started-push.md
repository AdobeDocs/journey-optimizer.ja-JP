---
solution: Journey Optimizer
product: journey optimizer
title: プッシュ通知の基本を学ぶ
description: Journey Optimizer でプッシュ通知を作成する方法を説明します
feature: Overview, Push
topic: Content Management
role: User
level: Beginner
exl-id: c1f16edd-efdf-41c2-a0ad-5f55009008f5
source-git-commit: 0ec43a204f5fcf0bddf38cfd381f0ea496c7de70
workflow-type: tm+mt
source-wordcount: '323'
ht-degree: 100%

---

# プッシュ通知の基本を学ぶ {#gs-push-notification}

>[!IMPORTANT]
>
>プッシュ通知を初めて作成する場合は、プッシュチャネルが設定されていることを確認してください。[詳細情報](push-gs.md)。

プッシュ通知は、モバイルアプリのユーザー、特にアプリを積極的に使用していないユーザーにいつでもリーチするのに役立ちます。プッシュ通知は、サービスに関するアップデートのお知らせ、ユーザーに対するアクションの実行の依頼、新しい取引に対するユーザーへの警告など、様々なユースケースの実現に役立ちます。デバイスプラットフォームでは、エンドユーザーが通知を受信または表示する前にオプトインが必要です。ユーザーのオプトインは、インストール後にアプリを初めて起動した後の早い段階で受け取ることも、必要に応じて後続のセッションやワークフローで受け取ることもできます。

[!DNL Journey Optimizer] はプッシュ通知をサポートし、関連性の高い通知を業界最高のスループット率で送信できます。Adobe Experience Cloud でのブランドのデータインサイトを活用するために、プッシュ通知には、パーソナライゼーションとジャーニーベースのコンテキストを含めることができます。

プッシュ通知は次の場所で作成できます。

* **ジャーニー**&#x200B;の場合：ジャーニーにプッシュアクティビティを追加し、基本設定を定義したら、右側の&#x200B;**[!UICONTROL アクション : プッシュ]**&#x200B;パネルを使用して、プッシュ通知のコンテンツを作成します。[ジャーニーを作成する方法について説明します](../building-journeys/journey-gs.md)

* **キャンペーン**&#x200B;の場合：キャンペーンを作成したら、アクションとして「プッシュ通知」を選択し、基本設定を定義します。[キャンペーンの作成方法を学ぶ](../campaigns/create-campaign.md#configure)

専用のタブを使用して、**iOS** および **Android** オペレーティングシステムのプッシュ通知設定を定義します。

>[!NOTE]
>
>**[!DNL Journey Optimizer]** には、メールや SMS メッセージのオプトアウトを管理する方法が用意されていますが、プッシュ通知の場合は、受信者が自分のデバイスを介して登録解除できるので、ユーザー側でのアクションは不要です。例えば、アプリのダウンロード時や使用時に、通知の停止を選択できます。同様に、モバイルオペレーティングシステムから通知設定を変更することもできます。

<table style="table-layout:fixed"><tr style="border: 0;">
<td>
<a href="create-push.md">
<img alt="リード" src="../assets/do-not-localize/push-create.jpg">
</a>
<div><a href="create-push.md"><strong>プッシュ通知の作成</strong>
</div>
<p>
</td>
<td>
<a href="design-push.md">
<img alt="低頻度" src="../assets/do-not-localize/push-design.jpg">
</a>
<div>
<a href="design-push.md"><strong>プッシュ通知のデザイン</strong></a>
</div>
<p></td>
<td>
<a href="send-push.md">
<img alt="検証" src="../assets/do-not-localize/push-sending.jpg">
</a>
<div>
<a href="send-push.md"><strong>プッシュ通知の送信</strong></a>
</div>
<p>
</td>
<td>
<a href="push-gs.md">
<img alt="検証" src="../assets/do-not-localize/push-config.jpg">
</a>
<div>
<a href="push-gs.md"><strong>プッシュ通知の設定</strong></a>
</div>
<p>
</td>
</tr></table>
