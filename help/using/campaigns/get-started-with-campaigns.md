---
title: キャンペーンの基本を学ぶ
description: キャンペーンについて詳しくは、 [!DNL Journey Optimizer] で説明します。
feature: Overview
topic: Content Management
role: User
level: Intermediate
hide: true
hidefromtoc: true
exl-id: e2506a43-e4f5-48af-bd14-ab76c54b7c90
source-git-commit: 1ab038e8b2f0582ad947400c7d070a70e1a84b9b
workflow-type: tm+mt
source-wordcount: '313'
ht-degree: 79%

---

# キャンペーンの基本を学ぶ {#get-started-campaigns}

>[!CONTEXTUALHELP]
>id="campaigns_list"
>title="キャンペーン"
>abstract="キャンペーンを使用すれば、複数のチャネルをまたいだ特定のセグメントに 1 回限りのコンテンツを配信できます。新しいキャンペーンを作成する前に、メッセージプリセットと Adobe Experience Platform セグメントが使用できる状態になっていることを確認します。"

## キャンペーンについて {#about}

キャンペーンでは、複数のチャネルを使用して、特定のセグメントに 1 回限りのコンテンツを配信できます。アクションを順に実行するように設計されたジャーニーとは異なり、キャンペーンは、アクションを即座に、または指定したスケジュールで、同時に実行します。 

次の 2 種類のキャンペーンを作成できます。

* **予定キャンペーン** プロモーション、エンゲージメントキャンペーン、お知らせ、法律上の注意、ポリシーの更新など、マーケティングの使用例に対するシンプルなアドホックバッチ通信を可能にします。
* **API トリガーキャンペーン** を使用すると、REST API（パスワードリセット、カードの放棄など）を使用したシンプルなトランザクション/操作可能なメッセージで、プロファイル属性とペイロードのコンテキストデータを使用したパーソナライゼーションが必要になる場合があります。

キャンペーンとの連携方法を学ぶ：
* [キャンペーンの作成](create-campaign.md)
* [API でトリガーされるキャンペーンの作成](api-triggered-campaigns.md)
* [キャンペーンの変更または停止](modify-stop-campaign.md)
* [キャンペーンのライブレポート](campaign-live-report.md)
* [キャンペーンのグローバルレポート](campaign-global-report.md)

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
* **[!UICONTROL 完了]**：キャンペーンは完了しています。
* **[!UICONTROL アーカイブ済み]**：キャンペーンはアーカイブされています。

>[!NOTE]
>
>**[!UICONTROL ライブ]**&#x200B;または&#x200B;**[!UICONTROL スケジュール済み]**&#x200B;ステータスの横にある「ドラフトバージョンを開く」アイコンは、キャンペーンの新しいバージョンが作成され、まだアクティブ化されていないことを示します（[キャンペーンを変更](modify-stop-campaign.md#modify)を参照）。
