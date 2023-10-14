---
solution: Journey Optimizer
product: journey optimizer
title: キャンペーンの基本を学ぶ
description: Journey Optimizer でのキャンペーンについて学ぶ
Feature: Campaigns
topic: Content Management
role: User
level: Beginner
keywords: キャンペーン, 方法, 開始, Optimizer
exl-id: e2506a43-e4f5-48af-bd14-ab76c54b7c90
source-git-commit: 3f96cc0037b5bcdb2ce94e2721b02ba13b3cff36
workflow-type: tm+mt
source-wordcount: '468'
ht-degree: 96%

---

# キャンペーンの基本を学ぶ {#get-started-campaigns}

>[!CONTEXTUALHELP]
>id="ajo_homepage_card3"
>title="キャンペーンの作成"
>abstract="用途 **Adobe Journey Optimizer** 様々なチャネルを使用して特定のオーディエンスに 1 回限りのコンテンツを配信する。 ジャーニーを使用する場合、アクションは順番に実行されます。キャンペーンでは、アクションは指定したスケジュールに基づいて同時にまたは即時に実行されます。"


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

1. **適切な権限が必要です**。キャンペーンは、Campaign 管理者、Campaign 承認者、Campaign マネージャー、Campaign ビューアなど、キャンペーンに関係する&#x200B;**[!UICONTROL 製品プロファイル]**&#x200B;へのアクセス権を持つユーザーのみが使用できます。

   キャンペーンにアクセスできない場合は、権限を拡張する必要があります。組織の [Adobe Admin Console](https://adminconsole.adobe.com/){target="_blank"} へのアクセス権を持っている場合は、次の手順に従います。そうでない場合は、Journey Optimizer 管理者に問い合わせてください。

   キャンペーン権限の割り当て方法を説明します

   対応する&#x200B;**[!UICONTROL 製品プロファイル]**&#x200B;をユーザーに割り当てるには、次の手順を実行します。

   1. [Adobe Admin Console](https://adminconsole.adobe.com/){target="_blank"} で、[!DNL Adobe Experience Platform] 製品を選択します。

   1. 「**[!UICONTROL 製品プロファイル]**」タブを参照し、組み込みのキャンペーン関連の&#x200B;**[!UICONTROL 製品プロファイル]**&#x200B;である Campaign 管理者、Campaign 承認者、Campaign マネージャー、Campaign ビューアのいずれかを選択します。

      Journey Optimizer キャンペーンの&#x200B;**[!UICONTROL 製品プロファイル]**&#x200B;と&#x200B;**[!UICONTROL 権限]**&#x200B;について詳しくは、[こちらのページを参照してください](../administration/ootb-product-profiles.md)。

      ![](assets/do-not-localize/admin_1.png)

   1. 「**[!UICONTROL ユーザーを追加]**」をクリックし、選択した&#x200B;**[!UICONTROL 製品プロファイル]**&#x200B;をユーザーに割り当てます。

      ![](assets/do-not-localize/admin_2.png)

   1. ユーザーの名前、グループまたはメールアドレスを入力し、「**[!UICONTROL 保存]**」をクリックします。

   これで、ユーザーが&#x200B;**[!UICONTROL キャンペーン]**&#x200B;にアクセスできるようになりました。

+++

1. **オーディエンスが必要です**。キャンペーンを作成するには、まずオーディエンスを使用可能にする必要があります。オーディエンスについて詳しくは、[このページ](../audience/about-audiences.md)を参照してください。
1. **チャネルサーフェスが必要です**。チャネルを選択するには、対応するチャネルサーフェス（例：プリセット）を作成し、使用可能にする必要があります。チャネルサーフェスについて詳しくは、[こちらのページ](../configuration/channel-surfaces.md)を参照してください。

## チュートリアルビデオ {#video}

最初のキャンペーンの作成方法について説明します。

>[!VIDEO](https://video.tv.adobe.com/v/346680?quality=12)
