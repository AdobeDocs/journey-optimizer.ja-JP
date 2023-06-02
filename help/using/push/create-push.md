---
solution: Journey Optimizer
product: journey optimizer
title: プッシュ通知の設定
description: Journey Optimizer でプッシュ通知を作成する方法を説明します
feature: Overview
topic: Content Management
role: User
level: Beginner
exl-id: 2ebbcd7d-dcfc-4528-974d-6230fc0dca3d
source-git-commit: 64be9c41085dead10ff08711be1f39760a81ff95
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# プッシュ通知の作成 {#create-push-notification}

>[!CONTEXTUALHELP]
>id="ajo_message_push"
>title="プッシュメッセージの作成"
>abstract="プッシュメッセージを追加し、式エディターを使用してパーソナライズを開始します。"

## ジャーニーまたはキャンペーンでのプッシュ通知の作成 {#create}

プッシュ通知を作成するには、次の手順に従います。

>[!BEGINTABS]

>[!TAB ジャーニーへのプッシュの追加]

1. ジャーニーを開き、パレットの「アクション」セクションからプッシュアクティビティをドラッグ＆ドロップします。

   ![](assets/push_create_1.png)

1. メッセージに関する基本情報（ラベル、説明、カテゴリ）を入力したあと、使用するメッセージサーフェスを選択します。**[!UICONTROL サーフェス]**&#x200B;フィールドはデフォルトで、ユーザーがチャネルで最後に使用したサーフェスで事前入力されます。

   ![](assets/push_create_2.png)

   >[!NOTE]
   >
   >ジャーニーからプッシュ通知を送信する場合、Adobe Journey Optimizer の送信時間の最適化機能を利用して、メッセージ送信の最適な時間を予測し、過去の開封率とクリック率に基づいてエンゲージメントを最大化できます。[送信時間の最適化の操作方法を学ぶ](../building-journeys/journeys-message.md#send-time-optimization)

   ジャーニーの設定方法について詳しくは、[このページ](../building-journeys/journey-gs.md)を参照してください。

1. ジャーニー設定画面で、「**[!UICONTROL コンテンツを編集]**」ボタンをクリックして、プッシュコンテンツを設定します。[プッシュ通知のデザイン](design-push.md)

1. メッセージコンテンツを定義したら、テストプロファイルを使用してプレビューとテストを行うことができます。

1. プッシュの準備が整ったら、[ジャーニー](../building-journeys/journey-gs.md)の設定を完了させて送信します。

   プッシュの開封やインタラクションを通じて受信者の行動をトラッキングするには、トラッキングセクションの専用オプションが[メールアクティビティ](../building-journeys/journeys-message.md)で有効になっていることを確認してください。

>[!TAB キャンペーンへのプッシュの追加]

1. スケジュール済みまたは API トリガーキャンペーンを新しく作成し、アクションとして「**[!UICONTROL プッシュ通知]**」を選択し、使用する&#x200B;**[!UICONTROL アプリサーフェス]**&#x200B;を選択します。 [詳しくは、プッシュ設定を参照してください](push-configuration.md)。

   ![](assets/push_create_3.png)

1. 「**[!UICONTROL 作成]**」をクリックします。

1. 「**[!UICONTROL プロパティ]**」セクションで、Campaignの&#x200B;**[!UICONTROL タイトル]**&#x200B;と&#x200B;**[!UICONTROL 説明]**&#x200B;を編集します。

   ![](assets/push_create_4.png)

1. 「**[!UICONTROL オーディエンスを選択]**」ボタンをクリックして、使用可能な Adobe Experience Platform セグメントのリストからターゲットオーディエンスを定義します。 [詳細情報](../segment/about-segments.md)。

1. 「**[!UICONTROL ID 名前空間]**」フィールドで、選択したセグメントから個人を識別するために使用する名前空間を選択します。[詳細情報](../event/about-creating.md#select-the-namespace)。

   ![](assets/push_create_5.png)

1. 「**[!UICONTROL 実験を作成]**」をクリックしてコンテンツ実験の設定を開始し、パフォーマンスを測定してターゲットオーディエンスに最適なオプションを特定するための処理を作成します。[詳細情報](../campaigns/content-experiment.md)

1. キャンペーンは、特定の日付に実行するか、繰り返し頻度で実行するように設計されています。キャンペーンの&#x200B;**[!UICONTROL スケジュール]**&#x200B;を設定する方法については、[この節](../campaigns/create-campaign.md#schedule)を参照してください。

1. **[!UICONTROL アクショントリガー]**&#x200B;メニューから、プッシュ通知の「**[!UICONTROL 頻度]**」を選択します。

   * 1 回
   * 毎日
   * 毎週
   * 毎月

1. キャンペーンの設定画面で、「**[!UICONTROL コンテンツを編集]**」ボタンをクリックして、プッシュコンテンツを設定します。[プッシュ通知のデザイン](design-push.md)

1. メッセージコンテンツを定義したら、テストプロファイルを使用してプレビューとテストを行うことができます。

1. プッシュの準備が整ったら、[キャンペーン](../campaigns/create-campaign.md)の設定を完了させて送信します。

   プッシュの開封やインタラクションを通じて受信者の行動をトラッキングするには、トラッキングセクションの専用オプションが[キャンペーン](../campaigns/create-campaign.md)で有効になっていることを確認してください。

>[!ENDTABS]

**関連トピック**

* [プッシュチャネルの設定](push-gs.md)
* [ジャーニーでのメッセージの追加](../building-journeys/journeys-message.md)

## 迅速配信モード {#rapid-delivery}

>[!CONTEXTUALHELP]
>id="ajo_campaigns_rapid_delivery"
>title="迅速配信モード"
>abstract="迅速配信モードを利用すると、プッシュチャネルで 3,000 万件未満のオーディエンスサイズに高速メッセージ送信を実行できます。"

以前はジャーニーのバーストモードと呼ばれていた迅速配信モードは、キャンペーンを通じて大量のプッシュメッセージを非常に高速に送信できるようにする [!DNL Journey Optimizer] アドオンです。

迅速配信は、メッセージ配信の遅延がビジネス上の重要な問題になる状況で、携帯電話に緊急のプッシュアラートを送信するときに使用します（ニュースチャネルアプリをインストールしたユーザーにニュース速報を流すなど）。

迅速配信モードを使用する際のパフォーマンスについて詳しくは、[Adobe Journey Optimizer 製品の説明](https://helpx.adobe.com/jp/legal/product-descriptions/adobe-journey-optimizer.html)を参照してください。

### 前提条件 {#prerequisites}

迅速配信メッセージには、次の要件があります。

* 迅速配信は&#x200B;**[!UICONTROL スケジュール型]**&#x200B;キャンペーンでのみ使用でき、API トリガーキャンペーンでは使用できません。
* プッシュメッセージはパーソナライズできません。
* ターゲットオーディエンスに含まれるプロファイルの数は 3,000 万未満にする必要があります。
* 迅速配信モードを使用すると、最大 5 つのキャンペーンを同時に実行できます。

### 迅速配信モードの有効化

1. プッシュ通知キャンペーンを作成し、「**[!UICONTROL 迅速配信]**」オプションをオンに切り替えます。

![](assets/create-campaign-burst.png)

1. メッセージコンテンツを設定し、ターゲットにするオーディエンスを選択します。[キャンペーンの作成方法について学ぶ](#create)

   >[!IMPORTANT]
   >
   >メッセージコンテンツにパーソナライゼーションが含まれていないことと、オーディエンスに含まれるプロファイルの数が 3,000 万未満であることを確認します。

1. 通常どおり、キャンペーンをレビューしてアクティブ化します。テストモードでは、メッセージは迅速配信モードで送信されません。