---
solution: Journey Optimizer
product: journey optimizer
title: ロイヤルティの課題の作成
description: Adobe Journey Optimizerでロイヤルティの課題を作成し設定する方法を説明します。
feature: Journeys
topic: Content Management
role: User
level: Intermediate
hide: true
hidefromtoc: true
badge: label="Private Beta" type="Informative"
source-git-commit: 831809b4c1dd19fdaeeb646695f606c02ec21265
workflow-type: tm+mt
source-wordcount: '888'
ht-degree: 2%

---


# 課題の作成 {#create-challenges}

>[!BEGINSHADEBOX]

**ロイヤルティの課題に関するドキュメント：**

* [&#x200B; ロイヤルティの課題の概要 &#x200B;](get-started.md) – 概要、ワークフロー、前提条件
* [&#x200B; ロイヤルティの課題へのアクセス &#x200B;](access-loyalty-challenges.md) – 在庫とフィルタリング
* **課題の作成** ◀︎ **現在の状況** – 課題の作成と設定
* [&#x200B; タスクの作成 &#x200B;](create-tasks.md) – 課題タスクの定義
* [&#x200B; 課題の管理 &#x200B;](manage-challenges.md) – 編集、監視、最適化

>[!ENDSHADEBOX]

>[!AVAILABILITY]
>
>この機能は現在 **Private Beta** であり、お使いの環境では使用できない場合があります。アクセス権をリクエストするには、Adobe担当者にお問い合わせください。 詳細情報 [&#x200B; 可用性ラベル &#x200B;](../rn/releases.md#availability-labels)。

## 仕組み {#how-it-works}

<!-- SCHEMA: Visual workflow showing the 5 main steps with icons: Create challenge → Add tasks → Design content cards → Configure messaging → Review and publish -->

ロイヤルティの課題の作成と開始は、次のワークフローに従います。

1. **チャレンジの作成** – 名前、タイプ（標準、ストリーク、順次）、オーディエンス、日付範囲など、基本的なチャレンジのプロパティを定義します。

1. **タスクを追加** - タスクのタイプ（購入、支出、訪問など）、数量、製品フィルター、報酬など、顧客が完了する必要がある特定のアクションを定義します。

1. **コンテンツカードの設計** – お客様のデバイスに表示されるJourney Optimizer コンテンツカードを使用して、課題を視覚的に表現します。

1. **メッセージの設定** （オプション） – ローンチ、処理中、完了などの主要なステージに対して、マルチチャネルメッセージ（アプリ内、メール、プッシュ、SMS）を設定します。

1. **レビューして公開** - テストプロファイルを使用して課題をテストし、公開して、ターゲットオーディエンスで利用できるようにします。

## 課題の作成 {#create-challenge}

<!-- SCREENSHOT: Challenge creation screen showing challenge properties form with fields for name, type, audience, dates -->

新しいロイヤルティの課題を作成するには：

1. Journey Optimizerの **[!UICONTROL ロイヤルティの課題]** に移動します。

1. 「**[!UICONTROL 課題]** タブを選択します。

1. **[!UICONTROL チャレンジを作成]** を選択します。

1. チャレンジのプロパティを設定します。

   **チャレンジ名**：チャレンジのわかりやすい名前を入力します。 この名前は、課題インベントリに表示され、課題を特定するのに役立ちます。

   **チャレンジの種類**：次のいずれかのタイプを選択します。
   * **[!UICONTROL Standard]**：顧客は、任意の順序で任意の数のタスクを完了します
   * **[!UICONTROL Streak]**：お客様が同じタスクを複数回連続して完了する
   * **[!UICONTROL 順次]**：顧客が定義された順序でタスクを完了します

   **ターゲットオーディエンス**：この課題に参加できるユーザーを定義するオーディエンスセグメントを選択します。 課題を作成する前に、Experience Platformでオーディエンスを作成する必要があります。 詳しくは、[&#x200B; オーディエンスの基本を学ぶ &#x200B;](../audience/about-audiences.md) を参照してください。

   **開始日**：顧客がチャレンジを利用できるタイミングを設定します。

   **終了日**：チャレンジの有効期限が切れ、新しい完了を受け入れなくなる時期を設定します。

<!-- VISUAL: Comparison table or diagram showing the three challenge types (Standard, Streak, Sequential) with examples of each -->

### タスクを追加 {#add-tasks}

タスクは、顧客が報酬を得るために完了する必要がある特定のアクションまたはマイルストーンを定義します。 タスクのタイプ（購入、支出、訪問、エンゲージメント、カスタムイベント）、数量、製品フィルターおよび報酬を設定します。

課題の種類に応じて、顧客のタスクの実行方法は異なります。

* **標準的な課題**：任意の順序で任意の指定数のタスクを完了する
* **一連の課題**：同じタスクを連続して複数回完了する
* **順次的な課題**：定義された順序でタスクを完了する

課題にタスクを追加するには、「タスク」セクションで **[!UICONTROL タスクを追加]** を選択し、タスクのプロパティを設定します。

タスクの作成と設定について詳しくは、[&#x200B; タスクの作成 &#x200B;](create-tasks.md) を参照してください。

### コンテンツカードの設定 {#configure-content-cards}

<!-- SCREENSHOT: Content cards configuration section in the challenge editor -->

コンテンツカードは、お客様のデバイス上の課題を視覚的に表現し、課題の情報、進行状況、報酬を表示します。 詳細情報 [&#x200B; コンテンツカード &#x200B;](../content-card/create-content-card.md)。

<!-- VISUAL: Example content card designs showing different states: challenge start, in-progress with progress bar, completion with reward -->

課題に合わせてコンテンツカードを設定するには：

1. チャレンジ エディターで、「**[!UICONTROL コンテンツカード]**」セクションに移動します。

1. **[!UICONTROL コンテンツカードを作成]** を選択するか、既存のテンプレートを選択します。

1. コンテンツカードをデザインします。
   * 画像、テキスト、ブランディング要素の追加
   * [&#x200B; パーソナライゼーショントークン &#x200B;](../personalization/personalization-syntax.md) を含めて、顧客固有の情報を表示する
   * チャレンジ進行状況インジケーターの表示
   * 報酬とインセンティブの表示

1. コンテンツカードの表示時期を設定します。
   * **チャレンジ開始**：チャレンジが使用可能になる時期を表示します
   * **処理中**：顧客が積極的に参加している間に表示します
   * **完了**：顧客がすべてのタスクを完了した後に表示します

1. 様々なデバイスでコンテンツカードをプレビューして、適切に表示されるようにします。

1. コンテンツカード設定を保存します。

コンテンツカードのデザインとパーソナライズについて詳しくは、[&#x200B; コンテンツカードのデザイン &#x200B;](../content-card/design-content-card.md) を参照してください。

### メッセージングの設定 {#configure-messaging}

<!-- SCREENSHOT: Messaging configuration section showing the three lifecycle stages: Launch, In-progress, Completion -->

チャレンジライフサイクルの主要な段階で顧客を引き付けるためのマルチチャネルメッセージを設定します。

<!-- VISUAL: Timeline diagram showing when each message type is sent during the challenge lifecycle -->

課題に合わせてメッセージングを設定するには：

1. 課題エディターで、「**[!UICONTROL メッセージング]**」セクションに移動します。

1. 各ライフサイクルステージに対するメッセージの設定：

   **メッセージを開始** – 課題が始まったときに顧客に通知します。
   * チャネルを選択：[&#x200B; アプリ内 &#x200B;](../in-app/get-started-in-app.md)、[&#x200B; メール &#x200B;](../email/get-started-email.md)、[&#x200B; プッシュ通知 &#x200B;](../push/get-started-push.md) または [SMS](../sms/get-started-sms.md)
   * 課題の詳細とcall-to-actionを使用したメッセージのデザイン
   * タイミングを設定：チャレンジが開始されたときや、特定の時間スケジュールされたときに直ちに送信します

   **進行中のメッセージ** – 課題が発生している間も顧客のエンゲージメントを維持できます。
   * トリガー条件（50% 完了、特定のタスクが完了など）を定義する
   * 継続的な参加を促すためのリマインダーメッセージの作成
   * 進行状況の更新と次の手順を含める

   **完了メッセージ** – 成功を祝い、報酬を提供します。
   * お客様が課題を完了したことをお祝いします
   * 報酬配分の確認
   * 報酬の支払い方法を説明する
   * 次の課題またはアクションを提案

特定のチャネル向けのメッセージの作成について詳しくは、以下を参照してください。

* [アプリ内メッセージドキュメント](../in-app/get-started-in-app.md)
* [メールメッセージドキュメント](../email/get-started-email.md)
* [プッシュ通知ドキュメント](../push/get-started-push.md)
* [SMS メッセージドキュメント](../sms/get-started-sms.md)

## 課題のレビューと公開 {#review-and-publish}

<!-- SCREENSHOT: Review screen showing summary of challenge configuration with all components listed -->

課題を公開する前に：

1. **すべてのコンポーネントのレビュー**：課題のプロパティ、タスク、報酬、コンテンツカードおよびメッセージ設定を確認します。

1. **エクスペリエンスのテスト**:[&#x200B; テストプロファイル &#x200B;](../test-approve/test-profiles.md) を使用して、コンテンツカードの表示とタスクトリガーの動作を検証します。

1. **公開**: **[!UICONTROL 公開]** を選択して、ターゲットオーディエンスがチャレンジを利用できるようにします。

<!-- SCREENSHOT: Journeys inventory showing the auto-generated journey in Draft status with name format "Challenge: [Challenge Name]" -->

課題を公開すると、Journey Optimizerによって自動的に [&#x200B; ジャーニー &#x200B;](../building-journeys/journey-gs.md) がドラフトステータスで作成されます。 自動生成されたジャーニーは、「チャレンジ：[ チャレンジ名 ]」という名前形式でジャーニーインベントリに表示されます。

課題を顧客に提供するには：

1. Journey Optimizerの **[!UICONTROL ジャーニー]** インベントリに移動します。

1. 自動生成されたジャーニーを見つけます（名前にプレフィックスとして「Challenge:」が含まれます）。

1. [&#x200B; ジャーニーをアクティベート &#x200B;](../building-journeys/publishing-the-journey.md) します。

ジャーニーは、指定したチャレンジ開始日に自動的に開始します。

>[!NOTE]
>
>自動生成されたジャーニーはジャーニーインベントリに表示され、必要に応じてカスタマイズできます。 ただし、ジャーニーに直接加えられた変更は、チャレンジ設定には同期されません。

## 次の手順 {#next-steps}

* [&#x200B; 課題の管理 &#x200B;](manage-challenges.md) – 課題を編集、監視、最適化する方法を説明します。
* [&#x200B; ロイヤルティの課題について &#x200B;](get-started.md) – 機能と性能の確認

