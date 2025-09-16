---
solution: Journey Optimizer
product: journey optimizer
title: スキーマの基本を学ぶ
description: Adobe Journey Optimizer での Adobe Experience Platform スキーマの使用方法について説明します。
feature: Data Model, Datasets, Data Management
role: Data Engineer, Data Architect, Admin
level: Experienced
keywords: スキーマ, Platform, データ, 構造
exl-id: c2a8df2e-ff94-4f9a-a53e-bbf9f663cc81
source-git-commit: 70f647cf4e95c1152a5c16395b88b11a6b72865c
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# スキーマの基本を学ぶ {#schemas-gs}

[!DNL Adobe Journey Optimizer] は、**Adobe Experience Platform スキーマを利用して** 一貫した再利用可能な方法でデータの構造を記述しています。 スキーマは、実際のオブジェクト（人など）の抽象的な定義を提供し、そのオブジェクトの各インスタンスに含めるデータ（名前、生年月日など）の概要を示します。 データがExperience Platformに取り込まれると、常に **XDM スキーマ** に従って構造化されます。

## 標準スキーマとリレーショナルスキーマ

Adobe Experience Platformには次の 2 種類のスキーマがあります。

* **標準スキーマ** は、クラスおよびフィールドグループを使用してレコードまたは時系列データをキャプチャする階層スキーマです。

  標準スキーマは、次の要素で構成されます。

   * **クラス** （データの動作を定義します：レコードまたは時系列）。
   * 1 つ以上の **フィールドグループ** （スキーマに特定のフィールドを追加します）。

  Journey Optimizerでは、通常、標準スキーマを使用して **個人とその属性** を表し、クリック、購入、ログインなどの **時系列のインタラクション** をキャプチャし、セグメント化とパーソナライゼーションのための **リアルタイム顧客プロファイル** を強化します。

  ➡️[ このビデオで標準スキーマの作成および設定方法を説明します ](#video-schema) （ビデオ）

* **リレーショナルスキーマ** は、クラスやフィールドグループを使用しない、フラットな非階層スキーマです。 リレーショナルエンティティのレコードデータを取得するために使用され、主に [!DNL Journey Optimizer] オーケストレートキャンペーン **で使用され** す。

  リレーショナルエンティティの例を次に示します。
   * 予約、契約または購読
   * 製品またはカタログ
   * ストア、ロケーション、パートナー

  リレーショナルスキーマを使用すると、エンティティ（予約、サブスクリプションなど）ごとに 1 つのメッセージを送信し、エンティティ属性（製品カテゴリ、ストアの場所など）に基づいてセグメントを作成し、エンティティにリンクされたすべての連絡先にアクセスすることでアドレス可能性を向上させることができます。

  リレーショナルスキーマの機能：

   1. **手動でスキーマを作成するか、DDL を使用してインポートする**
   1. **スキーマをリンク**：エンティティと人物の関係を定義します（例：メンバーにリンクされたロイヤルティトランザクション、ブランドにリンクされた報酬）。
   1. サポートされているソースからデータセットに&#x200B;**データを取得**&#x200B;します。

  ➡️ [ リレーショナルスキーマとデータセットの管理方法を学ぶ ](../orchestrated/gs-schemas.md)
➡️[ オーケストレートキャンペーンの概要 ](../orchestrated/gs-schemas.md)

## チュートリアルビデオ{#video-schema}

標準スキーマの作成、フィールドグループの追加、カスタムフィールドグループの作成および設定の方法について説明します。

>[!VIDEO](https://video.tv.adobe.com/v/334461?quality=12)

>[!MORELIKETHIS]
>
>* [スキーマとデータセットの作成およびデータの取り込みによる Journey Optimizer へのテストプロファイルの追加](../audience/creating-test-profiles.md)
>* [XDM システムの概要](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=ja){target="_blank"}
>* [データモデリングのベストプラクティス](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/best-practices.html?lang=ja){target="_blank"}
>* [Schema Registry API を使用したスキーマの作成](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-api.html?lang=ja){target="_blank"}
>* [スキーマエディターを使用した 2 つのスキーマ間の関係の定義](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/relationship-ui.html?lang=ja){target="_blank"}
