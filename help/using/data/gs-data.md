---
solution: Journey Optimizer
product: journey optimizer
title: Journey Optimizer におけるデータ管理の基本を学ぶ
description: 主要な概念、設定手順、ガードレールなど、Adobe Journey Optimizerとデータの間の流れを確認できます。
feature: Data Management
role: Developer, Admin, User
level: Beginner, Intermediate
exl-id: 25519acb-a017-446a-992b-653d3a8a3d96
source-git-commit: 89d575834871a5c55bfce75511083b4b651301b8
workflow-type: tm+mt
source-wordcount: '2444'
ht-degree: 2%

---


# データ管理の基本を学ぶ {#about-data}

データは、[!DNL Adobe Journey Optimizer]で提供するすべてのジャーニー、決定、およびメッセージの基盤です。

このページでは、次のことを理解するための実用的な出発点を紹介します。

* Journey Optimizerで使用されるコアデータ構築ブロック（スキーマ、データセット、ID、プロファイル）
* Journey OptimizerでのAdobe Experience Platform データの使用方法
* ジャーニーやキャンペーンを構築する前にチームが完了しなければならないデータ設定ステップ
* 詳細な設定とベストプラクティスのために次に行うべきこと

このガイドをデータエンジニア、管理者、マーケターと一緒に使用することで、Journey Optimizerにデータが流れ込む様子を全員が共有することができます。

>[!TIP]
>Journey Optimizerを初めて利用する場合？ スキーマ、データセット、ソースの実用的で初心者向けのチュートリアルについては、[&#x200B; データ概要チュートリアルの設定](https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/data-management/set-up-data-overview){target="_blank"}をご覧ください。

## Journey OptimizerでのAdobe Experience Platform データの使用方法 {#aep-data}

[!DNL Adobe Journey Optimizer]は[!DNL Adobe Experience Platform]にビルドされています。 独立したデータストアは管理しません。 他のExperience Cloudアプリケーションと同じデータ基盤を使用しています。

スキーマとデータセットはAdobe Experience Platformにあります。 IDと[&#x200B; リアルタイム顧客プロファイル &#x200B;](../audience/get-started-profiles.md)は、ID サービスとプロファイル サービスによって管理されます。 Journey Optimizerは、Adobe Experience Platformからプロファイルとイベントデータを読み取り、ジャーニーの条件を評価し、メッセージをパーソナライズして、オファーを選択します。 このモデルは、送信、開封、クリック、バウンスのイベントや、ジャーニーステップイベントなどのインタラクションデータをExperience Platformデータセットに書き込みます。 また、実行時に、そのデータをプロファイルにコピーすることなく、追加のデータセットを検索することもできます。

>[!TIP]
>Adobe Experience Platformは中心的なデータ層として、Journey Optimizerは共有されたデータ基盤を使用してジャーニーとメッセージを調整するアプリケーションとして考えてください。

➡️ [Journey Optimizer アーキテクチャの詳細](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/get-started/essentials/understanding-ajo#architecture-details){target="_blank"}

## Journey Optimizerの主要なデータコンセプト {#key-concepts}

Journey Optimizerでデータを扱う場合、いくつかの関連する概念が出てきます。 次の表では、簡単な概要を説明します。以下のセクションでは、各コンセプトをより詳しく説明しています。

| コンセプト | 現状 | Journey Optimizerのプライマリ利用 |
|---|---|---|
| XDM スキーマ | データを表すルール、検証、およびフォーマットするルール（クラスとフィールドグループから構築） | モデルプロファイル属性と行動イベント |
| データセット | スキーマに準拠するデータの格納テーブル | プロファイル、イベント、システム生成データの保持 |
| Source コネクタ | 外部システムからのデータをAEPにストリーミングまたはバッチ処理 | CRM、分析、web データの取り込み |
| データソース | ジャーニー内のAEPまたは外部フィールドを公開します | ジャーニーの条件とメッセージのパーソナライゼーションを強化する |
| ID | 個々の顧客を一意に表す識別子 | チャネルをまたいでプロファイルを連携 |
| ルックアップデータセット | プロファイルストレージを使用しないAEP データへのランタイム参照 | ライブ参照データを使用したメッセージの強化 |

### スキーマ （XDM スキーマ） {#schema}

スキーマとは、データを表し、検証し、フォーマットする一連のルールのことです。 これは、**クラス** （基本ビヘイビアーを定義するレコードまたは時系列）と、オプションの&#x200B;**フィールドグループ** （特定のフィールドを追加する）で構成されます。 スキーマは、Experience Data Model （XDM）標準を使用して定義され、Adobe Experience Platformで公開されます。

XDMは、実際の問題を解決するために存在します。同じ概念（顧客、購入、製品）でも、ソースシステム間で名前と構造が異なります。 XDMは、データの生成元に関係なく、これらの概念を単一の定義の下に統合する共有言語を提供します。 これにより、Journey Optimizerで、CRM、web サイト、モバイルアプリ、データウェアハウスからのデータを同時に収集し、一貫性のある方法で作業できます。

Journey Optimizerでは、通常、顧客属性（名前、嗜好、同意）の&#x200B;**XDM Individual Profile** スキーマと、行動イベント（購入、ページビュー、サインアップ）の&#x200B;**XDM ExperienceEvent** スキーマを使用します。

➡️ [&#x200B; スキーマの詳細](get-started-schemas.md)

### データセット {#dataset}

データセットとは、スキーマに準拠するデータを保存および管理するための構造体です。スキーマは、列と行のセットが定義されたテーブルとして考えることができます。 Journey Optimizerで使用されるすべてのデータは、Adobe Experience Platform データセットに保存されます。 これには、プロファイルデータセット（リアルタイム顧客プロファイルに貢献）、イベントデータセット（ジャーニーと分析用の行動データの保存）、トラッキング、フィードバック、ジャーニーステップイベント用にJourney Optimizerで自動的に作成されたシステムデータセットなどが含まれます。

➡️ [&#x200B; データセットの詳細](get-started-datasets.md)

### Source コネクタ {#source-connector}

ソースコネクタ （**ソース**&#x200B;とも呼ばれます）を使用すると、Adobe Analytics、Adobe Experience Platform Web SDK、クラウドストレージ（S3、Azure Blob）、CRM データベースなど、複数のシステムからAdobe Experience Platformにデータを取り込むことができます。 コネクタを使用すると、生の取り込みだけでなく、XDM スキーマへのフィールドマッピングやデータガバナンスラベル付けなど、Experience Platform サービスを使用してデータの構造化、ラベル付けおよび強化が可能になります。

➡️ [&#x200B; ソースコネクタの詳細](../start/get-started-sources.md)

### データソース（Journey Optimizer） {#data-source}

Journey Optimizerのデータソースは、ジャーニーやメッセージ内で公開されるAdobe Experience Platform（または外部API）のフィールドを定義します。 Journey Optimizer UIで設定されたデータソースには、通常、組み込みのAdobe Experience Platform データソース（リアルタイム顧客プロファイル属性とイベントを公開）と、ジャーニーランタイムに呼び出されるオプションの外部データソースまたはカスタムデータソースが含まれ、さらにエンリッチメントが行われます。 ジャーニーの条件、カスタムアクション、メッセージのパーソナライゼーションに使用されます。

➡️ [&#x200B; データソースの詳細](../datasource/about-data-sources.md)

>[!NOTE]
>[Adobe Experience Platform用語集](https://experienceleague.adobe.com/en/docs/experience-platform/landing/glossary){target="_blank"}では、「データソース」をデータの生成元（CRM、モバイルアプリなど）として一般的に定義しています。 Journey Optimizerでは、**データソース**&#x200B;には特定の意味があります。ジャーニーとメッセージ内で公開されるフィールドを制御するUI設定です。

### IDとリアルタイムの顧客プロファイル {#identity}

IDとは、Cookie ID、デバイス ID、メールアドレス、CRM IDなど、個々の顧客を一意に表す識別子です。 IDは名前空間（電子メール、ECID、CRMID）に整理され、同じユーザーの複数のIDが統合されたID グラフに合成されます。 そのグラフを使用して、オンライン、オフライン、CRM、サードパーティなど、複数のチャネルからのデータを組み合わせ、個々の顧客の全体像を維持します。

初心者向けの重要なコンセプトは、**プロファイルフラグメント** モデルです。 web サイト、モバイルアプリ、実店舗など、顧客が特定のデバイスやチャネルで企業と接触するたびに、そのインタラクションはプロファイルフラグメントとして記録されます。つまり、特定の顧客接点にもとづいた顧客の全体像です。 Adobe Real-Time CDPは、共有されたID値にもとづいて、これらのフラグメントを継続的につなぎ合わせ、包括的かつ最新のプロファイルを構築します。 Journey Optimizerは、この収集されたプロファイルから読み取り、条件の評価、オファーの選択、メッセージのパーソナライズをリアルタイムで実行します。

➡️ [Journey OptimizerのIDについて詳しく見る](../audience/get-started-identity.md)

### ルックアップデータセット {#lookup-dataset}

ルックアップデータセットを使用すると、Journey Optimizerは、リアルタイム顧客プロファイルにデータを保存することなく、Adobe Experience Platform データセットから実行時に参照データまたはトランザクションデータを取得できます。 これは、頻繁に変更される参照データ（価格、在庫、店舗時間）や、メッセージ時に必要ですが、プロファイルには属さないトランザクションデータに役立ちます。 Journey Optimizerは、製品IDなどのキーに基づいて、ジャーニーまたはメッセージの実行中にルックアップを実行します。

➡️ [&#x200B; ルックアップデータセットの詳細](lookup-aep-data.md)

## データ準備チェックリスト {#checklist}

マーケターがジャーニーやキャンペーンの構築を始める前に、データ準備の一連のステップを完了する必要があります。 これにより、Journey Optimizerは適切なデータをタイミングよく、コンプライアンスに準拠した方法で利用できるようになります。

>[!NOTE]
>次の手順には、データエンジニア、管理者、マーケターなど、複数の役割が関与します。 このチェックリストを、環境を準備するための共有プランとして使用します。 手順1～4はAdobe Experience Platformで完了し、手順5～6はJourney Optimizerで設定します。

次の6つのステップでは、ID設定から、データがJourney Optimizerに正しく取り込まれることを確認するまで、完全なデータ設定プロセスを順を追って説明します。

1. ID戦略の策定
1. プロファイルデータとイベントデータのスキーマの設計
1. プロファイル対応データセットの作成
1. ソースからデータを取り込みます
1. Journey Optimizerでのデータソースの設定
1. トラッキング、フィードバック、ジャーニーのデータセットを検証する

+++ ID戦略の策定

お客様のプライマリ ID （ECID、電子メール、CRMIDなど）を選択し、Adobe Experience Platform Identity Serviceで対応する名前空間を設定します。 ID フィールドがプロファイル対応スキーマに存在することを確認し、プロファイルがID グラフに正しく合成されていることを検証します。

➡️ [Journey OptimizerのIDについて詳しく見る](../audience/get-started-identity.md)

+++

+++ プロファイルデータとイベントデータのスキーマの設計

**XDM個人プロファイル** スキーマを作成して、名前や連絡先情報、好みや興味、ライフサイクルステージや同意状態などの顧客属性を取得します。 **XDM ExperienceEvent** スキーマを作成して、webやアプリのイベント、購入、オフラインのインタラクションなどの行動データやトランザクションデータを取得します。 適切な場合は、正しいフィールドをIDおよびプロファイル属性としてマークします。

➡️ [&#x200B; スキーマの詳細](get-started-schemas.md)

+++

+++ プロファイル対応データセットの作成

Adobe Experience Platformでは、XDM スキーマに基づいてデータセットを作成し、リアルタイム顧客プロファイルに貢献する必要があるデータセットでプロファイルを有効にします。 Journey Optimizerで作成されたシステム生成データセットがデータセット ワークスペースに表示されていることを確認します。

➡️ [&#x200B; データセットの詳細](get-started-datasets.md)

+++

+++ ソースからデータを取り込みます

Adobe Analytics、Adobe Experience Platform Web SDK、CRMおよびPOS プラットフォームなどのエンタープライズシステム用のソースコネクタを設定し、XDM スキーマに受信フィールドをマッピングします。 データが正しいデータセットに格納され、予想される場所にリアルタイム顧客プロファイルに表示されることを検証します。

➡️ [&#x200B; ソースコネクタの詳細](../start/get-started-sources.md)

➡️ [&#x200B; チュートリアル：データセットの作成とデータの取り込み](https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/data-management/create-datasets-and-ingest-data){target="_blank"}

+++

+++ Journey Optimizerでのデータソースの設定

データソースは、Journey Optimizer固有の概念です。データソースは、データが存在する場所ではなく、ジャーニーやメッセージの実行中にJourney Optimizerが読み取り可能なフィールドを宣言する場所です。 「顧客はロイヤルティメンバーか？」などの条件を評価できます 名を付けてメッセージをパーソナライズするには、関連するプロファイルフィールドをデータソース設定を通じて公開する必要があります。

Journey Optimizerには、リアルタイム顧客プロファイル属性に直接アクセスできる組み込みの[Adobe Experience Platform データソース &#x200B;](../datasource/adobe-experience-platform-data-source.md)が含まれています。 パーソナライゼーションのためのプロファイル属性の読み取り、同意と環境設定フィールドのチェックなど、ほとんどのユースケースをカバーしています。 また、[外部データソース &#x200B;](../datasource/external-data-sources.md)を設定して、ジャーニーランタイムでサードパーティ APIを呼び出すことができます。例えば、リアルタイムのロイヤルティスコア、商品レコメンデーション、Adobe Experience Platformに保存されていないストア在庫レベルを取得できます。

>[!NOTE]
>組み込みのAdobe Experience Platform データソースを介したエクスペリエンスイベントデータへのダイレクトアクセスは廃止され、段階的に無効になります。 [詳細情報](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/orchestrate-journeys/journey-use-cases/exp-event-lookup){target="_blank"}

データソースの設定は、ジャーニー作成者とマーケターのデータレイヤー全体のロックを解除する管理タスクです。 データソースを通じてフィールドが公開されると、ジャーニー条件ビルダー、メッセージパーソナライゼーションエディター、オファー決定ルールでフィールドを使用できるようになります。ジャーニー構築時に追加のエンジニアリング作業は必要ありません。

➡️ [&#x200B; データソース設定の詳細](../datasource/about-data-sources.md)

+++

+++ トラッキング、フィードバック、ジャーニーのデータセットを検証する

Journey Optimizer システム生成データセットがデータセットワークスペースで使用できることを確認します。 ジャーニーとキャンペーンをテストし、クエリエディターを使用して、送信、開封、クリック、バウンスのイベントが記録され、ジャーニーステップのイベントと状態が正しく取得されていることを確認します。 これらのデータセットは、継続的なモニタリング、トラブルシューティング、ジャーニーの最適化に使用できます。

➡️ [Journey Optimizerのクエリについて詳しく見る](get-started-queries.md)

+++

## ガードレールとデータ設計の考慮事項 {#guardrails}

製品のガードレールや制限事項により、データモデルやジャーニーの設計方法が異なる場合があります。 後のやり直しを避けるために、これらのステップを早い段階で見直しましょう。

>[!IMPORTANT]
>最新の情報については、常に[Journey Optimizerのガードレールと制限](../start/guardrails.md) ページを参照してください。 以下の要約では、主要な項目を取り上げますが、時間の経過とともに変化する可能性があります。

### Journey OptimizerのシステムデータセットとTTL {#datasets-ttl}

Journey Optimizerは、トラッキング、フィードバック、ジャーニーステップイベント用に、システム生成データセットをいくつか作成します。 2025年2月の時点で、一部のデータセットにはTTL （Time-to-Live）ガードレールが展開されています。これは、分析とトラブルシューティングのためにデータを保持する時間に影響を与える可能性があります。

➡️ [&#x200B; データセット TTL ガードレールの詳細](datasets-ttl.md)

### ストリーミングセグメンテーションとJourney Optimizerイベント {#streaming-segmentation}

2024年11月1日（PT）をもって、ストリーミングセグメンテーションでは、Journey Optimizer トラッキングおよびフィードバックデータセットからのイベントの送信とオープンがサポートされなくなりました。 頻度の上限や疲労管理などのユースケースでは、送信/開封イベントに基づいてセグメントをストリーミングする代わりに[&#x200B; ビジネスルール &#x200B;](../conflict-prioritization/rule-sets.md)を使用します。

➡️ [&#x200B; データセットの詳細](get-started-datasets.md)

### データセットの検索と決定 {#lookup-guardrails}

データセット検索は、頻繁に変化する属性（在庫、価格設定、天候）や、リアルタイム顧客プロファイルに保存する必要のないデータに適しています。 ルックアップ戦略を設計する前に、関連ドキュメントでデータセットのサイズ制限やクエリキャップなどの製品固有のガードレールを確認してください。

➡️ [&#x200B; ルックアップデータセットの詳細](lookup-aep-data.md)

## 例：ウェルカムジャーニーのデータの準備 {#example}

次の例は、このページの概念が簡単なシナリオでどのように連携するかを示しています。

1. データエンジニアは、顧客属性（名前、電子メール、ロイヤルティ層、同意）用に[XDM個人プロファイルスキーマ &#x200B;](get-started-schemas.md)を作成し、web サインアップイベント用にXDM ExperienceEvent スキーマを作成します。
1. [&#x200B; プロファイル対応データセット &#x200B;](get-started-datasets.md)は、各スキーマに対して作成されます。CRM属性用に1つ、サインアップイベント用に1つです。
1. Web チームとモバイル チームは、Adobe Experience Platform Web SDKを介してサインアップイベントをストリーミングします。CRM データは[&#x200B; ソースコネクタ &#x200B;](../start/get-started-sources.md)を介して取り込まれます。
1. 管理者がJourney Optimizerの[Adobe Experience Platform データソース &#x200B;](../datasource/adobe-experience-platform-data-source.md)を設定し、`profile.person.name.firstName`、`profile.personalEmail.address`、`profile.loyaltyTier`などのフィールドを公開します。
1. マーケター[は、サインアップイベントをリッスンし、これらのプロファイル属性を使用して](../building-journeys/journey-gs.md) ウェルカムメールをパーソナライズするウェルカムジャーニー[を作成します](../personalization/personalize.md)。 Journey Optimizerは、送信および開くイベントをトラッキングデータセットに書き込み、ジャーニーステップイベントデータセットでジャーニーの進行状況を記録します。
1. 開発者は[&#x200B; クエリエディター](get-started-queries.md)を使用して、イベントが正しく流れていることを確認し、パフォーマンス（開封数、クリック数、送信時間）を分析します。 Ma チームは、これらのインサイトにもとづいて、カスタマージャーニーとコンテンツを調整します。

このフローでは、スキーマ、データセット、ソース、データソース、クエリが、初心者にも使いやすい包括的なユースケースでどのように連携するのかを示しています。

## 関連リソース {#related-resources}

:::: landing-cards-container

:::
![icon](https://cdn.experienceleague.adobe.com/icons/code-branch.svg)

**スキーマの基本を学ぶ**

Adobe Experience PlatformでXDM スキーマを作成する方法、適切なクラスとフィールドグループを選択する方法、プロファイル属性と行動イベントをモデル化する方法について説明します。

[詳細情報](get-started-schemas.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/database.svg)

**データセットの操作**

プロファイル対応およびイベントデータセットの作成方法、データ取り込みのモニター方法、トラッキング、フィードバック、ジャーニーステップイベント用にJourney Optimizerが自動的に作成するシステム生成データセットの調査方法について説明します。

[詳細情報](get-started-datasets.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/gear.svg)

**データソースの設定**

組み込みのAdobe Experience Platform データソースとオプションの外部データソースを設定して、ジャーニー内でプロファイルフィールドと外部API レスポンスを公開するためのステップバイステップガイダンス。

[詳細情報](../datasource/about-data-sources.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/puzzle-piece.svg)

**Adobe Experience Platform データ （ルックアップ）を使用**

AEP データセットの参照データまたはトランザクションデータを、リアルタイム顧客プロファイルに保存せずに、実行時にメッセージを強化する方法について説明します。

[詳細情報](lookup-aep-data.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/chart-line.svg)

**クエリの基本を学ぶ**

Adobe Experience Platform Query Serviceを使用して、Journey Optimizerのデータセットを分析し、イベントが正しく流れていることを検証して、送信、開く、クリック、バウンスなどのデータに関するクエリを作成できます。

[詳細情報](get-started-queries.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/bullseye.svg)

**プロファイルの基本を学ぶ**

Journey Optimizerでのリアルタイム顧客プロファイルの仕組みと、Platform UIでの個々の顧客プロファイルの参照、検査、検証方法について説明します。

[詳細情報](../audience/get-started-profiles.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/circle-play.svg)

**データ概要チュートリアルの設定**

Journey Optimizerでのデータ設定に関する初心者向けのビデオチュートリアル。スキーマ、データセット、ソースをエンドツーエンドで説明します。

[&#x200B; チュートリアルを見る](https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/data-management/set-up-data-overview){target="_blank"}
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/circle-play.svg)

**データセットの作成とデータの取り込みチュートリアル**

Adobe Experience Platformでデータセットを作成し、ソースコネクタを使用してデータを取り込む方法を示す実践的なチュートリアルと、独自のサンドボックスで実行できるステップバイステップの説明です。

[&#x200B; チュートリアルを見る](https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/data-management/create-datasets-and-ingest-data){target="_blank"}
:::

::::
