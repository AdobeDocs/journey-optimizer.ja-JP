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
source-git-commit: b8d56578aae90383092978446cb3614a4a033f80
workflow-type: tm+mt
source-wordcount: '818'
ht-degree: 99%

---

# テキストメッセージの基本を学ぶ {#get-started-sms}

[!DNL Journey Optimizer] を使用すると、顧客のモバイルデバイスにテキストメッセージ（SMS／MMS／RCS）を送信できます。SMS／MMS／RCS エディターで、テキスト形式のメッセージの作成、パーソナライズおよびプレビューを行うことができます。

テキストメッセージは、ジャーニーまたはキャンペーンで作成して送信できます。SMS、MMS、RCS の場合は、SMS アクションを使用します。

* **ジャーニー**&#x200B;の場合：ジャーニーを作成し、SMS アクティビティを追加し、基本設定を定義します。次に、右側の SMS アクションパネルを参照して、SMS、MMS または RCS メッセージのコンテンツを作成します。[ジャーニーを作成する方法について説明します](../building-journeys/journey-gs.md)

* **キャンペーン**&#x200B;の場合：キャンペーンを作成し、アクションとして SMS を選択し、基本設定を定義します。次に、メッセージコンテンツを編集して、送信する SMS、MMS または RCS メッセージを定義します。[キャンペーンを作成する方法について説明します](../campaigns/campaign-action.md#action-campaign-action)

>[!IMPORTANT]
>
>テキストメッセージを初めて作成する場合は、SMS チャネルが設定済みであることを確認してください。[詳細情報](sms-configuration.md)

## テキストメッセージ機能 {#sms-capabilities}

Adobe Journey Optimizer には、複数のチャネルをまたいで顧客と関与するための包括的なテキストメッセージ機能が用意されています。

**SMS（ショートメッセージサービス）**

最大 160 文字のテキストのみのメッセージを送信します。SMS は、すべてのモバイルデバイスで最も広くサポートされているテキストメッセージ形式です。

**MMS（マルチメディアメッセージサービス）**

ビデオ、画像、オーディオクリップ、GIF などのマルチメディアコンテンツを使用して通信を強化します。MMS メッセージでは、メディアファイルに加えて最大 1600 文字のテキストを使用できます。[MMS の制限の詳細情報](../start/guardrails.md#sms-guardrails)

**RCS（リッチ通信サービス）**

カルーセル、リッチカード、推奨アクション、拡張メディアサポートなどの高度な機能を使用して、ブランド化されたインタラクティブなメッセージを送信します。RCS は、サポート対象のデバイスでよりリッチなメッセージエクスペリエンスを提供します。

## 主な特長 {#key-features}

**パーソナライゼーションと動的コンテンツ**

パーソナライゼーションエディターを使用して、パーソナライズされたテキストメッセージを作成します。プロファイル属性、条件付きコンテンツ、動的データを追加して、個々の受信者に合わせてメッセージをカスタマイズします。[パーソナライゼーションの詳細情報](../personalization/personalize.md)

**複数のプロバイダーのサポート**

Adobe Journey Optimizer は、次の主要な SMS サービスプロバイダーと統合されます。

* **Sinch** - [設定ガイド](sms-configuration-sinch.md)
* **Twilio** - [設定ガイド](sms-configuration-twilio.md)
* **Infobip** - [設定ガイド](sms-configuration-infobip.md)
* **カスタムプロバイダー** - カスタム API 統合を使用して他の SMS プロバイダーを設定します。[詳細情報](sms-configuration-custom.md)

**URL 短縮とトラッキング**

エンゲージメントを監視するために、追跡可能な短縮 URL をメッセージに追加します。URL 短縮機能には、サブドメインの設定が必須です。[SMS サブドメインの設定方法の詳細情報](sms-subdomains.md)

**オプトアウト管理**

組み込みのオプトアウト管理を通じて、業界標準および規制への準拠を確保します。Journey Optimizer は、Sinch および Infobip プロバイダーの標準のオプトアウトキーワード（STOP、QUIT、CANCEL など）を自動的に処理します。[オプトアウト管理の詳細情報](sms-opt-out.md)

**プレビューとテスト**

テストプロファイルとサンプルデータを使用して、テキストメッセージを送信する前にテストします。パーソナライゼーション、コンテンツ、書式設定をプレビューして、メッセージが正しく表示されることを確認します。[メッセージの送信方法の詳細情報](send-sms.md)

**レポートと分析**

次の包括的なレポート機能を使用して、SMS キャンペーンとジャーニーのパフォーマンスを追跡します。

* [SMS キャンペーンレポート](../reports/campaign-global-report-cja-sms.md)
* [SMS ジャーニーレポート](../reports/journey-global-report-cja-sms.md)

## 設定要件 {#configuration-requirements}

テキストメッセージを送信する前に、次の操作を行う必要があります。

1. **SMS プロバイダーを選択** - Sinch、Twilio、Infobip から選択するか、カスタムプロバイダーを設定します
2. **API 資格情報を設定** - プロバイダーの API トークンとサービス ID を Journey Optimizer と統合します
3. **チャネル設定を作成** - マーケティングメッセージとトランザクションメッセージ用の SMS 設定を指定します
4. **サブドメインを設定（オプション）** - メッセージで URL 短縮を使用する予定がある場合にのみ必須です

これらの設定手順は通常、システム管理者が実行します。[SMS 設定の基本を学ぶ](sms-configuration.md)

## クイックスタートガイド {#quick-start}

<table style="table-layout:fixed"><tr style="border: 0;">
<td>
<a href="sms-configuration.md">
<img alt="検証" src="../assets/do-not-localize/sms-config.jpg">
</a>
<div>
<a href="sms-configuration.md"><strong>SMS チャネルの設定</strong></a>
</div>
<p>SMS プロバイダーとチャネル設定を指定します</p>
</td>
<td>
<a href="create-sms.md">
<img alt="リード" src="../assets/do-not-localize/sms-create.jpeg">
</a>
<div><a href="create-sms.md"><strong>テキストメッセージの作成</strong></a>
</div>
<p>SMS、MMS、RCS コンテンツをデザインおよびパーソナライズします</p>
</td>
<td>
<a href="send-sms.md">
<img alt="低頻度" src="../assets/do-not-localize/sms-sending.jpg">
</a>
<div>
<a href="send-sms.md"><strong>プレビューと送信</strong></a>
</div>
<p>テキストメッセージをテストしてオーディエンスに送信します</p>
</td>
<td>
<a href="sms-opt-out.md">
<img alt="検証" src="../assets/do-not-localize/sms-opt-out.jpg">
</a>
<div>
<a href="sms-opt-out.md"><strong>オプトアウトの管理</strong></a>
</div>
<p>登録解除リクエストを処理し、コンプライアンスを確保します</p>
</td>
</tr></table>

## その他のリソース {#additional-resources}

Journey Optimizer でのテキストメッセージについて詳しくは、以下のトピックを参照してください。

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

* [SMS／MMS メッセージの作成](create-sms.md)
* [メッセージのプレビュー、テスト、送信](send-sms.md)
* [テキストメッセージのパーソナライゼーション](../personalization/personalize.md)
* [動的コンテンツ](../personalization/get-started-dynamic-content.md)

+++

+++コンプライアンスとプライバシー

テキストメッセージが規制とプライバシー標準に準拠していることを確認します。

* [オプトアウト管理](sms-opt-out.md)
* [プライバシーと同意](../privacy/opt-out.md#opt-out-decision-management)

+++

+++パフォーマンストラッキング

SMS キャンペーンとジャーニーのパフォーマンスを監視および分析します。

* [SMS キャンペーンレポート](../reports/campaign-global-report-cja-sms.md)
* [SMS ジャーニーレポート](../reports/journey-global-report-cja-sms.md)

+++

+++ジャーニーとキャンペーンの統合

SMS をカスタマージャーニーやキャンペーンに組み込む方法について説明します。

* [ジャーニーへの SMS メッセージの追加](../building-journeys/journeys-message.md)
* [SMS キャンペーンの作成](../campaigns/create-campaign.md)

+++

## チュートリアルビデオ {#videos}

**SMS メッセージの設定と送信**

SMS メッセージを設定、作成およびカスタマージャーニーに含める方法について説明します。

+++こちらのビデオをご覧ください

>[!VIDEO](https://video.tv.adobe.com/v/3420509?learn=on)

+++

**モバイルメッセージ機能の探索**

Adobe Journey Optimizer がマーケターに提供する包括的なモバイルメッセージ機能について説明します。

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
* [SMS とモバイルメッセージのチュートリアル ](https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/channels/sms-channel/sms-mms-messages-overview){target="_blank"}
