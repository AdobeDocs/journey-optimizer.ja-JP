---
solution: Journey Optimizer
product: journey optimizer
title: キャンペーンの基本を学ぶ
description: Journey Optimizer でのキャンペーンについて学ぶ
feature: Campaigns
topic: Content Management
role: User
level: Beginner
keywords: キャンペーン, 方法, 開始, Optimizer
exl-id: e2506a43-e4f5-48af-bd14-ab76c54b7c90
source-git-commit: 50473c401e05b483387f8ff3c5c480020e8d5c14
workflow-type: tm+mt
source-wordcount: '437'
ht-degree: 95%

---

# キャンペーンの基本を学ぶ {#get-started-campaigns}

>[!CONTEXTUALHELP]
>id="ajo_homepage_card3"
>title="キャンペーンの作成"
>abstract="**Adobe Journey Optimizer** を使用すると、様々なチャネルを使用して、特定のオーディエンスに 1 回限りのコンテンツを配信できます。ジャーニーを使用する場合、アクションは順番に実行されます。キャンペーンでは、アクションは指定したスケジュールに基づいて同時にまたは即時に実行されます。"


>[!CONTEXTUALHELP]
>id="campaigns_list"
>title="キャンペーン"
>abstract="キャンペーンを作成して、様々なチャネルで特定のオーディエンスに 1 回限りのコンテンツを配信します。キャンペーンを作成する前に、チャネルサーフェスとAdobe Experience Platform オーディエンスが使用できる状態になっていることを確認します。"

Journey Optimizer キャンペーンを使用すると、様々なチャネルを使用して、特定のオーディエンスに 1 回限りのコンテンツを配信できます。ジャーニーを使用する場合、アクションは順番に実行されます。キャンペーンでは、アクションは指定したスケジュールに基づいて同時にまたは即時に実行されます。

2 種類のキャンペーンを作成できます。

* **スケジュール済みキャンペーン**&#x200B;を使用すると、プロモーションオファー、エンゲージメントキャンペーン、お知らせ、法律上の注意、ポリシーの更新など、マーケティングのユースケースに対するシンプルなアドホックバッチ通信が可能になります。
* **API トリガーキャンペーン**&#x200B;を使用すると、適切なタイミングでオーディエンスにリーチするマーケティング通信や、パスワードのリセットなどの個人に対するトランザクション／運用メッセージが可能になります。これらの場合、プロファイル属性だけでなく、REST API ペイロードであるトリガー内のリアルタイムコンテキストデータも使用したパーソナライゼーションが必要になる可能性があります。

キャンペーンを作成するための主な手順は次のとおりです。

![](assets/create-campaign-process.png)

➡️ [この機能をビデオで確認](#video)

## 開始する前に {#campaign-prerequisites}

Journey Optimizer で最初のキャンペーンの作成を開始する前に、次の前提条件を確認してください。

1. **適切な権限が必要です**。キャンペーンは、Campaign 管理者、Campaign 承認者、Campaign マネージャー、Campaign 閲覧者など、キャンペーンに関係する&#x200B;**[!UICONTROL 製品プロファイル]**&#x200B;へのアクセス権を持つユーザーのみが使用できます。キャンペーンにアクセスできない場合は、権限を拡張する必要があります。

   +++キャンペーン関連の役割の割り当て方法を説明します

   1. [!DNL Permissions] 製品でユーザーに役割を割り当てるには、「**[!UICONTROL 役割]**」タブに移動し、組み込みのキャンペーン関連の&#x200B;**[!UICONTROL 役割]**&#x200B;である Campaign 管理者、Campaign 承認者、Campaign マネージャー、Campaign 閲覧者のいずれかを選択します。

   1. 「**[!UICONTROL ユーザー]**」タブで「**[!UICONTROL ユーザーを追加]**」をクリックします。

   1. ユーザーの名前またはメールアドレスを入力するか、リストからユーザーを選択して、「**[!UICONTROL 保存]**」をクリックします。

      まだユーザーを作成していない場合は、[ユーザーの追加についてのドキュメント](https://experienceleague.adobe.com/ja/docs/experience-platform/access-control/ui/users)を参照してください。

   これにより、ユーザーをインスタンスへリダイレクトするメールがユーザーに送られます。

+++

1. **オーディエンスが必要です**。キャンペーンを作成するには、まずオーディエンスを使用可能にする必要があります。オーディエンスについて詳しくは、[このページ](../audience/about-audiences.md)を参照してください。
1. **チャネルサーフェスが必要です**。チャネルを選択するには、対応するチャネルサーフェス（例：プリセット）を作成し、使用可能にする必要があります。チャネルサーフェスについて詳しくは、[こちらのページ](../configuration/channel-surfaces.md)を参照してください。

## チュートリアルビデオ {#video}

最初のキャンペーンの作成方法について説明します。

>[!VIDEO](https://video.tv.adobe.com/v/346680?quality=12)
