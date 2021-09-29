---
title: ドキュメントの更新
description: 最新のドキュメントの更新について学ぶ
exl-id: 83c8f206-bce3-4cc8-94a3-575ec1d999bc
source-git-commit: d6228aade93bc9fa2b5f2ad2b76db5e193208242
workflow-type: tm+mt
source-wordcount: '712'
ht-degree: 56%

---

# このドキュメントの最新の更新点

このページでは、[!DNL Journey Optimizer] のドキュメントの更新点がすべてリストアップされています。

## 2021年9月

* 次の機能ページが更新されました。[sethours](https://experienceleague.adobe.com/docs/journeys/using/building-advanced-conditions-journeys/main-functions-journey/date/functionsethours.html)、[getListItem](https://experienceleague.adobe.com/docs/journeys/using/building-advanced-conditions-journeys/main-functions-journey/list/functiongetlistitem.html)、[inSegment](https://experienceleague.adobe.com/docs/journeys/using/building-advanced-conditions-journeys/main-functions-journey/adobe-experience-platform/functioninsegment.html)

* 次の関数が追加されました。[filter](https://experienceleague.adobe.com/docs/journeys/using/building-advanced-conditions-journeys/main-functions-journey/list/functionfilter.html)、[intersect](https://experienceleague.adobe.com/docs/journeys/using/building-advanced-conditions-journeys/main-functions-journey/list/functiontintersect.html)、[toDateOnly](https://experienceleague.adobe.com/docs/journeys/using/building-advanced-conditions-journeys/main-functions-journey/conversion/functiontodateonly.html)

* dateOnly日付タイプが式エディターのドキュメントに追加されました。 [詳細情報](https://experienceleague.adobe.com/docs/journeys/using/building-advanced-conditions-journeys/syntax/data-types.html?lang=en)

* カスタムアクションのキャッシュ時間の詳細を追加しました。 [詳細情報](datasource/external-data-sources.md#section_wjp_nl5_nhb)

* カスタムアクションのデフォルトポートに関する情報を追加しました。 [詳細情報](action/about-custom-action-configuration.md#url-configuration)

* 複数のビジネスイベントの使用例に関する情報を追加しました。 [詳細情報](event/about-creating-business.md#multiple-business-events)

* データレイクでのイベントステップイベントのジャーニークエリによく使用される例を追加しました。 [詳細情報](reports/query-examples.md)

* 新しい&#x200B;**制限**&#x200B;ページを追加しました。 [詳細情報](limitations.md)

* **クイックスタート**&#x200B;ページが改善され、様々なペルソナの手順が追加されました。 [詳細情報](quick-start.md)

   <!--* Added a new section on how to define and personalize content for offers' representations. [Read more](offers/offer-library/creating-personalized-offers.md#content)-->

* ここで、専用の節で説明しているすべてのDecision Management機能が、Decision Application Serviceを利用するAdobe Experience Platformユーザーにも適用されるようになりました。 [詳細情報](offers/get-started/starting-offer-decisioning.md)

* 制約を適用して特定の配置のオファーの選択を制限する際の、セグメントと判定ルールの使用の違いを明確にする節を追加しました。 [詳細情報](offers/offer-activities/create-offer-activities.md#segments-vs-decision-rules)

* 実際の使用例を説明するために、特定のランキング式の例を追加しました。 [詳細情報](offers/offer-library/create-ranking-formulas.md#ranking-formula-examples)

* IPプールの編集方法に関する節を追加しました。 [詳細情報](configuration/ip-pools.md#edit-ip-pool)

## 2021 年 8 月

*  [!DNL Journey Optimizer] の 8 月 21 日リリースに含まれているすべての新機能と機能強化について、ドキュメントで詳しく説明しました。 [詳細情報](release-notes.md)
* 決定管理権限を更新しました。 [詳細情報](administration/ootb-product-profiles.md)
* 電子メールデザイナーのスクリーンショットに最新の UI を反映しました。
* カスタムアクションの設定手順に動的 URL パスと動的ヘッダーを反映しました。[詳細情報](action/about-custom-action-configuration.md#url-configuration)
* アクセシビリティ機能とショートカットに関する節を追加しました。[詳細情報](user-interface.md#accessibility)
* セグメント評価方法に関する節を追加しました。[詳細情報](segment/about-segments.md#evaluation-method-in-journey-optimizer)
* 抑制リスト、許可リストおよびメールのグローバル／ライブレポートの各節にメモを追加し、「抑制」および「許可されていない」のステータスを持つプロファイルがメールレポートの「送信済み」指標から除外されることを明記しました。[詳細情報](reports/email-global-report.md)
* 許可リストに登録されていなかったので送信から除外されたメールアドレスまたはドメインを取得する方法を説明する新しい節を追加しました。[詳細情報](allow-list.md#reporting)
* 「許可リストの有効化」の節を更新しました。 [詳細情報](allow-list.md#enable-allow-list)
* 「メッセージプリセットの監視」の節を更新して、プリセット作成失敗の考えられる理由と、そうしたエラーの詳細を追加しました。[詳細情報](configuration/message-presets.md#monitor-message-presets)
* メッセージプリセットのメール再試行設定を調整できるようになったことを反映するために、「再試行期間」の節を更新し、名前を変更しました。 [詳細情報](configuration/retries.md#retry-duration)
* ワンクリックオプトアウトリンクをメールコンテンツに挿入する方法を説明する新しい節を追加しました。[詳細情報](message-tracking.md#one-click-opt-out-link)
* サブドメインのデリゲートの節を更新し、Adobeが実行する検証プロセスに関する詳細情報を追加しました。 [詳細情報](configuration/delegate-subdomain.md#subdomain-validation)
* 抑制リストに電子メールアドレスとドメインを手動で追加する方法を説明する節を追加しました。 [詳細情報](configuration/manage-suppression-list.md#add-addresses-and-domains)
* [「抑制リスト](configuration/manage-suppression-list.md#access-suppression-list) 」セクションと「[再試行](configuration/retries.md) 」セクションを更新し、新しいユーザーインターフェイスを反映させました。
* オファーの作成時に表示域を追加および設定するための新しいフローが、ドキュメントに追加されました。 [詳細情報](offers/offer-library/creating-personalized-offers.md#representations)


## 2021 年 7 月

* [!DNL Journey Optimizer] の 7 月 21 日リリースに含まれているすべての新機能と機能強化について、ドキュメントで詳しく説明しました。[詳細情報](release-notes.md)
* [!DNL Journey Optimizer] ホームページと目次に Experience Platform サービスのドキュメントへの直接リンクが追加されました
* Experience Platform サービスの新しいランディングページが [!DNL Journey Optimizer] で利用可能になりました 
* [!DNL Journey Optimizer] 製品説明へのリンクがホームページに追加されました
* 複数のページにチュートリアルビデオが追加されました
* ホームページの画像が最適化されました
* 「メッセージトラッキング」の節が移動し、改善され、タイトルが「リンクの追加とメッセージのトラッキング」に変更されました。 [詳細を読む](message-tracking.md)
* ミラーページにサブセクションが追加されました。 [詳細を読む](message-tracking.md#mirror-page)
* ドキュメントと画面で、「オファーアクティビティ」が「決定」に、「決定」が「決定範囲」にそれぞれ名称変更されました。 [詳細を読む](offers/get-started/starting-offer-decisioning.md)
* 新しいユースケース：[ヘルパー関数を使用したメッセージのパーソナライズ](personalization/personalization-use-case-helper-functions.md)が追加されました
* マテリアライズドセグメントの影響を反映するように、セグメントの読み取りに関するドキュメントを更新しました。 [詳細を読む](building-journeys/read-segment.md)
* ジャーニーの制限が更新されました。 [詳細を読む](limitations.md)
* 決定のオファーの設定の節を更新しました。 [詳細情報](offers/offer-activities/configure-offer-selection.md)
* イベントベースのオファーは現在サポートされていないという警告を追加しました。[詳細情報](offers/offer-library/creating-personalized-offers.md#eligibility)
* 意思決定管理の新しい「**[!UICONTROL 概要]**」タブについて説明しました。 [詳細情報](offers/get-started/user-interface.md#overview)
* オファーおよび判定リストで使用可能な操作について説明する新しい節を追加しました。[オファーリスト](offers/offer-library/creating-personalized-offers.md#offer-list)と[判定リスト](offers/offer-activities/create-offer-activities.md#decision-list)。
