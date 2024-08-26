---
product: Journey Optimizer
audience: end-user
user-guide-title: Journey Optimizer ガイド
user-guide-description: Journey Optimizer を使用して、連続性があり、コンキストに即してパーソナライズされたエクスペリエンスを構築し、顧客に提供します。
type: Documentation
solution: Journey Optimizer
source-git-commit: 8fb87d2e2085d98dd8b014df6aa4d734bab4e997
workflow-type: tm+mt
source-wordcount: '1972'
ht-degree: 97%

---

# Adobe Journey Optimizer ヘルプ {#using}

+ [Journey Optimizer ドキュメント](ajo-home.md)
+ 新着情報 {#whats-new}
   + [早期リリースノート](using/rn/e-release-notes.md)
   + [最新のリリースノート](using/rn/release-notes.md)
   + 以前のリリースノート {#previous-rn-new}
      + [2024年](using/rn/release-notes-2024.md)
      + [2023年](using/rn/release-notes-2023.md)
      + [2022年](using/rn/release-notes-2022.md)
      + [2021年](using/rn/release-notes-2021.md)
   + [ドキュメントの更新](using/rn/documentation-updates.md)
   + [ジャーニーキャンバスの改善](using/rn/new-canvas.md)
+ はじめに {#get-started}
   + [Journey Optimizer について](using/start/get-started.md)
   + クイックスタートガイド{#quick-start}
      + [概要](using/start/quick-start.md)
      + [マーケター向けの基本を学ぶ](using/start/path/marketer.md)
      + [データエンジニア向けの基本を学ぶ](using/start/path/data-engineer.md)
      + [管理者向けの基本を学ぶ](using/start/path/administrator.md)
      + [開発者向けの基本を学ぶ](using/start/path/developer.md)
   + [ユーザーインターフェイス](using/start/user-interface.md)
   + [検索、フィルター、分類](using/start/search-filter-categorize.md)
   + [アクセシビリティ](using/start/accessibility.md)
   + [ユースケースプレイブック](using/start/playbooks.md)
   + [AI アシスタントの操作](using/start/ai-assistant.md)
   + [統合](using/start/ajo-integrations.md)
   + [ガードレール](using/start/guardrails.md)
   + [ベストプラクティス](using/start/best-practices.md)
+ ジャーニー {#orchestrate-journeys}
   + [ジャーニーの基本を学ぶ](using/building-journeys/journey.md)
   + ジャーニーの作成{#create-journey}
      + [初めてのジャーニーの作成](using/building-journeys/journey-gs.md)
      + [ジャーニーのプロパティの設定](using/building-journeys/journey-properties.md)
      + [ジャーニーのデザイン](using/building-journeys/using-the-journey-designer.md)
      + [ジャーニーのテスト](using/building-journeys/testing-the-journey.md)
      + [ジャーニーのシミュレート](using/building-journeys/journey-simulation.md)
      + [ジャーニーの公開](using/building-journeys/publishing-the-journey.md)
   + ジャーニーの管理{#manage-journey}
      + [プロファイルエントリ管理](using/building-journeys/entry-management.md)
      + [タイムゾーン管理](using/building-journeys/timezone-management.md)
      + [ジャーニーの終了](using/building-journeys/end-journey.md)
      + [別のサンドボックスへのジャーニーのコピー](using/building-journeys/copy-to-sandbox.md)
      + [ジャーニーのトラブルシューティング](using/building-journeys/troubleshooting.md)
      + [インテリジェントサービスとの統合](using/building-journeys/ai-services-overview.md)
   + アクティビティ {#about-journey-building}
      + [ジャーニーのアクティビティの基本を学ぶ](using/building-journeys/about-journey-activities.md)
      + [一般イベント](using/building-journeys/general-events.md)
      + [反応](using/building-journeys/reaction-events.md)
      + [オーディエンスの選定](using/building-journeys/audience-qualification-events.md)
      + [条件](using/building-journeys/condition-activity.md)
      + [待機](using/building-journeys/wait-activity.md)
      + [オーディエンスを読み取り](using/building-journeys/read-audience.md)
      + [メール, アプリ内, プッシュ, SMS](using/building-journeys/journeys-message.md)
      + [カスタムアクション](using/building-journeys/using-custom-actions.md)
      + [Adobe Campaign Standard のアクション](using/building-journeys/using-adobe-campaign-standard.md)
      + [Adobe Campaign v7／v8 のアクション](using/building-journeys/using-adobe-campaign-v7-v8.md)
      + [ジャンプ](using/building-journeys/jump.md)
      + [プロファイルを更新](using/building-journeys/update-profiles.md)
   + 式の作成 {#building-advanced-conditions-journeys}
      + [高度な式エディターの操作](using/building-journeys/expression/expressionadvanced.md)
      + 構文 {#syntax}
         + [高度な式エディターの構文](using/building-journeys/expression/generalities.md)
         + [条件付き手順](using/building-journeys/expression/conditional-instruction.md)
         + [データタイプ](using/building-journeys/expression/data-types.md)
         + [フィールド参照](using/building-journeys/expression/field-references.md)
         + [コレクション管理関数](using/building-journeys/expression/collection-management-functions.md)
         + [演算子](using/building-journeys/expression/operators.md)
         + [ジャーニーのプロパティ](using/building-journeys/expression/journey-properties.md)
         + [例](using/building-journeys/expression/advanced-editor-use-cases.md)
      + 関数 {#main-functions-journey}
         + [主な関数](using/building-journeys/expression/functions.md)
         + Adobe Experience Platform {#adobe-experience-platform}
            + [inAudience](using/building-journeys/functions/functioninaudience.md)
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
         + [カスタムアクションを使用した Experience Platform のジャーニーイベントの書き込み](using/building-journeys/custom-action-aep.md)
+ キャンペーン{#campaigns}
   + [キャンペーンの基本を学ぶ](using/campaigns/get-started-with-campaigns.md)
   + [キャンペーンの作成](using/campaigns/create-campaign.md)
   + [キャンペーンのレビューとアクティブ化](using/campaigns/review-activate-campaign.md)
   + [キャンペーンの管理](using/campaigns/modify-stop-campaign.md)
   + [API を使用したキャンペーンのトリガー](using/campaigns/api-triggered-campaigns.md)
+ メールチャネル {#email}
   + [メールの基本を学ぶ](using/email/get-started-email.md)
   + [メールの作成](using/email/create-email.md)
   + メールコンテンツのデザイン {#design-email}
      + [メールデザインの基本を学ぶ](using/email/get-started-email-design.md)
      + コンテンツ作成の開始 {#start-creating-content}
         + [コンテンツのゼロからのデザイン](using/email/content-from-scratch.md)
         + [コンテンツの読み込み](using/email/existing-content.md)
         + [コンテンツを独自にコーディング](using/email/code-content.md)
         + [メールテンプレートを使用](using/email/use-email-templates.md)
      + コンテンツのデザイン {#add-content}
         + [コンテンツコンポーネントの使用](using/email/content-components.md)
         + [ビジュアルフラグメントを活用](using/email/use-visual-fragments.md)
         + [リンクの追加とメッセージの追跡](using/email/message-tracking.md)
         + [パーソナライズされたオファーの挿入](using/email/add-offers-email.md)
         + [テキストバージョンの生成](using/email/text-version-email.md)
         + [プリヘッダーを追加](using/email/preheader.md)
      + スタイルの編集 {#edit-style}
         + [メールスタイルの基本を学ぶ](using/email/get-started-email-style.md)
         + [背景設定の編集](using/email/backgrounds.md)
         + [垂直方向の整列とパディングを調整する](using/email/alignment-and-padding.md)
         + [インラインのスタイル属性の追加](using/email/inline-styling.md)
   + [Experience Manager テンプレートの使用](using/email/aem-templates.md)
   + [メールオプトアウトの管理](using/email/email-opt-out.md)
   + メールチャネルの設定 {#configure-email}
      + [メール設定の基本を学ぶ](using/email/get-started-email-config.md)
      + [メール設定を指定](using/email/email-settings.md)
      + [メール設定のパーソナライズ](using/email/surface-personalization.md)
+ アプリ内チャネル{#in-app}
   + [アプリ内チャネルの基本を学ぶ](using/in-app/get-started-in-app.md)
   + [アプリ内チャネルの前提条件](using/in-app/inapp-configuration.md)
   + [モバイルアプリ内メッセージの作成](using/in-app/create-in-app.md)
   + [Web アプリ内メッセージの作成](using/in-app/create-in-app-web.md)
   + [アプリ内コンテンツのデザイン](using/in-app/design-in-app.md)
   + [アプリ内通知の確認および送信](using/in-app/send-in-app.md)
+ プッシュ通知チャネル{#push}
   + [プッシュ通知の基本を学ぶ](using/push/get-started-push.md)
   + [プッシュ通知の作成](using/push/create-push.md)
   + [プッシュ通知のデザイン](using/push/design-push.md)
   + [プッシュ通知の確認と送信](using/push/send-push.md)
   + プッシュ通知の設定{#push-config}
      + [プッシュ通知フロー](using/push/push-gs.md)
      + [プッシュ通知チャネルの設定](using/push/push-configuration.md)
      + [モバイルオンボーディングのクイックスタートワークフロー](using/push/mobile-onboarding-wf.md)
+ SMS／MMS チャネル{#sms}
   + [テキストメッセージの基本を学ぶ](using/sms/get-started-sms.md)
   + [テキストメッセージ（SMS／MMS）の作成](using/sms/create-sms.md)
   + [テキストメッセージの確認および送信](using/sms/send-sms.md)
   + [テキストメッセージのオプトアウトの管理](using/sms/sms-opt-out.md)
   + [SMS サブドメインの設定](using/sms/sms-subdomains.md)
   + SMS／MMS チャネルの設定{#configure-sms}
      + [SMS 設定の基本を学ぶ](using/sms/sms-configuration.md)
      + [Sinch プロバイダーの設定](using/sms/sms-configuration-sinch.md)
      + [Infobip プロバイダーの設定](using/sms/sms-configuration-infobip.md)
      + [Twilio プロバイダーの設定](using/sms/sms-configuration-twilio.md)
      + [カスタムプロバイダーの設定（ベータ版）](using/sms/sms-configuration-custom.md)
      + [SMS 設定の作成](using/sms/sms-configuration-surface.md)
+ ダイレクトメール {#direct-mail}
   + [ダイレクトメールの基本を学ぶ](using/direct-mail/get-started-direct-mail.md)
   + [ダイレクトメールの作成](using/direct-mail/create-direct-mail.md)
   + [ダイレクトメールメッセージの確認と送信](using/direct-mail/test-send-direct-mail.md)
   + [ダイレクトメールの設定](using/direct-mail/direct-mail-configuration.md)
+ Web チャネル {#web}
   + [Web チャネルの基本を学ぶ](using/web/get-started-web.md)
   + Web チャネルを設定 {#configure-web-channel}
      + [Web チャネルの前提条件](using/web/web-prerequisites.md)
      + [Web サブドメインの設定](using/web/web-delegated-subdomains.md)
      + [Web チャネル設定の作成](using/web/web-configuration.md)
   + [Web エクスペリエンスの作成](using/web/create-web.md)
   + Web ページの作成 {#author-web-pages}
      + [Web ページコンテンツの編集](using/web/edit-web-content.md)
      + [変更の管理](using/web/manage-web-modifications.md)
      + [Web キャンペーンの監視](using/web/monitor-web-campaigns.md)
      + [シングルページアプリケーションの作成](using/web/web-spa.md)
+ コードベースのエクスペリエンス {#code-based-experience}
   + [コードベースチャネルの基本を学ぶ](using/code-based/get-started-code-based.md)
   + [ガードレールと前提条件](using/code-based/code-based-prerequisites.md)
   + [コードベースのエクスペリエンス設定の作成](using/code-based/code-based-configuration.md)
   + [実装方法のサンプル](using/code-based/code-based-implementation-samples.md)
   + [コードベースエクスペリエンスを作成](using/code-based/create-code-based.md)
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
+ コンテンツ管理 {#content-management}
   + AI アシスタントの操作{#ai-assistant}
      + [AI アシスタントの基本を学ぶ](using/content-management/gs-generative.md)
      + [メールの生成](using/content-management/generative-email.md)
      + [プッシュの生成](using/content-management/generative-push.md)
      + [SMS の生成](using/content-management/generative-sms.md)
      + [AI アシスタントを使用したコンテンツ実験](using/content-management/generative-experimentation.md)
   + 多言語コンテンツの操作 {#content-multilingual}
      + [多言語コンテンツの基本を学ぶ](using/content-management/multilingual-gs.md)
      + [手動翻訳を使用した多言語コンテンツの作成](using/content-management/multilingual-manual.md)
      + [自動翻訳を使用した多言語コンテンツの作成](using/content-management/multilingual-automated.md)
   + コンテンツ実験の操作 {#content-experiment}
      + [コンテンツ実験の基本を学ぶ](using/content-management/get-started-experiment.md)
      + [コンテンツ実験を作成](using/content-management/content-experiment.md)
      + [実験レポートの設定](using/content-management/reporting-configuration.md)
      + テクニカルノート {#technotes}
         + [統計計算について](using/content-management/experiment-calculations.md)
         + [実験レポートの統計計算について](using/content-management/experiment-report-calculations.md)
   + Assets／画像 {#assets-images}
      + [Experience Manager Assets の操作](using/content-management/assets.md)
      + [Adobe Stock との連携](using/content-management/stock.md)
   + パーソナライズ機能 {#personalization}
      + [パーソナライゼーションの基本を学ぶ](using/personalization/personalize.md)
      + [パーソナライゼーションのコンテキスト](using/personalization/personalization-contexts.md)
      + [パーソナライゼーション構文](using/personalization/personalization-syntax.md)
      + [パーソナライゼーションに関する Adobe Experience Platform データの使用](using/personalization/lookup-aep-data.md)
      + パーソナライゼーションエディターの操作 {#expression-editor}
         + [パーソナライゼーションエディターについて](using/personalization/personalization-build-expressions.md)
         + [お気に入りに属性を追加](using/personalization/personalization-favorites.md)
         + [式フラグメントを使用](using/personalization/use-expression-fragments.md)
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
      + パーソナライズ機能のユースケース{#personalization-use-cases}
         + [注文ステータスの通知](using/personalization/personalization-use-case.md)
         + [買い物かご放棄に関するメール](using/personalization/personalization-use-case-helper-functions.md)
         + [医療保険処方箋のメール](using/personalization/perso-uc-plan-prescriptions.md)
   + コンテンツテンプレート {#content-templates}
      + [コンテンツテンプレートの基本を学ぶ](using/content-management/content-templates.md)
      + [テンプレートへのアクセスと管理](using/content-management/access-content-templates.md)
      + [コンテンツテンプレートの作成](using/content-management/create-content-templates.md)
      + [コンテンツテンプレートのテスト](using/content-management/test-content-templates.md)
      + [コンテンツテンプレートの使用](using/content-management/use-content-templates.md)
   + 再利用可能なコンテンツフラグメント {#fragments}
      + [フラグメントの基本を学ぶ](using/content-management/fragments.md)
      + [フラグメントを作成](using/content-management/create-fragments.md)
      + [既存のコンテンツをフラグメントとして保存](using/content-management/save-fragments.md)
      + [カスタマイズ可能なフラグメント](using/content-management/customizable-fragments.md)
      + [フラグメントを管理](using/content-management/manage-fragments.md)
   + 動的コンテンツ {#dynamic}
      + [動的コンテンツの基本を学ぶ](using/personalization/get-started-dynamic-content.md)
      + [条件付きルールの作成](using/personalization/create-conditions.md)
      + [動的コンテンツの作成](using/personalization/dynamic-content.md)
   + コンテンツのプレビューとテスト {#preview-test}
      + [プレビューとテストの基本を学ぶ](using/content-management/preview-test.md)
      + [テストプロファイルを選択](using/content-management/test-profiles.md)
      + [コンテンツのプレビュー](using/content-management/preview.md)
      + [メール配達確認を送信](using/content-management/proofs.md)
      + [メールのレンダリングをテスト](using/content-management/rendering.md)
      + [メールスパムレポート](using/content-management/spam-report.md)
+ オーディエンス、プロファイル、ID{#audiences-profiles-identities}
   + オーディエンス {#audiences}
      + [オーディエンスの基本を学ぶ](using/audience/about-audiences.md)
      + [セグメント定義の作成](using/audience/creating-a-segment-definition.md)
      + オーディエンスの作成 {#audience-orchestration}
         + [オーディエンス構成の基本を学ぶ](using/audience/get-started-audience-orchestration.md)
         + [コンポジションワークフローの作成](using/audience/create-compositions.md)
         + [コンポジションキャンバスの操作](using/audience/composition-canvas.md)
         + [オーディエンスへのアクセスと管理](using/audience/access-audiences.md)
      + [連合オーディエンス構成（限定提供）](https://experienceleague.adobe.com/ja/docs/federated-audience-composition/using/home)
   + プロファイル{#profiles}
      + [プロファイルの基本を学ぶ](using/audience/get-started-profiles.md)
      + [テストプロファイルの作成](using/audience/creating-test-profiles.md)
      + [計算属性の操作](using/audience/computed-attributes.md)
   + [ID](using/audience/get-started-identity.md)
   + [ライセンス使用状況](using/audience/license-usage.md)
+ トラッキングとモニタリング {#reporting}
   + ライブレポート {#live-report}
      + [ライブレポートの概要](using/reports/live-report.md)
      + [コンポーネントのリスト](using/reports/live-report-components.md)
      + [ジャーニーライブレポート](using/reports/journey-live-report.md)
      + [キャンペーンのライブレポート](using/reports/campaign-live-report.md)
      + [ランディングページライブレポート](using/reports/lp-report-live.md)
      + [購読リストライブレポート](using/reports/subscription-report-live.md)
   + グローバルレポート {#global-report}
      + [グローバルレポートの基本を学ぶ](using/reports/global-report.md)
      + [コンポーネントのリスト](using/reports/global-report-components.md)
      + [ジャーニーのグローバルレポート](using/reports/journey-global-report.md)
      + [キャンペーンのグローバルレポート](using/reports/campaign-global-report.md)
      + [目標レポート](using/reports/objective-report.md)
      + [ランディングページグローバルレポート](using/reports/lp-report-global.md)
      + [購読リストグローバルレポート](using/reports/subscription-report-global.md)
   + チャネルレポート {#channel-report}
      + [チャネルレポートの基本を学ぶ](using/reports/channel-report-gs.md)
      + [チャネルレポート](using/reports/channel-report.md)
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
      + [新しい DMARC 要件](using/configuration/dmarc-record-update.md)
   + [アラート](using/reports/alerts.md)
   + [Customer Journey Analytics の操作](using/reports/cja-ajo.md)
   + [除外の理由](using/reports/exclusion-list.md)
+ 新しいレポートインターフェイス（LA）{#channel-report}
   + [新しいレポートインターフェイスの基本を学ぶ](using/reports/report-gs-cja.md)
   + [レポートの管理](using/reports/report-cja-manage.md)
   + [ジャーニーレポート](using/reports/journey-global-report-cja.md)
   + [キャンペーンレポート](using/reports/campaign-global-report-cja.md)
   + [概要レポート](using/reports/channel-report-cja.md)
   + [ランディングページのレポート](using/reports/lp-report-global-cja.md)
   + [購読リストのレポート](using/reports/subscription-report-global-cja.md)
+ 決定 {#decisioning}
   + 意思決定管理 {#offer-decisioning}
      + 意思決定管理の基本を学ぶ {#get-started-decision}

         + [意思決定管理について](using/offers/get-started/starting-offer-decisioning.md)
         + [ユーザーインターフェイス](using/offers/get-started/user-interface.md)
         + [オファーを作成および管理するための主な手順](using/offers/offer-library/key-steps.md)
         + [ユースケース：メールへのオファーの挿入](using/offers/offers-e2e.md)
      + コンポーネントの作成 {#create-components}
         + [プレースメントの作成](using/offers/offer-library/creating-placements.md)
         + [決定ルールの作成](using/offers/offer-library/creating-decision-rules.md)
         + [コレクション修飾子の作成](using/offers/offer-library/creating-tags.md)
      + ランキングの作成 {#rankings}
         + [ランキングの基本を学ぶ](using/offers/ranking/get-started-rankings.md)
         + [ランキング式](using/offers/ranking/create-ranking-formulas.md)
         + AI モデル {#ai-models}
            + [AI モデルについて](using/offers/ranking/ai-models.md)
            + AI モデルタイプ {#ai-model-types}
            + [自動最適化モデル](using/offers/ranking/auto-optimization-model.md)
            + [パーソナライズされた最適化モデル](using/offers/ranking/personalized-optimization-model.md)
            + [AI モデルの作成](using/offers/ranking/create-ranking-strategies.md)
      + オファーの作成と管理 {#managing-offers-in-the-offer-library}
         + オファーの設定 {#configure-offers}
            + [パーソナライズされたオファーの作成](using/offers/offer-library/creating-personalized-offers.md)
            + [表示域を追加](using/offers/offer-library/add-representations.md)
            + [制約を追加](using/offers/offer-library/add-constraints.md)
         + [フォールバックオファーを作成](using/offers/offer-library/creating-fallback-offers.md)
         + [コレクションの作成](using/offers/offer-library/creating-collections.md)
      + 決定の作成と管理 {#create-manage-activities}
         + [決定の作成](using/offers/offer-activities/create-offer-activities.md)
         + [決定でのオファー選択の設定](using/offers/offer-activities/configure-offer-selection.md)
         + [シミュレーションを作成](using/offers/offer-activities/simulation.md)
      + [Batch Decisioning の使用](using/offers/batch-delivery.md)
      + イベントデータの収集 {#collect-event-data}
         + [データ収集の基本を学ぶ](using/offers/data-collection/data-collection.md)
         + [イベントを収集するデータセットの作成](using/offers/data-collection/create-dataset.md)
         + [イベントキャプチャの設定](using/offers/data-collection/schema-requirement.md)
      + 意思決定管理レポートの作成 {#create-reports}
         + [意思決定管理イベントの操作](using/offers/reports/get-started-events.md)
         + [イベントの XDM フィールドへのアクセス](using/offers/reports/xdm-fields.md)
      + オファーカタログのエクスポート{#export-catalog}
         + [オファーカタログエクスポートの基本を学ぶ](using/offers/export-catalog/get-started-export.md)
         + [書き出したオファーカタログへのアクセス](using/offers/export-catalog/access-dataset.md)
         + [パーソナライズされたオファーデータセット](using/offers/export-catalog/export-offers.md)
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
            + コレクション修飾子 {#tags}
               + [コレクション修飾子のリスト](using/offers/api-reference/offers-api/tags/tags-list.md)
               + [コレクション修飾子の参照](using/offers/api-reference/offers-api/tags/lookup.md)
               + [コレクション修飾子の作成](using/offers/api-reference/offers-api/tags/create.md)
               + [コレクション修飾子の更新](using/offers/api-reference/offers-api/tags/update.md)
               + [コレクション修飾子の削除](using/offers/api-reference/offers-api/tags/delete.md)
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
               + [フォールバックオファーを作成](using/offers/api-reference/offers-api/fallback-offers/create.md)
               + [フォールバックオファーの更新](using/offers/api-reference/offers-api/fallback-offers/update.md)
               + [フォールバックオファーの削除](using/offers/api-reference/offers-api/fallback-offers/delete.md)
            + 決定 {#decisions-api}
               + [決定のリスト](using/offers/api-reference/activities-api/activities/activities-list.md)
               + [決定の参照](using/offers/api-reference/activities-api/activities/lookup.md)
               + [決定の作成](using/offers/api-reference/activities-api/activities/create.md)
               + [決定の更新](using/offers/api-reference/activities-api/activities/update.md)
               + [決定の削除](using/offers/api-reference/activities-api/activities/delete.md)
            + レガシー API {#legacy-api}
               + [レガシー API について](using/offers/api-reference/offers-api/legacy-apis/about-legacy-apis.md)
               + プレースメント {#placements}
                  + [プレースメントのリスト](using/offers/api-reference/offers-api/legacy-apis/placements/placements-list.md)
                  + [プレースメントの参照](using/offers/api-reference/offers-api/legacy-apis/placements/lookup.md)
                  + [プレースメントの作成](using/offers/api-reference/offers-api/legacy-apis/placements/create.md)
                  + [プレースメントの更新](using/offers/api-reference/offers-api/legacy-apis/placements/update.md)
                  + [プレースメントの削除](using/offers/api-reference/offers-api/legacy-apis/placements/delete.md)
               + 決定ルール{#decision-rules}
                  + [決定ルールのリスト](using/offers/api-reference/offers-api/legacy-apis/decision-rules/rules-list.md)
                  + [決定ルールの参照](using/offers/api-reference/offers-api/legacy-apis/decision-rules/lookup.md)
                  + [決定ルールの作成](using/offers/api-reference/offers-api/legacy-apis/decision-rules/create.md)
                  + [決定ルールの更新](using/offers/api-reference/offers-api/legacy-apis/decision-rules/update.md)
                  + [決定ルールの削除](using/offers/api-reference/offers-api/legacy-apis/decision-rules/delete.md)
               + コレクション修飾子 {#tags}
                  + [コレクション修飾子のリスト](using/offers/api-reference/offers-api/legacy-apis/tags/tags-list.md)
                  + [コレクション修飾子の参照](using/offers/api-reference/offers-api/legacy-apis/tags/lookup.md)
                  + [コレクション修飾子の作成](using/offers/api-reference/offers-api/legacy-apis/tags/create.md)
                  + [コレクション修飾子の更新](using/offers/api-reference/offers-api/legacy-apis/tags/update.md)
                  + [コレクション修飾子の削除](using/offers/api-reference/offers-api/legacy-apis/tags/delete.md)
               + パーソナライズされたオファー{#personalized-offers}
                  + [パーソナライズされたオファーのリスト](using/offers/api-reference/offers-api/legacy-apis/personalized-offers/offers-list.md)
                  + [パーソナライズされたオファーの参照](using/offers/api-reference/offers-api/legacy-apis/personalized-offers/lookup.md)
                  + [パーソナライズされたオファーの作成](using/offers/api-reference/offers-api/legacy-apis/personalized-offers/create.md)
                  + [パーソナライズされたオファーの更新](using/offers/api-reference/offers-api/legacy-apis/personalized-offers/update.md)
                  + [パーソナライズされたオファーの削除](using/offers/api-reference/offers-api/legacy-apis/personalized-offers/delete.md)
               + フォールバックオファー{#fallback-offers}
                  + [フォールバックオファーのリスト](using/offers/api-reference/offers-api/legacy-apis/fallback-offers/fallback-list.md)
                  + [フォールバックオファーの参照](using/offers/api-reference/offers-api/legacy-apis/fallback-offers/lookup.md)
                  + [フォールバックオファーを作成](using/offers/api-reference/offers-api/legacy-apis/fallback-offers/create.md)
                  + [フォールバックオファーの更新](using/offers/api-reference/offers-api/legacy-apis/fallback-offers/update.md)
                  + [フォールバックオファーの削除](using/offers/api-reference/offers-api/legacy-apis/fallback-offers/delete.md)
               + コレクション{#collections}
                  + [コレクションのリスト](using/offers/api-reference/offers-api/legacy-apis/collections/collections-list.md)
                  + [コレクションの参照](using/offers/api-reference/offers-api/legacy-apis/collections/lookup.md)
                  + [コレクションの作成](using/offers/api-reference/offers-api/legacy-apis/collections/create.md)
                  + [コレクションの更新](using/offers/api-reference/offers-api/legacy-apis/collections/update.md)
                  + [コレクションの削除](using/offers/api-reference/offers-api/legacy-apis/collections/delete.md)
               + 決定 {#decisions-api}
                  + [決定のリスト](using/offers/api-reference/offers-api/legacy-apis/activities-api/activities-list.md)
                  + [決定の参照](using/offers/api-reference/offers-api/legacy-apis/activities-api/lookup.md)
                  + [決定の作成](using/offers/api-reference/offers-api/legacy-apis/activities-api/create.md)
                  + [決定の更新](using/offers/api-reference/offers-api/legacy-apis/activities-api/update.md)
                  + [決定の削除](using/offers/api-reference/offers-api/legacy-apis/activities-api/delete.md)
         + API を使用したオファーの配信 {#offer-delivery-api}
            + [オファー配信 API の基本を学ぶ](using/offers/api-reference/offer-delivery-api/start-offer-delivery-apis.md)
            + [Decisioning API](using/offers/api-reference/offer-delivery-api/decisioning-api.md)
            + [Edge Decisioning API](using/offers/api-reference/offer-delivery-api/edge-decisioning-api.md)
            + [Batch Decisioning API](using/offers/api-reference/offer-delivery-api/batch-decisioning-api.md)
   + エクスペリエンス決定（LA）{#experience-decisioning}
      + [エクスペリエンス決定の基本を学ぶ](using/experience-decisioning/gs-experience-decisioning.md)
      + API リファレンス{#api-reference}
         + 決定項目{#decision-items}
            + [決定項目の作成](using/experience-decisioning/api-reference/decisions-items/create.md)
            + [決定項目リスト](using/experience-decisioning/api-reference/decisions-items/decision-items-list.md)
            + [決定項目の削除](using/experience-decisioning/api-reference/decisions-items/delete.md)
            + [決定項目の参照](using/experience-decisioning/api-reference/decisions-items/lookup.md)
            + [決定項目の更新](using/experience-decisioning/api-reference/decisions-items/update.md)
         + 項目コレクション{#items-collections}
            + [項目コレクションの作成](using/experience-decisioning/api-reference/items-collections/create.md)
            + [項目コレクションの削除](using/experience-decisioning/api-reference/items-collections/delete.md)
            + [項目コレクションリスト](using/experience-decisioning/api-reference/items-collections/items-collections-list.md)
            + [項目コレクションの参照](using/experience-decisioning/api-reference/items-collections/lookup.md)
            + [項目コレクションの更新](using/experience-decisioning/api-reference/items-collections/update.md)
         + 選択戦略{#selection-strategies}
            + [選択戦略の作成](using/experience-decisioning/api-reference/selection-strategies/create.md)
            + [選択戦略の削除](using/experience-decisioning/api-reference/selection-strategies/delete.md)
            + [選択戦略の参照](using/experience-decisioning/api-reference/selection-strategies/lookup.md)
            + [選択戦略リスト](using/experience-decisioning/api-reference/selection-strategies/selection-strategies-list.md)
            + [選択戦略の更新](using/experience-decisioning/api-reference/selection-strategies/update.md)
      + 決定項目の管理 {#decision-items}
         + [項目カタログの設定](using/experience-decisioning/catalogs.md)
         + [決定項目の作成](using/experience-decisioning/items.md)
         + [項目コレクションの管理](using/experience-decisioning/collections.md)
      + 項目の選択の設定 {#selection}
         + [決定ルールの作成](using/experience-decisioning/rules.md)
         + [ランキング方法の作成](using/experience-decisioning/ranking.md)
         + [コンテキストデータの活用](using/experience-decisioning/context-data.md)
      + [選択戦略の作成](using/experience-decisioning/selection-strategies.md)
      + [決定ポリシーを作成](using/experience-decisioning/create-decision.md)
      + [Customer Journey Analytics でのレポート](using/experience-decisioning/cja-reporting.md)
+ データ管理 {#data-management}
   + [データ管理の基本を学ぶ](using/data/gs-data.md)
   + [スキーマの操作](using/data/get-started-schemas.md)
   + Journey Optimizer データセット {#datasets}
      + [データセットの基本を学ぶ](using/data/get-started-datasets.md)
      + [Journey Optimizer データセットの書き出し](using/data/export-datasets.md)
      + [クエリの例](using/data/datasets-query-examples.md)
      + [ビルトインスキーマ／](https://experienceleague.adobe.com/tools/ajo-schemas/schema-dictionary.html?lang=ja)
   + [クエリ](using/data/get-started-queries.md)
+ 設定 {#configuration}
   + [Journey Optimizer の設定の基本を学ぶ](using/configuration/get-started-configuration.md)
   + [チャネル設定の指定](using/configuration/channel-surfaces.md)
   + ガイド付きチャネル設定 {#guided-setup}
      + [ガイド付きチャネル設定の基本を学ぶ](using/configuration/set-mobile-config.md)
      + [Android モバイルチャネルの設定](using/configuration/set-mobile-android.md)
      + [iOS モバイルチャネルの設定](using/configuration/set-mobile-ios.md)
      + [Web チャネルの設定](using/configuration/set-mobile-web.md)
   + メールサブドメインのデリゲート {#delegate-subdomains}
      + [サブドメインデリゲーションの基本を学ぶ](using/configuration/about-subdomain-delegation.md)
      + [サブドメインのデリゲート](using/configuration/delegate-subdomain.md)
      + [DMARC レコードの設定](using/configuration/dmarc-record.md)
      + [Google TXT レコードの追加](using/configuration/google-txt.md)
      + [PTR レコードへのアクセスと編集](using/configuration/ptr-records.md)
      + [IP プールの作成](using/configuration/ip-pools.md)
   + IP ウォームアッププランの実装 {#implement-ip-warmup-plan}
      + [IP ウォームアッププランの概要](using/configuration/ip-warmup-gs.md)
      + [IP ウォームアップキャンペーンを作成](using/configuration/ip-warmup-campaign.md)
      + [IP ウォームアッププランの作成](using/configuration/ip-warmup-plan.md)
      + [IP ウォームアッププランの実行](using/configuration/ip-warmup-execution.md)
      + [IP ウォームアッププランのファイル](using/configuration/ip-warmup-plan-files.md)
   + メールアドレスの監視 {#monitor-reputation}
      + [抑制リスト](using/configuration/manage-suppression-list.md)
      + [再試行](using/configuration/retries.md)
      + [許可リスト](using/configuration/allow-list.md)
   + [シードリストの使用](using/configuration/seed-lists.md)
   + [アーカイブのサポート](using/configuration/archiving-support.md)
   + [実行アドレスの変更](using/configuration/primary-email-addresses.md)
   + [ビジネスルールの設定](using/configuration/frequency-rules.md)
   + [ルールセットの操作](using/configuration/rule-sets.md)
   + ジャーニーの設定 {#configure-journeys}
      + [データソース、イベント、アクションについて](using/configuration/about-data-sources-events-actions.md)
      + 外部システムとの統合 {#external-systems}
         + [ジャーニーと外部システムとの統合](using/configuration/external-systems.md)
         + [Capping API](using/configuration/capping.md)
         + [Throttling API](using/configuration/throttling.md)
      + イベント設定 {#events-journeys}
         + [ジャーニーイベントの活用](using/event/about-events.md)
         + 単一イベントの設定 {#unitary-events}
            + [単一イベントの基本を学ぶ](using/event/about-creating.md)
            + [ExperienceEvent スキーマについて](using/event/experience-event-schema.md)
            + [Adobe Analytics の操作](using/event/about-analytics.md)
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
         + [カスタムアクションでの API 呼び出し応答の使用](using/action/action-response.md)
         + [Marketo Engage との統合](using/action/marketo-engage.md)
   + [ソース](using/start/get-started-sources.md)
+ アクセス制御 {#access-control}
   + アクセス制御の概要 {#privacy}
      + [ユーザー管理の基本を学ぶ](using/administration/permissions-overview.md)
      + [組み込みの役割](using/administration/ootb-product-profiles.md)
      + [組み込みの権限](using/administration/ootb-permissions.md)
      + [権限レベル](using/administration/high-low-permissions.md)
   + [ユーザーと役割の管理](using/administration/permissions.md)
   + [属性ベースのアクセス制御](using/administration/attribute-based-access.md)
   + [オブジェクトレベルのアクセス制御](using/administration/object-based-access.md)
   + [サンドボックス管理](using/administration/sandboxes.md)
+ プライバシー {#privacy}
   + [プライバシーの基本を学ぶ](using/privacy/get-started-privacy.md)
   + [プライバシーリクエスト](using/privacy/requests.md)
   + [ リソースに対する監査アクション](using/privacy/audit-logs.md)
   + [データハイジーン操作の実行](using/privacy/data-hygiene.md)
   + 同意の管理 {#consent}
      + [オプトアウトの管理](using/privacy/opt-out.md)
      + [同意ポリシーの使用](using/action/consent.md)
   + [データガバナンス](using/action/action-privacy.md)
   + [顧客管理キーの設定と管理](using/privacy/cmk.md)