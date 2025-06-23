---
solution: Journey Optimizer
product: journey optimizer
title: データライフサイクル操作の実行
description: データライフサイクル操作の実行方法について説明します。
feature: Privacy, Monitoring
role: User
level: Intermediate
exl-id: 8045b559-bf5e-4b5f-9da4-accd44641a68
source-git-commit: a5b292e6eb4145fa29774fbeb4ce823bc71b849c
workflow-type: ht
source-wordcount: '221'
ht-degree: 100%

---

# データライフサイクル操作の実行 {#data-hygiene}

>[!AVAILABILITY]
>
>データライフサイクル機能は、現在、**Healthcare Shield** および&#x200B;**プライバシーとセキュリティシールド**&#x200B;アドオン機能を購入した組織でのみ利用できます。

Adobe Experience Platform にデータが継続的に取り込まれるので、組織のポリシーに従って意図したとおりにデータを使用し、必要に応じて更新し、削除することが重要になります。

これらのタスクは、**[!UICONTROL データライフサイクル]**&#x200B;メニューを使用して実行できます。ここでは、データライフサイクルの設定とスケジュールを行い、レコードが適切に維持されるようにします。

![](assets/data-hygiene.png)


## レコメンデーション {#data-hygiene-recommendations}

データハイジーン操作（ID やデータセットの削除など）を実行する際、削除した ID に関連付けられた過去の配信イベントは、標準レポートやデータレイククエリに表示されなくなります。これにより、特に古いジャーニーの場合、**配信済み**&#x200B;として報告されたメールの数と受信者のインボックスの&#x200B;**受信済み**&#x200B;メールの数に矛盾が生じる場合があります。

大規模な削除を実行する前に、必要な配信データまたはレポートデータを検証して書き出します。データハイジーン後に紐付けが必要な場合は、アドビサポートと調整して、アーカイブ済みログにアクセスするか、メッセージフィードバックイベントデータセットクエリを使用して最新データを取得します。

## 詳細情報 {#data-hygiene-learn-more}

Privacy Service とデータライフサイクル操作の実行方法について詳しくは、Adobe Experience Platform のドキュメントを参照してください。

* [Privacy Service の概要](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=ja)
* [Adobe Experience Platform のデータライフサイクル](https://experienceleague.adobe.com/docs/experience-platform/hygiene/home.html?lang=ja)
