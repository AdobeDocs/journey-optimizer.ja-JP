---
title: カスタムチャネルの基本を学ぶ
description: ' [!DNL Journey Optimizer]''s Channel Builder to bring any outbound messaging channel into [!DNL Journey Optimizer] を使用して、キャンペーン、ジャーニー、およびオーケストレーションされたキャンペーンで使用する方法を説明します。'
feature: Channel Configuration
topic: Content Management
role: User
level: Beginner
badge: label="限定提供" type="Informative"
source-git-commit: 94ca2d9458152fb471e9590d053c4729a4a5134f
workflow-type: tm+mt
source-wordcount: '628'
ht-degree: 5%

---


# カスタムチャネルの基本を学ぶ {#get-started-custom-channel}

>[!AVAILABILITY]
>
>この機能は、限定提供で使用できます。 アクセス権を取得するには、アドビ担当者にお問い合わせください。

<!--Multilingual support, business rules enforcement, and [!DNL Adobe Experience Decisioning] integration are planned for a future release.-->

[!DNL Journey Optimizer]の&#x200B;**カスタムチャネル**&#x200B;機能を使用すると、任意のアウトバウンドチャネルを[!DNL Journey Optimizer]に取り込むことができ、ネイティブチャネルと同様に、キャンペーン、ジャーニー、オーケストレーションされたキャンペーンで使用できます。 **チャネルビルダー**&#x200B;を使用すると、管理者はエンジニアの関与なしに新しいチャネルを作成および設定でき、マーケターはすぐに顧客とのコミュニケーションに使用を開始できます。

## どのような問題を解決するのか？ {#why-custom-channels}

[!DNL Journey Optimizer]は、電子メール、SMS、プッシュ通知、WhatsApp、LINE、その他のチャネルをネイティブでサポートしています。 しかし、多くの組織は、ネイティブに統合されていないメッセージングプラットフォーム（WeChat、Kakao Talk、Messenger、外部プロバイダーなど）を使用しており、独自のベンダーと引き続き配信しながら、オーケストレーションやキャンペーン作成に[!DNL Journey Optimizer]で使用したいと考えています。

<!--TBC: Another use case is when organizations have a legacy messaging gateway that exposes an HTTP endpoint, and they want to use it in [!DNL Journey Optimizer] without having to build a custom integration.-->

カスタムチャネルはこのギャップを埋めます。任意のアウトバウンド HTTP エンドポイントをフル [!DNL Journey Optimizer] チャネルとして使用でき、次のロックを解除します。

* **フルチャネル機能** – 最適化（コンテンツの実験とターゲティング）、OOTB レポートと監視、同意とガバナンスの適用、式のフラグメント。<!--Multilingual and business rules are planned for a future release.-->
* **統合オーケストレーション** – 基盤となる配信プロバイダーに関係なく、すべてのメッセージングチャネルを1か所で管理します。
* **ノーコード設定** – 管理者はチャネルビルダーUIを使用してチャネルを設定します。カスタムコードやエンジニアリングの作業は必要ありません。

## カスタムチャネルとカスタムアクションの違い {#custom-channel-vs-custom-action}

以前[!DNL Journey Optimizer]件のジャーニーで[&#x200B; カスタムアクション &#x200B;](../action/action.md)を使用したことがある場合、カスタムチャネルは異なるユースケースのセットに対応します。

**WeChat、Kakao Talk、カスタムメッセージングゲートウェイなど、[!DNL Journey Optimizer]でネイティブにサポートされていないプラットフォームを通じてエンドユーザーにメッセージを送信する必要がある場合**&#x200B;は、カスタムチャネルを使用します。 カスタムチャネルは、キャンペーン、ジャーニー、オーケストレーションされたキャンペーン、サポートで利用できます。

* ネイティブのアウトバウンドチャネルと同様の、パーソナライゼーションエディターによる完全なパーソナライゼーション
* ビジュアル/フォームペイロードエディター、プレビューおよびプルーフ
* コンテンツの実験とターゲティング
* OOTB レポートとモニタリング
* 複数のAPI資格情報とチャネル設定
* RBAC/ABAC

カスタムチャネルは、唯一のHTTP メソッドとしてPOSTをサポートします。

**コールセンター、ロギングプラットフォーム、オフラインデータベースなどの情報を外部システムから取得または外部システムにプッシュする必要がある場合**&#x200B;は、ジャーニー内のステップとしてカスタムアクションを使用します。 カスタムアクションはジャーニーでのみ使用でき、GET、PUT、POST メソッドをサポートします。

<!--
| | Custom Action | Custom Channel |
| --- | --- | --- |
| **Primary use case** | Retrieve data from or send information to external systems (call centers, offline systems, logging) | Send messages to end users through channels not natively supported in [!DNL Journey Optimizer] |
| **Available in** | Journeys only | Campaigns, journeys, and orchestrated campaigns |
| **Supported HTTP methods** | GET, PUT, POST | POST only |
| **Full personalization (PE)** | No | Yes, through the personalization editor, similar to native outbound channels |
| **Visual/form editor** | No | Yes |
| **Preview and proof** | No | Yes |
| **Content experimentation** | No | Yes |
| **Targeting** | No | Yes |
| **OOTB Reporting** | Yes | Yes |
| **Multiple API credentials and channel configurations** | No | Yes |
| **RBAC/ABAC** | No | Yes |
-->

>[!TIP]
>
>一般的な推奨事項として、エンドユーザーにメッセージを送信するチャネルのユースケースには、カスタムチャネルを使用します。 データの取得や外部システムのトリガーなど、ジャーニーで必要なその他のコネクタのようなユースケースの場合、カスタムアクションを引き続き使用できます。

## ユースケース {#use-cases}

カスタムチャネルは、次のような場合に最適です。

* **サポートされていないメッセージングプラットフォーム** - WeChat、Kakao Talk、Messenger、Telegram、またはネイティブ [!DNL Journey Optimizer] チャネルを持たない地域メッセージングサービスなどのチャネル。
* **カスタム配信プロバイダー** - メッセージ配信に引き続き使用する外部プロバイダーに投資しているが、オーケストレーション、パーソナライゼーション、キャンペーン管理に[!DNL Journey Optimizer]を活用することを希望する組織。
* **レガシーチャネル** - HTTP エンドポイントを公開する独自またはレガシーメッセージングゲートウェイ。
* **業界固有のチャネル** – 医療、銀行通知システム、または政府通知サービス向けの安全なメッセージ。

## 仕組み {#how-it-works}

カスタムチャネルの設定と使用は、次の主な手順に従います。

1. **Configure** （管理者） – 管理者は、**チャネルビルダー**&#x200B;にカスタムチャネルを作成し、エンドポイント、認証、スロットリングポリシー、メッセージペイロード構造を定義します。 チャネル設定が作成され、カスタムチャネルにリンクされます。 [詳細情報](configure-custom-channel.md)
1. **作成** （マーケター） – マーケターがカスタムチャネルをジャーニー、キャンペーン、またはオーケストレーションされたキャンペーンに追加し、チャネル設定を選択し、[!DNL Journey Optimizer]のパーソナライゼーションエディターを使用してメッセージペイロードを作成します。 [詳細情報](create-custom-experience.md)
1. **送信** - プロファイルが適格である場合、[!DNL Journey Optimizer]は設定されたエンドポイントにパーソナライズされたペイロードを送信します。 外部システムは呼び出しを処理し、メッセージを配信します。
1. **監視** （管理者/マーケター） – 管理者とマーケターは、[!DNL Journey Optimizer]のレポートと監視ダッシュボードを使用して、カスタムチャネルのパフォーマンスと信頼性を監視できます。 [詳細情報](monitor-custom-channel.md)

<!--
## Next steps {#next-steps}

* Review the prerequisites and permissions before setting up your first custom channel. [Learn more](custom-channel-prerequisites.md)
* Configure your first custom channel using the Channel Builder. [Learn more](custom-channel-configuration.md)
* Create a custom channel experience in a journey or campaign. [Learn more](create-custom-experience.md)
-->
