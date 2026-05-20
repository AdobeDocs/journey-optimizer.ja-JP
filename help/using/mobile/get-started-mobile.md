---
solution: Journey Optimizer
product: journey optimizer
title: モバイルメッセージの基本を学ぶ
description: Journey Optimizer でテキストメッセージを作成して送信する方法を学ぶ
feature: SMS
topic: Content Management
role: User
level: Beginner
exl-id: c1027268-0bbe-4e35-a5a6-2aef78083dd3
TQID: https://experienceleague.adobe.com/Ev0xJ86fpweQxgf-VjGUEl4ebk6BdzhVof2BgiMR9EM
product_v2: id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2: id: ad78185d-8f79-40ad-9bad-cbde74af74eeid: d556b755-390a-43f0-be32-a08cf6236126id: d998adac-2f81-400b-a669-d07bb196e4ebid: dc22c819-3f29-4e91-8b7d-5c6719831141
subfeature_v2: id: cf64c7f6-7428-4ae5-b158-8df9771f38f4id: e5329d1b-e590-4e24-a3fb-ef3fe0f2c721id: fb9a80eb-bebc-492f-a0e9-584595621ebb
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: c13ff12d-60f1-49cd-833a-d43359628223id: d00e9f03-e50b-4162-b143-0c0817c937c2id: e0eb8757-182f-49f3-94a4-1587d16f5094id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 9a68782b0ca1a9a65db621209cf4f39ea5ce911d
workflow-type: tm+mt
source-wordcount: 1005
ht-degree: 30%

---

# モバイルメッセージの基本を学ぶ {#get-started-sms}

>[!IMPORTANT]
>
>モバイルメッセージを初めて作成する場合は、モバイルメッセージチャネルが設定されていることを確認します。 [詳細情報](mobile-configuration.md)

[!DNL Journey Optimizer]を使用して、コンテンツを作成、パーソナライズ、プレビューできる単一のSMS/MMS/RCS エディターから、**SMS**、**MMS**、**RCS**&#x200B;の3つのチャネルで顧客にモバイルメッセージを送信します。

* **SMS （ショートメッセージサービス）**：最大160文字のテキストのみのメッセージを送信し、すべてのモバイルデバイスでサポートします。
* **MMS （マルチメディアメッセージサービス）**：画像、ビデオ、オーディオクリップ、GIFに加えて、最大1,600文字のテキストでメッセージを充実させます。 [MMS の制限の詳細情報](../start/guardrails.md#sms-guardrails)
* **RCS （リッチコミュニケーションサービス）**:Deliver ブランドのインタラクティブなコンテンツを、お客様のネイティブメッセージングアプリで直接使用できます。追加のアプリのダウンロードは必要ありません。

モバイルメッセージは、次のモバイルメッセージアクションを使用して、ジャーニーまたはキャンペーンで作成および送信できます。

* **ジャーニー**&#x200B;で：モバイル メッセージ アクションをジャーニーに追加し、基本設定を定義してから、右側のモバイル メッセージ アクション ペインでコンテンツを構成します。 [詳しくは、ジャーニーの作成方法を参照してください。](../building-journeys/journey-gs.md)

* キャンペーンの&#x200B;**キャンペーン**:Create&#x200B;で、「モバイルメッセージ」をアクションとして選択し、基本設定を定義してから、メッセージコンテンツを編集します。 詳しくは、[アクションキャンペーン](../campaigns/campaign-action.md#action-campaign-action) | [API トリガーキャンペーン](../campaigns/api-triggered-campaigns.md) | [オーケストレーションキャンペーン](../orchestrated/create-orchestrated-campaign.md#create)を作成する方法を参照してください


## 主な特長 {#key-features}

| 機能 | 説明 |
|---|---|
| **パーソナライゼーション** | パーソナライゼーションエディターを使用して、プロファイル属性、条件付きコンテンツ、動的データでメッセージをカスタマイズします。 [詳細情報](../personalization/personalize.md) |
| **プロバイダーのサポート** | API統合を介して、[Sinch](mobile-configuration-sinch.md)、[Twilio](mobile-configuration-twilio.md)、[Infobip](mobile-configuration-infobip.md)、または任意の[ カスタムプロバイダー](mobile-configuration-custom.md)と接続します。 |
| **URL短縮** | エンゲージメントを監視するために、追跡可能な短縮URLを追加します。 サブドメイン設定が必要です。 [詳細情報](mobile-subdomains.md) |
| **オプトアウト管理** | 標準のオプトアウトキーワード（停止、終了、キャンセルなど）の組み込みの処理 SinchとInfobipの。 [詳細情報](mobile-opt-out.md) |
| **プレビューとテスト** | 送信前に、テストプロファイルとサンプルデータを使用してコンテンツを検証します。 [詳細情報](send-mobile-message.md) |
| **レポーティング** | 専用の[ キャンペーンレポート ](../reports/campaign-global-report-cja-sms.md)と[ ジャーニーレポート ](../reports/journey-global-report-cja-sms.md)を使用して、キャンペーンとジャーニーのパフォーマンスを追跡します。 |

## 設定要件 {#configuration-requirements}

テキストメッセージを送信する前に、次の操作を行う必要があります。

1. **SMS プロバイダーを選択**: Sinch、Twilio、Infobipから選択するか、カスタム プロバイダーを設定します
2. **API資格情報の設定**: プロバイダーのAPI トークンとサービス IDをJourney Optimizerと統合します
3. **チャネル設定の作成**: マーケティングおよびトランザクションメッセージ用のSMS設定の設定
4. **サブドメインの設定（オプション）**: メッセージでURL短縮を使用する場合にのみ必要です

これらの設定手順は通常、システム管理者が実行します。 [SMS 設定の基本を学ぶ](mobile-configuration.md)

### RCSの要件 {#requirement-rcs}

Journey OptimizerでRCSを使用するには、次の前提条件が必要です。

* **Sinch RCS API資格情報**：管理者は、Sinch RCS ベンダー（プロジェクト ID、アプリ ID、API トークン）のAPI資格情報を設定する必要があります。 [詳細情報](mobile-configuration-sinch.md)
* **モバイルメッセージチャネル設定**：管理者は、RCS対応の資格情報を選択してチャネル設定を作成する必要があります。これにより、メッセージはSMSではなくRCSとして配信されます。 [詳細情報](mobile-configuration.md)
* **フォールバック SMS**：強くお勧めします。 RCSをサポートしていないデバイスの受信者は、SMS フォールバックが利用可能でない限り、メッセージを受信しません。 既存のSMS ボリュームがない顧客は、SMSとショートコードを購入する必要があります。 [詳細情報](design-mobile.md#rcs-content)
* **サポートされているベンダー**：ネイティブ RCS オーサリングには、Sinch RCS （Adobe再販またはダイレクト）が必要です。 Twilio、Infobip、およびその他のプロバイダーは、カスタムプロバイダー統合を使用する必要があります。
* **デバイスサポート**: RCS配信は、AndroidおよびiOS デバイスでサポートされています。 キャリアおよび地域の可用性は異なり、RCSは世界中で一般的に利用できません。

## その他のリソース {#additional-resources}

Journey Optimizer でのテキストメッセージについて詳しくは、以下のトピックを参照してください。

+++設定ガイド

SMS 環境を設定する方法について説明します。

* [SMS チャネル設定の概要](mobile-configuration.md)
* [SMS チャネル設定の作成](mobile-configuration-surface.md)
* [URL 短縮用の SMS サブドメインの設定](mobile-subdomains.md)

+++

+++プロバイダー設定ガイド

各 SMS サービスプロバイダーのステップバイステップの設定：

* [Sinch プロバイダーの設定](mobile-configuration-sinch.md)
* [Twilio プロバイダーの設定](mobile-configuration-twilio.md)
* [Infobip プロバイダーの設定](mobile-configuration-infobip.md)
* [カスタム SMS プロバイダーの設定](mobile-configuration-custom.md)

+++

+++コンテンツの作成と管理

テキストメッセージコンテンツを作成、パーソナライズ、管理します。

* [SMS／MMS メッセージの作成](create-mobile-message.md)
* [メッセージのプレビュー、テスト、送信](send-mobile-message.md)
* [テキストメッセージのパーソナライゼーション](../personalization/personalize.md)
* [動的コンテンツ](../personalization/get-started-dynamic-content.md)
* [AI アシスタントを使用した SMS コンテンツの生成](../content-management/generative-text.md)

+++

+++コンプライアンスとプライバシー

テキストメッセージが規制とプライバシー標準に準拠していることを確認します。

* [オプトアウト管理](mobile-opt-out.md)
* [プライバシーと同意](../privacy/opt-out.md#opt-out-decision-management)

+++

+++パフォーマンストラッキング

SMS キャンペーンとジャーニーのパフォーマンスを監視および分析します。

* [SMS キャンペーンレポート](../reports/campaign-global-report-cja-sms.md)
* [SMS ジャーニーレポート](../reports/journey-global-report-cja-sms.md)

+++

+++ジャーニーとキャンペーンの統合

SMS をカスタマージャーニーやキャンペーンに組み込む方法について説明します。

* [ジャーニーへの SMS メッセージの追加](../building-journeys/journey-action.md)
* [SMS キャンペーンの作成](../campaigns/create-campaign.md)

+++

+++RCSに関するよくある質問

**ネイティブのRCS メッセージはTwilioまたはInfobipで利用できますか？**

いいえ。 Journey Optimizerのネイティブ RCS デザイナーは、TwilioやInfobipなどのサードパーティのSMS プロバイダーを使用している場合は使用できません。 ただし、RCS メッセージは[ カスタムプロバイダー統合](mobile-configuration-custom.md)を介して送信できます。

**なぜRCSと一緒にSMSを購入するのですか？**

SMS フォールバックを有効にするには、SMS ボリュームとショートコードを購入する必要があります。これは、推奨パスです。 SMSが設定されていない場合、デバイスまたはキャリアがRCSをサポートしていないプロファイルは、メッセージをまったく受信しません。

**Sinch ダイレクトのお客様はネイティブのRCS メッセージを利用できますか？**

はい。 Sinchの対話型APIを使用しているお客様は、Adobeの再販とSinchのダイレクトのお客様の両方を含む、ネイティブのRCS オーサリングにアクセスできます。

**RCSはどこでも利用できますか？**

いいえ。 キャリアの採用は世界的に拡大し続けていますが、RCSはすべてのキャリアと地域で一般的にサポートされているわけではありません。 RCS キャンペーンを計画する際には、地域の可用性とキャリアのサポートについて調査する必要があります。

**RCS メッセージはデバイス上のどこに表示されますか？**

RCS メッセージは、標準のSMS メッセージと同じ場所（デバイスのネイティブメッセージングアプリケーション）に表示されます。 その場合、受信者は、ブランドが設定された検証済みの送信者から電子メールを受信し、そのメッセージが正当なものであることを信頼するためのシグナルを受け取ります。

**RCS メッセージの文字数の上限を教えてください。**

リッチメディア（シングル）メッセージタイプは、最大3,072文字をサポートし、標準SMSの160文字の制限を大幅に上回ります。 基本的なRCS メッセージタイプは、標準のSMS制限に一致する160文字に制限されています。

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
