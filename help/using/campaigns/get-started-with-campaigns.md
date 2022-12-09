---
solution: Journey Optimizer
product: journey optimizer
title: キャンペーンの開始
description: のキャンペーンについて詳しくは、 [!DNL Journey Optimizer]
feature: Overview
topic: Content Management
role: User
level: Intermediate
exl-id: e2506a43-e4f5-48af-bd14-ab76c54b7c90
source-git-commit: 020c4fb18cbd0c10a6eb92865f7f0457e5db8bc0
workflow-type: tm+mt
source-wordcount: '385'
ht-degree: 0%

---

# キャンペーンの開始 {#get-started-campaigns}

>[!CONTEXTUALHELP]
>id="campaigns_list"
>title="キャンペーン"
>abstract="様々なチャンネルにわたって特定のセグメントに1度だけコンテンツを配信するためのキャンペーンを作成します。 キャンペーンを作成する前に、チャネルサーフェス (メッセージプリセット) があり、Adobe エクスペリエンスプラットフォームセグメントを使用できるようになっていることを確認してください。"

旅のオプティマイザーキャンペーンを使用して、様々なチャネルを使用して、特定のセグメントに1回限りのコンテンツを配信することができます。 Journeys を使用している場合、アクションは順番に実行されます。 キャンペーンを使用すると、直ちにアクションが実行されるか、または指定されたスケジュールに基づいてアクションが実行されます。

次の2種類のキャンペーンを作成できます。

* **定期的なキャンペーン** を使用すると、販促オファー、エンゲージメントキャンペーン、告知、法律上の注意、ポリシーの更新など、マーケティング用の用途に単純なアドホックなバッチ通信が可能になります。
* **API によってトリガー** される単純なトランザクション/操作メッセージには、REST api (パスワードリセット、カード abandonment など) を使用できます。これにより、プロファイル属性およびペイロードのコンテキストデータを使用して、必要に応じてカスタマイズを行うことができます。

キャンペーンを作成するための主な手順は次のとおりです。

![](assets/create-campaign-process.png)

➡️ [ ビデオでのこの機能の検出](#video)

## 開始する前に {#campaign-prerequisites}

最初のキャンペーンの作成を開始する前に、次に示す前提条件を確認してから、旅オプティマイザーで行います。

1. **適切な権限** が必要です。 キャンペーンは、キャンペーンアドミニストレーター、キャンペーン承認担当者、キャンペーンマネージャー、キャンペーンビューアなどのキャンペーン **[!UICONTROL Product profile]** にアクセスしているユーザーだけが使用できます。

   キャンペーンにアクセスできない場合は、アクセス許可を拡張する必要があります。 御社の Adobe Admin Console ](https://adminconsole.adobe.com/) {target = &quot;_blank&quot;} に [ アクセスできる場合は、以下の手順を実行してください。それ以外の場合は、旅オプティマイザーの管理者に連絡してください。

   + + + キャンペーンの権限の割り当て方法を参照してください。

   をユーザーに割り当てるには、次のようにし **[!UICONTROL Product profile]** ます。

   1. Adobe Admin Console ](https://adminconsole.adobe.com/) {target = &quot;_blank&quot;} から [ 製品を選択 [!DNL Adobe Experience Platform] します。

   1. タブに **[!UICONTROL Product profile]** 移動し、キャンペーンアドミニストレーター、キャンペーン承認者、キャンペーンマネージャー、またはキャンペーンビューアの **[!UICONTROL Product profile]** いずれかを選択します。

      詳細につい **[!UICONTROL Product profiles]** **[!UICONTROL Permissions]** ては、 [ このページ ](../administration/ootb-product-profiles.md) を参照してください。

      ![](assets/do-not-localize/admin_1.png)

   1. クリック **[!UICONTROL Add user]** すると、選択した **[!UICONTROL Product profile]** がユーザーに割り当てられます。

      ![](assets/do-not-localize/admin_2.png)

   1. ユーザーの名前、グループ、または電子メールアドレスを入力して、をクリック **[!UICONTROL Save]** します。
   ユーザーがにアクセス **[!UICONTROL Campaigns]** できるようになりました。

+++

1. **対象** 者が必要です。 キャンペーンを作成する前に、対象ユーザーセグメントを利用可能にする必要があります。 このページ ](../segment/about-segments.md) での参加者の作成 [ に関する詳細情報を表示します。
1. **チャンネル** を作成する必要があります。 チャンネルを選択できるようにするには、対応するチャンネルサーフェス (例えば、プリセット) を作成して、使用可能にする必要があります。 このページ ](../configuration/channel-surfaces.md) のチャンネルサーフェス [ について詳しくは、こちらを参照してください。

## 操作方法のビデオ {#video}

最初のキャンペーンの作成方法について説明します。

>[!VIDEO](https://video.tv.adobe.com/v/346680?quality=12)
