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
  - id: d998adac-2f81-400b-a669-d07bb196e4eb
  - id: fe338112-e2ce-4876-8989-fc4d497613f1
subfeature_v2:
  - id: fa683eda-48de-4558-af32-2673edcd44fe
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: f9b8e1590f14cdcd00432295c653769f753b9b40
workflow-type: tm+mt
source-wordcount: 235
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

データハイジーン操作（ID やデータセットの削除など）を実行する際、削除した ID に関連付けられた過去の配信イベントは、標準レポートやデータレイククエリに表示されなくなります。 これにより、特に古いジャーニーの場合、**配信済み**&#x200B;として報告されたメールの数と受信者のインボックスの&#x200B;**受信済み**&#x200B;メールの数に矛盾が生じる場合があります。

大規模な削除を実行する前に、必要な配信データまたはレポートデータを検証してエクスポートします。 データハイジーン後に紐付けが必要な場合は、アドビサポートと調整して、アーカイブ済みログにアクセスするか、メッセージフィードバックイベントデータセットクエリを使用して最新データを取得します。

## 詳細情報 {#data-hygiene-learn-more}

Privacy Service とデータライフサイクル操作の実行方法について詳しくは、Adobe Experience Platform のドキュメントを参照してください。

* [Privacy Service の概要](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=ja)
* [Adobe Experience Platform のデータライフサイクル](https://experienceleague.adobe.com/docs/experience-platform/hygiene/home.html?lang=ja)
