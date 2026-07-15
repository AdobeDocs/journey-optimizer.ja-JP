---
title: カスタムチャネルの設定 – 概要
description: チャネルの作成からチャネル設定の設定まで、Adobe Journey Optimizerでカスタムチャネルを設定するために管理者が実行する必要がある手順を説明します。
feature: Channel Configuration
topic: Content Management
role: Admin
level: Experienced
badge: label="限定提供" type="Informative"
source-git-commit: 4556e8b50fe71cf9d703d034a3c5772b8fea9d33
workflow-type: tm+mt
source-wordcount: '355'
ht-degree: 9%

---


# カスタムチャネルの設定 {#custom-channel-configuration}

>[!AVAILABILITY]
>
>この機能は、限定提供で使用できます。 アクセス権を取得するには、アドビ担当者にお問い合わせください。

カスタムチャネルの設定は、チャネルごとに1回実行される管理者タスクです。 チャネルを設定すると、マーケターは、ネイティブの[!DNL Journey Optimizer] チャネルと同様に、キャンペーン、ジャーニー、オーケストレーションされたキャンペーンですぐにチャネルを選択できます。

この設定プロセスでは、チャネル自体（エンドポイント、認証、ペイロード）の定義、リクエストの認証に使用されるAPI資格情報の管理、オプションでリンクトラッキング用のサブドメインのデリゲート、マーケターがオーサリング時に選択するチャネル設定の作成という4つのステップを実行します。

>[!NOTE]
>
>まず、必要な権限やサポートされている認証方法など、カスタムチャネルの前提条件とガードレールを確認してください。

## 設定の手順 {#steps}

カスタムチャネルの設定プロセスは、次の4つのステップで構成されています。 各工程については下記リンク先の記事で詳しく説明しています。

| 手順 | 実行すること | これが重要な理由 | リンク |
| --- | --- | --- | --- |
| **1. カスタムチャネルを作成** | チャネルビルダーで、エンドポイント URL、ヘッダー、スロットルポリシー、認証タイプ、メッセージペイロード構造を定義します。 | これがチャネルの定義です。 メッセージの送信方法とそのメッセージの外観を[!DNL Journey Optimizer]に伝えます。 | [詳細情報](create-custom-channel.md) |
| **2. API資格情報の管理** | エンドポイントに対するリクエストの認証に使用される認証情報のセットを作成および管理します。 | 複数の資格情報セットを使用すると、チャネルを複製することなく、異なるブランドや環境で同じチャネル定義を再利用できます。 | [詳細情報](custom-channel-api-credentials.md) |
| **3. サブドメイン** *（オプション）*&#x200B;をデリゲートします | カスタムチャネル専用のサブドメインをデリゲートします。 | メッセージペイロードに追跡可能なリンクが含まれている場合にのみ必要です。 デリゲートされたサブドメインがない場合、このチャネルではリンクトラッキングを利用できません。 | [詳細情報](custom-channel-subdomains.md) |
| **4. チャネル設定の作成** | カスタムチャネルを特定の資格情報セット、サブドメイン、およびオプションのペイロードのデフォルトにリンクする名前付きプリセットを作成します。 | キャンペーンやジャーニーを構築する際、マーケターはカスタムチャネルと関連するチャネル設定を選択します。 同じチャネルに複数の設定を作成できます（例えば、ブランドまたは地域ごとに1つ）。 | [詳細情報](custom-channel-configuration.md) |

<!--
## Get started {#get-started}

1. [Create the custom channel](create-custom-channel.md) by defining its endpoint, authentication method, and message payload structure in the Channel Builder.
1. [Set up API credentials](custom-channel-api-credentials.md) to authenticate requests sent to your endpoint — required for all authentication types other than **None**.
1. [Delegate a subdomain](custom-channel-subdomains.md) if your message payload includes trackable links and you want them served from a branded domain.
1. [Create a channel configuration](custom-channel-configuration.md) to produce the named preset that marketers will select when building campaigns and journeys.


-->