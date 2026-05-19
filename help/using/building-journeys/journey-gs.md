---
solution: Journey Optimizer
product: journey optimizer
title: 最初のジャーニーを作成
description: ' [!DNL Adobe Journey Optimizer]で最初のジャーニーを構築するための主な手順'
feature: Journeys, Get Started
topic: Content Management
role: User
level: Intermediate
keywords: ジャーニー, 最初, 開始, クイックスタート, オーディエンス, イベント, アクション
exl-id: d940191e-8f37-4956-8482-d2df0c4274aa
version: Journey Orchestration
TQID: https://experienceleague.adobe.com/7zNDOi2SUTyttgR6I1iOYQb61ejxpqLYznweU8alnPw
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2:
  - id: ad78185d-8f79-40ad-9bad-cbde74af74ee
  - id: b3538224-471e-4c63-a444-9b19d89ae29c
  - id: baecb07f-ce89-4ebb-9cd9-0f7c053f944f
  - id: d556b755-390a-43f0-be32-a08cf6236126
  - id: d998adac-2f81-400b-a669-d07bb196e4eb
  - id: dc22c819-3f29-4e91-8b7d-5c6719831141
subfeature_v2:
  - id: a6c67b0d-bd3e-4d5d-95a8-882e3709d632
  - id: b15c7c2e-788c-4eb7-86a8-390565b0d2c9
  - id: b32bb433-f8c6-4931-8e52-e657230a3bf2
  - id: b3a93754-a8b8-46eb-9421-7eccaeeb3dff
  - id: b9d00d1b-a371-4a75-a52a-3f8ea2029020
  - id: ba62ad25-65cb-4ea9-b7aa-0fa87c4a9fa0
  - id: da923278-9c80-47b0-bebd-b68c341e76fb
  - id: da93876b-ee00-430d-8321-f7d7f692b547
  - id: fa683eda-48de-4558-af32-2673edcd44fe
  - id: fb9a80eb-bebc-492f-a0e9-584595621ebb
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5520579-b31f-4df7-9281-f0d9f91e2edc
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: f9b8e1590f14cdcd00432295c653769f753b9b40
workflow-type: tm+mt
source-wordcount: 1455
ht-degree: 45%

---

# 最初のジャーニーを作成 {#jo-quick-start}

>[!CONTEXTUALHELP]
>id="ajo_homepage_card2"
>title="ジャーニーを作成"
>abstract="**[!DNL Adobe Journey Optimizer]** を使用すると、イベントやデータソースに保存されたコンテキストデータを活用して、リアルタイムオーケストレーションのユースケースを作成できます。"

>[!CONTEXTUALHELP]
>id="ajo_journey_create"
>title="ジャーニー"
>abstract="カスタマージャーニーを設計して、状況に即したパーソナライズされたエクスペリエンスを提供します。 Journey Optimizer を利用すると、イベントやデータソースに格納されているコンテキストデータを使用して、リアルタイムオーケストレーションのユースケースを構築できます。 「**概要**」タブには、ジャーニーに関連する主要指標を含むダッシュボードが表示されます。 「**参照**」タブには、既存のジャーニーのリストが表示されます。"

[!DNL Adobe Journey Optimizer]には、マーケターが一対一の顧客エンゲージメントとマーケティング アウトリーチを連携できるようにする、オムニチャネルオーケストレーションキャンバスが含まれています。 ユーザーインターフェイスを使用すると、パレットからキャンバスにアクティビティを簡単にドラッグ＆ドロップして、ジャーニーを作成できます。 ジャーニーのユーザーインターフェイスについて詳しくは、[このページ](journey-ui.md)を参照してください。

![ジャーニーキャンバスのサンプル](assets/journey38.png)

ジャーニーを作成する主な手順について詳しくは、このページを参照してください。 次のように効率化されています。

![ジャーニーの作成手順：作成、デザイン、テスト、公開](assets/journey-creation-process.png)

この記事では、デジタル CXの概要、重要性、ベストプラクティスを解説します。

* ジャーニーのエントリポイント（オーディエンスセグメントまたはリアルタイムイベント）を定義
* 電子メール、プッシュ通知、SMS、アプリ内メッセージ、web、コードベースのエクスペリエンス、コンテンツカードなど、チャネル全体でメッセージアクションを追加できます。 [&#x200B; サポートされているチャネルを見る](journey-action.md)
* アクティベーション前にプロファイルをテストして、ジャーニーをテスト
* ジャーニーを公開し、そのパフォーマンスを監視する

複数の手順から成るカスタマージャーニーを作成し、チャネルをまたいでインタラクション、オファーおよびメッセージのシーケンスをリアルタイムで開始します。 このアプローチにより、お客様の行動と関連するビジネスシグナルに基づいて、最適なタイミングで顧客と関与できるようになります。

<!--
>[!TIP]
>
>Not sure whether to use a journey or a campaign? [Learn how to choose the right approach](../start/journeys-vs-campaigns.md).
-->

## 事前準備 {#prerequisites}

構築する前に設定すべきことは、ジャーニーがどのようにトリガーされるかによって異なります。 多くのジャーニーは、次のふたつのエントリーポイントのどちらかから始まります。

* **オーディエンスベースのエントリ** — ジャーニーは、スケジュールされた時間に定義されたプロファイルのセットに対して実行されます。 ジャーニーを構築する前に、Adobe Experience Platformで[&#x200B; オーディエンス &#x200B;](../audience/about-audiences.md)を作成します。 Journey Optimizerを初めて使用する場合は、これを出発点として使用することをお勧めします。

* **イベントベースのエントリ** – 個人が購入やサインアップなどのアクションを実行すると、ジャーニーがリアルタイムでトリガーされます。 [トリガーとそのデータを定義するようにイベント &#x200B;](../event/about-events.md)を設定します。

**使用するエントリポイントが不明ですか？** 次の表は、最も一般的なユースケースを適切な開始アクティビティにマッピングしています。

| エントリポイント | 次の場合に使用… | プロファイル入力 |
|---|---|---|
| **[オーディエンスを読み取り](read-audience.md)** | スケジュールされたメッセージまたは定期的なメッセージを、定義されたプロファイルのセット（ニュースレター、プロモーション、オンボーディングシリーズ）に送信する場合。 | バッチオーディエンスからのすべてのプロファイルを一度またはスケジュールで取得できます。 |
| **[オーディエンスの選定](audience-qualification-events.md)** | プロファイルがオーディエンスに出入りしたときに、リアルタイムで対応する必要があります（ロイヤルティ層のアップグレード、解約リスクフラグ）。 | ストリーミングオーディエンスの適格性を判断した時点で、プロファイルを1つずつ作成します。 |
| **単一イベント** | プロファイルアクションを実行すると、即座に回答がトリガーされます（購入確認、フォーム送信、アプリログイン）。 | リアルタイムで単一のプロファイルを構築。 |
| **[ビジネスイベント](../event/about-creating-business.md)** | プロファイル以外のイベントは、一度に複数のユーザーに影響を与えます（フライトキャンセル、株式補充、速報アラート）。 | イベントに関連付けられたすべてのプロファイルは、自動オーディエンス読み取りステップを介して表示されます。 |

次の要素はオプションですが、ユースケースに応じて必要になる場合があります。

* **データソース** – 外部システムからのデータでジャーニーの条件やパーソナライゼーションを強化するには、[&#x200B; データソース &#x200B;](../datasource/about-data-sources.md)を設定します。

* **カスタムアクション** – 組み込みチャネルではなくサードパーティシステムを介してメッセージを配信する場合は、[&#x200B; カスタムアクション &#x200B;](../action/action.md)を設定します。

>[!NOTE]
>
>* 技術的な設定（イベント、データソース、アクション）を担当するデータエンジニアの場合は、[この節](../configuration/about-data-sources-events-actions.md)を参照してください。
>
>* ジャーニーのガードレールと制限について詳しくは、[このページ &#x200B;](../start/guardrails.md)を参照してください。

## ジャーニーの作成 {#jo-build}

複数の手順から成るジャーニーを作成するには、次の手順に従います。

1. 「ジャーニー管理」メニューセクションで、「**[!UICONTROL ジャーニー]**」をクリックします。

1. 「**[!UICONTROL ジャーニーを作成]**」ボタンをクリックして、新しいジャーニーを作成します。

1. ジャーニーの設定パネルを編集して、ジャーニーの名前を定義し、そのプロパティを設定します。 ジャーニーのプロパティを設定する方法について詳しくは、[このページ](journey-properties.md)を参照してください。

   >[!TIP]
   >
   >**どのジャーニータイプを選択すればよいですか？** Journey Optimizerを初めて使用する場合は、**[!UICONTROL オーディエンスを読み取り]** アクティビティを使用してオーディエンスベースのジャーニーを開始します。事前のイベント設定は必要なく、カンバスに慣れるには最も簡単な方法です。 リアルタイムのイベントトリガー型エクスペリエンス（購入やフォーム送信への反応など）の場合は、まずイベントを設定し、イベントベースのエントリを使用します。 さらなる詳細は、 [すべてのジャーニータイプとそのエントリルールを確認](entry-management.md#types-of-journeys)。

   ![設定オプションを含むジャーニーのプロパティパネル](assets/jo-properties.png)

その後、ジャーニーのデザインを開始できます。

## ジャーニーのデザイン {#jo-design}

ジャーニーデザイナーでは、直感的なドラッグ&amp;ドロップ操作のインターフェイスを使用して、マルチステップのジャーニーを構築できます。 左側のパレットのアクティビティは、**イベント**、**オーケストレーション**、**アクション**&#x200B;の3つのカテゴリに分類されます。 キャンバスとその制御の概要については、[このページ &#x200B;](using-the-journey-designer.md)を参照してください。

![アクティビティパレットとキャンバスを含むジャーニーデザイナーインターフェイス](assets/journey38.png)

ジャーニーをデザインするには、次の手順に従います。

1. **エントリポイントを追加** — イベントまたは&#x200B;**[!UICONTROL オーディエンスの読み取り]** アクティビティをパレットからキャンバスにドラッグします。 これにより、プロファイルがジャーニーに入る方法を定義します。個々にリアルタイム（イベントベース）で、または定義されたオーディエンスから一度にすべて（オーディエンスベース）で指定します。

   ![ターゲットオーディエンスを選択するオーディエンスを読み取りアクティビティ設定](assets/read-segment.png)

1. **メッセージアクションを追加** — パレットの&#x200B;**[!UICONTROL アクション]** セクションから、チャネルアクションをキャンバスにドラッグして、ジャーニーを流れるプロファイルにメッセージを送信します。 アクションは、電子メール、プッシュ通知、SMSなどで利用できます。

1. **オーケストレーションアクティビティを追加** — **[!UICONTROL 条件]** アクティビティを使用して、プロファイル属性または行動に基づいてジャーニーを複数のパスに分岐します。 **[!UICONTROL 待機]** アクティビティを使用して、ステップ間に時間の遅延を導入します。

>[!TIP]
>
>複数のフェーズまたは多数のタッチポイントを含むジャーニーの場合は、**[!UICONTROL ジャンプ]** アクティビティに接続された小さなサブジャーニーにエンドツーエンドのフローを分割することを検討してください。 これにより、複雑さが軽減され、各サブジャーニーの独自のテストが容易になります。 詳しくは、[&#x200B; デザイン戦略：一口サイズのサブジャーニー](jump.md#jump-strategy)を参照してください。

## ジャーニーのテスト {#jo-test}

ジャーニーを作成したら、公開する前にテストします。 Journey Optimizer では、ジャーニーに沿って進む際にテストプロファイルを表示し、アクティブ化の前に潜在的なエラーを検出する方法として、**テストモード**&#x200B;を提供しています。 クイックテストを実行すると、ジャーニーが正しく動作することを確認できるので、自信を持って公開できます。 ジャーニーをテストする方法について詳しくは、[この節](testing-the-journey.md)を参照してください。

また、**ドライラン**&#x200B;でジャーニーを実行することもできます。 ジャーニーのドライランは、Adobe Journey Optimizer の特別なジャーニー公開モードで、ジャーニー実務担当者は実際の顧客に連絡したり、プロファイル情報を更新したりすることなく、実際の実稼動データを使用してジャーニーをテストできます。 この機能により、ジャーニー実務担当者は、ジャーニーをライブで公開する前に、ジャーニーのデザインとオーディエンスのターゲティングに自信を持つことができます。 ドライランモードでのジャーニーの公開方法について詳しくは、[この節](journey-dry-run.md)を参照してください。

## ジャーニーの公開 {#jo-pub}

ジャーニーをアクティブ化し、新しいプロファイルが入力できるようにするには、ジャーニーを公開する必要があります。 ジャーニーを公開する前に、そのジャーニーが有効で、エラーがないことを確認します。 エラーのあるジャーニーは公開できません。 ジャーニーの公開について詳しくは、この[&#x200B; セクション &#x200B;](publish-journey.md)を参照してください。

![オーディエンス、条件、アクションを含む完全なジャーニーフロー](assets/jo-journeyuc2_32bis.png)

公開したら、専用のレポートツールを使用してジャーニーを監視し、ジャーニーの有効性を測定できます。

![パフォーマンス指標および統計を示すジャーニー分析レポート](assets/jo-dynamic_report_journey_12.png)

ジャーニーレポートについて詳しくは、[この節](../reports/live-report.md)を参照してください。

## よくあるユースケース {#use-cases}

どこから始めてよいかわからないものは、 ここでは、ジャーニーが最も価値を提供する3つの典型的なシナリオを紹介します。

<table style="table-layout:fixed">
  <tr style="border: 0;">
    <td>
      <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/use-cases/customer-onboarding" target="_blank">
        <img src="../assets/do-not-localize/icon-quick-start.svg" width="35px">
      </a>
      <div><strong> ウェルカムシリーズ </strong><br/> サインアップ後、一連のメッセージを新規ユーザーに自動的にオンボーディングし、製品またはサービスを通じてユーザーを導きます。</div>
    </td>
    <td>
      <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/use-cases/abandoned-cart" target="_blank">
        <img src="../assets/do-not-localize/icon-campaign.svg" width="35px">
      </a>
      <div><strong> カートの放棄</strong><br/> パーソナライズされたコンテンツを含むタイムリーなリマインダーを送信して、購入を完了せずに離脱した顧客をリエンゲージします。</div>
    </td>
    <td>
      <a href="jo-use-cases.md">
        <img src="../assets/do-not-localize/icon-content.svg" width="35px">
      </a>
      <div><strong> リエンゲージメント </strong><br/>最後に確認した行動に基づいて、ターゲットを絞ったオファーまたはアップデートを使用して、非アクティブなユーザーを取り戻します。</div>
    </td>
  </tr>
  <tr style="border: 0;">
    <td align="center"><a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/use-cases/customer-onboarding" target="_blank"><img src="../assets/do-not-localize/learn-more-button.svg"></a></td>
    <td align="center"><a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/use-cases/abandoned-cart" target="_blank"><img src="../assets/do-not-localize/learn-more-button.svg"></a></td>
    <td align="center"><a href="jo-use-cases.md"><img src="../assets/do-not-localize/learn-more-button.svg"></a></td>
  </tr>
</table>

## その他のリソース

* **[ジャーニーの種類とプロファイルのエントリ](entry-management.md)** – すべてのジャーニーの種類（単一イベント、ビジネスイベント、読み取りオーディエンス、オーディエンスの選定）と、プロファイルがジャーニーを入力、再入力、フローする方法を理解します。
* **[ジャーニーデザイナーの概要](using-the-journey-designer.md)** - ジャーニーキャンバスインターフェイスを習得して、カスタマージャーニーをデザインおよび調整します。
* **[ジャーニーアクティビティ](about-journey-activities.md)** - イベント、アクション、オーケストレーションコンポーネントを含む、使用可能なすべてのアクティビティを検出します。
* **[ジャーニーのテスト](testing-the-journey.md)** - 実稼動環境に公開する前に、テストモードを使用してジャーニーをテストする方法について説明します。
* **[ジャーニーの公開](publish-journey.md)** - ジャーニーの公開プロセスとライブジャーニーの管理方法について説明します。
* **[ジャーニーレポート](report-journey.md)** - 詳細な指標とインサイトを使用して、ジャーニーのパフォーマンスを追跡および分析します。
* **[ジャーニーのトラブルシューティング](troubleshooting.md)** - 一般的なジャーニーの問題に対する解決策とデバッグのベストプラクティスについて説明します。
* **[ジャーニーのチュートリアル](https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/journeys/introduction-to-building-a-journey){target="_blank"}** - ジャーニーの作成とベストプラクティスに関するステップバイステップのビデオチュートリアルを参照してください。

