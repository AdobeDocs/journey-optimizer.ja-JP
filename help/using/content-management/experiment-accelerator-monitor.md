---
solution: Journey Optimizer
product: journey optimizer
title: Journey Optimizer Experimentation Accelerator モニター
description: 効果的に実験を行い、インサイトを生み出す能力の向上
feature: Experimentation
topic: Content Management
role: User
level: Beginner
keywords: コンテンツ, 実験, 複数, オーディエンス, 処理
exl-id: 40a57083-d7b1-416b-af87-4b603b83052d
source-git-commit: 61ae9196f699c3b6aa1d9a5bb2259d36aaebc0e3
workflow-type: tm+mt
source-wordcount: '1095'
ht-degree: 5%

---

# 実験の追跡 {#monitor}

**[!UICONTROL 実験]** タブは、Adobe Journey OptimizerとAdobe Targetからのテストのトラッキングと分析を一元化します。 すべての実験を表示し、KPI を確認し、フィルターまたは検索して特定のテストを見つけることができます。

## ダッシュボード {#dashboard}

「実験」タブにアクセスすると、Journey OptimizerおよびAdobe Targetで使用可能なすべての実験が統合ビューに一覧表示されます。 これにより、両方のプラットフォームにわたる実験を 1 か所ですばやく確認および比較できます。
実験リストには、次のものが含まれます。

* キャンペーンまたはジャーニーのいずれかで作成されたJourney Optimizer実験。

* 同じ IMS 組織にリンクされたJourney Optimizer実稼動のデフォルトサンドボックスで使用できるAdobe Target実験。

「KPI」セクションには、作成された実験の合計数や現在進行中の数などの主要指標が表示され、実験アクティビティ全体のスナップショットが示されます

![](assets/do-not-localize/Smock_Filter_18_N.svg) をクリックしてフィルターにアクセスします。ここには、**[!UICONTROL タイプ]**、**[!UICONTROL Starred]**、**[!UICONTROL ステータス]**、**[!UICONTROL Source]** によるフィルタリングなど、コンテキスト固有のオプションが用意されています。 例えば、Journey Optimizer内のアクティブな実験のみを表示するようにフィルタリングできます。

または、検索バーに名前を入力して、実験をすばやく見つけます。

![](assets/experiment-monitor-dashboard.png)

## 実験の監視 {#monitor-page}

実験にアクセスして監視するには、「実験 ****」タブから実験のリストから以前に設定した実験を選択するか、詳細メニューを使用して **[!UICONTROL 詳細を表示]** または **[!UICONTROL ソースで開く]** します。

![](assets/experiment-accelerator-1.png)

実験の詳細ページは、次のセクションに分かれています。

* [実験結果](#experiment-outcome)
* [仮説](#hypothesis)
* [詳細](#details)
* [商談](#opportunities)
* [結果](#results)
* [実験インサイト](#insights)

### 実験結果 {#experiment-outcome}

![](assets/experiment-monitor-outcome.png)

**[!UICONTROL 実験結果]** では、実験における勝者のバリエーションをすばやく確認できます。

### 設定 {#set-up}

**[!UICONTROL 仮説]** では、テストする予定の変更を取り込み、プライマリ指標に対して予想される影響を文書化します。 明確な **[!UICONTROL 仮説]** を定義すると、各実験の目的が測定可能になり、結果の評価と、変更が有意義な改善につながるかどうかの判断が容易になります。

[ 実験インサイト ](#insights) を生成するには、仮説と処理の詳細および到達する統計的有意性を確認する必要があります。

1. 「**[!UICONTROL 追加]**」をクリックして、実験の **[!UICONTROL 仮説]** を作成します。

   ![](assets/experiment-monitor-setup-1.png)

1. 加えられた変更の詳細と、その変更がプライマリ指標に与える影響を説明して、**[!UICONTROL 仮説]** を入力します。

   「**[!UICONTROL 保存]**」をクリックします。

1. **[!UICONTROL レビュー]** をクリックして、各処理の画像を追加または置換します。

   ![](assets/experiment-monitor-setup-2.png)

1. 処理画像は自動的に生成されますが、必要に応じて、**[!UICONTROL 画像を追加]** または **[!UICONTROL 画像を置換]** を選択して、**[!UICONTROL 処理]** 用にローカルファイルから優先スクリーンショットをアップロードできます。

   スクリーンショットはページ全体を取り込む必要があります。

1. 必要 ![](assets/do-not-localize/Smock_Edit_18_N.svg) 応じて、アイコンをクリックして **[!UICONTROL 仮説]** を更新します。

**[!UICONTROL 仮説]** の設定が完了すると、価値のある [ インサイト ](#insights) と [ 商談 ](#opportunities) を得ることができます。

### 詳細 {#details}

![](assets/experiment-monitor-details.png)

**[!UICONTROL 実験エフェクト]** ウィジェットには、実験がターゲットオーディエンスセグメントに与えた影響の詳細が表示されます。 エンゲージメントと行動を評価するのに役立つ、次のような主要業績評価指標を示します。

* 実験の作成時に設定された内容に応じて、Journey Optimizerの **[!UICONTROL 成功指標]** またはAdobe Targetの **[!UICONTROL プライマリ指標]**。

* **[!UICONTROL 訪問者]**：実験に公開されたユニーク訪問者の合計数。

また、次の指標を使用して、主要な処理のパフォーマンスに関するリアルタイムスナップショットを表示することもできます。

* **[!UICONTROL 現在のリーダー]**：現在、最高のパフォーマンスを発揮している処理を特定します。

* **[!UICONTROL ベースライン上の上昇率]**：コントロールまたはベースラインと比較した先行処理の改善率を測定します。

* 実験の作成時に設定された内容に応じて、Journey Optimizerの **[!UICONTROL 成功指標]** またはAdobe Targetの **[!UICONTROL プライマリ指標]**。

ウィジェットの下部には、次のような実験設定の簡潔な概要が表示されます。

* 実験の作成時に設定された内容に応じて、Journey Optimizerの **[!UICONTROL 成功指標]** またはAdobe Targetの **[!UICONTROL プライマリ指標]**。

* **[!UICONTROL 処理数]**：テストしたバリエーションの合計数。

* **[!UICONTROL オーディエンス]**：実験のターゲットとなる定義済みのユーザーセグメント。

### 商談 {#opportunities}

>[!AVAILABILITY]
>
>商談機能は、テキストベースの変更を含む実験に制限されています。

**[!UICONTROL 機会]** パネルには、テストのパフォーマンスを向上させ、より広範なビジネス目標や KPI と連携するように設計された、AI によって生成されたレコメンデーションが表示されます。

実験の機会を生成するには、まず [ 仮説と処理の詳細を確認 ](#set-up) する必要があります。

1. 提案された商談を参照し、「**[!UICONTROL 商談を表示]**」をクリックします。

   ![](assets/experiment-monitor-opportunities.png)

1. 商談を選択すると、**商談の詳細** ウィンドウが開きます。このウィンドウには、Journey Optimizer Experimentation Acceleratorによって提案された具体的な処理やバリエーションの概要が表示されます。 このビューには次が含まれます。

   * **[!UICONTROL 仮説]**：提案された処理の期待される結果を説明する、AI によって生成された仮説。

   * **[!UICONTROL 根拠]**:Journey Optimizer Experimentation Acceleratorがこの機会を提案した理由の説明。

   * **[!UICONTROL オポチュニティ評価]**：以下に基づく推奨事項の二重評価。

      * **[!UICONTROL ラーニングの可能性]**：過去にテストされたものとの違いに基づき、オポチュニティが提供できる新しいinsightの推定量です。

      * **[!UICONTROL コンバージョンの可能性]**：過去にうまく機能した戦略との類似性に基づいて、現在の処理を上回る可能性の推定値。
   <!--
   * **[!UICONTROL New text treatment example]**: Words or phrases that demonstrate the style the AI recommends using.
   -->

   ![](assets/experiment-monitor-opportunities-2.png)

1. その後、「実験を開く **[!UICONTROL を選択して、実験に直接追加でき]** す。

1. 元の実験がAdobe Journey Optimizerで作成および管理された場合、このアクションにより、そのキャンペーン内に **[!UICONTROL コンテンツ実験パネル]** が開きます。

   **[!DNL Adobe Target]** から実行される実験の場合、提案された変更は、代わりに **[!DNL Adobe Target]** の実験ワークフローに読み込まれます。

   ➡️ [ 詳しくは、Adobe Target ドキュメントを参照してください ](https://experienceleague.adobe.com/en/docs/target/using/activities/abtest/test-ab)

1. 実験ビューでは、Journey Optimizer Experimentation Acceleratorで表示されるのと同じ AI **[!UICONTROL 実験の機会]** にアクセスできます。

   **[!UICONTROL 表示]** を選択して、オポチュニティの詳細を開きます。

1. 提案された変更を適用するために、「実験を変更 **[!UICONTROL を選択すると]** 既存の実験を直接編集できます。

### 結果 {#results}

![](assets/experiment-monitor-results.png)

**[!UICONTROL 結果]** テーブルには、実験内の各処理の詳細なパフォーマンス分類が表示されます。 これらの指標は、有効性、ユーザーエンゲージメントおよび主要ビジネス成果に対する全体的な影響を評価するのに役立ちます。

* **[!UICONTROL 場所]**：パフォーマンスに基づく処理のランキング位置で、他の処理との比較を示します。

* 実験の作成時に設定された内容に応じて、Journey Optimizerの **[!UICONTROL 成功指標]** またはAdobe Targetの **[!UICONTROL プライマリ指標]**。

* **[!UICONTROL ユーザー]**：メッセージのターゲットプロファイルに適格な、ユーザープロファイルの数。

* **[!UICONTROL 上昇率]**：ベースラインに対する特定の処理のコンバージョン率の向上率を測定します。

* **[!UICONTROL 信頼性]**：ある処理がベースライン処理と同じであることを示す証拠。[詳細情報](../content-management/experiment-calculations.md#understand-confidence)

* **[!UICONTROL コンバージョン率]**：処理を確認した後に目的のアクション（購入、サインアップなど）を完了したプロファイルの割合。

### 実験のインサイト {#insights}

>[!AVAILABILITY]
>
>実験インサイトの機能は、テキストベースの変更を含んだ実験に限定されます。

**[!UICONTROL 実験インサイト]** は、この実験から AI によって生成された学習事項です。 これらのインサイトは、実験が統計的有意性に達すると利用可能になり、成功に貢献した内容のコンテキスト理解を提供します。 勝者の処理に存在する主要な属性を強調しており、コントロールとは異なり、結果に影響を与える可能性が高くなります。

実験インサイトを生成するには、まず、仮説と処理の詳細 [ を確認し ](#set-up) 統計的有意性に到達する必要があります。

各インサイトの詳細を確認するには、「**[!UICONTROL 詳細を表示]**」をクリックします。

</br>

![](assets/experiment-monitor-insights.png)
