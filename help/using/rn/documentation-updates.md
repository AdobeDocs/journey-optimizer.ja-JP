---
solution: Journey Optimizer
product: journey optimizer
title: ドキュメントの更新
description: 最新のドキュメントの更新について学ぶ
feature: Release Notes
topic: Content Management
role: User
level: Beginner, Intermediate
exl-id: 83c8f206-bce3-4cc8-94a3-575ec1d999bc
source-git-commit: d95bd86a731e7d410ca40986ca792956f4e4c596
workflow-type: tm+mt
source-wordcount: '4010'
ht-degree: 93%

---

# ドキュメントの更新 {#latest-updates}

このページでは、[!DNL Journey Optimizer] のドキュメントの更新すべてを一覧で表示します。

## 2023年10月 {#oct-2023}

* に含まれるすべての新機能と改善点 [!DNL Journey Optimizer] 2023 年 10 月リリースの詳細はドキュメントに記載されています。 [詳細情報](release-notes.md)
* 次のような主な機能を説明するGIFを追加しました。 [コンテンツテンプレート](../content-management/content-templates.md), [フラグメント](../content-management/fragments.md), [計算済み属性](../audience/computed-attributes.md), [ダイレクトメール](../direct-mail/get-started-direct-mail.md), [タグ](../start/search-filter-categorize.md#tags), [決定管理の最適化モデル](../offers/ranking/personalized-optimization-model.md), [API トリガーキャンペーン](../campaigns/api-triggered-campaigns.md)、および [コンテンツ実験](../campaigns/content-experiment.md).
* スキーマの作成プロセスが更新され、Adobe Experience Platformの変更に伴うユーザーインターフェイスの最新の更新が反映されました。 [詳細情報](../audience/creating-test-profiles.md)
* 決定管理ガードレールが、ガードレールと制限ページに追加されました。 [詳細情報](../start/guardrails.md#decision-management)
* ヘッダーパラメーターの節が更新され、不在通知とチャレンジ応答の処理方法 ( **[!UICONTROL エラーメール]**) をクリックします。 [詳細情報](../email/email-settings.md#email-header)
* コンテンツのプレビューおよびテスト方法に関する新しい節が作成されました。 [詳細情報](../content-management/preview-test.md)
* 単一ページアプリケーションの実装ページは、 Experience Platform Web SDK のドキュメントにAdobeされました。 [詳細情報](https://experienceleague.adobe.com/docs/experience-platform/edge/personalization/ajo/web-spa-implementation.html){target="_blank"}
* 「キャッピング」の節が更新され、決定管理インターフェイスでのオファーキャッピングに関するラベルの変更が反映されました。 [詳細情報](../offers/offer-library/add-constraints.md#capping)
* E メールへの動的コンテンツの追加の節が更新され、バリアントの削除方法の詳細が追加されました。 [詳細情報](../personalization/dynamic-content.md#emails)
* キャッピングとスロットルの設定の例が更新されました。 [詳細情報](../configuration/external-systems.md)
* スカラー配列に関する制限は、外部データソースの節から削除されました。 [詳細情報](../datasource/external-data-sources.md)
* マルチチャネルジャーニーの使用例が更新されました。 [詳細情報](../building-journeys/journeys-uc.md)
* Journey Optimizerのドキュメントセットが更新され、新しいExperience Platformスキーマ作成プロセスが反映されました。

## 2023年9月 {#september-2023}

* [!DNL Journey Optimizer] の 2023年9月リリースに含まれているすべての新機能と機能強化については、ドキュメントで詳しく説明されています。[詳細情報](release-notes.md)
* スケーリングのベストプラクティスと、リアルタイムのステッチに関するガイダンスを含む新しいページが追加されました。[詳細情報](../start/best-practices.md)

  <!--  * The maximum wait duration has been changed from 30 to 29 days. [Read more](../building-journeys/wait-management.md) -->

* 送信時間の最適化に関する「よくある質問」の節が追加されました。[詳細情報](../building-journeys/journeys-message.md#faq-send-time)
* オーディエンスの選定アクティビティに関するメモが追加されました。アクティブになり、オーディエンスをエントリまたは離脱するプロファイルをリッスンするまでに最大 10 分かかる場合があります。[詳細情報](../building-journeys/audience-qualification-events.md#important-notes-segment-qualification)
* 決定ルールを作成する際に考慮すべき制限のリストを決定管理ドキュメントに追加しました。[詳細情報](../offers/offer-library/creating-decision-rules.md)
* アクセス制御に関するドキュメントへのリンクが更新されました。[詳細情報](../administration/permissions.md)
* アプリ内チャネルの前提条件が更新され、Adobe Experience Platform のデータ収集の詳細が追加されました。[詳細情報](../in-app/inapp-configuration.md)
* ランキング式の例で示されている式の一部が、検証エラーを回避するために更新されました。[詳細情報](../offers/ranking/create-ranking-formulas.md#ranking-formula-examples)
* 「判定範囲の定義」セクションに警告が追加され、AI モデルが評価条件グループで使用される場合、そのグループ内のすべての評価条件が同じ特定の AI モデルを持つ AI ランキングメソッドを使用する必要があることを指定できるようになりました。 また、AI モデルを使用できる評価基準グループは 1 つだけです。 [詳細情報](../offers/offer-activities/create-offer-activities.md#add-decision-scopes)

## 2023年8月 {#august-2023}

*  [!DNL Journey Optimizer] の 8月23日（PT）リリースに含まれているすべての新機能と機能強化については、ドキュメントに詳しく記載されています。[詳細情報](release-notes.md)
* ジャーニーの&#x200B;**認証キャッシュ管理**&#x200B;に関するメモを更新し、トークンは異なるジャーニー間で共有されないことを説明しました。[詳細情報](../datasource/external-data-sources.md#custom-authentication-mode)
* 動作を明確にするために、ジャーニーに関する&#x200B;**エントリ管理**&#x200B;ページを更新しました。[詳細情報](../building-journeys/entry-management.md)
* Offer Decisioning の&#x200B;**データセットを書き出し**&#x200B;が、デフォルトで有効になりました。以前の動作に関するメモを削除しました。[詳細情報](../offers/export-catalog/get-started-export.md)
* 様々な&#x200B;**キャンペーンレポート指標**&#x200B;の名前を、ライブレポートとグローバルレポートの両方で変更しました。[詳細情報](../reports/campaign-global-report.md)
* Web チャネルのコンテンツ実験の前提条件に関する新しい節を追加しました。[詳細情報](../web/web-prerequisites.md#experiment-prerequisites)
* メールコンテンツテンプレートのテスト時に現在追跡がサポートされていないことを示す警告を、**コンテンツテンプレートの操作**&#x200B;ページに追加しました。追跡をテストするには、メールでコンテンツテンプレートを使用し、配達確認を送信する必要があります。[詳細情報](../content-management/content-templates.md#test-template)
* 公開済みのページであっても、ページの作成時に定義した URL を web ブラウザーにコピー＆ペーストするだけでランディングページにアクセスすることはできないことを指定する、いくつかの警告を&#x200B;**ランディングページの作成と公開**&#x200B;の節に追加しました。代わりに、プレビュー機能を使用してテストできます。[詳細情報](../landing-pages/create-lp.md)
* ダイレクトメールチャネルで&#x200B;**同意を管理**&#x200B;する方法についての新しい節を追加しました。[詳細情報](../direct-mail/test-send-direct-mail.md)

## 2023年7月 {#july-2023}

* [!DNL Journey Optimizer] の 7月23日（PT）リリースに含まれているすべての新機能と機能強化について、ドキュメントで詳しく説明しました。[詳細情報](release-notes.md)
* 待機アクティビティのドキュメントページを改善し、グローバルタイムアウトと再エントリの使用に関連する追加情報とベストプラクティスを追加しました。[詳細情報](../building-journeys/wait-activity.md)
* エントリ管理に関するページを改善しました。[詳細情報](../building-journeys/entry-management.md)
* 「オーディエンスを読み取り」アクティビティのドキュメントに、スロットルレートに関する情報を追加しました。[詳細情報](../building-journeys/read-audience.md)
* 再試行に関する追加情報が追加されました。[詳細情報](../start/guardrails.md#general-actions-g)
* **パーソナライゼーションの同意の実装**&#x200B;の節を更新し、キャンペーンでパーソナライゼーションの同意を手動で実施する方法を説明しています。セグメントルールビルダーを使用すると、オプトアウトプロファイルを含んだオーディエンスを作成したり、分割アクティビティをコンポジションワークフローに追加したりできます。[詳細情報](../privacy/opt-out.md#opt-out-expression-editor)

## 2023年6月 {#june-2023}

* [!DNL Journey Optimizer] の 2023年6月リリースに含まれているすべての新機能と機能強化について、ドキュメントで詳しく説明しました。[詳細情報](release-notes.md)
* ジャーニーの概要画面に破棄率に関する情報が追加されました。[詳細情報](../building-journeys/journey-gs.md#journey-access)
* イベントの作成後に新しい列挙値でスキーマを変更する場合に従う手順を記載したメモが追加されました。[詳細情報](../event/about-creating.md)
* ジャーニーのクエリ時に journeyVersionName の代わりに journeyVersionID を使用するというレコメンデーションが追加されました。[詳細情報](../reports/sharing-common-fields.md#journeyversionid-field)
* 複数の条件と複数の決定範囲が使用されるケースの例を示すために、評価条件の順序に関する例を&#x200B;**決定の作成**&#x200B;の節に追加しました。[詳細情報](../offers/offer-activities/create-offer-activities.md#evaluation-criteria-order)
* 意思決定管理のドキュメントを明確にするために、動的コレクションではオブジェクトレベルのアクセス制御を使用できないことを明示するメモを追加しました。[詳細情報](../offers/offer-library/creating-collections.md)

## 2023年5月 {#may-2023}

* [!DNL Journey Optimizer] の 2023年5月リリースに含まれているすべての新機能と機能強化について、ドキュメントで詳しく説明しました。[詳細情報](release-notes.md)
* Web エクスペリエンスで Adobe Experience Manager Assets Essentials からのコンテンツの公開に使用するサブドメインの設定方法を説明する新しいページが追加されました。[詳細情報](../web/web-delegated-subdomains.md)
* E メールデザイナーで URL にパーソナライズされたトラッキングパラメーターを追加する方法を説明する新しい節が追加されました。[詳細情報](../email/message-tracking.md#url-tracking)
* パーソナライゼーションに使用するプロファイルデータをオプトアウトする顧客の選択を確実に行う方法を説明する新しい節が追加されました。[詳細情報](../privacy/opt-out.md#opt-out-personalization)
* メールコンテンツに含まれる URL での特殊な国際文字の使用に関するメモが追加されました。[詳細情報](../email/message-tracking.md#insert-links)
* ランディングページのテストと公開に必要な権限が追加されました。[詳細情報](../landing-pages/create-lp.md)
* カスタムイベントを意思決定管理のフリークエンシーキャップで考慮するために必要な Adobe Experience Platform エンドポイントに関するメモが追加されました。[詳細情報](../offers/data-collection/schema-requirement.md#track-custom-events)

## 2023年4月 {#apr-2023}

* [!DNL Journey Optimizer] の 2023年4月リリースに含まれているすべての新機能と機能強化について、このドキュメントで詳しく説明しています。[詳細情報](release-notes.md)
* 組み込みのアクションを削除できないことを示すメモが追加されました。[詳細情報](../start/guardrails.md#custom-actions-g)
* serviceEvents に関する情報と、serviceEvent の詳細を確認するクエリの例が追加されました。[詳細情報](../reports/query-examples.md#common-queries)
* 時系列に対してクエリを実行できないことを示すメモが追加されました。[詳細情報](../building-journeys/condition-activity.md)
* Adobe Experience Manager Assets Essentials と Adobe Stock をマルチソリューション統合ページに追加しました。[詳細情報](../start/ajo-integrations.md)
* 複数レベルのメールサブドメインがサポートされるようになったので、許可されていないという警告を削除しました。[詳細情報](../configuration/delegate-subdomain.md)
* ジャーニーのメッセージで使用されるオファーの決定に変更が加えられた場合は、ジャーニーを非公開にして、再公開する必要があることを示すメモを追加しました。[詳細情報](../building-journeys/publishing-the-journey.md)
* キャッピングカウンターでイベントが正しく考慮されていることを確認する方法は、意思決定管理&#x200B;**キャッピングイベント**&#x200B;の節で明確に説明されています。[詳細情報](../offers/offer-library/add-constraints.md#capping-event)
* **実行アドレスの変更**&#x200B;ページに新しい節が追加されました。ジャーニーの高度なパラメーターで、グローバルに設定された実行フィールドを上書きできるように指定しますが、メールアドレスの上書きは特定の使用例にのみ使用する必要があります。 ほとんどの場合、**実行フィールド**&#x200B;でプライマリアドレスとして定義されている値を使用する必要があります。[詳細情報](../configuration/primary-email-addresses.md#journey-parameters)
* **URL トラッキング**&#x200B;の節に、メールチャネルサーフェスでの URL トラッキング用に設定できるすべてのコンテキスト属性のリストと説明が表示されるようになりました。 [詳細情報](../email/email-settings.md#url-tracking)

## 2023年3月 {#march-2023}

* Journey Optimizer スキーマ辞書が利用可能になりました。各スキーマのフィールドと属性の完全なリストが表示されます。[詳細情報](https://experienceleague.adobe.com/tools/ajo-schemas/schema-dictionary.html?lang=ja)
* [!DNL Journey Optimizer] の 2023年3月リリースに含まれているすべての新機能と機能強化については、ドキュメントで詳しく説明しています。[詳細情報](release-notes.md)
* ジャーニーで Adobe Analytics イベントを有効にする手順を追加しました。[詳細情報](../event/about-analytics.md)
* Adobe Experience Platform でオファー決定支援フィードバックを収集する方法（表示されるオファーやユーザーの操作方法など）に関する新しい節が、意思決定管理ガイドに作成されました。 [詳細情報](../offers/data-collection/data-collection.md)
* **決定の作成**&#x200B;の節に、条件を順番に評価する場合と同時に評価する場合の違いを説明する新しいサブセクションが追加されました。[詳細情報](../offers/offer-activities/create-offer-activities.md#evaluation-criteria-order)
* 増分読み取りを使用した「オーディエンスを読み取り」ジャーニー用のガードレールが追加されました。新しいバージョンを作成することはできません。ジャーニーを複製する必要があります。[詳細情報](../start/guardrails.md#journey-versions-g)
* スループットを制限する方法に関するユースケースが、スロットル機能に関する情報で更新されました。[詳細情報](../building-journeys/limit-throughput.md)
* 応答ペイロード定義では、スカラー配列がサポートされていないことを指定するメモが追加されました。[詳細情報](../datasource/external-data-sources.md)
* プロファイルキャップの条件に関する節が更新されました。[詳細情報](../building-journeys/condition-activity.md#profile_cap)

## 2023年2月 {#feb-2023}

* [!DNL Journey Optimizer] の 2023年2月リリースに含まれているすべての新機能と機能強化について、ドキュメントで詳しく説明しました。[詳細情報](release-notes.md)
* キャンバスツールバーに関する情報が追加されました。[詳細情報](../building-journeys/using-the-journey-designer.md#gs-journey-design)
* URL および API では、内部 Adobe アドレスが許可されていないことを示す情報が追加されました。[詳細情報](../start/guardrails.md)
* API トリガーキャンペーンのドキュメントに、リクエストに渡すコンテキスト属性が 50 KB を超えることはできない旨を示す注記が追加されました。[詳細情報](../campaigns/api-triggered-campaigns.md#contextual)
* 受信者がランディングページで登録解除した後、オプトアウト情報を&#x200B;**同意サービスデータセット**&#x200B;に保存する方法に関する情報を追加しました。[詳細情報](../landing-pages/lp-use-cases.md#configure-opt-out)

## 2023年1月 {#jan-2023}

* [!DNL Journey Optimizer] の 2023年1月リリースに含まれているすべての新機能と機能強化について、ドキュメントで詳しく説明しました。[詳細情報](release-notes.md)
* キャッピングのドキュメントに、カスタム認証エンドポイントに関する情報が追加されました。[詳細情報](../configuration/external-systems.md)
* 新しいカスタム認証の例が外部データソースの節に追加されました。[詳細情報](../datasource/external-data-sources.md#custom-authentication-mode)
* イベントトリガージャーニーのデータ収集コアサービス（DCCS）に関するメモが追加されました。[詳細情報](../start/guardrails.md#events-g)
* ID 名前空間の取得に関するメモが、「[オーディエンスを読み取り](../building-journeys/read-audience.md)」、「[オーディエンスの選定](../building-journeys/audience-qualification-events.md)」、「[イベントの作成](../event/about-creating.md)」の節に追加されました。
* [!DNL Journey Optimizer] のアクセシビリティ機能を専用ページにグループ化しました。[詳細情報](../start/accessibility.md)
* 高度な式エディターのドキュメントの「演算子」の節で例が更新されました。[詳細情報](../building-journeys/expression/operators.md)
* オブジェクトの配列を使用したルックアップの制限に関するメモが追加されました。[詳細情報](../event/experience-event-schema.md#relationships_limitations)
* [!DNL Journey Optimizer] のデータ管理に関する新しいページを追加しました。[詳細情報](../data/gs-data.md)
* Decisioning API を使用してオファーを配信する際に、応答で返される可能性のあるすべてのコードをリストした表を追加しました。 [詳細情報](../offers/api-reference/offer-delivery-api/decisioning-api.md)

+++ 2022

## 2022年12月 {#december-2022}

* メッセージガイドは再編成され、次のチャネルごとの専用ガイドに分割されました。

   * [メールチャネル](../email/get-started-email.md)
   * [プッシュ通知チャネル](../push/get-started-push.md)
   * [SMS チャネル](../sms/get-started-sms.md)

* 設定ガイドが再編成され、読みやすくなりました。 [詳細情報](../configuration/get-started-configuration.md)

## 2022年11月 {#november-2022}

* Journey Optimizer の統合に関する新しいページを追加しました。[詳細情報](../start/ajo-integrations.md)
* ミラーページの URL の長さに関するレコメンデーションを追加しました。[詳細情報](../email/message-tracking.md)
* 適切な返信管理を確保するためのレコメンデーションを含む、メール設定の新しい節をメールアドレスへの返信に追加しました。[詳細情報](../email/email-settings.md#reply-to-email)
* ライブジャーニーでメッセージのコンテンツを変更する方法に関する節を追加しました。[詳細情報](../building-journeys/journeys-message.md#update-live-content)

## 2022年10月 {#october-2022}

* 外部データソースとカスタムアクションを使用してスループットを制限する方法に関するジャーニーのユースケースを追加しました。[詳細情報](../building-journeys/limit-throughput.md)
* ジャーニーのユースケースの節では、[ビジネスユースケース](../building-journeys/journeys-uc.md)と[テクニカルユースケース](../building-journeys/collections.md) の 2 つのカテゴリに再編成しました。
* **エンティティデータセット**&#x200B;の節を更新し、詳細を追加しました。[詳細情報](../data/datasets-query-examples.md#entity-dataset)
* オプトアウト管理および同意ポリシーの節の構成を変更しました。[詳細情報](../privacy/opt-out.md)
* ジャーニーメッセージの詳細設定パラメーターに関する節が明確になり、メールアドレスの上書きは特定のユースケースにのみ使用する必要があることを指定しました。ほとんどの場合、**実行フィールド**&#x200B;でプライマリアドレスとして定義されている値を使用してください。
* **ランディングページのサブドメインの設定**&#x200B;の節に、ランディングページのサブドメインでは大文字を使用できないことを示すメモを追加しました。[詳細情報](../landing-pages/lp-subdomains.md)

## 2022年9月 {#september-2022}

* [!DNL Journey Optimizer] の 2022年9月リリースに含まれているすべての新機能と機能強化について、ドキュメントで詳しく説明しました。[詳細情報](release-notes.md)
* 繰り返しの「オーディエンスを読み取り」ジャーニーでの待機アクティビティの使用に関するベストプラクティスを追加しました。[詳細情報](../building-journeys/read-audience.md#configuring-segment-trigger-activity)
* 新しい手順のイベントクエリの例と、ID、instanceid、profileid の違いに関する情報を追加しました。[詳細情報](../reports/query-examples.md)。
* [toDateOnly](../building-journeys/functions/functiontodateonly.md) および [toString](../building-journeys/functions/functiontostring.md) 関数に関するページを更新しました。
* 時間条件パラメーターの詳細を追加しました。[詳細情報](../building-journeys/condition-activity.md#time_condition)
* 組み込みデータセットに関する情報を追加しました。[詳細情報](../data/get-started-datasets.md#access-datasets)
* グローバルレポートとライブレポートの節を改善し、構成を変更しました。[詳細情報](../reports/global-report.md)
* Adobe Journey Optimizer で使用できるすべてのレポート指標のリストを追加しました。
  [詳細情報](../reports/global-report.md#email-and-sms-metrics)
* BCC メールの節を新しいアーカイブのサポートページに移動しました。[詳細情報](../configuration/archiving-support.md)

## 2022年8月 {#august-2022}

*  [!DNL Journey Optimizer] の 8月22日（PT）リリースに含まれているすべての新機能と機能強化については、ドキュメントに詳しく記載されています。[詳細情報](release-notes.md)
* 頻度ルールのセクションが更新され、新しいインラインメッセージフローが反映されました。[詳細情報](../configuration/frequency-rules.md#apply-frequency-rule)
* サブスクリプションの設定とランディングページの作成方法を示すビデオが、ランディングページの概要のセクションで参照できるようになりました。[詳細情報](../landing-pages/get-started-lp.md#video)
* 「オーディエンスを読み取り」アクティビティを使用するジャーニーの制限事項が追加されました。[詳細情報](../building-journeys/read-audience.md)
* 式エディターの演算子ページが改善されました。[詳細情報](../building-journeys/expression/operators.md)
* キャンペーンのスケジュール方法に関する節が追加されました。[詳細情報](../campaigns/create-campaign.md)
* 式エディターの一般的な構文ルールに関する節が更新され、リテラル関数でのバックスラッシュ記号のエスケープに関する新しいルールが考慮されるようになりました。 既存の公開済みメッセージは、この変更による影響を受けません。 更新する必要があるのは、新規メッセージまたはドラフトメッセージのみです。 [詳細情報](../personalization/personalization-syntax.md#general-rules)

## 2022年7月 {#july-2022}

* [!DNL Journey Optimizer] の 7月22日（PT）リリースに含まれているすべての新機能と機能強化について、ドキュメントで詳しく説明しました。[詳細情報](release-notes.md)
* **チャネルサーフェスの設定**&#x200B;の節が更新され、より明確になり、SMS チャネルの設定方法を説明するページへのリンクが追加されました。[詳細情報](../configuration/channel-surfaces.md#create-channel-surface)
* ジャーニーのプロパティの「**プロファイルのタイムゾーン**」オプションが、デフォルトで無効になりました。 [詳細情報](../building-journeys/timezone-management.md#timezone-from-profiles)
* **待機**&#x200B;アクティビティで、「**固定日付**」オプションは使用できなくなりました。 [詳細情報](../building-journeys/wait-activity.md)
* **オーディエンスを読み取り**&#x200B;アクティビティに「**増分読み取り**」オプションに関する詳細情報を追加しました。[詳細情報](../building-journeys/read-audience.md#configuring-segment-trigger-activity)
* **プロファイルキャップ**&#x200B;条件タイプに関するレコメンデーションを追加しました。[詳細情報](../building-journeys/condition-activity.md#profile_cap)
* ビジネスイベントに関する制限事項を追加しました。 [詳細情報](../start/guardrails.md#events-g)

## 2022年6月 {#june-2022}

* [!DNL Journey Optimizer] の 2022年6月リリースに含まれているすべての新機能と機能強化について、ドキュメントで詳しく説明しました。[詳細情報](release-notes.md)
* プライバシーリクエストに関する新しい節がドキュメントに追加されました。[詳細情報](../privacy/requests.md)
* リソースの監査ログに関する新しい節がドキュメントに追加されました。[詳細情報](../privacy/audit-logs.md)
* Adobe Experience Cloud アセットライブラリからオファー表示域に HTML または JSON コンテンツを追加する方法に関する新しい節がドキュメントに追加されました。[詳細情報](../offers/offer-library/add-representations.md#html-json)
* ジャーニーのライフサイクルに新しいページを追加しました。[詳細情報](../building-journeys/journey.md#journey-versions)
* 待機アクティビティページを更新しました。[詳細情報](../building-journeys/wait-activity.md)
* Adobe Journey Optimizer データセットのリストとクエリ例を追加しました。[詳細情報](../data/datasets-query-examples.md)
* 許可リストページが「設定」セクションに移動しました。[詳細情報](../configuration/allow-list.md)
* 抑制リストページが更新され、ASCII コードが 32～126 のすべての ASCII 文字が抑制フィールドの理由で使用できることなど、一部の情報が明確になりました。[詳細情報](../configuration/manage-suppression-list.md)
* 意思決定管理のガードレールおよび静的制限へのリンクが追加されました。[詳細情報](../start/guardrails.md)
* すべてのお客様が送信時間の最適化を利用できるようになりました。ベータ版のメンションは削除されました。[詳細情報](../building-journeys/journeys-message.md#send-time-optimization)
* パーソナライズされたオファーを配信するために、Batch Decisioning API が使用可能な API のリストに追加されました。 [詳細情報](../offers/api-reference/offer-delivery-api/start-offer-delivery-apis.md)

## 2022年5月 {#may-2022}

* [!DNL Journey Optimizer] の 2022年5月リリースに含まれているすべての新機能と機能強化について、ドキュメントで詳しく説明しました。[詳細情報](release-notes.md)
* [オーディエンスの選定](../reports/query-examples.md#segment-qualification-queries)および[イベント](../reports/query-examples.md#event-based-queries)に関連するクエリの新しい例が追加されました。
* メールデザインの節で、コンテンツの開始に使用できる新しい組み込みテンプレートに関する記述が追加されました。関連するスクリーンショットを更新しました。[詳細情報](../email/get-started-email-design.md)
* 主要リソースへのリンクが、Journey Optimizer ドキュメントのホームページで更新されました。
* ランディングページおよび購読レポートのスクリーンショットが更新されました。[詳細情報](../reports/live-report.md)
* Delete メソッドがカスタムアクションでサポートされていないことを示す注記を追加しました。[詳細情報](../action/about-custom-action-configuration.md)
* チュートリアルビデオへのリンクが更新されました。
* [メール設定](../configuration/about-subdomain-delegation.md)、[メッセージプリセット](../configuration/channel-surfaces.md)および[ランディングページの設定](../landing-pages/lp-subdomains.md)の節が再編成され、読みやすくなりました。
* URL トラッキングの節が更新および改訂され、例が追加されました。[詳細情報](../email/email-settings.md#url-tracking)
* 転送メールアドレスの設定に関する新しい節が追加されました。ユーザーインターフェイスでは実行できません。[詳細情報](../email/email-settings.md#forward-email)

## 2022年4月 {#april-2022}

* [!DNL Journey Optimizer] の 2022年4月リリースに含まれているすべての新機能と機能強化について、このドキュメントで詳しく説明しました。[詳細情報](release-notes.md)
* **反応**&#x200B;イベントのドキュメントページが更新されました。[詳細情報](../building-journeys/reaction-events.md)
* 意思決定管理機能に関するビデオが更新され、Journey Optimizer のユーザーインターフェイスが反映されました。[詳細情報](../offers/get-started/starting-offer-decisioning.md)
* **データセットの基本を学ぶ**&#x200B;の節が改善され、データセットへのアクセスおよび作成方法の詳細が追加されました。[詳細情報](../data/get-started-datasets.md)
* ヘルプガイドおよび製品リリースノートへのリンクが **Adobe Journey Optimizer ドキュメント**&#x200B;のホームページに追加されました。[詳細情報](https://experienceleague.adobe.com/docs/journey-optimizer.html?lang=ja)
* **メッセージプリセットの作成**&#x200B;の節で、選択した IP プールが編集中（**[!UICONTROL 処理中]**&#x200B;ステータス）で選択したサブドメインに関連付けられていないときは、プリセットの作成を続行できないことが明記されるようになりました。[詳細情報](../configuration/channel-surfaces.md#subdomains-and-ip-pools)
* 「メッセージプリセットの作成」の **URL トラッキング**&#x200B;の節が更新され、ユーザーインターフェイスの小さな変更が反映されました。[詳細情報](../configuration/channel-surfaces.md#url-tracking)

## 2022年3月 {#march-2022}

* [!DNL Journey Optimizer] の 2022年3月リリースに含まれているすべての新機能と機能強化については、ドキュメントで詳しく説明しています。[詳細情報](release-notes.md)
* [自動最適化モデル](../offers/ranking/auto-optimization-model.md)の詳細な説明、使用するアルゴリズム、技術的な詳細など、AI モデルの概要に関する新しいページが **Offer Decisioning** の節に追加されました。[詳細情報](../offers/ranking/ai-models.md)
* テストプロファイル作成ページは、**オーディエンス、プロファイル、ID**&#x200B;の節に移動しました。[詳細情報](../audience/creating-test-profiles.md)
* 式エディターで式をデフォルト値として追加する方法の例を追加しました。[詳細情報](../building-journeys/expression/field-references.md#default-value)
* **パーソナライズされたオファーの作成**&#x200B;の節が再編成され、読みやすくなりました。[詳細情報](../offers/offer-library/creating-personalized-offers.md)
* オファーの開始日や終了日の変更が、このオファーのフリークエンシーキャップに与える影響を説明する新しい節が追加されました。[詳細情報](../offers/offer-library/add-constraints.md#capping-change-date)
* **プライマリメールアドレスの変更**&#x200B;の節が更新され、ユーザーインターフェイスの変更が反映されました。[詳細情報](../configuration/primary-email-addresses.md)

## 2022年2月 {#feb-2022}

* [!DNL Journey Optimizer] の 2022年1月リリースに含まれているすべての新機能と機能強化について、ドキュメントで詳しく説明しました。[詳細情報](release-notes.md)
* この [replace](../building-journeys/functions/functionreplace.md#example_2) および [replaceAll](../building-journeys/functions/functionreplaceall.md#example) 関数のドキュメントページを更新し、ターゲットパラメーターに関する追加情報と例を追加しました。
* [演算子](../building-journeys/expression/operators.md#important-notes)ページにベストプラクティスが追加されました。

## 2022年1月 {#january-2022}

* [!DNL Journey Optimizer] の 2022年1月リリースに含まれているすべての新機能と機能強化について、ドキュメントで詳しく説明しました。[詳細情報](release-notes.md)
* **Offer Decisioning AI ランキング**&#x200B;の節が更新され、自動最適化モデルの詳細な説明が追加されました。[詳細情報](../offers/ranking/auto-optimization-model.md)
* AI モデルを使用する際にイベントタイプを送信できるようにするために必要な、スキーマ要件に関する新しい節が追加されました。[詳細情報](../offers/data-collection/schema-requirement.md)
* [!DNL Journey Optimizer] パーソナライズ機能に関連する節が再編成され、読みやすくなりました。[詳細情報](../personalization/personalize.md)
* この&#x200B;**メッセージプリセットの作成**&#x200B;の節は、わかりやすくするために複数のセクションに分かれています。[詳細情報](../configuration/channel-surfaces.md#create-channel-surface)
* この&#x200B;**オプトアウト管理**&#x200B;の節が明確になり、一部再編成されました。[詳細情報](../privacy/opt-out.md#opt-out-management)
* この&#x200B;**リンクを挿入**&#x200B;の節が更新され、最近のユーザーインターフェイスの変更が反映されました。[詳細情報](../email/message-tracking.md#insert-links)

+++

+++ 2021年

## 2021年11月 {#november-2021}

* ジャーニーで使用される&#x200B;**高度な式エディター**&#x200B;で、完全な説明が利用できるようになりました。[詳細情報](../building-journeys/expression/expressionadvanced.md)
* **CNAME サブドメインのデリゲーション方法**&#x200B;に関する新しい節が追加されました。[詳細情報](../configuration/delegate-subdomain.md#cname-subdomain-delegation)

## 2021年10月 {#october-2021}

* [!DNL Journey Optimizer] 10月21日リリースに含まれているすべての新機能と機能強化について詳しくは、ドキュメントを参照してください。[詳細情報](release-notes.md)
* **日時関数**&#x200B;の一覧を追加しました。[詳細情報](../personalization/functions/dates.md)
* **ユーザーペルソナごとの「基礎知識」節**&#x200B;を新しく用意しました。目標をより早く達成するには、自分に合ったパスを選んでください。[詳細情報](../start/quick-start.md)
* **メッセージプリセットの編集**&#x200B;の節を新しく用意しました。[詳細情報](../configuration/channel-surfaces.md#edit-channel-surface)
* **PTR レコードの編集**&#x200B;の節を新しく用意しました。[詳細情報](../configuration/ptr-records.md#edit-ptr-record)
* **メッセージプリセットの非アクティブ化**&#x200B;の節を新しく用意しました。[詳細情報](../configuration/channel-surfaces.md#edit-channel-surface#deactivate-a-surface)
* モバイル [!DNL Experience Edge] ワークフローでサポートされていないオファー制約に関する新しい制限事項が&#x200B;**意思決定管理 API 開発者ガイド**&#x200B;に追加されました。[詳細情報](../offers/api-reference/offers-api/personalized-offers/create.md#limitations)
* **シミュレーションの作成**&#x200B;の節を新しく用意しました。[詳細情報](../offers/offer-activities/simulation.md)
* **決定範囲の追加**&#x200B;の節を更新しました。[詳細情報](../offers/offer-activities/create-offer-activities.md#add-decision-scopes)
* カスタムテキストの定義とパーソナライズの方法に関する新しい[サブセクション](../offers/offer-library/creating-personalized-offers.md#custom-text)を追加するなど、**表示域のコンテンツの定義**&#x200B;の節を更新しました。[詳細情報](../offers/offer-library/creating-personalized-offers.md#content)

## 2021年9月 {#september-2021}

* [sethours](../building-journeys/functions/functionsethours.md)、[getListItem](../building-journeys/functions/functiongetlistitem.md)、[inSegment](../building-journeys/functions/functioninsegment.md) の各関数のページが更新されました。

* [filter](../building-journeys/functions/functionfilter.md)、[intersect](../building-journeys/functions/functionintersect.md)、[toDateOnly](../building-journeys/functions/functiontodateonly.md) の各関数が追加されました。

* dateOnly 日付タイプが式エディターのドキュメントに追加されました。[詳細情報](../building-journeys/expression/data-types.md)

* カスタムアクションのキャッシュ時間の詳細を追加しました。[詳細情報](../datasource/external-data-sources.md#custom-authentication-mode)

* カスタムアクションのデフォルトポートに関する情報を追加しました。[詳細情報](../action/about-custom-action-configuration.md#url-configuration)

* 複数のビジネスイベントユースケースに関する情報を追加しました。[詳細情報](../event/about-creating-business.md#multiple-business-events)

* データレイクのジャーニーステップイベントをクエリする一般的な例を追加しました。[詳細情報](../reports/query-examples.md)

* **制限**&#x200B;ページを新しく追加しました。[詳細情報](../start/guardrails.md)

* **クイックスタート**&#x200B;ページが改善され、様々なペルソナの手順が追加されました。[詳細情報](../start/quick-start.md)

* 該当する節で説明しているすべての意思決定管理機能が、Offer Decisioning アプリケーションサービスを利用する Adobe Experience Platform ユーザーにも当てはまるようになりました。[詳細情報](../offers/get-started/starting-offer-decisioning.md)

* 制約を適用して特定のプレースメントに対応するオファーの選択を制限する際に、オーディエンスを使用する場合と決定ルールを使用する場合の違いを明確にするための節を追加しました。[詳細情報](../offers/offer-activities/create-offer-activities.md#segments-vs-decision-rules)

* 現実的なユースケースを説明するために、ランキング式の具体的な例を追加しました。[詳細情報](../offers/ranking/create-ranking-formulas.md#ranking-formula-examples)

* IP プールの編集方法に関する節を追加しました。[詳細情報](../configuration/ip-pools.md#edit-ip-pool)

## 2021 年 8 月 {#august-2021}

*  [!DNL Journey Optimizer] の 8 月 21 日リリースに含まれているすべての新機能と機能強化について、ドキュメントで詳しく説明しました。[詳細情報](release-notes.md)
* 意思決定管理権限を更新しました。
[詳細情報](../administration/ootb-product-profiles.md)
* E メールデザイナーのスクリーンショットに最新の UI を反映しました。
* カスタムアクションの設定手順に動的 URL パスと動的ヘッダーを反映しました。[詳細情報](../action/about-custom-action-configuration.md#url-configuration)
* アクセシビリティ機能とショートカットに関する節を追加しました。[詳細情報](../start/user-interface.md#accessibility)
* オーディエンス評価方法に関する節を追加しました。[詳細情報](../audience/about-audiences.md#evaluation-method-in-journey-optimizer)
* 抑制リスト、許可リストおよびメールのグローバル／ライブレポートの各節にメモを追加し、「抑制」および「許可されていない」のステータスを持つプロファイルがメールレポートの「送信済み」指標から除外されることを明記しました。[詳細情報](../reports/global-report.md)
* 許可リストに登録されていなかったので送信から除外されたメールアドレスまたはドメインを取得する方法を説明する新しい節を追加しました。[詳細情報](../configuration/allow-list.md#reporting)
* 「許可リストの有効化」の節を更新しました。[詳細情報](../configuration/allow-list.md#enable-allow-list)
* 「メッセージプリセットの監視」の節を更新して、プリセット作成失敗の考えられる理由と、そうしたエラーの詳細を追加しました。[詳細情報](../configuration/channel-surfaces.md#monitor-channel-surfaces)
* メッセージプリセットのメール再試行設定を調整できるようになったことを反映するために、「再試行期間」の節を更新し、名前を変更しました。[詳細情報](../configuration/retries.md#retry-duration)
* ワンクリックオプトアウトリンクをメールコンテンツに挿入する方法を説明する新しい節を追加しました。[詳細情報](../privacy/opt-out.md#one-click-opt-out-link)
* 「サブドメインのデリゲート」の節を更新して、アドビで実行される検証プロセスについて詳しく説明しました。[詳細情報](../configuration/delegate-subdomain.md#subdomain-validation)
* 抑制リストにメールアドレスとドメインを手動で追加する方法に関する節を追加しました。[詳細情報](../configuration/manage-suppression-list.md#add-addresses-and-domains)
* [抑制リストへのアクセス](../configuration/manage-suppression-list.md#access-suppression-list)の節と[再試行](../configuration/retries.md)の節を更新して、新しいユーザーインターフェイスを反映しました。
* オファーの作成時に表示域を追加および設定するための新しいフローが、ドキュメントに追加されました。[詳細情報](../offers/offer-library/creating-personalized-offers.md#representations)

## 2021 年 7 月 {#july-2021}

* [!DNL Journey Optimizer] の 7 月 21 日リリースに含まれているすべての新機能と機能強化について、ドキュメントで詳しく説明しました。[詳細情報](release-notes.md)
* [!DNL Journey Optimizer] ホームページと目次に Experience Platform サービスのドキュメントへの直接リンクが追加されました
* Experience Platform サービスの新しいランディングページが [!DNL Journey Optimizer] で利用可能になりました 
* [!DNL Journey Optimizer] 製品説明へのリンクがホームページに追加されました
* 複数のページにチュートリアルビデオが追加されました
* ホームページの画像が最適化されました
* 「メッセージトラッキング」の節が移動し、改善され、タイトルが「リンクの追加とメッセージのトラッキング」に変更されました。[詳細情報](../email/message-tracking.md)
* ミラーページにサブセクションが追加されました。[詳細情報](../email/message-tracking.md#mirror-page)
* ドキュメントと画面上で、「オファーアクティビティ」が「決定」、「決定」が「決定範囲」に名称変更されました。[詳細情報](../offers/get-started/starting-offer-decisioning.md)
* 新しいユースケース：[ヘルパー関数を使用したメッセージのパーソナライズ](../personalization/personalization-use-case-helper-functions.md)が追加されました
* 「オーディエンスを読み取り」に関するドキュメントを更新して、セグメントの具体的な影響を反映しました。[詳細情報](../building-journeys/read-audience.md)
* ジャーニーの制限が更新されました。[詳細情報](../start/guardrails.md)
* 「決定でのオファー選択の設定」の節を更新しました。[詳細情報](../offers/offer-activities/configure-offer-selection.md)
* イベントベースのオファーは現在サポートされていないという警告を追加しました。[詳細情報](../offers/offer-library/creating-personalized-offers.md#eligibility)
* 意思決定管理の新しい「**[!UICONTROL 概要]**」タブについて説明しました。[詳細情報](../offers/get-started/user-interface.md#overview)
* オファーリストと決定リストから使用できるアクションを説明するために、[オファーリスト](../offers/offer-library/creating-personalized-offers.md#offer-list)と[決定リスト](../offers/offer-activities/create-offer-activities.md#decision-list)の節を新しく追加しました。

+++
