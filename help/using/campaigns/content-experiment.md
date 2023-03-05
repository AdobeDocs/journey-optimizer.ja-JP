---
solution: Journey Optimizer
product: journey optimizer
title: コンテンツ実験の作成
description: キャンペーンでコンテンツ実験を作成する方法を学ぶ
feature: A/B Testing
topic: Content Management
role: User
level: Beginner
keywords: コンテンツ, 実験, 複数, オーディエンス,
hide: true
hidefromtoc: true
exl-id: bd35ae19-8713-4571-80bc-5f40e642d121
source-git-commit: 2bf4883fa4b649a807608403d48f6a68b73a8626
workflow-type: ht
source-wordcount: '1137'
ht-degree: 100%

---

# コンテンツ実験の作成 {#content-experiment}

>[!CONTEXTUALHELP]
>id="ajo_campaigns_content_experiment"
>title="コンテンツ実験"
>abstract="複数の配信処理を定義してオーディエンスに最適な組み合わせを決定するために、配信コンテンツ、件名、送信者を変更することを選択できます。"

>[!AVAILABILITY]
>
>**コンテンツ実験**&#x200B;機能は現在、一連の組織でのみ使用できます（使用制限あり）。詳しくは、アドビ担当者にお問い合わせください。

Journey Optimizer のコンテンツ実験を使用すると、複数の配信処理を定義して、ターゲットオーディエンスに最適なパフォーマンスを発揮する配信を測定できます。配信コンテンツ、件名または送信者を変更できます。関心のあるオーディエンスが各処理にランダムに割り当てられて、指定の指標に関して最も効果が高い処理が判断されます。

>[!NOTE]
>
>コンテンツ実験を開始する前に、レポート設定がカスタムデータセットに対応するよう設定されていることを確認します。詳しくは、[この節](reporting-configuration.md)を参照してください。

次の例では、配信ターゲットが 2 つのグループ（それぞれがターゲット母集団の 45％を表す）に分割されています。10％の除外グループは配信を受け取りません。

ターゲットオーディエンスの各ユーザーには、1 つのバージョンのメール（件名は次の 2 つのいずれか）が届きます。

* 1 つは、新しいコレクションと画像に関する 10％のオファーを直接プロモーションするものです。
* もう 1 つは、画像なしで 10％オフを指定せずに、特別なオファーを広告するだけのものです。

ここでの目標は、受信した実験に応じて、受信者がメールとやり取りするかどうかを確認することです。 そのため、このコンテンツ実験の主な目標指標として「**[!UICONTROL メール開封数]**」を選択します。

![](assets/content_experiment.png)

## キャンペーンの作成 {#campaign-experiment}

1. **[!UICONTROL キャンペーン]**&#x200B;ページから、「**[!UICONTROL キャンペーンを作成]**」をクリックします。

   ![](assets/content_experiment_1.png)

1. チャネルを選択したあと、この配信に使用する「**[!UICONTROL サーフェス]**」を選択して、「**[!UICONTROL 作成]**」をクリックします。詳しくは、[チャネルサーフェス](../configuration/channel-surfaces.md)ページを参照してください。

   ![](assets/content_experiment_2.png)

1. 配信の&#x200B;**[!UICONTROL プロパティ]**&#x200B;を次のように設定します。
   * **[!UICONTROL 名前]**
   * **[!UICONTROL 説明]**

1. ターゲットとするオーディエンスを定義します。それには、「**[!UICONTROL オーディエンスを選択]**」ボタンをクリックして、使用可能な Adobe Experience Platform セグメントのリストを表示します。[セグメントについて詳しくはこちらを参照](../segment/about-segments.md)

   「**[!UICONTROL ID 名前空間]**」フィールドで、選択したセグメントから個人を識別するために使用する名前空間を選択します。[詳細情報](get-started-experiment.md#content-experiment-work)

   ![](assets/content_experiment_16.png)

1. 「**[!UICONTROL アクショントラッキング]**」セクションで、配信に対する受信者の反応を追跡するかどうかを指定します。クリック数や開封数を追跡できます。

   キャンペーンが実行されると、キャンペーンレポートからトラッキング結果にアクセスできるようになります。

1. キャンペーンを特定の日付に実行したり、繰り返し実行したりするには、「**[!UICONTROL スケジュール]**」セクションを設定します。 [詳細情報](create-campaign.md)

1. 「**[!UICONTROL コンテンツを編集]**」をクリックして、配信のパーソナライズを開始します。[詳細情報](../email/content-from-scratch.md)

   ![](assets/content_experiment_17.png)

1. **[!UICONTROL コンテンツを編集]**&#x200B;ウィンドウから、処理 A のパーソナライズを開始します。

   この処理では、件名に特別なオファーを直接指定し、パーソナライゼーションを加えます。

   ![](assets/content_experiment_5.png)

## コンテンツ実験の設定 {#configure-experiment}

1. 配信をパーソナライズしたら、キャンペーンの概要ページで「**[!UICONTROL 実験を作成]**」をクリックして、コンテンツ実験の設定を開始します。

   ![](assets/content_experiment_3.png)

1. 実験に設定する&#x200B;**[!UICONTROL 成功指標]**&#x200B;を選択します。

   この実験では、件名にプロモーションコードが含まれている場合に受信者がメールを開くかどうかをテストするために、「**[!UICONTROL メールの開封]**」を選択します。

   ![](assets/content_experiment_11.png)

1. 「**[!UICONTROL 処理を追加]**」をクリックして、新しい処理を必要な数だけ作成します。

   ![](assets/content_experiment_8.png)

1. 処理の「**[!UICONTROL タイトル]**」を変更して、区別しやすくします。

1. 配信に&#x200B;**[!UICONTROL 除外]**&#x200B;グループを追加することを選択します。このグループは、このキャンペーンからコンテンツを受け取りません。

   切り替えバーをオンにすると、母集団の 10%が自動的に取得されます。必要に応じて、この割合を調整できます。

   ![](assets/content_experiment_12.png)

1. その後、各&#x200B;**[!UICONTROL 処理]**&#x200B;に正確な割合を割り当てるか、**[!UICONTROL 等しく分布]**&#x200B;切り替えバーをオンにするかを選択できます。

   ![](assets/content_experiment_13.png)

1. 設定が完了したら、「**[!UICONTROL 作成]**」をクリックします。

## 処理の設計 {#treatment-experiment}

1. **[!UICONTROL コンテンツを編集]**&#x200B;ウィンドウで、処理 B を選択してコンテンツを変更します。

   ここでは、「**[!UICONTROL 件名]**」でオファーを指定しないようにします。

   ![](assets/content_experiment_18.png)

1. 「**[!UICONTROL メール本文を編集]**」をクリックして、処理 B をさらにパーソナライズします。

   ![](assets/content_experiment_9.png)

1. 処理を設計したら、「**[!UICONTROL その他のアクション]**」をクリックして、処理に関連するオプション（「**[!UICONTROL 名前変更]**」、「**[!UICONTROL 複製]**」および「**[!UICONTROL 削除]**」）にアクセスします。

   ![](assets/content_experiment_7.png)

1. 必要に応じて、 **[!UICONTROL 実験の設定]**&#x200B;メニューにアクセスして、処理の設定を変更します。

   ![](assets/content_experiment_19.png)

1. メッセージコンテンツを定義したら、「**[!UICONTROL コンテンツをシミュレート]**」ボタンをクリックして配信のレンダリングを制御したり、テストプロファイルでパーソナライズ設定を確認したります。[詳細情報](../email/preview.md)

1. コンテンツ実験の準備が整ったら、キャンペーンの概要ページで「**[!UICONTROL アクティブ化するレビュー]**」をクリックして、キャンペーンの概要を表示できます。パラメーターが正しくない、または見つからない場合は、警告が表示されます。

   ![](assets/content_experiment_15.png)

1. キャンペーンが正しく設定されていることを確認し、「**[!UICONTROL アクティブ化]**」をクリックしてキャンペーンを開始します。

   ![](assets/content_experiment_14.png)

実験とキャンペーンを設定したら、キャンペーンのレポートを使用して、問題なく配信できたかどうかを追跡できます。

## 目標レポート {#objectives-global}

>[!AVAILABILITY]
>
>コンテンツ実験機能は現在、特定の組織のみが使用できます（使用制限あり）。詳しくは、アドビ担当者にお問い合わせください。

![](assets/performance_report.gif)

キャンペーンレポートの「**[!UICONTROL 目標]**」タブを使用すると、1 つの特定の指標をターゲット設定することで、配信のレポートをより細かく調整できます。

一覧表示された&#x200B;**[!UICONTROL 目標]**&#x200B;は、追加情報を取得するためのシステムへの接続を定義する&#x200B;**[!UICONTROL データセット]**&#x200B;にリンクされています。ビルトインの&#x200B;**[!UICONTROL 目標]**&#x200B;リストが用意されていますが、新しい&#x200B;**[!UICONTROL データセット]**&#x200B;を追加することで独自の目標を追加できます。詳細な手順については、こちらの[節](reporting-configuration.md)を参照してください。

ターゲットにする目標を選択した後、2 つの&#x200B;**[!UICONTROL パフォーマンスの概要]**&#x200B;および&#x200B;**[!UICONTROL キャンペーン目標]**&#x200B;ウィジェットには、配信パフォーマンスの詳細な概要が表示されます。

**[!UICONTROL キャンペーン目標]**&#x200B;ウィジェットを使用して、主な目標を別の指標と比較することもできます。

必要に応じて、各ウィジェットのサイズを変更することや削除することができます。詳しくは、この[節](../reports/global-report.md#modify-dashboard)を参照してください。

## 実験レポート {#experimentation-global}

>[!CONTEXTUALHELP]
>id="ajo_campaigns_content_experiment_click"
>title="成功指標"
>abstract="実験の作成時に以前に選択した成功指標の合計値を、プロファイル数で割った値です。"

>[!AVAILABILITY]
>
>コンテンツ実験機能は現在、特定の組織のみが使用できます（使用制限あり）。詳しくは、アドビ担当者にお問い合わせください。

![](assets/experimentation_report_3.png)

キャンペーンの&#x200B;**[!UICONTROL グローバルレポート]**&#x200B;の「**[!UICONTROL 実験]**」タブには、各バリアントのパフォーマンスや最も優れたパフォーマンス関する情報が表示されます。

最も高いパフォーマンスの判定には時間がかかる場合があり、このアイコン ![](assets/experimentation_report_1.png) が表示されます。

**[!UICONTROL 実験結果]**&#x200B;ウィジェットは、各バリアントのパフォーマンスの詳細を説明します。ベースラインを変更するには、**[!UICONTROL ベースライン]**&#x200B;ドロップダウンから処理の 1 つを選択します。最も優れた処理には、星のアイコンが表示されます。

このテーブルは、次の指標を表しています。

* **[!UICONTROL プロファイル]**：この処理の対象となるプロファイルの数。

* **[!UICONTROL ユニークアウトバウンドクリック数]**：アウトバウンドチャネルでのクリック総数。

* **[!UICONTROL プロファイルあたりのカウント]**：実験の目的の指標の合計値を、プロファイル数で割った値です。

* **[!UICONTROL 信頼区間]**：ベースラインと最もパフォーマンスの高い処理との間のパフォーマンスの差の割合。[詳細情報](../campaigns/experiment-calculations.md#confidence-intervals)。

* **[!UICONTROL 平均上昇率]**：ベースラインに対する特定の処理のコンバージョン率における改善の割合。 [詳細情報](../campaigns/experiment-calculations.md#understand-lift)

* **[!UICONTROL 信頼性]**：ある処理がベースライン処理と同じであることを示す証拠。[詳細情報](../campaigns/experiment-calculations.md#understand-confidence)

これらの結果の詳細と解釈について詳しくは、[このページ](../campaigns/get-started-experiment.md#interpret-results)を参照してください。
