---
solution: Journey Optimizer
product: journey optimizer
title: ユースケースを通じて学ぶ
description: ジャーニーのユースケースの概要
feature: Journeys, Use Cases
role: User, Data Engineer
level: Intermediate, Experienced
keywords: ユースケース, マルチチャネル, ジャーニー, イベント
exl-id: 28f3f06b-3576-43a7-9c1b-8e616390907b
version: Journey Orchestration
source-git-commit: 8218c4666588bb58e0529a73eebcddef3209cbd0
workflow-type: tm+mt
source-wordcount: '770'
ht-degree: 54%

---

# ユースケースを通じて学ぶ {#jo-uc-gs}

この節では、Adobe Journey Optimizer を最大限に活用するのに役立つ実用的なユースケースのコレクションについて説明します。抑制ロジック、パーソナライゼーション手法、ジャーニー終了戦略などの戦術パターンや、マーケティングワークフローとテクニカルワークフローを対象とした完全なエンドツーエンドのシナリオを探している場合は、関連するサンプルへの以下のリンクを参照してください。

ジャーニーのデザイン、データのモデリング、アクティベーションロジックの作成時に、このライブラリを参照ポイントとして使用します。各例には、特定のニーズに合わせてカスタマイズできるレコメンデーションが含まれています。


## エクスペリエンスイベントの操作

<table style="table-layout:fixed">
<tr style="border: 0;">
  <td>
    <div>
    <a href="exp-event-lookup.md">
    <img alt="エクスペリエンスイベント参照のベストプラクティス" src="../assets/do-not-localize/icon-quick-start.svg" /></a> 
    <br>Adobe Journey Optimizer のエクスペリエンスイベントを最大限に活用する一般的なパターンとスケーラブルなアプローチについて説明します。これらのユースケースは、オプトアウトの管理、メッセージ頻度の制御、ユーザー行動に基づくコンテンツのパーソナライズ、リアルタイムシグナルへの対応など、頻繁に発生する課題の解決に役立つように設計されています。
    </div>
      <div>
     <a href="exp-event-lookup.md">詳細情報</a></div>
    </div>
  </td>
</tr>
</table>


## ジャーニーデータセットのクエリ

<table style="table-layout:fixed">
<tr style="border: 0;">
  <td>
    <div>
    <a href="../data/datasets-query-examples.md">
    <img alt="クエリのサンプル" src="../assets/do-not-localize/icon-configure.svg"/></a> 
    <br>ユースケースを作成するには、トラッキングエクスペリエンスイベントを取り込むシステムデータセット、ジャーニーのステップイベントを取り込むデータセット、ユーザーへのオファー提案を取り込むデータセットなど、Adobe Journey Optimizer データセットのクエリを実行する必要があります。
    </div>
      <div>
     <a href="../data/datasets-query-examples.md">詳細情報</a></div>
    </div>
  </td>
</tr>
</table>

また、一般的に使用されるいくつかの[ジャーニーステップイベントのクエリを実行する例](../reports/query-examples.md)も参照してください。


## ビジネスユースケース

<table style="table-layout:fixed"><tr style="border: 0;">
<td>
<a href="../building-journeys/journeys-uc.md">
<img alt="マルチチャネルメッセージの送信" src="../assets/do-not-localize/start-journey.jpeg">
</a>
<div>
<a href="../building-journeys/journeys-uc.md"><strong>マルチチャネルメッセージの送信</strong></a>
</div>
<p>
</td>
<td>
<a href="ajo-ac.md">
<img alt="Campaign を使用したメッセージの送信" src="../assets/do-not-localize/start-interface.jpeg">
</a>
<div><a href="ajo-ac.md"><strong>Campaign v7／v8 を使用した送信</strong>
</div>
<p>
</td>
<td>
<a href="message-to-subscribers-uc.md">
<img alt="サブスクライバーへのメッセージの送信" src="../assets/do-not-localize/start-quick.png">
</a>
<div>
<a href="message-to-subscribers-uc.md"><strong>サブスクライバーへの送信</strong></a>
</div>
<p></td>
</tr></table>

## テクニカルユースケース

<table style="table-layout:fixed"><tr style="border: 0;">
<td>
<a href="collections.md">
<img alt="カスタムアクションを使用したコレクションの動的な受け渡し" src="../assets/do-not-localize/icon-configure.svg">
</a>
<div>
<a href="collections.md"><strong>カスタムアクションを使用したコレクションの動的な受け渡し</strong></a>
</div>
<p>
</td>
<td>
<a href="limit-throughput.md">
<img alt="外部データソースとカスタムアクションを使用したスループットの制限" src="../assets/do-not-localize/icon-first-journey.svg">
</a>
<div><a href="limit-throughput.md"><strong>外部データソースとカスタムアクションを使用したスループットの制限</strong></a>
</div>
<p>
</td>
<td>
<a href="../building-journeys/journey-pause.md#apply-an-exit-criteria-in-a-paused-journey">
<img alt="ライブジャーニーからのプロファイルの削除" src="../assets/do-not-localize/icon_profile-audience.svg">
</a>
<div><a href="../building-journeys/journey-pause.md#apply-an-exit-criteria-in-a-paused-journey"><strong>外部データソースとカスタムアクションを使用したスループットの制限</strong></a>
</div>
<p>
</td>
</tr></table>

## ビデオチュートリアル

Adobe Journey Optimizerの最も一般的なユースケースを構築するための主な手順については、ビデオチュートリアルをご覧ください。


<table style="table-layout:auto">
  <tr style="border: 0;">
    <td>
      <img src="../assets/do-not-localize/icon-quick-start.svg" width="35px">
    <br/>
      <strong> 顧客のオンボーディング </strong><br/><p>Journey Optimizerでカスタマーオンボーディングジャーニーを実装する方法を説明します。</p> - <a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/use-cases/customer-onboarding" target="_blank"> ユースケースビデオをご覧ください </a>
    </td>
    <td>
      <img src="../assets/do-not-localize/icon-campaign.svg" width="35px">
    <br/>
      <strong> 放棄されたカート </strong><br/><p>Adobe Journey Optimizer のプレイブック機能を使用して、放棄された買い物かごのユースケースを実装する方法について説明します。</p><a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/use-cases/abandoned-cart" target="_blank"> ユースケースビデオをご覧ください </a>
    </td>
    <td>
      <img src="../assets/do-not-localize/icon-content.svg" width="35px">
    <br/>
      <strong> 再エンゲージメント </strong><br/><p>Adobeが Luma デモサイトを操作するためにインテリジェントな再エンゲージメントのユースケースを適応させた方法を、データアーキテクトとデータエンジニアのチュートリアルおよびExperience Platform Web SDK チュートリアルに記載されている基盤実装に基づいて説明します。</p><a href="https://experienceleague.adobe.com/ja/docs/experience-platform/rtcdp/use-cases/personalization-insights-engagement/use-cases-luma" target="_blank"> ユースケースビデオをご覧ください </a> 
    </td>
  </tr>
  <tr style="border: 0;">
    <td>
      <img src="../assets/do-not-localize/icon-experience.svg" width="35px">
    <br/>
      <strong> リアルタイムオファーのパーソナライゼーション </strong><br/><p>Adobe Journey Optimizerの天候関連のデータを使用してオファーを提供すると、企業は、実際のリアルタイムの環境条件に基づいてカスタマーエクスペリエンスをパーソナライズできます。</p><a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/personalizing-offers-with-real-time-weather-data/introduction" target="_blank"> 段階的なチュートリアルに従う </a>
    </td>
    <td>
      <img src="../assets/do-not-localize/icon-configure.svg" width="35px">
    <br/>
      <strong> 決定を介して配信されるオファーのトラッキングとレポート </strong><br/><p>Adobe Journey Optimizerを通じて配信されるオファーのレポートとパフォーマンス分析を有効にする：コンテキストに基づいてオファーをパーソナライズして配信する場合、インプレッションとユーザーインタラクションの両方をトラッキングして効果を評価することが不可欠です。</p><a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/reporting-on-ajo-od/introduction" target="_blank"> 段階的なチュートリアルに従う </a> 
    </td>
    <td>
      <img src="../assets/do-not-localize/icon_profile-audience.svg" width="35px">
    <br/>
      <strong> ランキング式を使用したオファーのパーソナライズ </strong><br/><p>Adobe Journey Optimizerで郵便番号や年収などのユーザー属性を活用して、パーソナライズされた金融オファーを提供する方法を説明します。 ランキング式を使用すると、場所に固有のプロモーションと収入ベースの実施要件に基づいて、オファーをインテリジェントにスコアリングし、優先順位を付けることができます。</p><a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/personalizing-offers-with-ranking-formulas-based-on-user-zip-code-and-income/introduction" target="_blank"> 段階的なチュートリアルに従う </a> 
    </td>
  </tr>
</table>

[Adobe Journey Optimizerでのオーケストレーションをオムニチャネルエンゲージメントに拡大 ](https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/scaling-orchestration-to-omnichannel-engagement/introduction){target="_blank"} するためのビデオチュートリアルも参照してください。6 つのレッスンを通じて、シンプルなアウトバウンドメッセージから高度なオムニチャネルエクスペリエンスにビジネスコミュニケーションを向上させる方法を学びます。 実践的な例を通じて、プロアクティブなアウトリーチとレスポンシブなエンゲージメントをシームレスにブレンドするカスタマージャーニーを作成するためのインサイトを得ます。



## ブログ投稿

ジャーニーを作成する際のガイダンスとベストプラクティスについて詳しくは、次のブログ投稿を参照してください。

<table style="table-layout:fixed"><tr style="border: 0;">
<td>
<img alt="ブログ投稿" src="../assets/do-not-localize/community.jpeg">
<div>
<p><a href="https://experienceleaguecommunities.adobe.com/t5/journey-optimizer-blogs/how-to-send-emails-only-on-weekdays-in-adobe-journey-optimizer/ba-p/760400" target="_blank">ユースケース：Adobe Journey Optimizer で平日にのみメールを送信する方法</a></p>
<p><a href="https://experienceleaguecommunities.adobe.com/t5/journey-optimizer-blogs/advanced-approval-strategies-in-adobe-journey-optimizer/ba-p/761396" target="_blank">ユースケース：高度な承認戦略</a></p>
<p><a href="https://experienceleaguecommunities.adobe.com/t5/journey-optimizer-blogs/elevate-customer-experience-with-daily-frequency-capping-in-ajo/ba-p/761510" target="_blank">ユースケース：毎日のフリークエンシーキャップ</a></p>
<p><a href="https://experienceleaguecommunities.adobe.com/t5/journey-optimizer-blogs/mastering-read-audience-journeys-in-adobe-journey-optimizer-a/ba-p/761445" target="_blank">ベストプラクティス：オーディエンスを読み取りジャーニー</a></p>
<p><a href="https://experienceleaguecommunities.adobe.com/t5/journey-optimizer-blogs/from-plan-to-perfection-how-to-test-your-ajo-journeys-for-10/ba-p/761270" target="_blank">ユースケース：ジャーニーのテスト</a></p>
<p><a href="https://experienceleaguecommunities.adobe.com/t5/journey-optimizer-blogs/deliver-with-confidence-approval-workflows-across-adobe-journey/ba-p/760900" target="_blank">ユースケース：承認ワークフロー</a></p>
<p><a href="https://experienceleaguecommunities.adobe.com/t5/journey-optimizer-blogs/mastering-journey-entry-and-exit-criteria-in-adobe-journey/ba-p/760958" target="_blank">ユースケース：ジャーニーのエントリ条件と終了条件</a></p>
</div>
<p>
</td>
<td>
<img alt="ジャーニーのステップイベント" src="../assets/do-not-localize/list.jpeg">
<div>
<a href="https://experienceleaguecommunities.adobe.com/t5/journey-optimizer-blogs/mastering-step-events-in-adobe-journey-optimizer-fundamentals/ba-p/762024" target="_blank">Adobe Journey Optimizer のステップイベントの習得：データ駆動型キャンペーンの基本、スキーマおよび基本的なクエリ
</a></p>
<p><a href="https://experienceleaguecommunities.adobe.com/t5/journey-optimizer-blogs/fast-external-audience-activation-with-custom-upload/ba-p/761658" target="_blank">ユースケース：カスタムアップロードを使用した高速な外部 Audience Activation</a></p>
<p><a href="https://experienceleaguecommunities.adobe.com/t5/journey-optimizer-blogs/personalization-beyond-the-ajo-profile-bringing-non-profile/ba-p/769225" target="_blank">ユースケース：プロファイルを超えたPersonalization
</a></p>
<p><a href="https://experienceleaguecommunities.adobe.com/t5/journey-optimizer-blogs/take-flight-with-personalization-how-airlines-can-elevate-offers/ba-p/767513" target="_blank">Personalizationで空を飛ぶ：航空会社がAdobe Journey Optimizerでオファーを高める方法
</a></p>
<p><a href="https://experienceleaguecommunities.adobe.com/t5/journey-optimizer-blogs/mastering-real-time-personalization-a-marketer-s-guide-to-aem/ba-p/762606" target="_blank">リアルタイム Personalizationの習得：マーケター向けAEM コンテンツフラグメントおよびAdobe Journey Optimizerガイド
</a></p>
</div>
<p></td>
<td>
<img alt="カスタムアクション" src="../assets/do-not-localize/step-event.jpeg">
<div><p><a href="https://experienceleaguecommunities.adobe.com/t5/journey-optimizer-blogs/how-to-extend-adobe-journey-optimizer-with-custom-actions/ba-p/761323" target="_blank">カスタムアクションを使用してAdobe Journey Optimizerを拡張する方法：統合の使用例
</a></p>
</div>
<div><p><a href="https://experienceleaguecommunities.adobe.com/t5/journey-optimizer-blogs/breaking-down-barriers-how-adobe-journey-optimizer-s-custom/ba-p/759223" target="_blank">Adobe Journey Optimizerのカスタム委任機能は、企業コンプライアンスの課題を解決します
</a></p>
</div>
<div><p><a href="https://experienceleaguecommunities.adobe.com/t5/journey-optimizer-blogs/line-in-ajo-from-first-campaign-to-advanced-expression-fragment/ba-p/771048" target="_blank">Journey Optimizerの行：最初のキャンペーンから高度な式フラグメントおよびカスタムアクションのユースケースまで
</a></p>
</div>
<div><p><a href="https://experienceleaguecommunities.adobe.com/t5/journey-optimizer-blogs/ajo-universal-link-integration-guide-for-ios/ba-p/768669" target="_blank">iOSのJourney Optimizer Universal Link 統合ガイド
</a></p>
</div>
</td>
</tr></table>