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
TQID: https://experienceleague.adobe.com/fWsW9Rvyd8L4nphczzc7GF1rbO7HuYsjqDBBpy3uoGU
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2:
  - id: aeebb91a-f216-4d5f-8da1-3a7e6f696ed0
subfeature_v2:
  - id: b3a93754-a8b8-46eb-9421-7eccaeeb3dff
  - id: a1cdc218-59b7-4eef-b5cf-2a7ad74b3371
  - id: d6e5c7fd-c1d6-4137-98cd-138ccde6752f
  - id: cf3fbcd7-c075-4ae4-8de5-96e736ab2ea3
  - id: e30b0a1a-b594-47b8-af94-1e3a2be6df11
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b23e006f-0a29-4f1d-8fd0-77aa56f3d12b
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: 79b0c44fffb4297a9a5675200f086c5de544ec88
workflow-type: tm+mt
source-wordcount: 609
ht-degree: 72%

---

# スキーマの基本を学ぶ {#schemas-gs}

>[!BEGINSHADEBOX]

**このページでは、** Adobe Experience Platformの標準スキーマとリレーショナルスキーマがデータ構造をどのように定義しているかを理解します。これにより、Adobe Journey Optimizerでパーソナライズおよびオーケストレーションされたキャンペーンのために、プロファイル、行動イベント、リレーショナルエンティティをモデル化できます。

>[!ENDSHADEBOX]

[!DNL Adobe Journey Optimizer] では、**Adobe Experience Platform スキーマ**&#x200B;に依存して、一貫性のある再利用可能な方法でデータの構造を記述します。 スキーマは、現実のオブジェクト（人物など）の概念上の定義を提供し、そのオブジェクトの各インスタンスに含める必要があるデータ（名前や誕生日など）の概要を説明します。 データが Experience Platform に取り込まれると、常に **XDM スキーマ**&#x200B;に応じて構造化されます。

## 標準スキーマとリレーショナルスキーマ

Adobe Experience Platform には、2 つのタイプのスキーマがあります。

* **標準スキーマ**&#x200B;は、クラスとフィールドグループを使用してレコードまたは時系列データを取り込む階層スキーマです。

  標準スキーマは、次の要素で構成されます。

   * **クラス**（レコードまたは時系列のデータの動作を定義します）。
   * 1 つ以上の&#x200B;**フィールドグループ**（特定のフィールドをスキーマに追加します）。

  Journey Optimizer では、標準スキーマは通常、**個々の人物とその属性**&#x200B;を表し、クリック、購入、ログインなどの&#x200B;**時系列のインタラクション**&#x200B;をキャプチャし、セグメント化とパーソナライゼーションの&#x200B;**リアルタイム顧客プロファイル**&#x200B;を強化することを目的に使用されます。

  ➡️ [標準スキーマの作成と設定の方法について詳しくは、このビデオを参照してください。](#video-schema)（ビデオ）

* **リレーショナルスキーマ**&#x200B;は、クラスやフィールドグループを使用しないフラットな非階層スキーマです。 これらはリレーショナルエンティティのレコードデータを取得することを目的に使用され、主に [!DNL Journey Optimizer] **オーケストレーションキャンペーン**&#x200B;で使用されます。

  リレーショナルエンティティの例を次に示します。
   * 予約、契約または購読
   * 製品またはカタログ
   * ストア、ロケーション、パートナー

  リレーショナルスキーマを使用すると、エンティティごと（例：予約ごと、購読ごと）に 1 つのメッセージを送信し、エンティティの属性（例：製品カテゴリ、ストアの場所）に基づいてセグメントを作成し、エンティティにリンクされているすべての連絡先にリーチすることでアドレサビリティを向上させることができます。

  リレーショナルスキーマの仕組み：

   1. **スキーマを手動で作成または DDL 経由で読み込む**
   1. **スキーマをリンク**&#x200B;して、エンティティと人物の関係を定義します（例：メンバーにリンクされたロイヤルティトランザクション、ブランドにリンクされた報酬）。
   1. サポートされているソースからデータセットに&#x200B;**データを取得**&#x200B;します。

  ➡️ [リレーショナルスキーマとデータセットの管理方法を学ぶ](../orchestrated/gs-schemas.md)
➡️ [オーケストレーションキャンペーンの基本を学ぶ](../orchestrated/gs-schemas.md)

>[!IMPORTANT]
>
>リアルタイム顧客プロファイルのスキーマを有効にすることは、永続的な決定です。有効にすると、スキーマを無効にしたり削除したりすることはできません。 そのスキーマ上に構築されたデータセットは、個別に無効化または削除できますが、そうすることで、関連するプロファイルレコードが削除され、セグメント化とアクティベーションのワークフローに影響を与える可能性があります。 有効にする前に、ID設定とフィールドグループの選択を確定します。 詳しいガイダンスについては、Adobe Experience Platform ドキュメントの「[&#x200B; プロファイルのイネーブルメント計画](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/schema/profile-enablement-planning){target="_blank"}」および「[&#x200B; プロファイル対応スキーマの管理](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/schema/best-practices#managing-profile-enabled-schemas){target="_blank"}」を参照してください。

## チュートリアルビデオ{#video-schema}

標準スキーマの作成、フィールドグループの追加、カスタムフィールドグループの作成および設定の方法について説明します。

>[!VIDEO](https://video.tv.adobe.com/v/334461?quality=12)

>[!MORELIKETHIS]
>
>* [Journey Optimizer におけるデータ管理の基本を学ぶ](gs-data.md)
>* [スキーマとデータセットの作成およびデータの取り込みによる Journey Optimizer へのテストプロファイルの追加](../audience/creating-test-profiles.md)
>* [XDM システムの概要](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=ja){target="_blank"}
>* [データモデリングのベストプラクティス](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/best-practices.html?lang=ja){target="_blank"}
>* [&#x200B; プロファイルのイネーブルメント計画](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/schema/profile-enablement-planning){target="_blank"}
>* [&#x200B; プロファイル対応スキーマの管理](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/schema/best-practices#managing-profile-enabled-schemas){target="_blank"}
>* [Schema Registry API を使用したスキーマの作成](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-api.html?lang=ja){target="_blank"}
>* [スキーマエディターを使用した 2 つのスキーマ間の関係の定義](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/relationship-ui.html?lang=ja){target="_blank"}
