---
solution: Journey Optimizer
product: journey optimizer
title: Journey Optimizer におけるデータ管理の基本を学ぶ
description: 主な概念、設定手順、ガードレールなど、Adobe Journey Optimizer へのデータの入出力のフローの仕組みについて説明します。
feature: Data Management
role: Developer, Admin, User
level: Beginner, Intermediate
exl-id: 25519acb-a017-446a-992b-653d3a8a3d96
TQID: https://experienceleague.adobe.com/Dq8mzkfuxvcoAPI1vjq9lFHjz4Z5j9s42-kfMy59PeI
product_v2: id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2: id: aeebb91a-f216-4d5f-8da1-3a7e6f696ed0
subfeature_v2: id: a1cdc218-59b7-4eef-b5cf-2a7ad74b3371id: d6e5c7fd-c1d6-4137-98cd-138ccde6752fid: cf3fbcd7-c075-4ae4-8de5-96e736ab2ea3id: e30b0a1a-b594-47b8-af94-1e3a2be6df11
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adebid: cc72dcf1-72e1-48cc-b434-e7c27d62d67cid: d095671a-1355-40aa-8b5f-06c33c68080bid: ebde5b41-29c9-4f5e-9ef6-1197e85409e3id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 4cb75d06f45f9d15cdbeda5afa06acf8e27d13de
workflow-type: tm+mt
source-wordcount: 2652
ht-degree: 98%

---

# データ管理の基本を学ぶ {#about-data}

>[!BEGINSHADEBOX]

**このページでは、** Adobe Journey Optimizerとの間でデータがどのように流れ込むのか、スキーマ、データセット、ID、プロファイル、およびデータソースについて実用的な概要を説明します。これにより、ジャーニーやキャンペーンを構築する前に、データ準備ステップを完了できます。

>[!ENDSHADEBOX]

データは、[!DNL Adobe Journey Optimizer] で配信するすべてのジャーニー、決定、メッセージの基盤です。

このページでは、次を理解するための実用的な開始点について説明します。

* Journey Optimizer で使用されるコアデータ構成要素（スキーマ、データセット、ID、プロファイル）
* Journey Optimizer での Adobe Experience Platform データの使用方法
* ジャーニーやキャンペーンを作成する前にチームが完了する必要があるデータ設定手順
* 詳細な設定とベストプラクティスの次の参照先

このガイドをデータエンジニア、管理者、マーケターと一緒に使用することで、全員が Journey Optimizer へのデータの入出力のフローに関する一般的な認識を共有できます。

>[!TIP]
>Journey Optimizer のデータ管理を初めて使用しますか？ スキーマ、データセット、データソースの実用的で初心者にもわかりやすいチュートリアルについて詳しくは、[データの設定の概要チュートリアル](https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/data-management/set-up-data-overview){target="_blank"}を参照してください。

## Journey Optimizer での Adobe Experience Platform データの使用方法 {#aep-data}

[!DNL Adobe Journey Optimizer] は [!DNL Adobe Experience Platform] に作成されます。 分離され、独立したデータストアを維持しません。 代わりに、他の Experience Cloud アプリケーションと同じデータ基盤を使用します。

スキーマとデータセットは、Adobe Experience Platform に保存されます。 ID および[リアルタイム顧客プロファイル](../audience/get-started-profiles.md)は、ID サービスとプロファイルサービスにより管理されます。 Journey Optimizer は、Adobe Experience Platform からプロファイルとイベントデータを読み取り、ジャーニーの条件を評価し、メッセージをパーソナライズして、オファーを選択します。 これにより、送信、開封、クリック、バウンスの各イベント、ジャーニーステップイベントなどのインタラクションデータが、Experience Platform データセットに書き込まれます。 また、そのデータをプロファイルにコピーすることなく、実行時に追加のデータセットを検索することもできます。

>[!TIP]
>Adobe Experience Platform を中心的なデータレイヤーとして考え、Journey Optimizer をその共有されたデータ基盤を使用してジャーニーとメッセージを調整するアプリケーションとして考えてください。

➡️ [Journey Optimizer アーキテクチャの詳細情報](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/get-started/essentials/understanding-ajo#architecture-details){target="_blank"}

## Journey Optimizer の主なデータの概念 {#key-concepts}

Journey Optimizer でデータを操作する際、いくつかの関連する概念が発生します。 次の表に、簡単な概要を示します。続く各節では、それぞれの概念についてより詳しく説明します。

| 概念 | 概要 | Journey Optimizer での主な用途 |
|---|---|---|
| XDM スキーマ | データ（クラスとフィールドグループから作成）を表現、検証、書式設定するルール | プロファイル属性と行動イベントをモデル化 |
| データセット | スキーマに準拠するデータのストレージテーブル | プロファイル、イベント、システム生成データを保持 |
| ソースコネクタ | 外部システムから AEP へデータをストリームまたはバッチ | CRM、分析、web データを取り込み |
| データソース | ジャーニー内で AEP または外部フィールドを公開 | ジャーニー条件とメッセージのパーソナライゼーションを強化 |
| ID | 個々の顧客を一意に表す識別子 | チャネルをまたいでプロファイルをステッチ |
| 参照データセット | プロファイルストレージを使用しない AEP データへのランタイム参照 | ライブ参照データでメッセージを強化 |

### スキーマ（XDM スキーマ） {#schema}

スキーマは、データを表現、検証、書式設定する一連のルールです。 これは、**クラス**（基本動作、つまりレコードまたは時系列を定義する）と、オプションの&#x200B;**フィールドグループ**（特定のフィールドを追加する）で構成されます。 スキーマは、エクスペリエンスデータモデル（XDM）標準を使用して定義され、Adobe Experience Platform で公開されます。

XDM は、同じ概念（顧客、購入、製品）がソースシステム間で名前や構造が異なるという、実際の問題を解決するために存在します。 XDM には、データの生成元に関係なく、これらの概念を単一の定義の下に統合する共通言語が用意されています。 これにより、Journey Optimizer は、CRM、web サイト、モバイルアプリ、データウェアハウスからのデータを同時に一貫して操作することが可能になります。

Journey Optimizer では通常、顧客属性（名前、好み、同意）には **XDM 個人プロファイル**&#x200B;スキーマを、行動イベント（購入、ページビュー、新規登録）には **XDM ExperienceEvent** スキーマを操作します。

➡️ [スキーマの詳細情報](get-started-schemas.md)

### データセット {#dataset}

データセットは、スキーマに準拠するデータを格納し管理するための構造です。列と行のセットが定義されたテーブルとして考えてください。 Journey Optimizer で使用されるすべてのデータは、Adobe Experience Platform データセットに保存されます。 これらは、トラッキング、フィードバック、ジャーニーステップイベント用に Journey Optimizer で自動的に作成される、プロファイルデータセット（リアルタイム顧客プロファイルに貢献）、イベントデータセット（ジャーニーと分析用の行動データを保存）、システムデータセットである場合があります。

➡️[データセットの詳細情報](get-started-datasets.md)

### ソースコネクタ {#source-connector}

ソースコネクタ（**ソース**&#x200B;とも呼ばれる）を使用すると、Adobe Analytics、Adobe Experience Platform Web SDK、クラウドストレージ（S3、Azure Blob）、CRM データベースなど、複数のシステムから Adobe Experience Platform にデータを取り込むことができます。 生の取り込み以外にも、コネクタを使用することで、Experience Platform サービスを使用してデータの構造化、ラベル付け、機能強化を行うことができます。これには、XDM スキーマへのフィールドマッピングやデータガバナンスのラベル付けなどが含まれます。

➡️ [ソースコネクタの詳細情報](../start/get-started-sources.md)

### データソース（Journey Optimizer） {#data-source}

Journey Optimizer のデータソースは、ジャーニーやメッセージ内で公開する Adobe Experience Platform（または外部 API）のフィールドを定義します。 Journey Optimizer UI で設定されるデータソースには通常、組み込みの Adobe Experience Platform データソース（リアルタイム顧客プロファイル属性を公開）と、追加のエンリッチメント用にジャーニー実行時に呼び出されるオプションの外部データソースまたはカスタムデータソースが含まれます。 これらは、ジャーニーの条件、カスタムアクション、メッセージのパーソナライゼーションに使用されます。

➡️ [データソースの詳細情報](../datasource/about-data-sources.md)

>[!NOTE]
>[Adobe Experience Platform 用語集](https://experienceleague.adobe.com/ja/docs/experience-platform/landing/glossary){target="_blank"}では、「データソース」を一般的にデータ（CRM、モバイルアプリなど）のオリジンとして定義しています。 Journey Optimizer では、**データソース**&#x200B;には特定の意味があります。ジャーニーやメッセージ内で公開されるフィールドを制御する UI 設定です。

### ID とリアルタイム顧客プロファイル {#identity}

ID は、cookie ID、デバイス ID、メールアドレス、CRM ID など、個々の顧客を一意に表す識別子です。 ID は、名前空間（メール、ECID、CRMID）に整理され、同じユーザーの複数の ID は統合された ID グラフにステッチされます。 リアルタイム顧客プロファイルは、このグラフを使用して、オンライン、オフライン、CRM、サードパーティソースなど、複数のチャネルのデータを組み合わせて、個々の顧客の総合的なビューを維持します。

初心者向けの主な概念は、**プロファイルフラグメント**&#x200B;モデルです。 顧客が特定のデバイスやチャネル（web サイト、モバイルアプリ、ストア）でブランドとやり取りするたびに、このインタラクションはプロファイルフラグメントとして記録されます。これは、この特定のタッチポイントに基づいた顧客の一部のビューです。 リアルタイム顧客プロファイルは、共有された ID 値に基づいてこれらのフラグメントを継続的に一緒にステッチし、完全で最新のプロファイルを作成します。 Journey Optimizer は、この組み立てられたプロファイルから読み取り、状況を評価し、オファーを選択し、メッセージをリアルタイムでパーソナライズします。

➡️ [Journey Optimizer の ID の詳細情報](../audience/get-started-identity.md)

### 参照データセット {#lookup-dataset}

参照データセットを使用すると、Journey Optimizer は、リアルタイム顧客プロファイルにデータを保存することなく、実行時に Adobe Experience Platform データセットから参照データまたはトランザクションデータを取得できます。 これは、頻繁に変更される参照データ（価格、在庫、ストアの時間）や、メッセージ時に必要ですがプロファイルには属さないトランザクションデータに役立ちます。 Journey Optimizer は、製品 ID などのキーに基づいて、ジャーニーまたはメッセージの実行中に参照を実行します。

➡️ [参照データセットの詳細情報](lookup-aep-data.md)

## データ準備チェックリスト {#checklist}

マーケターがジャーニーやキャンペーンの作成を開始する前に、組織は一連のデータ準備手順を完了する必要があります。 これにより、Journey Optimizer は適切なデータを、適切なタイミングで、コンプライアンスに準拠した方法で使用できるようになります。

>[!NOTE]
>以下の手順には、データエンジニア、管理者、マーケターなど、複数の役割が関与します。 このチェックリストを、環境を準備するための共有プランとして使用します。 手順 1～4 は Adobe Experience Platform で完了し、手順 5～6 は Journey Optimizer で設定します。

以下の 6 つの手順では、ID 設定からデータが Journey Optimizer に正しくフローされることの確認まで、完全なデータ設定プロセスを順を追って説明します。

1. ID 戦略を定義
1. プロファイルとイベントデータのスキーマをデザイン
1. プロファイル対応データセットを作成
1. ソースからデータを取り込む
1. Journey Optimizer でデータソースを設定
1. トラッキング、フィードバック、ジャーニーのデータセットを確認

+++ ID 戦略を定義

顧客のプライマリ ID（ECID、メール、CRMIDなど）を選択し、Adobe Experience Platform ID サービスで対応する名前空間を設定します。 プロファイル対応スキーマに ID フィールドが存在することを確認し、プロファイルが ID グラフに正しくステッチされていることを検証します。

➡️ [Journey Optimizer の ID の詳細情報](../audience/get-started-identity.md)

+++

+++ プロファイルとイベントデータのスキーマをデザイン

名前や連絡先情報、好みや関心、ライフサイクルステージや同意状態などの顧客属性をキャプチャするには、**XDM 個人プロファイルスキーマ**&#x200B;を作成します。 Web やアプリのイベント、購入、オフラインでのインタラクションなどの行動データとトランザクションデータをキャプチャするには、**XDM ExperienceEvent** スキーマを作成します。 該当する場合は、正しいフィールドを ID およびプロファイル属性としてマークします。

➡️ [スキーマの詳細情報](get-started-schemas.md)

+++

+++ プロファイル対応データセットを作成

Adobe Experience Platform で、XDM スキーマに基づいてデータセットを作成し、リアルタイム顧客プロファイルに貢献する必要があるデータセットでプロファイルを有効にします。 Journey Optimizer で作成したシステム生成データセットがデータセットワークスペースに表示されていることを確認します。

➡️[データセットの詳細情報](get-started-datasets.md)

+++

+++ ソースからデータを取り込む

Adobe Analytics、Adobe Experience Platform Web SDK、CRM および POSプラットフォームなどのエンタープライズシステム用のソースコネクタを設定し、受信フィールドを XDM スキーマにマッピングします。 データが正しいデータセットに保存され、リアルタイム顧客プロファイルに期待どおりに表示されることを検証します。

➡️ [ソースコネクタの詳細情報](../start/get-started-sources.md)

➡️ [チュートリアル：データセットの作成とデータの取り込み](https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/data-management/create-datasets-and-ingest-data){target="_blank"}

+++

+++ Journey Optimizer でデータソースを設定

データソースは Journey Optimizer 固有の概念です。データソースはデータが存在する場所ではなく、Journey Optimizer がジャーニーやメッセージの実行中に読み取ることを許可するフィールドを宣言する場所です。 ジャーニーで 「顧客はロイヤルティメンバーですか？」などの条件を評価したり、 名を付けてメッセージをパーソナライズしたりするには、データソース設定を通じて関連するプロファイルフィールドを公開する必要があります。

Journey Optimizer には、リアルタイム顧客プロファイル属性に直接アクセス権を付与する組み込みの [Adobe Experience Platform データソース](../datasource/adobe-experience-platform-data-source.md)が含まれています。 これは、パーソナライゼーションのためにプロファイル属性を読み取ったり、同意や環境設定フィールドを確認したりするなど、ほとんどのユースケースを対象としています。 また、ジャーニー実行時にサードパーティ API を呼び出すように[外部データソース](../datasource/external-data-sources.md)を設定することもできます。例えば、Adobe Experience Platform に保存されていないリアルタイムのロイヤルティスコア、製品のレコメンデーション、ストアの在庫レベルを取得する場合です。

>[!NOTE]
>組み込みの Adobe Experience Platform データソース経由のエクスペリエンスイベントデータへの直接アクセスは非推奨（廃止予定）となり、段階的に無効になります。 [学習を増やす](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/orchestrate-journeys/journey-use-cases/exp-event-lookup){target="_blank"}。

データソースの設定は、ジャーニー作成者やマーケターが完全なデータレイヤーを使用できるようにする管理タスクです。 データソースを通じてフィールドが公開されると、ジャーニー条件ビルダー、メッセージパーソナライゼーションエディター、オファー決定支援ルールで使用できるようになります。ジャーニー作成時に追加のエンジニアリング作業は必要ありません。

➡️ [データソース設定の詳細情報](../datasource/about-data-sources.md)

+++

+++ トラッキング、フィードバック、ジャーニーのデータセットを確認

Journey Optimizer システム生成データセットがデータセットワークスペースで使用できることを確認します。 テスト用のジャーニーとキャンペーンを実行し、クエリエディターを使用して、送信、開封、クリック、バウンスの各イベントが記録されていることと、ジャーニーステップイベントと状態が正しくキャプチャされていることを確認します。 これらのデータセットは、継続的な監視、トラブルシューティング、ジャーニーの最適化に使用します。

➡️ [Journey Optimizer のクエリの詳細情報](get-started-queries.md)

+++

## ガードレールとデータデザインの考慮事項 {#guardrails}

製品のガードレールや制限事項により、データモデルやジャーニーのデザイン方法に影響を与える場合があります。 後のリワークを回避するために、早めにこれらを確認してください。

>[!IMPORTANT]
>最新の情報について詳しくは、常に [Journey Optimizer のガードレールと制限](../start/guardrails.md)ページを参照してください。 以下の概要では、主な項目を取り上げますが、時間の経過と共に変更する場合があります。

### Journey Optimizer システムデータセットと TTL {#datasets-ttl}

Journey Optimizer は、トラッキング、フィードバック、ジャーニーステップイベント用に、システム生成データセットをいくつか作成します。 2025年2月以降、これらのデータセットの一部に有効期間（TTL）ガードレールがロールアウトされ、分析やトラブルシューティングのためにデータが保持される期間に影響を与える場合があります。

➡️ [データセット TTL ガードレールの詳細情報](datasets-ttl.md)

### ストリーミングセグメント化とJourney Optimizer イベント {#streaming-segmentation}

2024年11月1日（PT）以降、ストリーミングセグメント化では、Journey Optimizer のトラッキングデータセットとフィードバックデータセットからの送信イベントと開封イベントがサポートされなくなります。 フリークエンシーキャップや疲労管理などのユースケースでは、送信／開封イベントに基づくストリーミングセグメントの代わりに、[ビジネスルール](../conflict-prioritization/rule-sets.md)を使用します。

➡️[データセットの詳細情報](get-started-datasets.md)

### データセット参照と決定 {#lookup-guardrails}

データセット参照は、頻繁に変更される属性（在庫、価格、天候）や、リアルタイム顧客プロファイルに保存する必要のないデータに最適です。 参照戦略をデザインする前に、関連ドキュメントでデータセットのサイズ制限やクエリキャップなど、製品固有のガードレールを確認してください。

➡️ [参照データセットの詳細情報](lookup-aep-data.md)

## 例：ウェルカムジャーニーのデータの準備 {#example}

次の例では、このページで説明されている概念が、簡単なシナリオで連携する仕組みを示しています。

1. データエンジニアは、顧客属性（名前、メール、ロイヤルティ層、同意）に関する [XDM 個人プロファイルスキーマ](get-started-schemas.md)と、web 新規登録イベントに関する XDM ExperienceEvent スキーマを作成します。
1. [プロファイル対応データセット](get-started-datasets.md)は、各スキーマに対して作成されます。CRM 属性用に 1 つ、新規登録イベント用に 1 つです。
1. Web チームとモバイルチームは、Adobe Experience Platform Web SDK を介して新規登録イベントをストリーミングし、CRM データは[ソースコネクタ](../start/get-started-sources.md)を介して取り込まれます。
1. 管理者は、Journey Optimizer で [Adobe Experience Platform データソース](../datasource/adobe-experience-platform-data-source.md)を設定し、`profile.person.name.firstName`、`profile.personalEmail.address`、`profile.loyaltyTier` などのフィールドを公開します。
1. マーケターは、新規登録イベントをリッスンし、これらのプロファイル属性を使用して[ウェルカムメールをパーソナライズ](../personalization/personalize.md)する[ウェルカムジャーニーを作成](../building-journeys/journey-gs.md)します。 Journey Optimizer は、送信イベントと開くイベントをトラッキングデータセットに書き込み、ジャーニーの進行状況をジャーニーステップイベントデータセットに記録します。
1. 開発者は、[クエリエディター](get-started-queries.md)を使用して、イベントが正しくフローされていることを確認し、パフォーマンス（開封数、クリック数、送信時間）を分析します。 チームは、これらのインサイトに基づいて、ジャーニーとコンテンツを調整します。

このフローでは、スキーマ、データセット、ソース、データソース、クエリが連携する仕組みを、初心者にもわかりやすい完全なユースケースで示しています。

## 関連リソース {#related-resources}

:::: landing-cards-container

:::
![icon](https://cdn.experienceleague.adobe.com/icons/code-branch.svg)

**スキーマの基本を学ぶ**

Adobe Experience Platform で XDM スキーマを作成する方法、適切なクラスとフィールドグループを選択する方法、プロファイル属性と行動イベントをモデル化する方法について説明します。

[詳細情報](get-started-schemas.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/database.svg)

**データセットの操作**

プロファイル対応データセットとイベントデータセットの作成方法、データ取り込みの監視方法、Journey Optimizer がトラッキング、フィードバック、ジャーニーステップイベント用に自動的に作成するシステム生成データセットの探索方法について説明します。

[詳細情報](get-started-datasets.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/gear.svg)

**データソースの設定**

組み込みの Adobe Experience Platform データソースと、オプションの外部データソースを設定して、ジャーニー内でプロファイルフィールドと外部 API 応答を公開する手順について説明します。

[詳細情報](../datasource/about-data-sources.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/puzzle-piece.svg)

**Adobe Experience Platform データ（参照）の使用**

リアルタイム顧客プロファイルにデータを保存することなく、AEP データセットからの参照データまたはトランザクションデータを使用して、実行時にメッセージを強化する方法について説明します。

[詳細情報](lookup-aep-data.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/chart-line.svg)

**クエリの基本を学ぶ**

クエリサービスを使用して、Journey Optimizer のデータセットを分析し、イベントが正しくフローされていることを確認し、送信、開封、クリック、バウンスの各データに関するレポートクエリを作成します。

[詳細情報](get-started-queries.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/bullseye.svg)

**プロファイルの基本を学ぶ**

Journey Optimizer でのリアルタイム顧客プロファイルの仕組みと、Platform UI で個々の顧客プロファイルを参照、検査、検証する方法について説明します。

[詳細情報](../audience/get-started-profiles.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/circle-play.svg)

**データの設定の概要チュートリアル**

スキーマ、データセット、ソースをエンドツーエンドで説明する、Journey Optimizer でのデータ設定の初心者にもわかりやすいビデオチュートリアルです。

[チュートリアルを視聴](https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/data-management/set-up-data-overview){target="_blank"}
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/circle-play.svg)

**データセットの作成とデータの取り込みチュートリアル**

Adobe Experience Platform でデータセットを作成し、ソースコネクタを使用してデータを取り込む方法を、独自のサンドボックスで実行できる手順と共に示す実践的なチュートリアルです。

[チュートリアルを視聴](https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/data-management/create-datasets-and-ingest-data){target="_blank"}
:::

::::
