---
product: Journey Optimizer
audience: end-user
user-guide-title: 「フライトオプティマイザーガイド」
user-guide-description: 旅のオプティマイザーを使用して、接続された状況に合わせて、状況に応じたエクスペリエンスを作成し、顧客に提供します。
type: Documentation
solution: Journey Optimizer
source-git-commit: c6498633fdfdc9442203a3bf980f1b12bd1c6a6b
workflow-type: tm+mt
source-wordcount: '1297'
ht-degree: 0%

---

# Adobe 旅オプティマイザーのヘルプ {#using}

+ [旅オプティマイザーのドキュメント](ajo-home.md)
+ 新機能 {#whats-new}
   + [最新リリースノート](using/rn/release-notes.md)
   + 前のリリースノート {#previous-rn-new}
      + [2022リリースノート](using/rn/release-notes-2022.md)
      + [2021リリースノート](using/rn/release-notes-2021.md)
   + [ドキュメントの更新](using/rn/documentation-updates.md)
+ はじめに{#get-started}
   + [旅オプティマイザーについて](using/start/get-started.md)
   + クイックスタートガイド{#quick-start}
      + [大まか](using/start/quick-start.md)
      + [Marketer での作業の開始](using/start/path/marketer.md)
      + [データエンジニアとしての作業の開始](using/start/path/data-engineer.md)
      + [管理者としての作業の開始](using/start/path/administrator.md)
      + [開発者向けの入門](using/start/path/developer.md)
   + [ユーザーインターフェイス](using/start/user-interface.md)
   + [統合](using/start/ajo-integrations.md)
   + [Guardrails](using/start/guardrails.md)
+ Journeys {#orchestrate-journeys}
   + [Journeys での作業の開始](using/building-journeys/journey.md)
   + 旅の作成{#create-journey}
      + [初めての旅の作成](using/building-journeys/journey-gs.md)
      + [旅のデザイン](using/building-journeys/using-the-journey-designer.md)
      + [旅のテスト](using/building-journeys/testing-the-journey.md)
      + [旅のパブリッシュ](using/building-journeys/publishing-the-journey.md)
   + Journeys の管理{#mannage-journey}
      + [旅の終了](using/building-journeys/end-journey.md)
      + [タイムゾーン管理](using/building-journeys/timezone-management.md)
      + [プロファイルの入口の管理](using/building-journeys/entry-management.md)
      + [他のサンドボックスへの旅のコピー](using/building-journeys/copy-to-sandbox.md)
      + [旅のトラブルシューティング](using/building-journeys/troubleshooting.md)
      + [インテリジェントサービスとの連携](using/building-journeys/ai-services-overview.md)
   + アイテム {#about-journey-building}
      + [旅についての作業の開始](using/building-journeys/about-journey-activities.md)
      + [一般的なイベント](using/building-journeys/general-events.md)
      + [応答](using/building-journeys/reaction-events.md)
      + [セグメントの認定](using/building-journeys/segment-qualification-events.md)
      + [条件](using/building-journeys/condition-activity.md)
      + [時間](using/building-journeys/wait-activity.md)
      + [セグメントの読み取り](using/building-journeys/read-segment.md)
      + [電子メール、SMS、プッシュ](using/building-journeys/journeys-message.md)
      + [カスタムアクション](using/building-journeys/using-custom-actions.md)
      + [Adobe キャンペーンの標準的なアクション](using/building-journeys/using-adobe-campaign-standard.md)
      + [Adobe キャンペーン v7/v8 アクション](using/building-journeys/using-adobe-campaign-classic.md)
      + [移っ](using/building-journeys/jump.md)
      + [プロファイルの更新](using/building-journeys/update-profiles.md)
   + 構築式 {#building-advanced-conditions-journeys}
      + [大まか](using/building-journeys/expression/expressionadvanced.md)
      + ? {#syntax}
         + [Generalities](using/building-journeys/expression/generalities.md)
         + [条件付き命令](using/building-journeys/expression/conditional-instruction.md)
         + [データ型](using/building-journeys/expression/data-types.md)
         + [フィールドリファレンス](using/building-journeys/expression/field-references.md)
         + [コレクション管理関数](using/building-journeys/expression/collection-management-functions.md)
         + [Operators](using/building-journeys/expression/operators.md)
         + [旅のプロパティ](using/building-journeys/expression/journey-properties.md)
         + [例](using/building-journeys/expression/advanced-editor-use-cases.md)
      + 業務 {#main-functions-journey}
         + [メイン関数](using/building-journeys/expression/functions.md)
         + Adobe エクスペリエンスプラットフォーム {#adobe-experience-platform}
            + [inSegment](using/building-journeys/functions/functioninsegment.md)
         + 総計 {#aggregation}
            + [平均](using/building-journeys/functions/functionavg.md)
            + [ティック](using/building-journeys/functions/functioncount.md)
            + [countOnlyNull](using/building-journeys/functions/functioncountonlynull.md)
            + [countWithNull](using/building-journeys/functions/functioncountwithnull.md)
            + [distinctCount](using/building-journeys/functions/functiondistinctcount.md)
            + [distinctCountWithNull](using/building-journeys/functions/functiondistinctcountwithnull.md)
            + [最大](using/building-journeys/functions/functionmax.md)
            + [分](using/building-journeys/functions/functionmin.md)
            + [総額](using/building-journeys/functions/functionsum.md)
         + 処理 {#conversion}
            + [toBool](using/building-journeys/functions/functiontobool.md)
            + [toDateOnly](using/building-journeys/functions/functiontodateonly.md)
            + [toDateTime](using/building-journeys/functions/functiontodatetime.md)
            + [toDateTimeOnly](using/building-journeys/functions/functiontodatetimeonly.md)
            + [toDecimal](using/building-journeys/functions/functiontodecimal.md)
            + [toDuration](using/building-journeys/functions/functiontoduration.md)
            + [toInteger](using/building-journeys/functions/functiontointeger.md)
            + [toString](using/building-journeys/functions/functiontostring.md)
         + 古い {#date}
            + [currentTime&#x200B;InMillis](using/building-journeys/functions/functioncurrenttimeinmillis.md)
            + [郵便日付](using/building-journeys/functions/functioninlastdays.md)
            + [inLastHours](using/building-journeys/functions/functioninlasthours.md)
            + [「In Lastmonths」](using/building-journeys/functions/functioninlastmonths.md)
            + [inLastYears](using/building-journeys/functions/functioninlastyears.md)
            + [In Nextdays](using/building-journeys/functions/functioninnextdays.md)
            + [inNextHours](using/building-journeys/functions/functioninnexthours.md)
            + [「、Nextmonths」](using/building-journeys/functions/functioninnextmonths.md)
            + [「Nextyears」](using/building-journeys/functions/functioninnextyears.md)
            + [今](using/building-journeys/functions/functionnow.md)
            + [今すぐデルタ](using/building-journeys/functions/functionnowwithdelta.md)
            + [setHours](using/building-journeys/functions/functionsethours.md)
            + [setDays](using/building-journeys/functions/functionsetdays.md)
            + [updateTimeZone](using/building-journeys/functions/functionupdatetimezone.md)
         + 一連 {#list}
            + [異なっ](using/building-journeys/functions/functiondistinct.md)
            + [distinctWithNull](using/building-journeys/functions/functiondistinctwithnull.md)
            + [フィルタ](using/building-journeys/functions/functionfilter.md)
            + [getListItem](using/building-journeys/functions/functiongetlistitem.md)
            + [単位](using/building-journeys/functions/functionin.md)
            + [交わる](using/building-journeys/functions/functionintersect.md)
            + [制限](using/building-journeys/functions/functionlimit.md)
            + [listSize](using/building-journeys/functions/functionlistsize.md)
            + [serializeList](using/building-journeys/functions/functionserializelist.md)
            + [降順](using/building-journeys/functions/functionsort.md)
         + 演算 {#math}
            + [無作為](using/building-journeys/functions/functionrandom.md)
            + [数値](using/building-journeys/functions/functionround.md)
         + 値 {#string}
            + [連結](using/building-journeys/functions/functionconcat.md)
            + [ある](using/building-journeys/functions/functioncontain.md)
            + [containIgnoreCase](using/building-journeys/functions/functioncontainwithignorecase.md)
            + [endend](using/building-journeys/functions/functionendwith.md)
            + [endWithIgnorecase](using/building-journeys/functions/functionendwithignorecase.md)
            + [equalIgnoreCase](using/building-journeys/functions/functionequalignorecase.md)
            + [indexOf](using/building-journeys/functions/functionindexof.md)
            + [isEmpty](using/building-journeys/functions/functionisempty.md)
            + [isNotEmpty](using/building-journeys/functions/functionisnotempty.md)
            + [lastIndexOf](using/building-journeys/functions/functionlastindexof.md)
            + [長さ](using/building-journeys/functions/functionlength.md)
            + [古い](using/building-journeys/functions/functionlower.md)
            + [matchRegExp](using/building-journeys/functions/functionmatchregexp.md)
            + [notequalIgnoreCase](using/building-journeys/functions/functionnotequalignorecase.md)
            + [置き](using/building-journeys/functions/functionreplace.md)
            + [replaceAll](using/building-journeys/functions/functionreplaceall.md)
            + [分割](using/building-journeys/functions/functionsplit.md)
            + [startWith](using/building-journeys/functions/functionstartwith.md)
            + [startWithIgnoreCase](using/building-journeys/functions/functionstartwithignorecase.md)
            + [substr](using/building-journeys/functions/functionsubstr.md)
            + [裁断](using/building-journeys/functions/functiontrim.md)
            + [大](using/building-journeys/functions/functionupper.md)
            + [uuid](using/building-journeys/functions/functionuuid.md)
   + 使用例 {#journey-use-cases}
      + ビジネスユースケース {#business-use-cases}
         + [マルチチャンネルメッセージの送信](using/building-journeys/journeys-uc.md)
         + [キャンペーン v7/v8 を使用したメッセージの送信](using/building-journeys/ajo-ac.md)
         + [メッセージをサブスクライバーに送信する](using/building-journeys/message-to-subscribers-uc.md)
      + テクニカルユースケース {#technical-use-cases}
         + [カスタムアクションによるコレクションの動的なパス](using/building-journeys/collections.md)
         + [ランプアップ配信](using/building-journeys/ramp-up-deliveries-uc.md)
         + [外部データソースおよびカスタムアクションによるスループットの制限](using/building-journeys/limit-throughput.md)
+ キャンペーン{#campaigns}
   + [キャンペーンの開始](using/campaigns/get-started-with-campaigns.md)
   + [キャンペーンの作成](using/campaigns/create-campaign.md)
   + [キャンペーンの確認とアクティブ化](using/campaigns/review-activate-campaign.md)
   + [キャンペーンの管理](using/campaigns/modify-stop-campaign.md)
   + コンテンツの実験 {#content-experiment}
      + [コンテンツの実験について学習します。](using/campaigns/get-started-experiment.md)
      + [コンテンツ実験の作成](using/campaigns/content-experiment.md)
      + [統計計算について](using/campaigns/experiment-calculations.md)
      + [実験レポートの設定](using/campaigns/reporting-configuration.md)
   + [Api を使用してキャンペーンをトリガーします。](using/campaigns/api-triggered-campaigns.md)
+ 電子メールチャンネル {#email}
   + [電子メールでの作業の開始](using/email/get-started-email.md)
   + [電子メールの作成](using/email/create-email.md)
   + 電子メールコンテンツのデザイン {#design-email}
      + [電子メールデザインの概要](using/email/get-started-email-design.md)
      + コンテンツの作成を開始します {#start-creating-content}
         + [最初から作成](using/email/content-from-scratch.md)
         + [電子メールコンテンツの読み込み](using/email/existing-content.md)
         + [コンテンツのコード化](using/email/code-content.md)
         + [テンプレートを使用した作業](using/email/email-templates.md)
      + コンテンツのデザイン {#add-content}
         + [コンテンツコンポーネントの使用](using/email/content-components.md)
         + [リンクの追加と追跡メッセージ](using/email/message-tracking.md)
         + アセットの管理 {#manage-asset}
            + [アセットの基本事項の操作](using/email/assets-essentials.md)
            + [Adobe Stock での作業](using/email/stock.md)
         + [パーソナライズされたキャンペーンの挿入](using/email/add-offers-email.md)
         + [テキストバージョンの生成](using/email/text-version-email.md)
         + [プレヘッダーの追加](using/email/preheader.md)
      + スタイルの編集 {#edit-style}
         + [電子メールスタイルの使用を開始する](using/email/get-started-email-style.md)
         + [背景の設定の編集](using/email/backgrounds.md)
         + [垂直方向の配置と余白の調節](using/email/alignment-and-padding.md)
         + [リンクのスタイルの定義](using/email/styling-links.md)
         + [インラインスタイル属性の追加](using/email/inline-styling.md)
   + [電子メールのプレビューとテスト](using/email/preview.md)
   + [電子メールのオプトアウトの管理](using/email/email-opt-out.md)
   + 電子メールチャンネルの設定 {#configure-email}
      + [電子メール設定を使用した作業の開始](using/email/get-started-email-config.md)
      + [電子メールのサーフェス設定の設定](using/email/email-settings.md)
+ App In app channel{#in-app}
   + [アプリ内チャンネルの使用を開始します](using/in-app/get-started-in-app.md)
   + [アプリ内チャンネルの設定](using/in-app/inapp-configuration.md)
   + [アプリ内メッセージの作成](using/in-app/create-in-app.md)
   + [アプリ内コンテンツのデザイン](using/in-app/design-in-app.md)
   + [アプリ内レポート](using/in-app/inapp-report.md)
+ プッシュ通知チャネル{#push}
   + [プッシュ通知が開始されます。](using/push/get-started-push.md)
   + [プッシュ通知の作成](using/push/create-push.md)
   + [プッシュ通知のデザイン](using/push/design-push.md)
   + [Push 通知を送信します。](using/push/send-push.md)
   + プッシュ通知の設定{#push-config}
      + [プッシュ通知と Adobe 旅オプティマイザー](using/push/push-gs.md)
      + [プッシュ通知チャネルの設定](using/push/push-configuration.md)
+ SMS チャネル{#sms}
   + [SMS について学習します。](using/sms/get-started-sms.md)
   + [SMS メッセージの作成](using/sms/create-sms.md)
   + [SMS メッセージを送信します。](using/sms/send-sms.md)
   + [SMS オプトアウトの管理](using/sms/sms-opt-out.md)
   + [SMS チャネルの設定](using/sms/sms-configuration.md)
+ ダイレクトメール {#direct-mail}
   + [ダイレクトメールの作成](using/direct-mail/create-direct-mail.md)
   + [ダイレクトメールの設定](using/direct-mail/direct-mail-configuration.md)
+ Web チャンネル{#web}
   + [Web チャンネルの使用を開始する](using/web/get-started-web.md)
   + [Web エクスペリエンスの作成](using/web/create-web.md)
   + [Web ページの作成](using/web/author-web.md)
   + [ビジュアル編集ヘルパー拡張機能](using/web/visual-editing-helper.md)
   + [Web レポート](using/web/web-report.md)
+ ランディングページ {#landing-pages}
   + [ランディングページの使用を開始する](using/landing-pages/get-started-lp.md)
   + [ランディングページの作成](using/landing-pages/create-lp.md)
   + コンテンツのデザイン {#landing-pages-design}
      + [ランディングページのデザインについて](using/landing-pages/design-lp.md)
      + [ランディングページのコンテンツの作成](using/landing-pages/lp-content.md)
      + [テンプレートの作成](using/landing-pages/lp-templates.md)
      + [カスタム JavaScript の追加](using/landing-pages/lp-custom-js.md)
   + [購読リストの作成](using/landing-pages/subscription-list.md)
   + [ユースケースによる学習](using/landing-pages/lp-use-cases.md)
   + ランディングページの設定 {#lp-configuration}
      + [ランディングページのサブドメインの設定](using/landing-pages/lp-subdomains.md)
      + [ランディングページのプリセットの定義](using/landing-pages/lp-presets.md)
+ パーソナル化 &amp; ダイナミックコンテンツ {#personalized-dynamic-content}
   + パーソナライゼーション {#personalization}
      + [パーソナル化の開始](using/personalization/personalize.md)
      + [パーソナル化コンテキスト](using/personalization/personalization-contexts.md)
      + 構築式 {#build-expressions}
         + [パーソナル化構文](using/personalization/personalization-syntax.md)
         + エクスプレッションエディターを使用した操作 {#expression-editor}
            + [エクスプレッションエディターについて](using/personalization/personalization-build-expressions.md)
            + [「お気に入り」への属性の追加](using/personalization/personalization-favorites.md)
            + [保存したエクスプレッションの操作](using/personalization/personalization-library.md)
            + [パーソナル化の検証](using/personalization/personalization-validation.md)
         + ヘルパー関数{#functions}
            + [ヘルパー関数の使用について学習します。](using/personalization/functions/functions.md)
            + [集計関数](using/personalization/functions/aggregation.md)
            + [算術関数](using/personalization/functions/arithmetic-functions.md)
            + [配列とリスト関数](using/personalization/functions/arrays-list.md)
            + [日付関数](using/personalization/functions/dates.md)
            + [ブール関数と比較関数](using/personalization/functions/operators.md)
            + [ヘルパー](using/personalization/functions/helpers.md)
            + [マップ関数](using/personalization/functions/maps.md)
            + [オブジェクト関数](using/personalization/functions/objects.md)
            + [ストリング関数](using/personalization/functions/string.md)
      + 使用例{#personalization-use-cases}
         + [注文状況の通知](using/personalization/personalization-use-case.md)
         + [カート abandonment 電子メール](using/personalization/personalization-use-case-helper-functions.md)
   + 動的コンテンツ {#dynamic}
      + [動的コンテンツについて学習します。](using/personalization/get-started-dynamic-content.md)
      + [条件付きルールの作成](using/personalization/create-conditions.md)
      + [動的コンテンツの作成](using/personalization/dynamic-content.md)
+ セグメント、プロファイル、アイデンティティ{#segment}
   + 層 {#segments}
      + [セグメントでの作業の開始](using/segment/about-segments.md)
      + [セグメントの構築](using/segment/creating-a-segment.md)
   + プロファイル{#profiles}
      + [プロファイルの利用開始](using/segment/get-started-profiles.md)
      + [テストプロファイルの作成](using/segment/creating-test-profiles.md)
   + [情報](using/segment/get-started-identity.md)
   + 対象ユーザーの作成 {#audience-orchestration}
      + [対象ユーザー向けコンポジションの使用を開始する](using/segment/get-started-audience-orchestration.md)
      + [コンポジションワークフローの作成](using/segment/create-compositions.md)
      + [コンポジション canvas の操作](using/segment/composition-canvas.md)
      + [対象ユーザーへのアクセスと管理](using/segment/access-audiences.md)
   + [使用許諾契約](using/segment/license-usage.md)
+ トラックとモニター {#reporting}
   + ライブレポート {#live-report}
      + [ライブレポートでの作業の開始](using/reports/live-report.md)
      + [ライブレポートの旅](using/reports/journey-live-report.md)
      + [キャンペーンライブレポート](using/reports/campaign-live-report.md)
      + [ランディングページライブレポート](using/reports/lp-report-live.md)
      + [購読リストライブレポート](using/reports/subscription-report-live.md)
   + グローバルレポート {#global-report}
      + [グローバルレポートを使用した作業の開始](using/reports/global-report.md)
      + [「旅グローバル」レポート](using/reports/journey-global-report.md)
      + [キャンペーングローバルレポート](using/reports/campaign-global-report.md)
      + [ランディングページのグローバルレポート](using/reports/lp-report-global.md)
      + [購読リストグローバルレポート](using/reports/subscription-report-global.md)
   + 旅レポート {#reports}
      + [道報告の作成](using/reports/sharing-overview.md)
      + [ステップイベントフィールドリスト](using/reports/sharing-field-list.md)
      + 従来のステップのイベントフィールド {#legacy-step-event-fields}
         + [従来のフィールドについて](using/reports/sharing-legacy-fields.md)
         + [「旅」フィールド](using/reports/sharing-journey-fields.md)
         + [一般的なフィールド](using/reports/sharing-common-fields.md)
         + [アクション実行フィールド](using/reports/sharing-execution-fields.md)
         + [データ取得フィールド](using/reports/sharing-fetch-fields.md)
         + [Id フィールド](using/reports/sharing-identity-fields.md)
      + [クエリーの例](using/reports/query-examples.md)
   + Deliverability {#deliverability}
      + [Deliverability での作業の開始](using/reports/deliverability.md)
      + [抑制リストについて](using/reports/suppression-list.md)
   + [よる](using/reports/alerts.md)
   + [お客様の旅解析機能について](using/reports/cja-ajo.md)
+ 意思決定管理 {#offer-decisioning}
   + デシジョン管理について学習します。 {#get-started-decision}
      + [意思決定管理について](using/offers/get-started/starting-offer-decisioning.md)
      + [ユーザーインターフェイス](using/offers/get-started/user-interface.md)
      + [オファーを作成および管理するための主な手順](using/offers/offer-library/key-steps.md)
      + [用途: 電子メールへの「オファーの挿入」](using/offers/offers-e2e.md)
   + コンポーネントの作成 {#create-components}
      + [配置の作成](using/offers/offer-library/creating-placements.md)
      + [決定ルールの作成](using/offers/offer-library/creating-decision-rules.md)
      + [タグの作成](using/offers/offer-library/creating-tags.md)
   + ランキングの作成 {#rankings}
      + [ランキングでの作業の開始](using/offers/ranking/get-started-rankings.md)
      + [ランク付け式](using/offers/ranking/create-ranking-formulas.md)
      + AI モデル {#ai-models}
         + [AI モデルについて](using/offers/ranking/ai-models.md)
         + AI モデルタイプ {#ai-model-types}
            + [自動最適化モデル](using/offers/ranking/auto-optimization-model.md)
            + [カスタマイズされた最適化モデル](using/offers/ranking/personalized-optimization-model.md)
         + AI モデルの作成 {#configure-ai-model}
            + [イベントを収集するためのデータセットの作成](using/offers/ranking/create-dataset.md)
            + [AI モデルの作成](using/offers/ranking/create-ranking-strategies.md)
            + [イベントキャプチャの設定](using/offers/ranking/schema-requirement.md)
   + オファーの作成と管理 {#managing-offers-in-the-offer-library}
      + オファーの設定 {#configure-offers}
         + [パーソナライズされた特典の作成](using/offers/offer-library/creating-personalized-offers.md)
         + [プロダクト表現の追加](using/offers/offer-library/add-representations.md)
         + [制約の追加](using/offers/offer-library/add-constraints.md)
      + [予備製品の作成](using/offers/offer-library/creating-fallback-offers.md)
      + [コレクションの作成](using/offers/offer-library/creating-collections.md)
   + 決定事項の作成と管理 {#create-manage-activities}
      + [意思決定の作成](using/offers/offer-activities/create-offer-activities.md)
      + [「決定」の「選択項目を設定」を選択します。](using/offers/offer-activities/configure-offer-selection.md)
      + [シミュレーションの作成](using/offers/offer-activities/simulation.md)
   + [Batch decisioning](using/offers/batch-delivery.md)
   + 意思決定管理レポートの作成 {#create-reports}
      + [意思決定管理イベント入門](using/offers/reports/get-started-events.md)
      + [意思決定管理イベントキー情報](using/offers/reports/key-information.md)
      + [Access イベント &quot;XDM&quot; フィールド](using/offers/reports/xdm-fields.md)
   + オファーカタログの書き出し {#export-catalog}
      + [カタログの書き出し機能を使用して作業を開始します。 ](using/offers/export-catalog/get-started-export.md)
      + [エクスポートされたサービスカタログへのアクセス](using/offers/export-catalog/access-dataset.md)
      + [パーソナライズされたオファーデータセット](using/offers/export-catalog/export-offers.md)
      + [意思決定データセット](using/offers/export-catalog/export-decisions.md)
      + [配置データセット](using/offers/export-catalog/export-placements.md)
      + [フォールバックデータセット](using/offers/export-catalog/export-fallback.md)
   + API リファレンス {#api-reference}
      + [はじめに](using/offers/api-reference/getting-started.md)
      + Api を使用したオファーの作成と管理 {#offers-api}
         + 配置 {#placements}
            + [リストの配置](using/offers/api-reference/offers-api/placements/placements-list.md)
            + [配置の検索](using/offers/api-reference/offers-api/placements/lookup.md)
            + [配置の作成](using/offers/api-reference/offers-api/placements/create.md)
            + [配置の更新](using/offers/api-reference/offers-api/placements/update.md)
            + [配置の削除](using/offers/api-reference/offers-api/placements/delete.md)
         + 決定ルール {#decision-rules}
            + [意思決定ルールのリスト表示](using/offers/api-reference/offers-api/decision-rules/rules-list.md)
            + [意思決定ルールの参照](using/offers/api-reference/offers-api/decision-rules/lookup.md)
            + [意思決定ルールの作成](using/offers/api-reference/offers-api/decision-rules/create.md)
            + [決定ルールの更新](using/offers/api-reference/offers-api/decision-rules/update.md)
            + [決定ルールの削除](using/offers/api-reference/offers-api/decision-rules/delete.md)
         + タグ {#tags}
            + [タグの表示](using/offers/api-reference/offers-api/tags/tags-list.md)
            + [タグの検索](using/offers/api-reference/offers-api/tags/lookup.md)
            + [タグの作成](using/offers/api-reference/offers-api/tags/create.md)
            + [タグの更新](using/offers/api-reference/offers-api/tags/update.md)
            + [タグの削除](using/offers/api-reference/offers-api/tags/delete.md)
         + カスタマイズされたキャンペーン {#personalized-offers}
            + [パーソナライズされたキャンペーンのリスト](using/offers/api-reference/offers-api/personalized-offers/offers-list.md)
            + [パーソナライズされたオファーリングの検索](using/offers/api-reference/offers-api/personalized-offers/lookup.md)
            + [パーソナライズされたオファーの作成](using/offers/api-reference/offers-api/personalized-offers/create.md)
            + [パーソナライズされたオファーの更新](using/offers/api-reference/offers-api/personalized-offers/update.md)
            + [パーソナライズされたオファーの削除](using/offers/api-reference/offers-api/personalized-offers/delete.md)
         + コレクション {#collections}
            + [リストコレクション](using/offers/api-reference/offers-api/collections/collections-list.md)
            + [コレクションを検索します。](using/offers/api-reference/offers-api/collections/lookup.md)
            + [コレクションの作成](using/offers/api-reference/offers-api/collections/create.md)
            + [コレクションの更新](using/offers/api-reference/offers-api/collections/update.md)
            + [コレクションの削除](using/offers/api-reference/offers-api/collections/delete.md)
         + フォールバックオファー {#fallback-offers}
            + [フォールバックオファーのリスト](using/offers/api-reference/offers-api/fallback-offers/fallback-list.md)
            + [フォールバックオファーの参照](using/offers/api-reference/offers-api/fallback-offers/lookup.md)
            + [フォールバックオファーの作成](using/offers/api-reference/offers-api/fallback-offers/create.md)
            + [フォールバックオファーの更新](using/offers/api-reference/offers-api/fallback-offers/update.md)
            + [フォールバックオファーの削除](using/offers/api-reference/offers-api/fallback-offers/delete.md)
      + Api を使用した意思決定の作成と管理 {#activities-api}
         + [リストの決定](using/offers/api-reference/activities-api/activities/activities-list.md)
         + [意思決定の検索](using/offers/api-reference/activities-api/activities/lookup.md)
         + [意思決定の作成](using/offers/api-reference/activities-api/activities/create.md)
         + [意思決定の更新](using/offers/api-reference/activities-api/activities/update.md)
         + [意思決定の削除](using/offers/api-reference/activities-api/activities/delete.md)
      + Api を使用した提供を提供します。 {#offer-delivery-api}
         + [オファー配信 Api について学習します。](using/offers/api-reference/offer-delivery-api/start-offer-delivery-apis.md)
         + [Decisioning API](using/offers/api-reference/offer-delivery-api/decisioning-api.md)
         + [Edge Decisioning API](using/offers/api-reference/offer-delivery-api/edge-decisioning-api.md)
         + [Batch Decisioning API](using/offers/api-reference/offer-delivery-api/batch-decisioning-api.md)
+ データ管理 {#data-management}
   + [データ管理について学習します。](using/data/gs-data.md)
   + [スキーマの操作](using/data/get-started-schemas.md)
   + 旅のオプティマイザーデータセット {#datasets}
      + [データセットでの作業の開始](using/data/get-started-datasets.md)
      + [クエリーの例](using/data/datasets-query-examples.md)
   + [問い合わせる](using/data/get-started-queries.md)
+ 設定{#configuration}
   + [「旅のオプティマイザー設定」を使用して作業を開始します。](using/configuration/get-started-configuration.md)
   + 電子メールサブドメインの委任 {#delegate-subdomains}
      + [サブドメインの委任について](using/configuration/about-subdomain-delegation.md)
      + [サブドメインの委任](using/configuration/delegate-subdomain.md)
      + [Google TXT レコードの追加](using/configuration/google-txt.md)
      + [PTR レコードへのアクセスと編集](using/configuration/ptr-records.md)
      + [IP プールの作成](using/configuration/ip-pools.md)
   + [チャンネルサーフェスの設定](using/configuration/channel-surfaces.md)
   + 電子メールアドレスの監視 {#monitor-reputation}
      + [抑制リスト](using/configuration/manage-suppression-list.md)
      + [再送](using/configuration/retries.md)
      + [許可リスト](using/configuration/allow-list.md)
   + [アーカイブのサポート](using/configuration/archiving-support.md)
   + [頻度ルールの構成](using/configuration/frequency-rules.md)
   + [実行アドレスの管理](using/configuration/primary-email-addresses.md)
   + Journeys の構成 {#configure-journeys}
      + [データソース、イベント、アクションについて](using/configuration/about-data-sources-events-actions.md)
      + [外部システムとの統合](using/configuration/external-systems.md)
      + イベントの設定 {#events-journeys}
         + [一般的な原則](using/event/about-events.md)
         + ユニタリイベントの設定 {#unitary-events}
            + [ユニタリイベントを使用して作業を開始します。](using/event/about-creating.md)
            + [ExperienceEvent スキーマについて](using/event/experience-event-schema.md)
            + [Adobe アナリティクスの活用](using/event/about-analytics.md)
         + [業務イベントの設定](using/event/about-creating-business.md)
         + [イベントを送信するためのその他の手順](using/event/additional-steps-to-send-events-to-journey.md)
      + データソースの構成{#data-source-journeys}
         + [データソースについて](using/datasource/about-data-sources.md)
         + [データソースの設定](using/datasource/configure-data-sources.md)
         + [Adobe エクスペリエンス Platform データソース](using/datasource/adobe-experience-platform-data-source.md)
         + [外部データソース](using/datasource/external-data-sources.md)
      + アクションの設定 {#action-journeys}
         + [アクションについて](using/action/action.md)
         + [アクションを設定します。](using/action/about-custom-action-configuration.md)
         + [Adobe キャンペーン規格との統合](using/action/acs-action.md)
         + [Adobe キャンペーンとの統合 v7/v8](using/action/acc-action.md)
   + [給紙](using/start/get-started-sources.md)
+ アクセス制御 {#access-control}
   + [アクセス制御の概要](using/administration/permissions-overview.md)
   + [製品に組み込まれているプロファイル](using/administration/ootb-product-profiles.md)
   + [ユーザーおよび製品プロファイルの管理](using/administration/permissions.md)
   + [アクセス許可レベル](using/administration/high-low-permissions.md)
   + [サンドボックスの管理](using/administration/sandboxes.md)
   + [属性ベースのアクセス制御](using/administration/attribute-based-access.md)
   + [オブジェクトレベルのアクセス制御](using/administration/object-based-access.md)
+ 保護 {#privacy}
   + [プライバシーに関する作業の開始](using/privacy/get-started-privacy.md)
   + [プライバシー要求](using/privacy/requests.md)
   + [リソースに対する操作の監査](using/privacy/audit-logs.md)
   + 同意の管理 {#consent}
      + [オプトアウトの管理](using/privacy/opt-out.md)
      + [同意ポリシーを使用した作業](using/action/consent.md)
   + [データガバナンス](using/action/action-privacy.md)
