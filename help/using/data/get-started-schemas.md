---
solution: Journey Optimizer
product: journey optimizer
title: スキーマの基本を学ぶ
description: Adobe Journey Optimizer での Adobe Experience Platform スキーマの使用方法について説明します。
feature: Data Model, Datasets, Data Management
role: Developer, Admin
level: Experienced
keywords: スキーマ, Platform, データ, 構造
exl-id: c2a8df2e-ff94-4f9a-a53e-bbf9f663cc81
source-git-commit: 059670c143595b9cacdf7e82a8a5c3efda78f30b
workflow-type: tm+mt
source-wordcount: '394'
ht-degree: 100%

---

# スキーマの基本を学ぶ {#schemas-gs}

[!DNL Adobe Journey Optimizer] では、**Adobe Experience Platform スキーマ**&#x200B;に依存して、一貫性のある再利用可能な方法でデータの構造を記述します。スキーマは、現実のオブジェクト（人物など）の概念上の定義を提供し、そのオブジェクトの各インスタンスに含める必要があるデータ（名前や誕生日など）の概要を説明します。データが Experience Platform に取り込まれると、常に **XDM スキーマ**&#x200B;に応じて構造化されます。

## 標準スキーマとリレーショナルスキーマ

Adobe Experience Platform には、2 つのタイプのスキーマがあります。

* **標準スキーマ**&#x200B;は、クラスとフィールドグループを使用してレコードまたは時系列データを取り込む階層スキーマです。

  標準スキーマは、次の要素で構成されます。

   * **クラス**（レコードまたは時系列のデータの動作を定義します）。
   * 1 つ以上の&#x200B;**フィールドグループ**（特定のフィールドをスキーマに追加します）。

  Journey Optimizer では、標準スキーマは通常、**個々の人物とその属性**&#x200B;を表し、クリック、購入、ログインなどの&#x200B;**時系列のインタラクション**&#x200B;をキャプチャし、セグメント化とパーソナライゼーションの&#x200B;**リアルタイム顧客プロファイル**&#x200B;を強化することを目的に使用されます。

  ➡️ [標準スキーマの作成と設定の方法について詳しくは、このビデオを参照してください。](#video-schema)（ビデオ）

* **リレーショナルスキーマ**&#x200B;は、クラスやフィールドグループを使用しないフラットな非階層スキーマです。これらはリレーショナルエンティティのレコードデータを取得することを目的に使用され、主に [!DNL Journey Optimizer] **オーケストレーションキャンペーン**&#x200B;で使用されます。

  リレーショナルエンティティの例を次に示します。
   * 予約、契約または購読
   * 製品またはカタログ
   * ストア、ロケーション、パートナー

  リレーショナルスキーマを使用すると、エンティティごと（例：予約ごと、購読ごと）に 1 つのメッセージを送信し、エンティティの属性（例：製品カテゴリ、ストアの場所）に基づいてセグメントを作成し、エンティティにリンクされているすべての連絡先にリーチすることでアドレサビリティを向上させることができます。

  リレーショナルスキーマの仕組み：

   1. **スキーマを手動で作成または DDL 経由で読み込む**
   1. **スキーマをリンク**&#x200B;して、エンティティと人物の関係を定義します（例：メンバーにリンクされたロイヤルティトランザクション、ブランドにリンクされた報酬）。
   1. サポートされているソースからデータセットに&#x200B;**データを取得**&#x200B;します。

  ➡️ [リレーショナルスキーマとデータセットの管理方法について説明します。](../orchestrated/gs-schemas.md)
➡️[オーケストレーションキャンペーンの基本を学ぶ](../orchestrated/gs-schemas.md)

## チュートリアルビデオ{#video-schema}

標準スキーマの作成、フィールドグループの追加、カスタムフィールドグループの作成および設定の方法について説明します。

>[!VIDEO](https://video.tv.adobe.com/v/3417458?captions=jpn&quality=12)

>[!MORELIKETHIS]
>
>* [スキーマとデータセットの作成およびデータの取り込みによる Journey Optimizer へのテストプロファイルの追加](../audience/creating-test-profiles.md)
>* [XDM システムの概要](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=ja){target="_blank"}
>* [データモデリングのベストプラクティス](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/best-practices.html?lang=ja){target="_blank"}
>* [Schema Registry API を使用したスキーマの作成](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-api.html?lang=ja){target="_blank"}
>* [スキーマエディターを使用した 2 つのスキーマ間の関係の定義](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/relationship-ui.html?lang=ja){target="_blank"}
