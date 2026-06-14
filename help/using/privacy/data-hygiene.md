---
solution: Journey Optimizer
product: journey optimizer
title: データライフサイクル操作の実行
description: データライフサイクル操作の実行方法について説明します。
feature: Privacy, Monitoring
role: User
level: Intermediate
exl-id: 8045b559-bf5e-4b5f-9da4-accd44641a68
TQID: https://experienceleague.adobe.com/-zue9aNrWtfL3MGs7OjH-1CF436mzPh50fsru8OSEq8
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2:
  - id: aeebb91a-f216-4d5f-8da1-3a7e6f696ed0
  - id: bb359667-ec7d-4d4b-8663-5850fc219d32
subfeature_v2:
  - id: a9cf78bf-e9e4-4836-85a5-b6b3cf93bf56
  - id: f365ec33-2b99-4b7f-b4ee-c743dd7f615f
  - id: c8d5f2ce-ba44-43e9-a2bf-94a3d7d85ec3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 4e89993a998268ae2810c949d0669bf6dc458dd6
workflow-type: tm+mt
source-wordcount: 262
ht-degree: 89%

---

# データライフサイクル操作の実行 {#data-hygiene}

>[!BEGINSHADEBOX]

**このページでは、** データライフサイクル操作を設定およびスケジュールして、レコードを正確に保ち、意図したとおりに使用し、組織ポリシーに沿って削除できるようにします。

>[!ENDSHADEBOX]

>[!AVAILABILITY]
>
>データライフサイクル機能は、現在、**Healthcare Shield** および&#x200B;**プライバシーとセキュリティシールド**&#x200B;アドオン機能を購入した組織でのみ利用できます。

Adobe Experience Platform にデータが継続的に取り込まれるので、組織のポリシーに従って意図したとおりにデータを使用し、必要に応じて更新し、削除することが重要になります。

これらのタスクは、**[!UICONTROL データライフサイクル]**&#x200B;メニューを使用して実行できます。ここでは、データライフサイクルの設定とスケジュールを行い、レコードが適切に維持されるようにします。

![](assets/data-hygiene.png)


## レコメンデーション {#data-hygiene-recommendations}

データハイジーン操作（ID やデータセットの削除など）を実行する際、削除した ID に関連付けられた過去の配信イベントは、標準レポートやデータレイククエリに表示されなくなります。 これにより、特に古いジャーニーの場合、**配信済み**&#x200B;として報告されたメールの数と受信者のインボックスの&#x200B;**受信済み**&#x200B;メールの数に矛盾が生じる場合があります。

大規模な削除を実行する前に、必要な配信データまたはレポートデータを検証してエクスポートします。 データハイジーン後に紐付けが必要な場合は、アドビサポートと調整して、アーカイブ済みログにアクセスするか、メッセージフィードバックイベントデータセットクエリを使用して最新データを取得します。

## 詳細情報 {#data-hygiene-learn-more}

Privacy Service とデータライフサイクル操作の実行方法について詳しくは、Adobe Experience Platform のドキュメントを参照してください。

* [Privacy Service の概要](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=ja)
* [Adobe Experience Platform のデータライフサイクル](https://experienceleague.adobe.com/docs/experience-platform/hygiene/home.html?lang=ja)
