---
solution: Journey Optimizer
product: journey optimizer
title: キャンペーンの基本を学ぶ
description: キャンペーンについて詳しくは、 [!DNL Journey Optimizer] で説明します。
feature: Overview
topic: Content Management
role: User
level: Intermediate
exl-id: e2506a43-e4f5-48af-bd14-ab76c54b7c90
source-git-commit: 020c4fb18cbd0c10a6eb92865f7f0457e5db8bc0
workflow-type: tm+mt
source-wordcount: '403'
ht-degree: 100%

---

# キャンペーンの基本を学ぶ {#get-started-campaigns}

>[!CONTEXTUALHELP]
>id="campaigns_list"
>title="キャンペーン"
>abstract="キャンペーンを作成して、様々なチャネルをまたいだ特定のセグメントに 1 回限りのコンテンツを配信します。キャンペーンを作成する前に、チャネルサーフェス（例：メッセージプリセット）と Adobe Experience Platform セグメントが使用できる状態になっていることを確認します。"

Journey Optimizer キャンペーンを使用すると、様々なチャネルを使用して、特定のセグメントに 1 回限りのコンテンツを配信できます。ジャーニーを使用する場合、アクションは順番に実行されます。キャンペーンでは、アクションは指定したスケジュールに基づいて同時にまたは即時に実行されます。

2 種類のキャンペーンを作成できます。

* **スケジュール済みキャンペーン**&#x200B;を使用すると、プロモーションオファー、エンゲージメントキャンペーン、お知らせ、法律上の注意、ポリシーの更新など、マーケティングの使用例に対するシンプルなアドホックバッチ通信が可能になります。
* **API トリガーキャンペーン**&#x200B;を使用すると、REST API（パスワードリセット、カードの放棄など）を使用したシンプルなトランザクション／操作メッセージが可能で、プロファイル属性とペイロードのコンテキストデータを使用したパーソナライゼーションが必要になる場合があります。

キャンペーンを作成するための主な手順は次のとおりです。

![](assets/create-campaign-process.png)

➡️ [この機能をビデオで確認](#video)

## 開始する前に {#campaign-prerequisites}

Journey Optimizer で最初のキャンペーンの作成を開始する前に、次の前提条件を確認してください。

1. **適切な権限が必要です**。キャンペーンは、Campaign 管理者、Campaign 承認者、Campaign マネージャー、Campaign ビューアなど、キャンペーンに関係する&#x200B;**[!UICONTROL 製品プロファイル]**&#x200B;へのアクセス権を持つユーザーのみが使用できます。

   キャンペーンにアクセスできない場合は、権限を拡張する必要があります。組織の [Adobe Admin Console](https://adminconsole.adobe.com/){target=&quot;_blank&quot;} にアクセスできる場合は、次の手順に従います。そうでない場合は、Journey Optimizer 管理者に問い合わせてください。

   キャンペーン権限の割り当て方法を説明します

   対応する&#x200B;**[!UICONTROL 製品プロファイル]**&#x200B;をユーザーに割り当てるには、次の手順を実行します。

   1. [Adobe Admin Console](https://adminconsole.adobe.com/){target=&quot;_blank&quot;} で、[!DNL Adobe Experience Platform] 製品を選択します。

   1. 「**[!UICONTROL 製品プロファイル]**」タブを参照し、組み込みのキャンペーン関連の&#x200B;**[!UICONTROL 製品プロファイル]**&#x200B;である Campaign 管理者、Campaign 承認者、Campaign マネージャー、Campaign ビューアのいずれかを選択します。

      Journey Optimizer キャンペーンの&#x200B;**[!UICONTROL 製品プロファイル]**&#x200B;と&#x200B;**[!UICONTROL 権限]**&#x200B;について詳しくは、[こちらのページを参照してください](../administration/ootb-product-profiles.md)。

      ![](assets/do-not-localize/admin_1.png)

   1. 選択した&#x200B;**[!UICONTROL 製品プロファイル]**&#x200B;をユーザーに割り当てるには「**[!UICONTROL ユーザーを追加]**」をクリックします。

      ![](assets/do-not-localize/admin_2.png)

   1. ユーザーの名前、グループまたはメールアドレスを入力し、「**[!UICONTROL 保存]**」をクリックします。
   これで、ユーザーが&#x200B;**[!UICONTROL キャンペーン]**&#x200B;にアクセスできるようになりました。

+++

1. **オーディエンスが必要です**。キャンペーンを作成するには、オーディエンスセグメントを使用可能にする必要があります。オーディエンスの作成について詳しくは、[こちらのページ](../segment/about-segments.md)を参照してください。
1. **チャネルサーフェスが必要です**。チャネルを選択するには、対応するチャネルサーフェス（例：プリセット）を作成し、使用可能にする必要があります。チャネルサーフェスについて詳しくは、[こちらのページ](../configuration/channel-surfaces.md)を参照してください。

## ハウツービデオ {#video}

最初のキャンペーンの作成方法について説明します。

>[!VIDEO](https://video.tv.adobe.com/v/346680?quality=12)
