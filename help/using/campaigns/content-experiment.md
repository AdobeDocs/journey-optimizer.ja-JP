---
title: コンテンツ実験の作成
description: キャンペーンでコンテンツ実験を作成する方法を学ぶ
feature: Overview
topic: Content Management
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: bd35ae19-8713-4571-80bc-5f40e642d121
source-git-commit: 711fdf1dce0688d2e21d405a4e3e8777612b2f3b
workflow-type: tm+mt
source-wordcount: '971'
ht-degree: 67%

---

# コンテンツ実験の作成 {#content-experiment}

>[!AVAILABILITY]
>
>コンテンツ実験の機能は現在、一連の組織でのみ使用できます（使用制限があります）。詳しくは、アドビ担当者にお問い合わせください。

コンテンツ実験機能を使用すると、複数の配信処理を定義できます。関心のあるオーディエンスは、関心の指標に関してどれが最も効果が高いかを判断するために、各処理にランダムに割り当てられます。メールのコンテンツ、件名、送信者を変更できます。

次の例では、配信ターゲットが 2 つのグループ（それぞれがターゲット母集団の 45％を表す）に分割されています。10％の除外グループは配信を受け取りません。

ターゲットオーディエンスの各ユーザーには、1 つのバージョンのメールが届き、件名は次の 2 つのいずれかに該当します。

* 1 つは、新しいコレクションと画像に関する 10％のオファーを直接プロモーションするものです。
* もう 1 つは、画像なしで 10％オフを指定せずに、特別なオファーを広告するだけのものです。

ここでの目標は、受信した実験に応じて、受信者がメールとやり取りするかどうかを確認することです。 そのため、このコンテンツ実験の主な目標指標として「**[!UICONTROL メール開封数]**」を選択します。

![](assets/content_experiment.png)

## キャンペーンの作成 {#campaign-experiment}

1. **[!UICONTROL キャンペーン]**&#x200B;ページから、「**[!UICONTROL キャンペーンを作成]**」をクリックします。

   ![](assets/content_experiment_1.png)

1. 「**[!UICONTROL メール]**」を選択し、この配信に使用する「**[!UICONTROL サーフェス]**」を選択します。詳しくは、[チャネルサーフェス](../configuration/channel-surfaces.md)ページを参照してください。

   ![](assets/content_experiment_2.png)

1. 「**[!UICONTROL 作成]**」をクリックします。

1. 配信の&#x200B;**[!UICONTROL プロパティ]**&#x200B;を設定します。
   * **[!UICONTROL タイトル]**
   * **[!UICONTROL 説明]**
   * **[!UICONTROL カテゴリ]**：**[!UICONTROL マーケティング]**／**[!UICONTROL トランザクション]**

1. コンテンツ実験を開始するには、「**[!UICONTROL コンテンツ実験]**」オプションを切り替えます。**[!UICONTROL コンテンツ実験]**&#x200B;メニューが表示されます。

   ![](assets/content_experiment_3.png)

1. 配信の&#x200B;**[!UICONTROL オーディエンス]**&#x200B;と&#x200B;**[!UICONTROL スケジュール]**&#x200B;のパラメーターを設定します。[詳細情報](create-campaign.md)

1. 「**[!UICONTROL コンテンツを編集]**」をクリックして、様々な&#x200B;**[!UICONTROL 処理]**&#x200B;のパーソナライズを開始します。

   ![](assets/content_experiment_4.png)

## 処理の作成 {#treatment-experiment}

1. **[!UICONTROL コンテンツを編集]**&#x200B;ウィンドウから、処理 A メールの&#x200B;**[!UICONTROL 件名]**&#x200B;を追加し、「**[!UICONTROL 保存]**」をクリックします。

   この処理では、件名にオファーを直接指定します。

   ![](assets/content_experiment_5.png)

1. 「**[!UICONTROL E メール デザイナー]**」をクリックし、配信のパーソナライズを開始します。

   ![](assets/content_experiment_6.png)

1. メールをデザインしたら、「**[!UICONTROL 保存]**」をクリックして&#x200B;**[!UICONTROL コンテンツを編集]**&#x200B;ウィンドウに戻り、処理 B を作成します。

1. 「**[!UICONTROL その他のアクション]**」ボタンから、「**[!UICONTROL 複製]**」をクリックします。

   また、「**[!UICONTROL コンテンツ実験]**」ボタンをクリックして詳細オプションにアクセスし、「**[!UICONTROL 処理を追加]**」をクリックして、新しい処理を最初から開始することもできます。

   ![](assets/content_experiment_7.png)

1. 処理の&#x200B;**[!UICONTROL タイトル]**&#x200B;を変更し、より区別しやすくします。

   ![](assets/content_experiment_8.png)

1. 新しく作成した&#x200B;**[!UICONTROL 処理]**&#x200B;にリンクされたメール配信を選択します。

1. 配信の&#x200B;**[!UICONTROL 件名]**&#x200B;を追加します。

   この処理では、**[!UICONTROL 件名]**&#x200B;にオファーを指定しないことを選択します。

   ![](assets/content_experiment_9.png)

1. 必要に応じて、「**[!UICONTROL E メールデザイナー]**」をクリックして、処理 B の配信をさらにパーソナライズします。

処理がパーソナライズされたら、コンテンツ実験の設定を開始できます。

## コンテンツ実験の設定 {#configure-experiment}

1. 両方の配信がパーソナライズされている場合は、**[!UICONTROL コンテンツを編集]**&#x200B;ウィンドウから「**[!UICONTROL コンテンツ実験を設定]**」を選択します。

   ![](assets/content_experiment_10.png)

1. 実験に設定する目標を選択します。

   この実験では、件名にプロモーションコードが含まれている場合に受信者がメールを開くかどうかをテストするために、「**[!UICONTROL メール開封数]**」を選択します。

   ![](assets/content_experiment_11.png)

1. 配信に&#x200B;**[!UICONTROL 除外]**&#x200B;グループを追加することを選択します。このグループは、このキャンペーンからコンテンツを受け取りません。

   切り替えバーをオンにすると、母集団の 10%が自動的に取得されます。必要に応じて、この割合を調整できます。

   ![](assets/content_experiment_12.png)

1. その後、各&#x200B;**[!UICONTROL 処理]**&#x200B;に正確な割合を割り当てるか、**[!UICONTROL 等しく分布]**&#x200B;切り替えバーをオンにするかを選択できます。

   ![](assets/content_experiment_13.png)

1. 設定したら「**[!UICONTROL 保存]**」をクリックします。

1. コンテンツ実験の準備が整ったら、「**[!UICONTROL アクティブ化するレビュー]**」をクリックして、キャンペーンの概要を表示できます。パラメーターが正しくない、または見つからない場合は、警告が表示されます。

   ![](assets/content_experiment_15.png)

1. キャンペーンが正しく設定されていることを確認し、「**[!UICONTROL アクティブ化]**」をクリックしてキャンペーンを開始します。

   ![](assets/content_experiment_14.png)

実験とキャンペーンを設定したら、キャンペーンレポートで配信の成功をフォローできます。

## 目標レポート {#objectives-global}

>[!AVAILABILITY]
>
>コンテンツ実験の機能は現在、一連の組織でのみ使用できます（使用制限があります）。詳しくは、アドビ担当者にお問い合わせください。

![](assets/performance_report.gif)

この **[!UICONTROL 目標]** 」タブを使用すると、1 つの特定の指標をターゲット設定することで、配信のレポートをより細かく調整できます。

この **[!UICONTROL 目標]** リストは次にリンクされています： **[!UICONTROL データセット]** 追加情報を取得するためにシステムへの接続を定義する 組み込みの **[!UICONTROL 目標]** は使用できますが、新しい **[!UICONTROL データセット]**. 詳細な手順については、次を参照してください。 [セクション](reporting-configuration.md).

ターゲットにする目標を選択した後、2 つの目標 **[!UICONTROL パフォーマンスの概要]** および **[!UICONTROL キャンペーンの目的]** ウィジェットには、配信パフォーマンスの詳細な概要が表示されます。

を使用 **[!UICONTROL キャンペーンの目的]** ウィジェットを使用して、主な目標を別の指標と比較することもできます。

各ウィジェットは、必要に応じてサイズ変更や削除が可能です。 詳しくは、この[節](../reports/global-report.md#modify-dashboard)を参照してください。

## 実験レポート {#experimentation-global}

>[!AVAILABILITY]
>
>コンテンツ実験の機能は現在、一連の組織でのみ使用できます（使用制限があります）。詳しくは、アドビ担当者にお問い合わせください。

![](assets/experimentation_report_3.png)

キャンペーンから **[!UICONTROL グローバルレポート]**、 **[!UICONTROL 実験]** 「 」タブには、各バリアントのパフォーマンスに関する主な情報の詳細と、パフォーマンスが最も優れているかどうかに関する情報が表示されます。

最もパフォーマーの高いものを定義するには、しばらく時間がかかる場合があります。このアイコンが表示されます ![](assets/experimentation_report_1.png).

この **[!UICONTROL 実験結果]** ウィジェットは、各バリアントのパフォーマンスの詳細を説明します。 基準を変更するには、 **[!UICONTROL ベースライン]** ドロップダウン。 最も良い治療法は星のアイコンで表されます。

この表は、次の指標を示しています。

* **[!UICONTROL プロファイル]**:この治療の対象となるプロファイルの数。

* **[!UICONTROL 個別アウトバウンドクリック数]**:アウトバウンドチャネルでのクリック総数。

* **[!UICONTROL プロファイルあたりの数]**:実験の目的の指標の合計値を、プロファイル数で割った値です。

* **[!UICONTROL 信頼区間]**:ベースラインと最もパフォーマンスの高い治療との間の性能差の割合。 [詳細情報](../campaigns/experiment-calculations.md#confidence-intervals)。

* **[!UICONTROL 平均上昇率]**:ベースラインに対する特定の治療のコンバージョン率の改善率。 [詳細情報](../campaigns/experiment-calculations.md#understand-lift)

* **[!UICONTROL 信頼性]**:与えられた治療が基準治療と同じであるという証拠。 [詳細情報](../campaigns/experiment-calculations.md#understand-confidence)

これらの結果の詳細と解釈については、 [このページ](../campaigns/get-started-experiment.md#interpret-results).
