---
solution: Journey Optimizer
product: journey optimizer
title: 条件アクティビティ
description: 条件アクティビティについて学ぶ
feature: Journeys, Activities
topic: Content Management
role: User
level: Intermediate
keywords: アクティビティ，条件，キャンバス，ジャーニー，最適化
badge: label="限定提供" type="Informative"
source-git-commit: a770cbc1736e7add7e25f2cc8210d81bd8b2e375
workflow-type: tm+mt
source-wordcount: '1024'
ht-degree: 5%

---

# アクティビティを最適化 {#journey-path-optimization}

>[!CONTEXTUALHELP]
>id="ajo_journey_optimize"
>title="アクティビティを最適化"
>abstract="**最適化** アクティビティを使用すると、実験、ターゲティング、特定の条件など、特定の条件に基づいて複数のパスを作成することで、個人のジャーニーの進行状況を定義できます。"

>[!AVAILABILITY]
>
>この機能は、限定提供です。アクセス権を取得するには、アドビ担当者にお問い合わせください。

**最適化** アクティビティを使用すると、実験、ターゲティング、特定の条件などの特定の条件に基づいて複数の **パス** を作成して、個人がジャーニーをどのように進行するかを定義できます。これにより、最大限のエンゲージメントと成功を確保し、高度にカスタマイズされた効果的なジャーニーを作成できます。

**ジャーニーパス** は、次のいずれかで構成されます。

* 通信の順序付け；
* 中間の時間；
* 通信の数：
* またはこれらの 3 つの変数の任意の組み合わせ。

例えば、1 つのパスに 1 つのメールを含め、別のパスに 2 つの SMS メッセージを含め、3 番目のパスにメール、2 時間の [ 待機 ](wait-activity.md) ノード、そして SMS メッセージを含めることができます。

<!--With this feature, [!DNL Journey Optimizer] empowers you with the tools to deliver personalized and optimized paths to your audience, ensuring maximum engagement and success to create highly customized and effective journeys.-->

**最適化** アクティビティを通じて、次の操作を実行できます。

* 実行 [ パス実験 ](#experimentation)
* 各ジャーニーパスでの [ ターゲティング ](#targeting) ルールの活用
* パスへの [ 条件 ](#conditions) の適用

![](assets/journey-optimize.png)

ジャーニーがライブになると、プロファイルは定義された条件に基づいて評価され、一致条件に基づいてジャーニーから適切なパスに送信されます。

## 実験を使用 {#experimentation}

実験では、ランダム分割に基づいて様々なパスをテストし、事前定義された成功指標に基づいて最もパフォーマンスが高いパスを決定できます。

ジャーニーで実験を設定するには、次の手順に従います。

次の 3 つのパスを比較するとします。

* 1 つのパスと 1 つのメール
* 2 つ目のパス（2 日間の待機ノードとメール）。
* メールと SMS メッセージの 3 番目のパス。

1. **[!UICONTROL 最適化]** アクティビティをジャーニーキャンバスにドロップします。

1. レポートモードとテストモードのログでアクティビティを識別するオプションのラベルを追加します。

1. **[!UICONTROL 方法]** ドロップダウンリストから **[!UICONTROL 実験]** を選択します。

   ![](assets/journey-optimize-experiment.png){width=85%}

1. **[!UICONTROL 実験設定]** をクリックします。

1. 必要に応じて実験を設計および設定します。 [詳細情報](../content-management/content-experiment.md)

   <!--
    ![](../campaigns/assets/msg-optimization-create-experiment.png){width=85%}
    Replace with appropriate screenshot
    The experiment applies to all the activities in the journey.TBC
   -->

ジャーニーがライブになると、ユーザーは異なるパスを進むようにランダムに割り当てられます。 [!DNL Journey Optimizer] は、どのパスがより多くの購入を促進するかを追跡し、実用的なインサイトを提供します。

<!--Follow the success of your journey with the [Experimentation journey report](../reports/campaign-global-report-cja-experimentation.md). Is there a report specific to experimentation in journey?-->

### 実験を使用した使用例 {#uc-experiment}

次の例は、**[!UICONTROL 最適化]** アクティビティを **[!UICONTROL 実験]** メソッドと共に使用して、全体的に最適なパスを決定する方法を示しています。

**チャネルの有効性**

メールと SMS で最初のメッセージを送信することでコンバージョンが高くなるかどうかをテストします。

* コンバージョン率を最適化指標として使用します（例：購入、サインアップ）。

![](assets/journey-optimize-experiment-uc.png)

**メッセージの頻度**

実験を実行して、1 週間に 1 件のメールと 3 件のメールを送信した結果、購入が増えたかどうかを確認します。

* 最適化指標として、購入または購読解除率を使用します。

**通信間の待機時間**

フォローアップの前に 24 時間待機と 72 時間待機を比較して、エンゲージメントを最大化するタイミングを判断します。

* 最適化指標としてクリックスルー率または売上高を使用します。

## ターゲティングの活用 {#targeting}

ターゲティングを使用すると、特定のオーディエンスセグメント <!-- depending on profile attributes or contextual attributes--> に基づいて、ジャーニーパスの 1 つにエントリする資格を顧客が得るために満たす必要がある特定のルールまたは資格を決定できます。

特定のパスのランダムな割り当てである実験とは異なり、ターゲティングは、適切なオーディエンスまたはプロファイルが指定されたパスに確実に入るという点で決定的です。

ターゲティングを使用すると、次の条件に基づいて特定のルールを定義できます。

* **場所などのユーザープロファイル属性** ジオターゲティング）、年齢または環境設定。 例えば、米国のユーザーには「ゴールデンゲート」プロモーションが表示され、フランスのユーザーには「エッフェル塔」プロモーションが表示されます。

* **コンテキストデータ**：デバイスタイプ（例： デバイスターゲティング）、時間帯またはセッションの詳細。 例えば、デスクトップユーザーはデスクトップ用に最適化されたコンテンツを受信し、モバイルユーザーはモバイル用に最適化されたコンテンツを受信します。

* **オーディエンス**：特定のオーディエンスメンバーシップを持つプロファイルを含めたり除外したりするために使用できます。

ジャーニーでターゲティングを設定するには、次の手順に従います。

1. **[!UICONTROL 最適化]** アクティビティをジャーニーキャンバスにドロップします。

1. レポートモードとテストモードのログでアクティビティを識別するオプションのラベルを追加します。

1. **[!UICONTROL メソッド]** ドロップダウンリストから **[!UICONTROL ターゲティング]** を選択します。

   ![](assets/journey-optimize-targeting.png){width=85%}

1. **[!UICONTROL ターゲティングルールを作成]** をクリックします。

1. ルールビルダーを使用して条件を定義します。 例えば、米国居住者のルール、フランス居住者のルール、インド居住者のルールを定義します。

   ![](assets/journey-targeting-rule.png)

1. 必要に応じて「**[!UICONTROL フォールバックコンテンツを有効にする]** を選択します。 フォールバックコンテンツを使用すると、ターゲティングルールが認定されていない場合に、オーディエンスがデフォルトコンテンツを受け取ることができます。 このオプションを選択しない場合、上記で定義されたターゲティングルールに該当しないオーディエンスは、フォールバックパスに入りません。

1. ターゲティングルールの設定を保存します。

1. ジャーニーに戻り、特定のアクションをドロップして各パスをカスタマイズします。 例えば、米国居住者向けの特定のメールや、フランス居住者向けの別のメールなどを作成できます。

   ![](assets/journey-targeting-paths.png)

1. ターゲティングルールの設定で定義した各グループに適したコンテンツを設計します。 異なるパス間をシームレスに移動できます。

   ![](assets/journey-targeting-design.png)

   この例では、米国居住者の特定のパス、フランス居住者の別のパス、およびインド居住者の別のパスを設計します。

ジャーニーがライブになると、米国居住者が特定のパスに入れるように、フランス居住者が別のパスに入るように、セグメントごとに指定されたパスが処理されます。

### ターゲティングのユースケース {#uc-targeting}

次の例は、**[!UICONTROL 最適化]** アクティビティを **[!UICONTROL ターゲティング]** メソッドと共に使用して、様々なサブオーディエンスのパスをパーソナライズする方法を示しています。

**セグメント固有のチャネル**

ゴールドステータスロイヤルティメンバーは、パーソナライズされたオファーをメールで受け取ることができますが、他のすべてのメンバーは SMS リマインダーにリダイレクトされます。

* プロファイルあたりの売上高またはコンバージョン率を最適化指標として使用します。

![](assets/journey-optimize-targeting-uc.png)

**行動ベースのターゲティング**

メールを開いたがクリックしなかった顧客にはプッシュ通知を送信し、まったく開かなかった顧客には SMS を受信します。

* クリックスルー率またはダウンストリームコンバージョンを最適化指標として使用します。

**購入履歴のターゲット設定**

最近購入したお客様は、「ありがとうございました+ クロスセル」という短いパスを選択でき、購入履歴のないお客様は育成ジャーニーを終了できます。

* 最適化指標として、リピート購入率またはエンゲージメント率を使用します。

## 条件の追加 {#conditions}

条件を追加して、特定の条件に基づいて複数のパスを作成し、個人がジャーニーをどのように進めるかを定義できます。 また、タイムアウトやエラーを処理するための代替パスを設定して、シームレスなエクスペリエンスを確保することもできます。

![](assets/journey-condition.png)

条件を定義する方法については、[ この節 ](conditions.md) を参照してください。

使用可能な条件のタイプは次のとおりです。

* [データソースの条件](condition-activity.md#data_source_condition)
* [時間条件](condition-activity.md#time_condition)
* [パーセンテージ分割](condition-activity.md#percentage_split)
* [日付条件](condition-activity.md#date_condition)
* [プロファイルキャップ](condition-activity.md#profile_cap)
