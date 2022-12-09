---
solution: Journey Optimizer
product: journey optimizer
title: データセットでの作業の開始
description: Adobe の旅のオプティマイザーで Adobe エクスペリエンスプラットフォームのデータセットを使用する方法を学習します。
role: User
level: Beginner
exl-id: dcdd3c81-0f00-4259-a8a5-9062a4c40b6f
source-git-commit: 7e27f5502d64d0c91de2c67e4011e650e77c6a92
workflow-type: tm+mt
source-wordcount: '776'
ht-degree: 0%

---

# データセットでの作業の開始 {#datasets-gs}

Adobe エクスペリエンスプラットフォームに ingested れるデータはすべて、データセットとして Data Lake 内に保存されます。 データセットは、データのコレクション (通常はテーブルで、スキーマ (列) とフィールド (行) が含まれるテーブル) の格納と管理の構成要素です。

## データセットへのアクセス{#access-datasets}

ユーザーインターフェイスの [!DNL Adobe Journey Optimizer] データセット **ワークスペースを使用すると、** データを確認してデータセットを作成することができます。

左側のナビゲーションの「データセット **」を選択** すると、データセットのダッシュボードが表示されます。

![](assets/datasets-home.png)

へ [!DNL Adobe Experience Platform] のデータの追加は、プロファイルを作成するための基礎となります。 これにより、の [!DNL Adobe Journey Optimizer] プロファイルを利用できるようになります。 まず、スキーマを定義し、ETL ツールを使用してデータを準備して標準化した後、スキーマに基づいてデータセットを作成します。

**「参照** 」タブを選択すると、組織で利用可能なすべてのデータセットのリストが表示されます。詳しくは、表示されている各データセットについて、その名前、データセットが従うスキーマ、および最新のインジェスト実行のステータスを含めて表示されます。

初期設定では、ingested したデータセットのみが表示されます。 システムによって生成されたデータセットを表示するには、フィルターから「システムデータセット **を表示」をオンに** します。

![](assets/ajo-system-datasets.png)

データセットのアクティビティ画面にアクセスするためのデータセットの名前を選択し、選択したデータセットの詳細を確認します。 「アクティビティ」タブには、処理されているメッセージの比率を視覚的に示すグラフと、成功および失敗したバッチのリストが含まれています。

利用可能なデータセットは、次のとおりです。

**書**

* _レポート-メッセージフィードバックイベントデータセット_ : メッセージ配信ログ: レポート作成およびセグメント作成のための、旅オプティマイザーからのすべてのメッセージ配信に関する情報。 バウンス上の電子メール Isp からのフィードバックも、このデータセットに記録されます。
* _レポート-電子メール追跡エクスペリエンスイベントデータセット_ : 電子メールチャンネルのインタラクションログ: レポート作成とセグメント作成に使用されます。 保存されている情報では、エンドユーザーが電子メールで実行した操作 (開く、クリックなど) が通知されます。
* _レポート-プッシュトラッキングエクスペリエンスイベントデータセット_ : プッシュチャネルのインタラクションログ: レポート作成およびセグメント作成の目的で使用されます。 格納されている情報は、エンドユーザーが実行したアクションについて通知します。
* _レポート作成段階の手順イベント_ : 報告のようなサービスによって使用される、旅オプティマイザーによって生成されたすべてのステップ体験イベントを取得します。 また、ユーザーによる旅の分析において、レポートを作成する場合にも重要です。 、旅メタデータに関連付けられています。
* _レポート-Journeys_ : 各ステップのメタデータデータセットハウジングについて説明しています。
* _レポート-BCC_ : フィードバックイベントデータセット。 bcc 電子メールの配信ログが格納されています。 レポート用に使用されます。

**同意**

* _同意サービスデータセット_ : プロフィールの同意情報を格納します。

**インテリジェントサービス**

* _「送信時に最適化したスコア/エンゲージメント_ 」: AI の出力結果を示します。

## データセットのプレビュー{#preview-datasets}

データセット操作画面の右上にある「データ **セットのプレビュー」を選択し** て、このデータセットで最後に成功したバッチをプレビューします。データセットが空の場合は、「プレビュー」リンクが非アクティブになります。

![](assets/dataset-preview.png)

## データセットの作成{#create-datasets}

新しいデータセットを作成するには、まずデータセットダッシュボードの「データセット **を作成」を選択** します。

できます：

* スキーマからデータセットを作成します。 [詳しくは、このドキュメント ](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=en#schema) 内の詳細をご確認ください。 {target = &quot;_blank&quot;}
* CSV ファイルからデータセットを作成します。 [詳しくは、このドキュメント ](https://experienceleague.adobe.com/docs/experience-platform/ingestion/tutorials/map-a-csv-file.html) 内の詳細をご確認ください。 {target = &quot;_blank&quot;}

このビデオでは、データセットを作成し、それをスキーマにマップし、そのデータにデータを追加して、データが ingested されていることを確認する方法について説明しています。

>[!VIDEO](https://video.tv.adobe.com/v/334293?quality=12)

## データガバナンス

データセットで、データ「ガバナンス **」タブを参照** して、データセットとフィールドレベルのラベルを確認してください。Data ガバナンスは、適用されるポリシーの種類に応じて、データを分類します。

の [!DNL Adobe Experience Platform] 中核的な機能の1つは、複数のエンタープライズシステムからデータを取得して、マーケティング担当様による特定、理解、協力を強化することです。 このデータは、組織または法律上の規制によって定義されている使用制限の対象になります。 そのため、データ操作がデータ使用ポリシーに準拠していることを確認しておくことが重要です。

[!DNL Adobe Experience Platform Data Governance] では、お客様のデータを管理することができます。また、データの使用に関する規制、制限事項、ポリシーに関するコンプライアンスについてもご確認ください。 カタログ化、データ系統、データ使用状況のラベル付け、データ使用ポリシー、マーケティングアクション用のデータ使用の制御など、様々なレベルのエクスペリエンスプラットフォームにおいて重要な役割を果たします。

データガバナンスについて詳しくは、 [ ](https://experienceleague.adobe.com/docs/experience-platform/data-governance/labels/user-guide.html) data ガバナンスに関する説明を参照してください。 {target = &quot;_blank&quot;}

## サンプルと使用例{#uc-datasets}

このエンドツーエンドのサンプルで [ Adobe 旅オプティマイザーにテストプロファイルを追加するために、スキーマ、データセット、取り込むデータを作成する方法について説明します。](../segment/creating-test-profiles.md)

Adobe エクスペリエンスプラットフォームマニュアル ](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/overview.html) のデータセット作成について詳しくは、 [ target = &quot;_blank&quot;} を参照してください。

データ取り込みの概要マニュアル ](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html) でデータセット UI を使用する方法について説明し [ ます ({target = &quot;_blank&quot;})。

ここで ](../data/datasets-query-examples.md) は、クエリーの例として使用できる [ 用途の一覧を示します。

**関連項目**

* [ストリーミング取り込みの概要 ](https://experienceleague.adobe.com/docs/experience-platform/ingestion/streaming/overview.html) {target = &quot;_blank&quot;}
* [Adobe エクスペリエンス Platform ](https://experienceleague.adobe.com/docs/experience-platform/ingestion/tutorials/ingest-batch-data.html) へのデータの取り込み {target = &quot;_blank&quot;}
