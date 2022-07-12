---
title: キャンペーンの基本を学ぶ
description: キャンペーンの詳細については、 [!DNL Journey Optimizer]
feature: Overview
topic: Content Management
role: User
level: Intermediate
hide: true
hidefromtoc: true
source-git-commit: 6177a33edeb3b8381c3eb5609762b4d974dc93e3
workflow-type: tm+mt
source-wordcount: '313'
ht-degree: 7%

---


# キャンペーンの基本を学ぶ {#get-started-campaigns}

>[!CONTEXTUALHELP]
>id="campaigns_list"
>title="キャンペーン"
>abstract="キャンペーンを使用すれば、複数のチャネルをまたいで特定のセグメントに 1 回限りのコンテンツを配信できます。 新しいキャンペーンを作成する前に、メッセージプリセットとAdobe Experience Platformセグメントが使用できる状態になっていることを確認します。"

## キャンペーンについて {#about}

キャンペーンでは、複数のチャネルを使用して、特定のセグメントに 1 回限りのコンテンツを配信できます。 アクションを順に実行するように設計されたジャーニーとは異なり、キャンペーンは、アクションを即座に、または指定したスケジュールで同時に実行します。

次の 2 種類のキャンペーンを作成できます。

* **予定キャンペーン** プロモーション、エンゲージメントキャンペーン、お知らせ、法律上の注意、ポリシーの更新など、マーケティングの使用例に対するシンプルなアドホックバッチ通信を可能にします。
* **API トリガーキャンペーン** を使用すると、REST API（パスワードリセット、カードの放棄など）を使用したシンプルなトランザクション/操作可能なメッセージで、プロファイル属性とペイロードのコンテキストデータを使用したパーソナライゼーションが必要になる場合があります。

キャンペーンの操作方法を学ぶ：
* [キャンペーンの作成](create-campaign.md)
* [API でトリガーされるキャンペーンの作成](api-triggered-campaigns.md)
* [キャンペーンの変更または停止](modify-stop-campaign.md)
* [キャンペーンのライブレポート](campaign-live-report.md)
* [キャンペーンのグローバルレポート](campaign-global-report.md)

## キャンペーンへのアクセス {#access}

キャンペーンは、 **[!UICONTROL キャンペーン]** メニュー

デフォルトでは、リストには、 **[!UICONTROL ドラフト]**, **[!UICONTROL 予定]**、および **[!UICONTROL ライブ]** ステータス。 停止、完了およびアーカイブされたキャンペーンを表示するには、フィルターをクリアする必要があります。

![](assets/create-campaign-list.png)

## キャンペーンのステータス {#statuses}

キャンペーンには複数のステータスを設定できます。

* **[!UICONTROL ドラフト]**:キャンペーンは編集中です。アクティブ化されていません。
* **[!UICONTROL 有効化中]**:キャンペーンをアクティブ化中です。
* **[!UICONTROL ライブ]**:キャンペーンがアクティブ化されました。
* **[!UICONTROL 予定]**:キャンペーンは、特定の開始日にアクティブ化されるように設定されています。
* **[!UICONTROL 停止]**:キャンペーンは手動で停止されました。 これ以降は、アクティブ化または再利用できません ( [キャンペーンを停止](modify-stop-campaign.md#stop))
* **[!UICONTROL 完了]**:キャンペーンが完了しました。
* **[!UICONTROL アーカイブ済み]**:キャンペーンはアーカイブされました。

>[!NOTE]
>
>ドラフトバージョンを開くアイコン ( **[!UICONTROL ライブ]** または **[!UICONTROL 予定]** ステータスは、キャンペーンの新しいバージョンが作成済みで、まだアクティブ化されていないことを示します ( [キャンペーンの変更](modify-stop-campaign.md#modify)) をクリックします。
