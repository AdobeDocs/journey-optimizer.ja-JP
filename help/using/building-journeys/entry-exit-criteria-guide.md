---
solution: Journey Optimizer
product: journey optimizer
title: ジャーニーの入口と出口の基準
description: 実際の例とベストプラクティスを用いて、プロファイルがジャーニーにエントリしたり離脱したりする際に効果的に管理する方法を説明します
feature: Journeys, Profiles
role: User
level: Intermediate
keywords: 入口、出口、基準、ジャーニー、プロファイル、再エントリ、ベストプラクティス
version: Journey Orchestration
exl-id: e879a0f6-b969-4de0-a733-f2880d58d59b
TQID: https://experienceleague.adobe.com/6OJQsorJ9p7gtO1ep-rIss60J2TmKzqiNS3Btfhh8Gs
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2:
  - id: b3538224-471e-4c63-a444-9b19d89ae29c
  - id: bb359667-ec7d-4d4b-8663-5850fc219d32
  - id: d998adac-2f81-400b-a669-d07bb196e4eb
  - id: df64005d-8f9a-422e-ba4d-c6f6dc3454b4
  - id: fe338112-e2ce-4876-8989-fc4d497613f1
subfeature_v2:
  - id: c3f67a94-f1ff-4f5e-bf6f-bc22405930a3
  - id: ebd64fe4-362a-4a1c-9476-b2573ed12a95
  - id: f42b4d14-fe8a-428b-b62e-e7995eaab1b3
  - id: fa683eda-48de-4558-af32-2673edcd44fe
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: f9b8e1590f14cdcd00432295c653769f753b9b40
workflow-type: tm+mt
source-wordcount: 1670
ht-degree: 0%

---

# ジャーニーの入口および出口の基準の操作 {#entry-exit-criteria-guide}

顧客体験の連携では、顧客がジャーニーに出入りするのを正確に制御し、適切なメッセージを的確なタイミングで配信する必要があります。 入口と出口の基準を把握し、適切に設定することで、施策の成功、魅力的な施策の展開、機会損失、メッセージ疲労を把握することができます。

このガイドでは、実用的なガイダンス、実例、および[!DNL Adobe Journey Optimizer]でのジャーニーのエントリと離脱の基準を管理するためのベストプラクティスについて説明します。

## 入口と出口の基準は？ {#what-are-criteria}

**エントリ条件**&#x200B;は、[顧客プロファイル &#x200B;](../audience/get-started-profiles.md)が特定のジャーニーにエントリする条件を決定します。 プロファイルは次の基準で入力できます。

* **[顧客行動](../event/about-events.md)** – 購入、カートの放棄、モバイルアプリの起動など、トリガージャーニーをリアルタイムで入力する顧客の行動。

* **[プロファイル属性](../audience/get-started-profiles.md)** – 顧客特性は、ロイヤルティ層、場所、年齢、コミュニケーション設定など、プロファイルに保存されたデータに基づいて実施要件を決定します。

* **[外部イベント](../event/about-creating-business.md)** – 複数のお客様に同時に影響を与えるビジネスまたは環境トリガー（在庫不足、気象条件、価格変更など）。

* **[オーディエンスメンバーシップ](../audience/about-audiences.md)** – 特定のオーディエンスセグメントに属すると、価値の高い顧客、非アクティブなユーザー、新規購読者などのグループをターゲットにしたジャーニーを有効にできます。

**離脱条件**&#x200B;は、プロファイルがいつ、どのようにジャーニーから離脱するか、またはジャーニーから削除されるかを定義します。

* **ジャーニー完了** - プロファイルがすべてのジャーニーパス [&#128279;](end-journey.md)の末尾に到達すると、自動的に終了し、設計されたエクスペリエンスが完了します。

* **成功指標の達成** - プロファイルは、購入やアプリのダウンロードなど、[&#x200B; ジャーニー目標](success-metrics.md)を完了すると終了し、不要なフォローアップコミュニケーションは不要になります。

* **条件ベース** - [特定の条件](conditions.md)が満たされると、プロファイルは終了します。これは、設定された期間の非アクティブ化やプロファイル属性の変更など同様です。

* **イベントベースの** - [特定のイベント（](../event/about-events.md)）が発生した場合、サブスクリプションの解約や製品返品など）にプロファイルが終了します。

* **オーディエンスの失格** - プロファイルは、[&#x200B; ターゲットオーディエンスの条件](../audience/about-audiences.md)を満たさなくなると終了し、メッセージの関連性が維持されます。

## 入口と出口の基準が重要な理由 {#why-they-matter}

入口と出口の基準を適切に定義することで、大きなビジネス価値がもたらされます。

* **関連性**：適切な顧客のみがジャーニーに参加し、最適なタイミングで最も適切なオーディエンスをターゲットにすることで、エンゲージメントとコンバージョン率を向上させます。

* **効率性**：顧客が無関係なジャーニーに留まるのを防ぎ、不要なコミュニケーション、運用コスト、顧客の苛立ちを減らします。

* **Personalization**: リアルタイム データと行動に基づいてエクスペリエンスを動的にカスタマイズし、より有意義な顧客インタラクションを実現します。

* **コンプライアンス**：頻度の上限を管理し、過剰なコミュニケーションを避け、ブランドの評判を維持しながら顧客の嗜好と規制要件を尊重します。

## ジャーニーの入口と出口の実例 {#real-world-examples}

入口と出口の基準が実際にどのように機能するかを示す一般的なシナリオを次に示します。

**新規購読者のウェルカムキャンペーン**

新規登録者に対して、自社の製品やサービスの概要を自動的に説明することで、パーソナライズされた第一印象を提供できます。

* **エントリ**: プロファイルがニュースレターを購読すると、ジャーニーにエントリします
* **離脱**: プロファイルは、ウェルカムメールの一連の送信を完了した後、またはエンゲージしない場合は設定した時間を過ぎて離脱します
* **メリット**：新しい購読者が繰り返しのメッセージを避けながら、タイムリーなオンボーディングを受け取れるようにします

**カート放棄の回復**

失った商品をリマインドし、購入を完了するためのインセンティブを提供することで、失った売上を取り戻します。

* **エントリ**：顧客が買い物かごに商品を追加したものの、24時間以内にチェックアウトを完了しなかった場合、ジャーニーにエントリする
* **離脱**：購入を完了したプロファイル、または購入しなかった場合は7日後に離脱します
* **メリット**：興味のない顧客に迷惑メールを送ることなく、タイムリーなリマインダーを送信してコンバージョンを促進します

**ロイヤルティプログラムのエンゲージメント**

最も価値の高い顧客に対して、限定特典やパーソナライズされたコミュニケーションを提供し、ブランドロイヤルティを高め、生涯価値を高めます。

* **エントリ**：顧客は、特定のロイヤルティポイントのしきい値に達した後、ジャーニーに参加します
* **離脱**: プロファイルは、報酬の引き換え後、または60日間非アクティブな場合に離脱します
* **メリット**：パーソナライズされたオファーを通じて価値の高い顧客との関係を維持し、コミュニケーション疲れを回避します

**製品フィードバックコレクション**

納品後の最適なタイミングでフィードバックを要求することで、顧客満足度と製品パフォーマンスに関するインサイトを収集できます。

* **エントリ**：お客様は、製品配達確認イベントを受け取った後にジャーニーにエントリします
* **終了**: フィードバックが送信されると、または応答がない場合は10日後にプロファイルが終了します
* **メリット**：永続的なリクエストを持つ顧客に迷惑をかけることなく、貴重なフィードバックを迅速に取得します

## ジャーニー入力条件の設定方法 {#configure-entry}

>[!BEGINSHADEBOX]

**入学条件について知っておくべきことを、ここで説明します。**

* **[イベントベースのトリガー](../event/about-events.md)**:「プロファイル作成」、「トランザクション完了」、カスタムイベントなどのイベントを使用して、ジャーニーを開始します。 [管理&#x200B;]&#x200B;**/**&#x200B;[!UICONTROL &#x200B; イベント &#x200B;]&#x200B;**でイベント (../event/about-creating.md)を設定し、[&#x200B; イベントスキーマとフィールド &#x200B;](../event/experience-event-schema.md)を定義します。**&#x200B;次に、[&#x200B; ジャーニーデザイナー](using-the-journey-designer.md)の&#x200B;**[!UICONTROL イベント]** パレットからイベントを追加します。

* **[オーディエンスベースのエントリ](read-audience.md)**：ジャーニーを、1回限りのバッチまたは定期的なスケジュールのいずれかで、特定のオーディエンスに属するプロファイルにターゲティングします。 **[!UICONTROL オーディエンス]** メニューで[&#x200B; オーディエンス &#x200B;](../audience/creating-a-segment-definition.md)を作成してから、**[!UICONTROL オーディエンスの読み取り]** アクティビティを追加し、[&#x200B; スケジュールを設定](journey-properties.md#schedule)。 入力後、条件を使用して[分岐をセグメント化、除外、または結合](read-audience.md#audience-targeting-in-journeys)します。

* **[オーディエンス選定エントリ](audience-qualification-events.md)**: プロファイルが特定のトリガーに対してリアルタイムで選定または離脱する場合のオーディエンスジャーニー。 [&#x200B; ストリーミングオーディエンス &#x200B;](../audience/about-audiences.md)を定義し、**[!UICONTROL イベント]** パレットから&#x200B;**[!UICONTROL オーディエンス選定]**&#x200B;トリガーを追加して、イベントの種類を選択します。

* **[属性フィルター](conditions.md)**:AND/OR ロジックを使用して、イベントまたはオーディエンスをプロファイル属性およびコンテキストと組み合わせてエントリ条件を調整します。 [条件](conditions.md)を使用して、[&#x200B; プロファイル属性](../audience/get-started-profiles.md)、イベント、または[外部データ &#x200B;](../datasource/about-data-sources.md)を参照します。

* **[時間枠とスケジュール](journey-properties.md#schedule)**: ジャーニーをタイムリーかつ関連性のある状態に保つために、時間的制約を設定します。 読み取りオーディエンスアクティビティ [&#128279;](read-audience.md)で スケジュールを設定し、[待機アクティビティ &#x200B;](wait-activity.md)を使用し、[時間ベースの条件](conditions.md)を追加してタイミングを制御します。

>[!ENDSHADEBOX]

## ジャーニーの出口基準の設定方法 {#configure-exit}

>[!BEGINSHADEBOX]

**出口条件について知っておくべきことを、ここで説明します。**

* **[ジャーニー完了](end-journey.md)**: プロファイルは、ジャーニーの最後のステップに到達すると自動的に終了します。 **[!UICONTROL 終了]** アクティビティで終了するジャーニーパスをデザインします。

* **[成功指標の達成](journey-properties.md#exit-criteria)**：成功指標（購入やサブスクリプションなど）を定義し、完了時にプロファイルを終了します。 **[!UICONTROL 離脱条件を表示]** アイコンをクリックし、**[!UICONTROL 離脱条件を追加]**&#x200B;を選択し、離脱トリガーとして[&#x200B; イベント &#x200B;](../event/about-events.md)または[&#x200B; オーディエンス &#x200B;](../audience/about-audiences.md)を選択します。

* **[非アクティビティタイムアウト](wait-activity.md)**：設定された時間枠内にエンゲージメントが発生しない場合は、プロファイルを終了します。 最後のエンゲージメント日を確認するオーディエンスで[終了条件](journey-properties.md#exit-criteria)を使用し、定義された期間で[&#x200B; アクティビティ &#x200B;](wait-activity.md)を設定し、[条件](conditions.md)を使用してアクティビティを確認します。

* **[再入力ルール](entry-management.md)**: キャンペーン戦略に応じて、プロファイルがジャーニーに複数回または1回だけ再入力できるかどうかを決定します。 ジャーニー&#x200B;**[!UICONTROL プロパティ]**&#x200B;で&#x200B;**[!UICONTROL 再エントリ]**&#x200B;設定を構成して、待機期間を設定するか、強制的な再エントリを有効にするか、コンテキスト固有の再エントリに[補足識別子](supplemental-identifier.md)を使用します。

>[!ENDSHADEBOX]

## 詳細なジャーニー例 {#journey-examples}

完全な技術的詳細を含むステップバイステップの実装ガイダンスについては、次の文書化されたユースケースを検討してください。

* **[顧客オンボーディングジャーニー](https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/use-cases/customer-onboarding)** - オーディエンスの選定、イベントのタイムアウト、目標ベースの終了を使用して、パーソナライズされたウェルカムエクスペリエンスを構築します

* **[カート放棄の回復](https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/use-cases/abandoned-cart)** - イベントをトリガーにしたジャーニー、プレイブック、チャネル ルーティングを使用して、失われたセールスを回復します

* **[リエンゲージメントキャンペーン &#x200B;](https://experienceleague.adobe.com/en/docs/experience-platform/rtcdp/use-cases/personalization-insights-engagement/use-cases-luma)** – 行動ターゲティングと有料メディアのアクティベーションにより、非アクティブな顧客を取り戻します

* **[購読者にメッセージを送信](message-to-subscribers-uc.md)** – 購読オーディエンスとパーソナライズされたコンテンツで購読リストをターゲットにする

* **[マルチチャネルメッセージを送信](journeys-uc.md)** – 電子メールとプッシュを反応イベントとマルチパスロジックと組み合わせる

* **[平日のみメールを送信](weekday-email-uc.md)** – 時間ベースの条件と待機式を使用してコミュニケーションをスケジュールします

>[!TIP]
>
>その他のパターンと実装については、[ジャーニーユースケースライブラリ &#x200B;](jo-use-cases.md)で使用可能なすべてのユースケースを参照してください。 例としては、[配信の強化](ramp-up-deliveries-uc.md)、[&#x200B; エクスペリエンスイベントパターン &#x200B;](exp-event-lookup.md)、[&#x200B; ライブジャーニーからのプロファイルの削除](journey-pause.md#apply-an-exit-criteria-in-a-paused-journey)などが挙げられます。

## 入口と出口の管理に関するベストプラクティス {#best-practices}

**明確な定義**

明確なドキュメントと命名規則を確立することで、プロファイルがジャーニーをどのように移動するのかをチームが理解できるようになります。

* ジャーニーを構築する前に、入口と出口のロジックを文書化し、マーケティング部門と分析部門の連携を図ります
* 入口ポイント、ジャーニーパス、出口条件を示すフローチャートを作成します
* ビジネスルールを明確に定義する：「Xが発生したとき、またはY日後にプロファイルが離脱する」
* 記述的なラベルを使用する：「終了 – 購入完了」ではなく「終了1」
* レポートとフィルタリング用に一貫して[&#x200B; ジャーニー](../start/search-filter-categorize.md#tags)をタグ付け

**重複するジャーニーを避ける**

キャンペーンをまたいでジャーニー戦略を連携することで、顧客の混乱やメッセージの競合を防ぐことができます。

* 競合を防ぐために、類似のジャーニーを起動する前に[&#x200B; アクティブなジャーニー](journey-ui.md)を監査します
* [競合管理](../conflict-prioritization/conflicts.md)および[優先度スコア &#x200B;](../conflict-prioritization/priority-scores.md)を活用して、重複を解決し、ジャーニーの優先順位を決定します
* 互いに競争するのではなく、補完し合うジャーニーをデザインします

>[!NOTE]
>
>より優先度の高いジャーニーに適格な場合にプロファイルを自動的に削除するような高度なシナリオの場合は、出口条件の代わりに[&#x200B; ジャーニーの上限設定と調停](../conflict-prioritization/journey-capping.md)を使用します。

**監視と最適化**

ジャーニーのパフォーマンスを継続的に評価し、実際の顧客の行動にもとづいて入出口基準を調整します。

* [&#x200B; ジャーニーレポート &#x200B;](../reports/journey-global-report-cja.md)を使用して、各ジャーニーの開封率、離脱率、完了率を追跡します
* [成功指標](success-metrics.md)の監視：成功指標の完了率とタイムアウト率の比較
* [開始する前に、様々なプロファイルシナリオを使用して入出口基準](testing-the-journey.md)をテストします
* データに基づく調整：高い早期離脱の場合は、エントリ基準の関連性を確認します。成功指標の完了率が低い場合は、コンテンツとタイミングを分析します
* すべてのアクティブなジャーニーを四半期ごとに確認する

**使用頻度の上限を尊重**

あらゆるジャーニーのコミュニケーションをまたいでメッセージ頻度を制御することで、顧客の信頼とエンゲージメントを維持します。

* 適切な[再エントリ待機期間](entry-management.md)を設定するか、1回限りのジャーニーの再エントリを無効にします
* [頻度の上限ルール &#x200B;](../conflict-prioritization/rule-sets.md)を使用して、通信が過剰になるのを防ぎます
* コンプライアンスを確保するために、レポートで頻度の指標を監視する

>[!NOTE]
>
>複数のジャーニーをまたいで頻度制限とジャーニー入力上限を管理するには、[&#x200B; ジャーニーの上限と調停](../conflict-prioritization/journey-capping.md)および[&#x200B; チャネルごとの頻度上限](../conflict-prioritization/channel-capping.md)を使用します。

## まとめ {#conclusion}

ジャーニーの出入り基準は、[!DNL Adobe Journey Optimizer]でパーソナライズされた、タイムリーで効果的な顧客体験を提供するための基盤となります。 これらの条件を注意深く作成することで、マーケターはエンゲージメントを高め、摩擦を減らし、より強固な顧客関係を構築することができます。

まず、顧客のトリガーと離脱ポイントを明確にマッピングし、徹底的にテストをおこない、結果を監視することで、ジャーニーオーケストレーションを継続的に改善しましょう。

## 関連リソース {#related-resources}

**技術ドキュメント**

[Profile entrance management](entry-management.md) | [ジャーニープロパティと終了条件](journey-properties.md) | [&#x200B; ジャーニーの終了方法](end-journey.md) | [補足識別子](supplemental-identifier.md) | [ジャーニーデザイナー](using-the-journey-designer.md)

**チュートリアルと例**

[ジャーニーユースケース &#x200B;](jo-use-cases.md) | [お客様のオンボーディングビデオ &#x200B;](https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/use-cases/customer-onboarding) | [&#x200B; カート放棄ビデオ &#x200B;](https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/use-cases/abandoned-cart) | [&#x200B; コミュニティブログ：入口と出口の条件](https://experienceleaguecommunities.adobe.com/t5/journey-optimizer-blogs/mastering-journey-entry-and-exit-criteria-in-adobe-journey/ba-p/760958)

**関連する機能**

[&#x200B; オーディエンスの選定イベント &#x200B;](audience-qualification-events.md) | [成功指標と目標](success-metrics.md) | [競合管理](../conflict-prioritization/conflicts.md) | [頻度の上限設定](../conflict-prioritization/rule-sets.md) | [&#x200B; ジャーニー](testing-the-journey.md) | [&#x200B; アクティビティの最適化](optimize.md) | [反応イベント &#x200B;](reaction-events.md) | [&#x200B; アクティビティの待機](wait-activity.md)
