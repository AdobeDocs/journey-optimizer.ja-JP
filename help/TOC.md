---
product: Journey Optimizer
audience: end-user
user-guide-title: Journey Optimizer ガイド
user-guide-description: Journey Optimizer を使用して、連続性があり、コンキストに即してパーソナライズされたエクスペリエンスを構築し、顧客に提供します。
type: Documentation
solution: Journey Optimizer
source-git-commit: 81ab92022329788c1feea24c7a621ef154d33422
workflow-type: tm+mt
source-wordcount: '1312'
ht-degree: 100%

---

# Adobe Journey Optimizer ヘルプ {#using}

+ [Journey Optimizer ドキュメント](ajo-home.md)
+ 新着情報 {#whats-new}
   + [最新のリリースノート](using/rn/release-notes.md)
   + 以前のリリースノート {#previous-rn-new}
      + [2022年リリースノート](using/rn/release-notes-2022.md)
      + [2021年リリースノート](using/rn/release-notes-2021.md)
   + [ドキュメントの更新](using/rn/documentation-updates.md)
+ はじめに {#get-started}
   + [Journey Optimizer について](using/start/get-started.md)
   + クイックスタートガイド{#quick-start}
      + [概要](using/start/quick-start.md)
      + [マーケター向けの基本を学ぶ](using/start/path/marketer.md)
      + [データエンジニア向けの基本を学ぶ](using/start/path/data-engineer.md)
      + [管理者向けの基本を学ぶ](using/start/path/administrator.md)
      + [開発者向けの基本を学ぶ](using/start/path/developer.md)
   + [ユーザーインターフェイス](using/start/user-interface.md)
   + [アクセシビリティ](using/start/accessibility.md)
   + [統合](using/start/ajo-integrations.md)
   + [ガードレール](using/start/guardrails.md)
+ ジャーニー {#orchestrate-journeys}
   + [ジャーニーの基本を学ぶ](using/building-journeys/journey.md)
   + ジャーニーの作成{#create-journey}
      + [初めてのジャーニーの作成](using/building-journeys/journey-gs.md)
      + [ジャーニーのデザイン](using/building-journeys/using-the-journey-designer.md)
      + [ジャーニーのテスト](using/building-journeys/testing-the-journey.md)
      + [ジャーニーの公開](using/building-journeys/publishing-the-journey.md)
   + ジャーニーの管理{#mannage-journey}
      + [ジャーニーの終了](using/building-journeys/end-journey.md)
      + [タイムゾーンの管理](using/building-journeys/timezone-management.md)
      + [プロファイルエントリ管理](using/building-journeys/entry-management.md)
      + [別のサンドボックスへのジャーニーのコピー](using/building-journeys/copy-to-sandbox.md)
      + [ジャーニーのトラブルシューティング](using/building-journeys/troubleshooting.md)
      + [インテリジェントサービスとの統合](using/building-journeys/ai-services-overview.md)
   + アクティビティ {#about-journey-building}
      + [ジャーニーのアクティビティの基本を学ぶ](using/building-journeys/about-journey-activities.md)
      + [一般イベント](using/building-journeys/general-events.md)
      + [反応](using/building-journeys/reaction-events.md)
      + [セグメントの選定](using/building-journeys/segment-qualification-events.md)
      + [条件](using/building-journeys/condition-activity.md)
      + [待機](using/building-journeys/wait-activity.md)
      + [セグメントの読み取り](using/building-journeys/read-segment.md)
      + [メール、SMS、プッシュ](using/building-journeys/journeys-message.md)
      + [カスタムアクション](using/building-journeys/using-custom-actions.md)
      + [Adobe Campaign Standard のアクション](using/building-journeys/using-adobe-campaign-standard.md)
      + [Adobe Campaign v7／v8 のアクション](using/building-journeys/using-adobe-campaign-classic.md)
      + [ジャンプ](using/building-journeys/jump.md)
      + [プロファイルの更新](using/building-journeys/update-profiles.md)
   + 式の作成 {#building-advanced-conditions-journeys}
      + [概要](using/building-journeys/expression/expressionadvanced.md)
      + 構文 {#syntax}
         + [一般規則](using/building-journeys/expression/generalities.md)
         + [条件付き命令](using/building-journeys/expression/conditional-instruction.md)
         + [データタイプ](using/building-journeys/expression/data-types.md)
         + [フィールド参照](using/building-journeys/expression/field-references.md)
         + [コレクション管理関数](using/building-journeys/expression/collection-management-functions.md)
         + [演算子](using/building-journeys/expression/operators.md)
         + [ジャーニーのプロパティ](using/building-journeys/expression/journey-properties.md)
         + [例](using/building-journeys/expression/advanced-editor-use-cases.md)
      + 関数 {#main-functions-journey}
         + [主な関数](using/building-journeys/expression/functions.md)
         + Adobe Experience Platform {#adobe-experience-platform}
            + [inSegment](using/building-journeys/functions/functioninsegment.md)
         + 集計 {#aggregation}
            + [avg](using/building-journeys/functions/functionavg.md)
            + [count](using/building-journeys/functions/functioncount.md)
            + [countOnlyNull](using/building-journeys/functions/functioncountonlynull.md)
            + [countWithNull](using/building-journeys/functions/functioncountwithnull.md)
            + [distinctCount](using/building-journeys/functions/functiondistinctcount.md)
            + [distinctCountWithNull](using/building-journeys/functions/functiondistinctcountwithnull.md)
            + [max](using/building-journeys/functions/functionmax.md)
            + [min](using/building-journeys/functions/functionmin.md)
            + [sum](using/building-journeys/functions/functionsum.md)
         + コンバージョン {#conversion}
            + [toBool](using/building-journeys/functions/functiontobool.md)
            + [toDateOnly](using/building-journeys/functions/functiontodateonly.md)
            + [toDateTime](using/building-journeys/functions/functiontodatetime.md)
            + [toDateTimeOnly](using/building-journeys/functions/functiontodatetimeonly.md)
            + [toDecimal](using/building-journeys/functions/functiontodecimal.md)
            + [toDuration](using/building-journeys/functions/functiontoduration.md)
            + [toInteger](using/building-journeys/functions/functiontointeger.md)
            + [toString](using/building-journeys/functions/functiontostring.md)
         + 日付 {#date}
            + [currentTime&#x200B;InMillis](using/building-journeys/functions/functioncurrenttimeinmillis.md)
            + [inLastDays](using/building-journeys/functions/functioninlastdays.md)
            + [inLastHours](using/building-journeys/functions/functioninlasthours.md)
            + [inLastMonths](using/building-journeys/functions/functioninlastmonths.md)
            + [inLastYears](using/building-journeys/functions/functioninlastyears.md)
            + [inNextDays](using/building-journeys/functions/functioninnextdays.md)
            + [inNextHours](using/building-journeys/functions/functioninnexthours.md)
            + [inNextMonths](using/building-journeys/functions/functioninnextmonths.md)
            + [inNextYears](using/building-journeys/functions/functioninnextyears.md)
            + [now](using/building-journeys/functions/functionnow.md)
            + [nowWithDelta](using/building-journeys/functions/functionnowwithdelta.md)
            + [setHours](using/building-journeys/functions/functionsethours.md)
            + [setDays](using/building-journeys/functions/functionsetdays.md)
            + [updateTimeZone](using/building-journeys/functions/functionupdatetimezone.md)
         + リスト {#list}
            + [distinct](using/building-journeys/functions/functiondistinct.md)
            + [distinctWithNull](using/building-journeys/functions/functiondistinctwithnull.md)
            + [filter](using/building-journeys/functions/functionfilter.md)
            + [getListItem](using/building-journeys/functions/functiongetlistitem.md)
            + [in](using/building-journeys/functions/functionin.md)
            + [intersect](using/building-journeys/functions/functionintersect.md)
            + [制限](using/building-journeys/functions/functionlimit.md)
            + [listSize](using/building-journeys/functions/functionlistsize.md)
            + [serializeList](using/building-journeys/functions/functionserializelist.md)
            + [sort](using/building-journeys/functions/functionsort.md)
         + 数学 {#math}
            + [random](using/building-journeys/functions/functionrandom.md)
            + [round](using/building-journeys/functions/functionround.md)
         + 文字列 {#string}
            + [concat](using/building-journeys/functions/functionconcat.md)
            + [contain](using/building-journeys/functions/functioncontain.md)
            + [containIgnoreCase](using/building-journeys/functions/functioncontainwithignorecase.md)
            + [endWith](using/building-journeys/functions/functionendwith.md)
            + [endWithIgnorecase](using/building-journeys/functions/functionendwithignorecase.md)
            + [equalIgnoreCase](using/building-journeys/functions/functionequalignorecase.md)
            + [indexOf](using/building-journeys/functions/functionindexof.md)
            + [isEmpty](using/building-journeys/functions/functionisempty.md)
            + [isNotEmpty](using/building-journeys/functions/functionisnotempty.md)
            + [lastIndexOf](using/building-journeys/functions/functionlastindexof.md)
            + [length](using/building-journeys/functions/functionlength.md)
            + [lower](using/building-journeys/functions/functionlower.md)
            + [matchRegExp](using/building-journeys/functions/functionmatchregexp.md)
            + [notequalIgnoreCase](using/building-journeys/functions/functionnotequalignorecase.md)
            + [replace](using/building-journeys/functions/functionreplace.md)
            + [replaceAll](using/building-journeys/functions/functionreplaceall.md)
            + [split](using/building-journeys/functions/functionsplit.md)
            + [startWith](using/building-journeys/functions/functionstartwith.md)
            + [startWithIgnoreCase](using/building-journeys/functions/functionstartwithignorecase.md)
            + [substr](using/building-journeys/functions/functionsubstr.md)
            + [trim](using/building-journeys/functions/functiontrim.md)
            + [upper](using/building-journeys/functions/functionupper.md)
            + [uuid](using/building-journeys/functions/functionuuid.md)
   + ユースケース {#journey-use-cases}
      + ビジネスユースケース{#business-use-cases}
         + [マルチチャネルメッセージの送信](using/building-journeys/journeys-uc.md)
         + [Campaign v7／v8 を使用したメッセージの送信](using/building-journeys/ajo-ac.md)
         + [サブスクライバーへのメッセージの送信](using/building-journeys/message-to-subscribers-uc.md)
      + テクニカルユースケース{#technical-use-cases}
         + [カスタムアクションを使用したコレクションの動的な受け渡し](using/building-journeys/collections.md)
         + [配信を増やす](using/building-journeys/ramp-up-deliveries-uc.md)
         + [外部データソースとカスタムアクションを使用してスループットを制限する](using/building-journeys/limit-throughput.md)
+ キャンペーン{#campaigns}
   + [キャンペーンの基本を学ぶ](using/campaigns/get-started-with-campaigns.md)
   + [キャンペーンの作成](using/campaigns/create-campaign.md)
   + [キャンペーンのレビューとアクティブ化](using/campaigns/review-activate-campaign.md)
   + [キャンペーンの管理](using/campaigns/modify-stop-campaign.md)
   + コンテンツ実験 {#content-experiment}
      + [コンテンツ実験の基本を学ぶ](using/campaigns/get-started-experiment.md)
      + [コンテンツ実験の作成](using/campaigns/content-experiment.md)
      + [統計計算について](using/campaigns/experiment-calculations.md)
      + [実験レポートの設定](using/campaigns/reporting-configuration.md)
      + [実験レポートの統計計算](using/campaigns/experiment-report-calculations.md)
   + [API を使用したキャンペーンのトリガー](using/campaigns/api-triggered-campaigns.md)
+ メールチャネル {#email}
   + [メールの基本を学ぶ](using/email/get-started-email.md)
   + [メールの作成](using/email/create-email.md)
   + メールコンテンツのデザイン {#design-email}
      + [メールデザインの基本を学ぶ](using/email/get-started-email-design.md)
      + コンテンツ作成の開始 {#start-creating-content}
         + [ゼロから開始](using/email/content-from-scratch.md)
         + [メールコンテンツの読み込み](using/email/existing-content.md)
         + [コンテンツを独自にコーディング](using/email/code-content.md)
         + [テンプレートの操作](using/email/email-templates.md)
      + コンテンツのデザイン {#add-content}
         + [コンテンツコンポーネントの使用](using/email/content-components.md)
         + [リンクの追加とメッセージの追跡](using/email/message-tracking.md)
         + アセットの管理 {#manage-asset}
            + [Assets Essentials の操作](using/email/assets-essentials.md)
            + [Adobe Stock との連携](using/email/stock.md)
         + [パーソナライズされたオファーの挿入](using/email/add-offers-email.md)
         + [テキストバージョンの生成](using/email/text-version-email.md)
         + [プリヘッダーを追加](using/email/preheader.md)
      + スタイルの編集 {#edit-style}
         + [メールスタイルの基本を学ぶ](using/email/get-started-email-style.md)
         + [背景設定の編集](using/email/backgrounds.md)
         + [垂直方向の整列とパディングを調整する](using/email/alignment-and-padding.md)
         + [リンクのスタイルの定義](using/email/styling-links.md)
         + [インラインのスタイル属性の追加](using/email/inline-styling.md)
   + [メールのプレビューとテスト](using/email/preview.md)
   + [コンテンツテンプレートを作成](using/email/content-templates.md)
   + [メールオプトアウトの管理](using/email/email-opt-out.md)
   + メールチャネルの設定 {#configure-email}
      + [メール設定の基本を学ぶ](using/email/get-started-email-config.md)
      + [メールサーフェス設定の指定](using/email/email-settings.md)
+ アプリ内チャネル{#in-app}
   + [アプリ内チャネルの基本を学ぶ](using/in-app/get-started-in-app.md)
   + [アプリ内チャネルの設定](using/in-app/inapp-configuration.md)
   + [アプリ内メッセージの作成 ](using/in-app/create-in-app.md)
   + [アプリ内コンテンツのデザイン](using/in-app/design-in-app.md)
   + [アプリ内レポート](using/in-app/inapp-report.md)
+ プッシュ通知チャネル{#push}
   + [プッシュ通知の基本を学ぶ](using/push/get-started-push.md)
   + [プッシュ通知の作成](using/push/create-push.md)
   + [プッシュ通知のデザイン](using/push/design-push.md)
   + [プッシュ通知の送信](using/push/send-push.md)
   + プッシュ通知の設定{#push-config}
      + [プッシュ通知と Adobe Journey Optimizer](using/push/push-gs.md)
      + [プッシュ通知チャネルの設定](using/push/push-configuration.md)
+ SMS チャネル{#sms}
   + [SMS の基本を学ぶ](using/sms/get-started-sms.md)
   + [SMS メッセージの作成](using/sms/create-sms.md)
   + [SMS のプレビューとテスト](using/sms/send-sms.md)
   + [SMS オプトアウトの管理](using/sms/sms-opt-out.md)
   + [SMS チャネルの設定](using/sms/sms-configuration.md)
+ ダイレクトメール {#direct-mail}
   + [ダイレクトメールの作成](using/direct-mail/create-direct-mail.md)
   + [ダイレクトメールの設定](using/direct-mail/direct-mail-configuration.md)
+ Web チャネル{#web}
   + [Web チャネルの基本を学ぶ](using/web/get-started-web.md)
   + [Web エクスペリエンスの作成](using/web/create-web.md)
   + [Web ページの作成](using/web/author-web.md)
   + [Visual Editing Helper 拡張機能](using/web/visual-editing-helper.md)
   + [Web レポート](using/web/web-report.md)
+ ランディングページ {#landing-pages}
   + [ランディングページの基本を学ぶ](using/landing-pages/get-started-lp.md)
   + [ランディングページの作成](using/landing-pages/create-lp.md)
   + コンテンツのデザイン {#landing-pages-design}
      + [ランディングページの設計について](using/landing-pages/design-lp.md)
      + [ランディングページのコンテンツの作成](using/landing-pages/lp-content.md)
      + [テンプレートの作成](using/landing-pages/lp-templates.md)
      + [カスタム JavaScript の追加](using/landing-pages/lp-custom-js.md)
   + [サブスクリプションリストの作成](using/landing-pages/subscription-list.md)
   + [ユースケースを通じて学ぶ](using/landing-pages/lp-use-cases.md)
   + ランディングページの設定 {#lp-configuration}
      + [ランディングページのサブドメインの設定](using/landing-pages/lp-subdomains.md)
      + [ランディングページプリセットの定義](using/landing-pages/lp-presets.md)
+ パーソナライズ機能と動的コンテンツ {#personalized-dynamic-content}
   + パーソナライズ機能 {#personalization}
      + [パーソナライゼーションの基本を学ぶ](using/personalization/personalize.md)
      + [パーソナライゼーションのコンテキスト](using/personalization/personalization-contexts.md)
      + 式の作成 {#build-expressions}
         + [パーソナライゼーション構文](using/personalization/personalization-syntax.md)
         + 式エディターの操作 {#expression-editor}
            + [式エディターについて](using/personalization/personalization-build-expressions.md)
            + [お気に入りに属性を追加](using/personalization/personalization-favorites.md)
            + [保存済み式の使用](using/personalization/personalization-library.md)
            + [パーソナライゼーションの検証](using/personalization/personalization-validation.md)
         + ヘルパー関数{#functions}
            + [ヘルパー関数の基本を学ぶ](using/personalization/functions/functions.md)
            + [集計関数](using/personalization/functions/aggregation.md)
            + [演算関数](using/personalization/functions/arithmetic-functions.md)
            + [配列およびリスト関数](using/personalization/functions/arrays-list.md)
            + [日付関数](using/personalization/functions/dates.md)
            + [ブール関数と比較関数](using/personalization/functions/operators.md)
            + [ヘルパー](using/personalization/functions/helpers.md)
            + [マップ関数](using/personalization/functions/maps.md)
            + [数学関数](using/personalization/functions/math.md)
            + [オブジェクト関数](using/personalization/functions/objects.md)
            + [文字列関数](using/personalization/functions/string.md)
      + ユースケース{#personalization-use-cases}
         + [注文ステータスの通知](using/personalization/personalization-use-case.md)
         + [買い物かご放棄に関するメール](using/personalization/personalization-use-case-helper-functions.md)
   + 動的コンテンツ {#dynamic}
      + [動的コンテンツの基本を学ぶ](using/personalization/get-started-dynamic-content.md)
      + [条件付きルールの作成](using/personalization/create-conditions.md)
      + [動的コンテンツの作成](using/personalization/dynamic-content.md)
+ セグメント、プロファイル、ID{#segment}
   + セグメント {#segments}
      + [セグメントの基本を学ぶ](using/segment/about-segments.md)
      + [セグメントの作成](using/segment/creating-a-segment.md)
   + プロファイル{#profiles}
      + [プロファイルの基本を学ぶ](using/segment/get-started-profiles.md)
      + [テストプロファイルの作成](using/segment/creating-test-profiles.md)
   + [ID](using/segment/get-started-identity.md)
   + オーディエンスの作成 {#audience-orchestration}
      + [オーディエンスコンポジションの基本を学ぶ](using/segment/get-started-audience-orchestration.md)
      + [コンポジションワークフローの作成](using/segment/create-compositions.md)
      + [コンポジションキャンバスの操作](using/segment/composition-canvas.md)
      + [オーディエンスへのアクセスと管理](using/segment/access-audiences.md)
   + [ライセンス使用状況](using/segment/license-usage.md)
+ トラッキングとモニタリング {#reporting}
   + ライブレポート {#live-report}
      + [ライブレポートの概要](using/reports/live-report.md)
      + [ジャーニーライブレポート](using/reports/journey-live-report.md)
      + [キャンペーンのライブレポート](using/reports/campaign-live-report.md)
      + [ランディングページライブレポート](using/reports/lp-report-live.md)
      + [購読リストライブレポート](using/reports/subscription-report-live.md)
   + グローバルレポート {#global-report}
      + [グローバルレポートの基本を学ぶ](using/reports/global-report.md)
      + [ジャーニーグローバルレポート](using/reports/journey-global-report.md)
      + [キャンペーンのグローバルレポート](using/reports/campaign-global-report.md)
      + [ランディングページグローバルレポート](using/reports/lp-report-global.md)
      + [購読リストグローバルレポート](using/reports/subscription-report-global.md)
   + ジャーニーレポート {#reports}
      + [ジャーニーレポートの作成](using/reports/sharing-overview.md)
      + [ステップイベントフィールドのリスト](using/reports/sharing-field-list.md)
      + レガシーステップイベントのフィールド {#legacy-step-event-fields}
         + [レガシーフィールドについて](using/reports/sharing-legacy-fields.md)
         + [ジャーニーのフィールド](using/reports/sharing-journey-fields.md)
         + [共通フィールド](using/reports/sharing-common-fields.md)
         + [アクション実行フィールド](using/reports/sharing-execution-fields.md)
         + [データ取得フィールド](using/reports/sharing-fetch-fields.md)
         + [ID フィールド](using/reports/sharing-identity-fields.md)
      + [クエリの例](using/reports/query-examples.md)
   + 配信品質 {#deliverability}
      + [配信品質の基本を学ぶ](using/reports/deliverability.md)
      + [抑制リストについて](using/reports/suppression-list.md)
   + [アラート](using/reports/alerts.md)
   + [Customer Journey Analytics の操作](using/reports/cja-ajo.md)
+ 意志決定管理 {#offer-decisioning}
   + 意思決定管理の基本を学ぶ {#get-started-decision}

      + [意思決定管理について](using/offers/get-started/starting-offer-decisioning.md)
      + [ユーザーインターフェイス](using/offers/get-started/user-interface.md)
      + [オファーを作成および管理するための主な手順](using/offers/offer-library/key-steps.md)
      + [ユースケース：メールへのオファーの挿入](using/offers/offers-e2e.md)
   + コンポーネントの作成 {#create-components}
      + [プレースメントの作成](using/offers/offer-library/creating-placements.md)
      + [決定ルールの作成](using/offers/offer-library/creating-decision-rules.md)
      + [タグの作成](using/offers/offer-library/creating-tags.md)
   + ランキングの作成 {#rankings}
      + [ランキングの基本を学ぶ](using/offers/ranking/get-started-rankings.md)
      + [ランキング式](using/offers/ranking/create-ranking-formulas.md)
      + AI モデル {#ai-models}
         + [AI モデルについて](using/offers/ranking/ai-models.md)
         + AI モデルタイプ {#ai-model-types}
            + [自動最適化モデル](using/offers/ranking/auto-optimization-model.md)
            + [パーソナライズされた最適化モデル](using/offers/ranking/personalized-optimization-model.md)
         + AI モデルの作成 {#configure-ai-model}
            + [イベントを収集するデータセットの作成](using/offers/ranking/create-dataset.md)
            + [AI モデルの作成](using/offers/ranking/create-ranking-strategies.md)
            + [イベントキャプチャの設定](using/offers/ranking/schema-requirement.md)
   + オファーの作成と管理 {#managing-offers-in-the-offer-library}
      + オファーの設定 {#configure-offers}
         + [パーソナライズされたオファーの作成](using/offers/offer-library/creating-personalized-offers.md)
         + [表示域を追加](using/offers/offer-library/add-representations.md)
         + [制約を追加](using/offers/offer-library/add-constraints.md)
      + [フォールバックオファーの作成](using/offers/offer-library/creating-fallback-offers.md)
      + [コレクションの作成](using/offers/offer-library/creating-collections.md)
   + 決定の作成と管理 {#create-manage-activities}
      + [決定の作成](using/offers/offer-activities/create-offer-activities.md)
      + [決定でのオファー選択の設定](using/offers/offer-activities/configure-offer-selection.md)
      + [シミュレーションの作成](using/offers/offer-activities/simulation.md)
   + [Batch Decisioning](using/offers/batch-delivery.md)
   + 意思決定管理レポートの作成 {#create-reports}
      + [意思決定管理イベントの概要](using/offers/reports/get-started-events.md)
      + [意思決定管理イベントの主な情報](using/offers/reports/key-information.md)
      + [イベントの XDM フィールドへのアクセス](using/offers/reports/xdm-fields.md)
   + オファーカタログのエクスポート{#export-catalog}
      + [オファーカタログエクスポートの基本を学ぶ ](using/offers/export-catalog/get-started-export.md)
      + [書き出したオファーカタログへのアクセス](using/offers/export-catalog/access-dataset.md)
      + [パーソナライズされたオファーのデータセット](using/offers/export-catalog/export-offers.md)
      + [決定データセット](using/offers/export-catalog/export-decisions.md)
      + [プレースメントデータセット](using/offers/export-catalog/export-placements.md)
      + [フォールバックデータセット](using/offers/export-catalog/export-fallback.md)
   + API リファレンス{#api-reference}
      + [はじめに](using/offers/api-reference/getting-started.md)
      + API を使用したオファーの作成と管理 {#offers-api}
         + プレースメント {#placements}
            + [プレースメントのリスト](using/offers/api-reference/offers-api/placements/placements-list.md)
            + [プレースメントの参照](using/offers/api-reference/offers-api/placements/lookup.md)
            + [プレースメントの作成](using/offers/api-reference/offers-api/placements/create.md)
            + [プレースメントの更新](using/offers/api-reference/offers-api/placements/update.md)
            + [プレースメントの削除](using/offers/api-reference/offers-api/placements/delete.md)
         + 決定ルール{#decision-rules}
            + [決定ルールのリスト](using/offers/api-reference/offers-api/decision-rules/rules-list.md)
            + [決定ルールの参照](using/offers/api-reference/offers-api/decision-rules/lookup.md)
            + [決定ルールの作成](using/offers/api-reference/offers-api/decision-rules/create.md)
            + [決定ルールの更新](using/offers/api-reference/offers-api/decision-rules/update.md)
            + [決定ルールの削除](using/offers/api-reference/offers-api/decision-rules/delete.md)
         + タグ{#tags}
            + [タグのリスト](using/offers/api-reference/offers-api/tags/tags-list.md)
            + [タグの参照](using/offers/api-reference/offers-api/tags/lookup.md)
            + [タグの作成](using/offers/api-reference/offers-api/tags/create.md)
            + [タグの更新](using/offers/api-reference/offers-api/tags/update.md)
            + [タグの削除](using/offers/api-reference/offers-api/tags/delete.md)
         + パーソナライズされたオファー{#personalized-offers}
            + [パーソナライズされたオファーのリスト](using/offers/api-reference/offers-api/personalized-offers/offers-list.md)
            + [パーソナライズされたオファーの参照](using/offers/api-reference/offers-api/personalized-offers/lookup.md)
            + [パーソナライズされたオファーの作成](using/offers/api-reference/offers-api/personalized-offers/create.md)
            + [パーソナライズされたオファーの更新](using/offers/api-reference/offers-api/personalized-offers/update.md)
            + [パーソナライズされたオファーの削除](using/offers/api-reference/offers-api/personalized-offers/delete.md)
         + コレクション{#collections}
            + [コレクションのリスト](using/offers/api-reference/offers-api/collections/collections-list.md)
            + [コレクションの参照](using/offers/api-reference/offers-api/collections/lookup.md)
            + [コレクションの作成](using/offers/api-reference/offers-api/collections/create.md)
            + [コレクションの更新](using/offers/api-reference/offers-api/collections/update.md)
            + [コレクションの削除](using/offers/api-reference/offers-api/collections/delete.md)
         + フォールバックオファー{#fallback-offers}
            + [フォールバックオファーのリスト](using/offers/api-reference/offers-api/fallback-offers/fallback-list.md)
            + [フォールバックオファーの参照](using/offers/api-reference/offers-api/fallback-offers/lookup.md)
            + [フォールバックオファーの作成](using/offers/api-reference/offers-api/fallback-offers/create.md)
            + [フォールバックオファーの更新](using/offers/api-reference/offers-api/fallback-offers/update.md)
            + [フォールバックオファーの削除](using/offers/api-reference/offers-api/fallback-offers/delete.md)
      + API を使用した決定の作成と管理{#activities-api}
         + [決定のリスト](using/offers/api-reference/activities-api/activities/activities-list.md)
         + [決定の参照](using/offers/api-reference/activities-api/activities/lookup.md)
         + [決定の作成](using/offers/api-reference/activities-api/activities/create.md)
         + [決定の更新](using/offers/api-reference/activities-api/activities/update.md)
         + [決定の削除](using/offers/api-reference/activities-api/activities/delete.md)
      + API を使用したオファーの配信 {#offer-delivery-api}
         + [オファー配信 API の基本を学ぶ](using/offers/api-reference/offer-delivery-api/start-offer-delivery-apis.md)
         + [Decisioning API](using/offers/api-reference/offer-delivery-api/decisioning-api.md)
         + [Edge Decisioning API](using/offers/api-reference/offer-delivery-api/edge-decisioning-api.md)
         + [Batch Decisioning API](using/offers/api-reference/offer-delivery-api/batch-decisioning-api.md)
+ データ管理 {#data-management}
   + [データ管理の基本を学ぶ](using/data/gs-data.md)
   + [スキーマの操作](using/data/get-started-schemas.md)
   + [クエリ](using/data/get-started-queries.md)
   + Journey Optimizer データセット {#datasets}
      + [データセットの基本を学ぶ](using/data/get-started-datasets.md)
      + [クエリの例](using/data/datasets-query-examples.md)
+ 設定 {#configuration}
   + [Journey Optimizer の設定の基本を学ぶ](using/configuration/get-started-configuration.md)
   + メールサブドメインのデリゲート {#delegate-subdomains}
      + [サブドメインデリゲーションの基本を学ぶ](using/configuration/about-subdomain-delegation.md)
      + [サブドメインのデリゲート](using/configuration/delegate-subdomain.md)
      + [Google TXT レコードの追加](using/configuration/google-txt.md)
      + [PTR レコードへのアクセスと編集](using/configuration/ptr-records.md)
      + [IP プールの作成](using/configuration/ip-pools.md)
   + [チャネルサーフェスの設定](using/configuration/channel-surfaces.md)
   + メールアドレスの監視 {#monitor-reputation}
      + [抑制リスト](using/configuration/manage-suppression-list.md)
      + [再試行](using/configuration/retries.md)
      + [許可リスト](using/configuration/allow-list.md)
   + [アーカイブのサポート](using/configuration/archiving-support.md)
   + [頻度ルールの設定](using/configuration/frequency-rules.md)
   + [実行アドレスの管理](using/configuration/primary-email-addresses.md)
   + ジャーニーの設定 {#configure-journeys}
      + [データソース、イベント、アクションについて](using/configuration/about-data-sources-events-actions.md)
      + [外部システムとの統合](using/configuration/external-systems.md)
      + イベント設定 {#events-journeys}
         + [一般原則](using/event/about-events.md)
         + 単一イベントの設定 {#unitary-events}
            + [単一イベントの基本を学ぶ](using/event/about-creating.md)
            + [ExperienceEvent スキーマについて](using/event/experience-event-schema.md)
            + [Adobe Analytics の活用](using/event/about-analytics.md)
         + [ビジネスイベントの設定](using/event/about-creating-business.md)
         + [イベントを送信するための手順](using/event/additional-steps-to-send-events-to-journey.md)
      + データソース設定{#data-source-journeys}
         + [データソースについて](using/datasource/about-data-sources.md)
         + [データソースの設定](using/datasource/configure-data-sources.md)
         + [Adobe Experience Platform のデータソース](using/datasource/adobe-experience-platform-data-source.md)
         + [外部データソース](using/datasource/external-data-sources.md)
      + アクション設定 {#action-journeys}
         + [アクションについて](using/action/action.md)
         + [アクションの設定](using/action/about-custom-action-configuration.md)
         + [Adobe Campaign Standard との統合](using/action/acs-action.md)
         + [Adobe Campaign v7／v8 との統合](using/action/acc-action.md)
   + [ソース](using/start/get-started-sources.md)
+ アクセス制御 {#access-control}
   + [アクセス制御の概要](using/administration/permissions-overview.md)
   + [ビルトインの製品プロファイル](using/administration/ootb-product-profiles.md)
   + [ユーザーと製品プロファイルの管理](using/administration/permissions.md)
   + [権限レベル](using/administration/high-low-permissions.md)
   + [サンドボックス管理](using/administration/sandboxes.md)
   + [属性ベースのアクセス制御](using/administration/attribute-based-access.md)
   + [オブジェクトレベルのアクセス制御](using/administration/object-based-access.md)
+ プライバシー {#privacy}
   + [プライバシーの基本を学ぶ](using/privacy/get-started-privacy.md)
   + [プライバシーリクエスト](using/privacy/requests.md)
   + [ リソースに対する監査アクション](using/privacy/audit-logs.md)
   + [データハイジーン操作の実行](using/privacy/data-hygiene.md)
   + 同意の管理 {#consent}
      + [オプトアウトの管理](using/privacy/opt-out.md)
      + [同意ポリシーの使用](using/action/consent.md)
   + [データガバナンス](using/action/action-privacy.md)
