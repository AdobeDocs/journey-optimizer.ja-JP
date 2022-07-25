---
title: コンテンツ実験の作成
description: キャンペーンでコンテンツ実験を作成する方法を学ぶ
feature: Overview
topic: Content Management
role: User
level: Beginner
source-git-commit: 0e978d0eab570a28c187f3e7779c450437f16cfb
workflow-type: tm+mt
source-wordcount: '574'
ht-degree: 1%

---

# コンテンツ実験の作成 {#content-experiment}

コンテンツ実験機能を使用すると、複数の配信トリートメントを定義できます。 関心のあるオーディエンスは、関心の指標に関してどれが最も効果が高いかを判断するために、各治療にランダムに割り当てられます。 E メールの内容、件名、送信者を変更できます。

次の例では、配信ターゲットが 2 つのグループに分割されています。それぞれがターゲット母集団の 45%を表し、10%の除外グループは配信を受け取りません。

ターゲットオーディエンスの各ユーザーには、1 つのバージョンの E メールが届き、件名が次の 2 つのいずれかに該当します。

* 1 つは、新しいコレクションと画像に関する 10%のオファーを直接プロモーションする機能です。
* もう 1 つは、画像なしで 10%オフを指定せずに、特別なオファーを広告するだけのものです。

ここでの目標は、受信した実験に応じて、受信者が E メールとやり取りするかどうかを確認することです。 だから我々は選ぶ **[!UICONTROL メール開封数]** を、このコンテンツ実験の主な目標指標として使用します。

![](assets/content_experiment.png)

## キャンペーンの作成 {#campaign-experiment}

1. 次の **[!UICONTROL キャンペーン]** ページ、クリック **[!UICONTROL キャンペーンを作成]**.

   ![](assets/content_experiment_1.png)

1. 選択 **[!UICONTROL 電子メール]** その後 **[!UICONTROL サーフェス]** この配信にを使用します。 詳しくは、 [チャンネルサーフェス](../configuration/message-presets.md) ページ。

   ![](assets/content_experiment_2.png)

1. 「**[!UICONTROL 作成]**」をクリックします。

1. 設定 **[!UICONTROL プロパティ]** 配信の
   * **[!UICONTROL タイトル]**
   * **[!UICONTROL 説明]**
   * **[!UICONTROL カテゴリ]**: **[!UICONTROL マーケティング]** / **[!UICONTROL トランザクション]**

1. コンテンツ実験を開始するには、 **[!UICONTROL コンテンツ実験]** オプション。 この **[!UICONTROL コンテンツ実験]** メニューが表示されます。

   ![](assets/content_experiment_3.png)

1. 設定 **[!UICONTROL 対象ユーザ]** および **[!UICONTROL スケジュール]** 配信のパラメーター。 [詳細情報](create-campaign.md)

1. クリック **[!UICONTROL コンテンツを編集]** 異なる **[!UICONTROL 治療]**.

   ![](assets/content_experiment_4.png)

## 処理を作成する {#treatment-experiment}

1. 次の **[!UICONTROL コンテンツを編集]** ウィンドウ、 **[!UICONTROL 件名]** A メールを送信し、 **[!UICONTROL 保存]**.

   この処理の場合、件名行で直接オファーを指定します。

   ![](assets/content_experiment_5.png)

1. クリック **[!UICONTROL E メールデザイナー]** ：配信のパーソナライズを開始します。

   ![](assets/content_experiment_6.png)

1. E メールをデザインしたら、 **[!UICONTROL 保存]** そして、に戻ります。 **[!UICONTROL コンテンツを編集]** 処理 B を作成するウィンドウ

1. 次の **[!UICONTROL その他のアクション]** ボタン、クリック **[!UICONTROL 複製]**.

   また、 **[!UICONTROL コンテンツ実験]** ボタンをクリックして詳細オプションにアクセスし、 **[!UICONTROL 処理を追加]**.

   ![](assets/content_experiment_7.png)

1. を **[!UICONTROL タイトル]** これらをより良く区別するための治療の

   ![](assets/content_experiment_8.png)

1. 新しく作成したにリンクされた E メール配信を選択 **[!UICONTROL 治療]**.

1. を **[!UICONTROL 件名]** 配信に使用します。

   この処理のため、 **[!UICONTROL 件名]**.

   ![](assets/content_experiment_9.png)

1. クリック **[!UICONTROL E メールデザイナー]** 必要に応じて治療 B の配送をさらにパーソナライズする。

処理がパーソナライズされたら、コンテンツ実験の設定を開始できます。

## コンテンツ実験の設定 {#configure-experiment}

1. 両方の配信がパーソナライズされると、 **[!UICONTROL コンテンツを編集]** ウィンドウ：選択 **[!UICONTROL コンテンツ実験の設定]**.

   ![](assets/content_experiment_10.png)

1. 実験に設定する目標を選択します。

   実験では、 **[!UICONTROL メールを開く]** をクリックして、受信者がプロモーションコードが件名行に含まれている場合に e メールを開くかどうかをテストします。

   ![](assets/content_experiment_11.png)

1. 選択して **[!UICONTROL 除外]** グループを配信に追加します。 このグループはこのキャンペーンからコンテンツを受け取りません。

   切り替えバーをオンにすると、母集団の 10%が自動的に占められます。必要に応じて、この割合を調整できます。

   ![](assets/content_experiment_12.png)

1. その後、各 **[!UICONTROL 治療]** または、 **[!UICONTROL 等しく分布]** 切り替えバー。

   ![](assets/content_experiment_13.png)

1. クリック **[!UICONTROL 保存]** を設定します。

1. コンテンツ実験の準備が整ったら、「 **[!UICONTROL 有効化するレビュー]** ：キャンペーンの概要を表示します。 パラメータが正しくないか見つからない場合は、警告が表示されます。

   ![](assets/content_experiment_15.png)

1. キャンペーンが正しく設定されていることを確認し、 **[!UICONTROL 有効化]** をクリックして起動します。

   ![](assets/content_experiment_14.png)

