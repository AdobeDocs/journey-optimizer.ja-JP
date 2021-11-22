---
title: Journey Optimizer Get Started for Data Engineer
description: データエンジニアとして、Journey Optimizerの使用方法の詳細を学ぶ
level: Intermediate
exl-id: 8beaafc2-e68d-46a1-be5c-e70892575bfb
source-git-commit: f0c5b42984b76fee005fe0c0e10312d47f9d10e8
workflow-type: tm+mt
source-wordcount: '578'
ht-degree: 47%

---

# データエンジニア向けスタートガイド {#data-engineer}

![データエンジニア](assets/do-not-localize/user-1.png)

As a **Adobe Journey Optimizer Data Engineer**、顧客プロファイルデータを準備および維持して、 [!DNL Journey Optimizer]、スキーマで顧客データとビジネスデータをモデル化し、データを取り込むためのソースコネクタを設定します。 以下の作業を開始する前に、 [!DNL Adobe Journey Optimizer] を [システム管理者](administrator.md) により、アクセス権が付与され、環境が準備されました。


方法を学ぶ **データの特定とスキーマとデータセットの作成** データをAdobe Experience Platformに取り込むには、このページを参照してください。

>[!NOTE]
>
>**データ取り込み**&#x200B;の詳細：[Adobe Experience Platform ドキュメント](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html?lang=ja){target=&quot;_blank&quot;}.

ID 名前空間と、プロファイルに対して有効なデータセットを作成する手順、およびテストプロファイルについては、以下の節で詳しく説明します。

1. **ID 名前空間の作成**. Adobe [!DNL Journey Optimizer], **ID** デバイスやチャネルをまたいで消費者をリンクさせると、id グラフが生成されます。 リンクされた ID グラフは、すべてのビジネスタッチポイントにわたるインタラクションに基づいてエクスペリエンスをパーソナライズするために使用します。ID と ID 名前空間の詳細を説明します [このページ](../get-started-identity.md).

1. **スキーマの作成** プロファイルに対して有効にします。 スキーマは、データの構造と形式を表し、検証する一連のルールです。スキーマは、高いレベルで、実世界のオブジェクト（人など）の抽象的な定義を提供し、そのオブジェクトの各インスタンスに含めるデータ（名、姓、誕生日など）の概要を示します。スキーマの詳細を説明します [このページ](../get-started-schemas.md).

1. **データセットの作成** プロファイルに対して有効にします。 データセットは、スキーマ（列）とフィールド（行）を含んだデータコレクション（通常はテーブル）のストレージおよび管理用の構成体です。データセットには、保存するデータの様々な側面を記述したメタデータも含まれます。データセットを作成したら、既存のスキーマにマッピングし、データを追加できます。 データセットの詳細 [このページ](../get-started-datasets.md).

1. **ソースコネクタの設定**. AdobeジャーニーOptimizer を使用すると、データを外部ソースから取り込みながら、Platform サービスを使用して、受信データの構造化、ラベル付け、拡張をおこなうことができます。 アドビのアプリケーション、クラウドベースのストレージ、データベースなど、様々なソースからデータを取り込むことができます。ソースコネクタの詳細を説明します [このページ](../get-started-sources.md).

1. **テストプロファイルの作成**. テストプロファイルは、 [テストモード](../building-journeys/testing-the-journey.md) 旅の中で [メッセージのプレビューとテスト](../preview.md) 送信する前に テストプロファイルを作成する手順を確認する [このページ](../../using/building-journeys/creating-test-profiles.md).


また、ジャーニーでメッセージを送信するには、**[!UICONTROL データソース]**、**[!UICONTROL イベント]**&#x200B;および&#x200B;**[!UICONTROL アクション]**&#x200B;を設定する必要があります。 詳しくは、[この節](../../using/configuration/about-data-sources-events-actions.md)を参照してください。

![](../assets/admin-menu.png)

* **データソース**&#x200B;を設定すると、ジャーニーで使用される追加情報を取得するため、システムへの接続を定義できます。データソースの詳細を表示 [この節](../datasource/about-data-sources.md).

* **イベント**&#x200B;を使用すると、ジャーニーをまとめてトリガーし、ジャーニーに流入してくる個人にリアルタイムでメッセージを送信できます。イベントの設定では、ジャーニーで必要なイベントを設定します。受信イベントのデータは、Adobe Experience Data Model（XDM）に従って正規化されます。イベントは、認証済みイベントと未認証イベント（Adobe Mobile SDK イベントなど）のストリーミング取り込み API から取り込みます。イベントの詳細 [この節](../event/about-events.md).

* [!DNL Journey Optimizer] には、コンテンツをデザインし、メッセージを公開できる組み込みのメッセージ機能が備わっています。サードパーティシステム (Adobe Campaignなど ) を使用してメッセージを送信する場合は、 **カスタムアクション**. このアクションの詳細を表示 [この節](../action/action.md).
