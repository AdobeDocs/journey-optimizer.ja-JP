---
title: キャンペーンの基本を学ぶ
description: キャンペーンについて詳しくは、 [!DNL Journey Optimizer] で説明します。
feature: Overview
topic: Content Management
role: User
level: Intermediate
exl-id: e2506a43-e4f5-48af-bd14-ab76c54b7c90
source-git-commit: bc036fc52424adaf129ab379872dedfc5994c3bb
workflow-type: tm+mt
source-wordcount: '334'
ht-degree: 71%

---

# キャンペーンの基本を学ぶ {#get-started-campaigns}

>[!CONTEXTUALHELP]
>id="campaigns_list"
>title="キャンペーン"
>abstract="キャンペーンを使用すれば、複数のチャネルをまたいだ特定のセグメントに 1 回限りのコンテンツを配信できます。新しいキャンペーンを作成する前に、チャネルサーフェス（例：メッセージプリセット）と Adobe Experience Platform セグメントが使用できる状態になっていることを確認します。"

## キャンペーンについて {#about}

>[!IMPORTANT]
>
>この機能は、Campaign 管理者、Campaign 承認者、Campaign マネージャー、Campaign ビューアなど、Campaign 関連の製品プロファイルへのアクセス権を持つユーザーのみが使用できます。 製品プロファイルの割り当て方法について詳しくは、 [このページ](../administration/permissions.md).

キャンペーンでは、複数のチャネルを使用して、特定のセグメントに 1 回限りのコンテンツを配信できます。アクションを順に実行するように設計されたジャーニーとは異なり、キャンペーンは、アクションを即座に、または指定したスケジュールで、同時に実行します。 

これにより、プロモーションオファー、エンゲージメントキャンペーン、お知らせ、法律上の注意事項、ポリシーの更新などのマーケティング使用例に対して、シンプルなアドホックバッチ通信を送信できます。

➡️ [この機能をビデオで確認](#video)

<!--You can create two types of campaigns:

* **Scheduled campaigns** allow for simple ad-hoc batch communications for marketing use cases like promotional offers, engagement campaigns, announcements, legal notices, or policy updates.
* **API Triggered Campaigns** allow for simple transactional/operational messages with REST APIs (password reset, card abandonment, etc.), where the need may involve personalization using profile attributes and contextual data from payload.-->

## キャンペーンへのアクセス {#access}

キャンペーンは、**[!UICONTROL キャンペーン]**&#x200B;メニューからアクセスできます。

デフォルトでは、リストには&#x200B;**[!UICONTROL ドラフト]**、**[!UICONTROL スケジュール済み]**、**[!UICONTROL ライブ]**&#x200B;ステータスのすべてのキャンペーンが表示されます。停止、完了およびアーカイブされたキャンペーンを表示するには、フィルターをクリアする必要があります。

![](assets/create-campaign-list.png)

## キャンペーンのステータス {#statuses}

キャンペーンには複数のステータスがあります。

* **[!UICONTROL ドラフト]**：キャンペーンは編集中で、アクティブ化されていません。
* **[!UICONTROL アクティブ化中]**：キャンペーンをアクティブ化中です。
* **[!UICONTROL ライブ]**：キャンペーンはアクティブ化されています。
* **[!UICONTROL スケジュール済み]**：キャンペーンは、特定の開始日にアクティブ化されるように設定されています。
* **[!UICONTROL 停止]**：キャンペーンは手動で停止されました。アクティブ化または再利用できなくなりました（[キャンペーンを停止](modify-stop-campaign.md#stop)を参照）
* **[!UICONTROL 完了]**：キャンペーンは完了しています。このステータスは、キャンペーンがアクティブ化されてから 3 日後に、またはキャンペーンが繰り返し実行されている場合はキャンペーンの終了日に、自動的に割り当てられます。
* **[!UICONTROL アーカイブ済み]**：キャンペーンはアーカイブされています。

>[!NOTE]
>
>**[!UICONTROL ライブ]**&#x200B;または&#x200B;**[!UICONTROL スケジュール済み]**&#x200B;ステータスの横にある「ドラフトバージョンを開く」アイコンは、キャンペーンの新しいバージョンが作成され、まだアクティブ化されていないことを示します（[キャンペーンを変更](modify-stop-campaign.md#modify)を参照）。

## ハウツービデオ {#video}

最初のキャンペーンの作成方法を学びます。

>[!VIDEO](https://video.tv.adobe.com/v/346680?quality=12)
