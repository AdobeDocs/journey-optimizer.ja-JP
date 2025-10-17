---
solution: Journey Optimizer
product: journey optimizer
title: テキストメッセージ（SMS／MMS／RCS）の基本を学ぶ
description: Journey Optimizer でテキストメッセージを作成して送信する方法を学ぶ
feature: SMS
topic: Content Management
role: User
level: Beginner
exl-id: c1027268-0bbe-4e35-a5a6-2aef78083dd3
source-git-commit: 243d4e74c15057bc4bd334876a1bc87969d396e0
workflow-type: tm+mt
source-wordcount: '812'
ht-degree: 27%

---

# テキストメッセージの基本を学ぶ {#get-started-sms}

[!DNL Journey Optimizer] を使用すると、顧客のモバイルデバイスにテキストメッセージ（SMS／MMS／RCS）を送信できます。SMS／MMS／RCS エディターで、テキスト形式のメッセージの作成、パーソナライズおよびプレビューを行うことができます。

テキストメッセージは、ジャーニーまたはキャンペーンで作成して送信できます。SMS、MMS、RCS の場合は、SMS アクションを使用します。

* **ジャーニー**&#x200B;の場合：ジャーニーを作成し、SMS アクティビティを追加し、基本設定を定義します。次に、右側の SMS アクションパネルを参照して、SMS、MMS、または RCS メッセージのコンテンツを作成します。 [ジャーニーを作成する方法について説明します](../building-journeys/journey-gs.md)

* **キャンペーン**&#x200B;の場合：キャンペーンを作成し、アクションとして SMS を選択し、基本設定を定義します。次に、メッセージコンテンツを編集して、送信する SMS、MMS または RCS メッセージを定義します。[キャンペーンを作成する方法について説明します](../campaigns/create-campaign.md#configure)

>[!IMPORTANT]
>
>テキストメッセージを初めて作成する場合は、SMS チャネルが設定されていることを確認してください。 [詳細情報](sms-configuration.md)

## テキストメッセージ機能 {#sms-capabilities}

Adobe Journey Optimizerは、複数のチャネルで顧客を引き付けるための包括的なテキストメッセージ機能を提供します。

**SMS （ショートメッセージサービス）**

最大 160 文字のテキストのみのメッセージを送信します。 SMS は、すべてのモバイルデバイスで最も広くサポートされているテキストメッセージ形式です。

**MMS （マルチメディアメッセージサービス）**

ビデオ、画像、オーディオクリップ、GIF などのマルチメディアコンテンツとのコミュニケーションを強化します。 MMS メッセージでは、メディア ファイルに加えて最大 1600 文字のテキストを使用できます。 [MMS の制限事項に関する詳細情報 &#x200B;](../start/guardrails.md#sms-guardrails)

**RCS （Rich Communication Services）**

カルーセル、リッチカード、推奨アクション、拡張メディアサポートなどの高度な機能を備えた、ブランド化されたインタラクティブメッセージを送信します。 RCS は、サポート対象のデバイスに関するメッセージ機能を強化します。

## 主な特長 {#key-features}

**Personalizationと動的コンテンツ**

パーソナライゼーションエディターを使用して、パーソナライズされたテキストメッセージを作成します。 プロファイル属性、条件付きコンテンツ、動的データを追加して、個々の受信者に合わせてメッセージをカスタマイズします。 [&#x200B; パーソナライゼーションについて &#x200B;](../personalization/personalize.md)

**複数プロバイダーのサポート**

Adobe Journey Optimizerは、主要な SMS サービスプロバイダーと統合されています。

* **Sinch** - [&#x200B; 設定ガイド &#x200B;](sms-configuration-sinch.md)
* **Twilio** - [&#x200B; 設定ガイド &#x200B;](sms-configuration-twilio.md)
* **Infobip** - [&#x200B; 設定ガイド &#x200B;](sms-configuration-infobip.md)
* **カスタムプロバイダー** - カスタム API 統合を使用して他の SMS プロバイダーを設定する。 [詳細情報](sms-configuration-custom.md)

**URL 短縮およびトラッキング**

エンゲージメントを監視するために、メッセージに短縮された追跡可能な URL を追加します。 URL 短縮機能を使用するには、サブドメイン設定が必要です。 [SMS サブドメインの設定方法を学ぶ &#x200B;](sms-subdomains.md)

**オプトアウトの管理**

組み込みのオプトアウト管理により、業界標準および規制への準拠を確保します。 Journey Optimizerは、Sinch および Infobip プロバイダーの標準のオプトアウトキーワード（STOP、QUIT、CANCEL など）を自動的に処理します。 [&#x200B; オプトアウト管理について学ぶ &#x200B;](sms-opt-out.md)

**プレビューとテスト**

テストプロファイルとサンプルデータを使用して、送信前にテキストメッセージをテストします。 パーソナライゼーション、コンテンツ、書式設定をプレビューして、メッセージを正しく表示します。 [&#x200B; メッセージの送信方法を学ぶ &#x200B;](send-sms.md)

**レポートと分析**

包括的なレポート機能を使用して、SMS キャンペーンおよびジャーニーのパフォーマンスを追跡します。

* [キャンペーンレポートの SMS 送信](../reports/campaign-global-report-cja-sms.md)
* [SMS ジャーニーレポート](../reports/journey-global-report-cja-sms.md)

## 設定要件 {#configuration-requirements}

テキストメッセージを送信する前に、次の操作を行う必要があります。

1. **SMS プロバイダーの選択** - Sinch、Twilio、Infobip から選択するか、カスタムプロバイダーを設定します
2. **API 資格情報の設定** - プロバイダーの API トークンとサービス ID をJourney Optimizerに統合します
3. **チャネル設定の作成** - マーケティングメッセージとトランザクションメッセージ用の SMS 設定をセットアップする
4. **サブドメインの設定（オプション）** - メッセージで URL 短縮機能を使用する予定の場合のみ必須

これらの設定手順は、通常、システム管理者が実行します。 [SMS 設定の概要 &#x200B;](sms-configuration.md)

## クイックスタートガイド {#quick-start}

<table style="table-layout:fixed"><tr style="border: 0;">
<td>
<a href="sms-configuration.md">
<img alt="検証" src="../assets/do-not-localize/sms-config.jpg">
</a>
<div>
<a href="sms-configuration.md"><strong>SMS チャネルの設定</strong></a>
</div>
<p>SMS プロバイダーとチャネルの設定を行う</p>
</td>
<td>
<a href="create-sms.md">
<img alt="リード" src="../assets/do-not-localize/sms-create.jpeg">
</a>
<div><a href="create-sms.md"><strong> テキストメッセージの作成 </strong></a>
</div>
<p>SMS、MMS または RCS コンテンツの設計とパーソナライズ</p>
</td>
<td>
<a href="send-sms.md">
<img alt="低頻度" src="../assets/do-not-localize/sms-sending.jpg">
</a>
<div>
<a href="send-sms.md"><strong> プレビューと送信 </strong></a>
</div>
<p>テキストメッセージをテストしてオーディエンスに送信します</p>
</td>
<td>
<a href="sms-opt-out.md">
<img alt="検証" src="../assets/do-not-localize/sms-opt-out.jpg">
</a>
<div>
<a href="sms-opt-out.md"><strong> オプトアウトの管理 </strong></a>
</div>
<p>登録解除リクエストの処理とコンプライアンスの確保</p>
</td>
</tr></table>

## その他のリソース {#additional-resources}

Journey Optimizerでのテキストメッセージについて詳しくは、以下のトピックを参照してください。

+++設定ガイド

SMS 環境を設定する方法について説明します。

* [SMS チャネル設定の概要](sms-configuration.md)
* [SMS チャネル設定の作成](sms-configuration-surface.md)
* [URL 短縮用の SMS サブドメインの設定](sms-subdomains.md)

+++

+++プロバイダー設定ガイド

各 SMS サービスプロバイダーのステップバイステップの設定：

* [Sinch プロバイダーの設定](sms-configuration-sinch.md)
* [Twilio プロバイダーの設定](sms-configuration-twilio.md)
* [Infobip プロバイダーの設定](sms-configuration-infobip.md)
* [カスタム SMS プロバイダーの設定](sms-configuration-custom.md)

+++

+++コンテンツの作成と管理

テキストメッセージコンテンツを作成、パーソナライズ、管理します。

* [SMS/MMS メッセージの作成](create-sms.md)
* [メッセージのプレビュー、テスト、送信](send-sms.md)
* [テキストメッセージでのPersonalization](../personalization/personalize.md)
* [動的コンテンツ](../personalization/get-started-dynamic-content.md)

+++

+++コンプライアンスとプライバシー

テキストメッセージが規制やプライバシー標準に準拠していることを確認します。

* [オプトアウト管理](sms-opt-out.md)
* [プライバシーと同意](../privacy/opt-out.md#sms-opt-out-management-sms-opt-out-management)

+++

+++パフォーマンストラッキング

SMS キャンペーンとジャーニーのパフォーマンスを監視および分析します。

* [キャンペーンレポートの SMS 送信](../reports/campaign-global-report-cja-sms.md)
* [SMS ジャーニーレポート](../reports/journey-global-report-cja-sms.md)

+++

+++ジャーニーと Campaign の統合

SMS をカスタマージャーニーやキャンペーンに組み込む方法を説明します。

* [ジャーニーへの SMS メッセージの追加](../building-journeys/journeys-message.md)
* [SMS キャンペーンの作成](../campaigns/create-campaign.md)

+++

## チュートリアルビデオ {#videos}

**SMS メッセージの設定と送信**

SMS メッセージを設定、作成およびカスタマージャーニーに含める方法について説明します。

+++こちらのビデオをご覧ください

>[!VIDEO](https://video.tv.adobe.com/v/3420509?learn=on)

+++

**モバイルメッセージ機能の詳細**

Adobe Journey Optimizerがマーケターに提供する包括的なモバイルメッセージ機能について説明します。

+++こちらのビデオをご覧ください

>[!VIDEO](https://video.tv.adobe.com/v/3426021?quality=12&learn=on)

+++

**ブランド化された RCS メッセージの送信**

カスタム SMS プロバイダーを使用して、ブランド化されたインタラクティブな RCS メッセージを Adobe Journey Optimizer で設定および送信する方法について説明します。

+++こちらのビデオをご覧ください

>[!VIDEO](https://video.tv.adobe.com/v/3464755)

+++

**関連トピック**

* [ジャーニーでのメッセージの追加](../building-journeys/journeys-message.md)
* [マーケティングキャンペーンの作成](../campaigns/create-campaign.md)
* [ガードレールと制限](../start/guardrails.md#sms-guardrails)
