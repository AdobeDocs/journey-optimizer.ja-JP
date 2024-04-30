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
source-git-commit: f71795c99157ce43f5250aaf10eb0b97f235b454
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 79%

---

# キャンペーンの基本を学ぶ {#get-started-campaigns}

>[!CONTEXTUALHELP]
>id="ajo_homepage_card3"
>title="キャンペーンの作成"
>abstract="**Adobe Journey Optimizer** を使用すると、様々なチャネルを使用して、特定のオーディエンスに 1 回限りのコンテンツを配信できます。ジャーニーを使用する場合、アクションは順番に実行されます。キャンペーンでは、アクションは指定したスケジュールに基づいて同時にまたは即時に実行されます。"


>[!CONTEXTUALHELP]
>id="campaigns_list"
>title="キャンペーン"
>abstract="キャンペーンを作成して、様々なチャネルで特定のオーディエンスに 1 回限りのコンテンツを配信します。キャンペーンを作成する前に、チャネルサーフェス（例：メッセージプリセット）と Adobe Experience Platform オーディエンスが使用できる状態になっていることを確認します。"

Journey Optimizer キャンペーンを使用すると、様々なチャネルを使用して、特定のオーディエンスに 1 回限りのコンテンツを配信できます。ジャーニーを使用する場合、アクションは順番に実行されます。キャンペーンでは、アクションは指定したスケジュールに基づいて同時にまたは即時に実行されます。

2 種類のキャンペーンを作成できます。

* **スケジュール済みキャンペーン**&#x200B;を使用すると、プロモーションオファー、エンゲージメントキャンペーン、お知らせ、法律上の注意、ポリシーの更新など、マーケティングのユースケースに対するシンプルなアドホックバッチ通信が可能になります。
* **API トリガーキャンペーン**&#x200B;を使用すると、適切なタイミングでオーディエンスにリーチするマーケティング通信や、パスワードのリセットなどの個人に対するトランザクション／運用メッセージが可能になります。これらの場合、プロファイル属性だけでなく、REST API ペイロードであるトリガー内のリアルタイムコンテキストデータも使用したパーソナライゼーションが必要になる可能性があります。

キャンペーンを作成するための主な手順は次のとおりです。

![](assets/create-campaign-process.png)

➡️ [この機能をビデオで確認](#video)

## 開始する前に {#campaign-prerequisites}

Journey Optimizer で最初のキャンペーンの作成を開始する前に、次の前提条件を確認してください。

1. **適切な権限が必要です**。キャンペーンは、関連するキャンペーンへのアクセス権を持つユーザーのみが使用できます **[!UICONTROL 製品プロファイル]** campaign 管理者、Campaign 承認者、Campaign マネージャー、Campaign ビューアなど。キャンペーンにアクセスできない場合は、権限を拡張する必要があります。

   +++キャンペーン関連の役割を割り当てる方法を学ぶ

   1. でユーザーに役割を割り当てるには [!DNL Permissions] 製品、に移動します **[!UICONTROL 役割]** タブをクリックして、関連する組み込みキャンペーンのいずれかを選択します **[!UICONTROL 役割]**:Campaign 管理者、Campaign 承認者、Campaign マネージャーまたは Campaign ビューア。

   1. 「**[!UICONTROL ユーザー]**」タブで「**[!UICONTROL ユーザーを追加]**」をクリックします。

   1. ユーザーの名前またはメールアドレスを入力するか、リストからユーザーを選択して、「**[!UICONTROL 保存]**」をクリックします。

      ユーザーがまだ作成されていない場合は、を参照してください。 [ユーザー追加ドキュメント](https://experienceleague.adobe.com/en/docs/experience-platform/access-control/ui/users).

   これにより、ユーザーをインスタンスへリダイレクトするメールが、ユーザーに送られます。

+++

1. **オーディエンスが必要です**。キャンペーンを作成するには、まずオーディエンスを使用可能にする必要があります。オーディエンスについて詳しくは、[このページ](../audience/about-audiences.md)を参照してください。
1. **チャネルサーフェスが必要です**。チャネルを選択するには、対応するチャネルサーフェス（例：プリセット）を作成し、使用可能にする必要があります。チャネルサーフェスについて詳しくは、[こちらのページ](../configuration/channel-surfaces.md)を参照してください。

## チュートリアルビデオ {#video}

最初のキャンペーンの作成方法について説明します。

>[!VIDEO](https://video.tv.adobe.com/v/346680?quality=12)
