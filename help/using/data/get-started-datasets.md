---
solution: Journey Optimizer
product: journey optimizer
title: データセットの基本を学ぶ
description: Adobe Journey Optimizer での Adobe Experience Platform データセットの使用方法について説明します。
feature: Data Model, Datasets, Data Management
role: Developer, Admin
level: Experienced
keywords: プラットフォーム, データレイク, 作成, レイク, データセット, プロファイル
exl-id: dcdd3c81-0f00-4259-a8a5-9062a4c40b6f
source-git-commit: a6f2cc11f57c5cd766cd31e941649fb5003ae30b
workflow-type: tm+mt
source-wordcount: '849'
ht-degree: 79%

---

# データセットの基本を学ぶ {#datasets-gs}

Adobe Experience Platform に取り込まれたすべてのデータは、データレイク内にデータセットとして保持されます。データセットは、スキーマ（列）とフィールド（行）を含んだデータコレクション（通常はテーブル）のストレージおよび管理用の構成体です。

## ガードレールと制限

* 2024年11月1日（PT）以降、ストリーミングセグメント化では、[!DNL Journey Optimizer] のトラッキングデータセットとフィードバックデータセットからの送信イベントと開封イベントがサポートされなくなります。フリークエンシーキャップや疲労管理を実装する場合は、代わりにビジネスルールを使用してください。詳しくは、[この節](../conflict-prioritization/rule-sets.md)を参照してください。毎日のキャップに関するユースケースの説明などについて詳しくは、[こちら](https://experienceleaguecommunities.adobe.com/t5/journey-optimizer-blogs/elevate-customer-experience-with-daily-frequency-capping-in-ajo/ba-p/761510){target="_blank"}を参照してください。

* 2025 年 2 月から、Time-to-Live （TTL）ガードレールが、Journey Optimizer システム生成データセットにロールアウトされています。 [詳細情報](datasets-ttl.md)

## データセットへのアクセス {#access}

ユーザーインターフェイスの **データセット** ワークスペース [!DNL Adobe Journey Optimizer] 使用すると、データの調査とデータセットの作成を行えます。 データセットダッシュボードを開くには、左側のナビゲーションで **データセット** を選択します。

![](assets/datasets-home.png)

「**参照**」タブを選択し、組織で使用可能なすべてのデータセットのリストを表示します。リストに表示された各データセットに関する詳細（名前、データセットが準拠するスキーマ、最新の取得実行のステータスなど）が表示されます。 デフォルトでは、取り込んだデータセットのみが表示されます。システム生成データセットを表示する場合は、フィルターの「**システムデータセットを表示**」切替スイッチをオンに切り替えます。

![](assets/ajo-system-datasets.png)


データセットの名前を選択して、そのデータセットのアクティビティ画面にアクセスし、選択したデータセットの詳細を確認します。「アクティビティ」タブには、消費されるメッセージの割合を視覚化したグラフと、成功および失敗したバッチのリストが含まれます。

データセットをプレビューするには、画面の右上隅付近の **データセットをプレビュー** を選択し、このデータセットで成功した最新のバッチをプレビューします。 データセットが空の場合、プレビューリンクは非アクティブになります。

![](assets/dataset-preview.png)

## [!DNL Journey Optimizer] システムデータセット {#system-datasets}

ここでは、[!DNL Journey Optimizer] で使用されるシステムデータセットの一覧を示します。 各スキーマのフィールドと属性の完全なリストを表示するには、[Journey Optimizer スキーマ辞書](https://experienceleague.adobe.com/tools/ajo-schemas/schema-dictionary.html?lang=ja){target="_blank"}を参照してください。

>[!CAUTION]
>
> システムデータセットは&#x200B;**変更できません**。製品が更新されるたびに、変更は自動的に元に戻されます。

* レポート

   * _レポート - メッセージフィードバックイベントデータセット_：メッセージ配信ログ。 レポートやオーディエンス作成を目的とした Journey Optimizer からのすべてのメッセージ配信に関する情報です。バウンスに関するメール ISP からのフィードバックも、このデータセットに記録されます。
   * _レポート - メールトラッキングエクスペリエンスイベントデータセット_：レポートやオーディエンス作成のために使用されるメールチャネルのインタラクションログ。エンドユーザーがメールで実行したアクション（開封やクリックなど）に関する情報が保存されます。
   * _レポート - プッシュトラッキングエクスペリエンスイベントデータセット_：レポートやオーディエンス作成のために使用されるプッシュチャネルのインタラクションログ。プッシュ通知時にエンドユーザーが実行したアクションに関する情報が保存されます。
   * _レポート - ジャーニーステップイベント_：Journey Optimizer から生成され、レポーティングなどのサービスで使用されるすべてのジャーニーステップエクスペリエンスイベントをキャプチャします。また、YoY 分析用に Customer Journey Analytics でレポートを作成する場合にも重要です。ジャーニーメタデータに関連付けます。
   * _レポート - ジャーニー_：ジャーニーの各ステップの情報を格納するメタデータのデータセット。
   * _レポート - BCC_：BCC メールの配信ログを保存するフィードバックイベントのデータセット。レポート目的で使用されます。

* 同意

  _同意サービスデータセット_：プロファイルの同意情報を保存します。

* インテリジェントサービス

  _送信時間の最適化スコア／エンゲージメントスコア_：ジャーニー AI の出力スコア。


## データセットの作成{#create-datasets}

[!DNL Adobe Experience Platform] にデータを追加することは、プロファイルを作成するための基盤となります。そうすれば、[!DNL Adobe Journey Optimizer] でプロファイルを活用できるようになります。まず、スキーマを定義し、ETL ツールを使用してデータを準備および標準化したあと、スキーマに基づいてデータセットを作成します。

スキーマまたは CSV ファイルからデータセットを作成できます。 データセットの作成方法について詳しくは、[!DNL Adobe Experience Platform] のドキュメントを参照してください。

* [&#x200B; 既存のスキーマを使用したデータセットの作成 &#x200B;](https://experienceleague.adobe.com/en/docs/experience-platform/catalog/datasets/user-guide#schema){target="_blank"}
* [&#x200B; 既存の XDM スキーマへの CSV ファイルのマッピング &#x200B;](https://experienceleague.adobe.com/en/docs/experience-platform/ingestion/tutorials/map-csv/existing-schema){target="_blank"}

データセットの作成、スキーマへのマッピング、データの追加、データの取り込み確認の方法についてこのビデオで説明しています。

>[!VIDEO](https://video.tv.adobe.com/v/334293?quality=12)

## データガバナンス

データセットで、「**データガバナンス**」タブを参照し、データセットレベルとフィールドレベルでラベルを確認します。データガバナンスは、適用されるポリシーのタイプに従ってデータを分類します。

[!DNL Adobe Experience Platform] の主な機能の 1 つは、複数の企業システムのデータを統合して、マーケターが顧客を識別かつ理解し、惹きつけられるようにすることです。このデータは、組織または法規制によって定義された使用制限の対象となる場合があります。したがって、データ操作が、データ使用ポリシーを確実に準拠できるようにすることが重要です。

 [!DNL Adobe Experience Platform Data Governance] を使用すると、顧客データを管理し、データの使用に適用される規制、制限、ポリシーへのコンプライアンスを確保できます。Experience Platform 内の様々なレベルで重要な役割を果たします（例えば、カタログ化、データ系列、データ使用ポリシー、マーケティングアクションのデータに関するアクセス制御など）。

データガバナンスとデータ使用ラベルについて詳しくは、[データガバナンスドキュメント](https://experienceleague.adobe.com/docs/experience-platform/data-governance/labels/user-guide.html?lang=ja){target="_blank"}を参照してください

## サンプルとユースケース {#samples}

* [&#x200B; チュートリアル - Adobe Experience Platformへのデータの取り込 &#x200B;](https://experienceleague.adobe.com/docs/experience-platform/ingestion/tutorials/ingest-batch-data.html?lang=ja){target="_blank"}
* [&#x200B; エンドツーエンドのユースケース &#x200B;](../audience/creating-test-profiles.md) - スキーマとデータセットを作成し、データを取り込んで [!DNL Adobe Journey Optimizer] にテストプロファイルを追加する
* [&#x200B; クエリの例 &#x200B;](../data/datasets-query-examples.md) - [!DNL Adobe Journey Optimizer] データセットと関連する使用例。

>[!MORELIKETHIS]
>
>* [&#x200B; データセットドキュメント &#x200B;](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/overview.html?lang=ja){target="_blank"}
>* [&#x200B; データ取り込みのドキュメント &#x200B;](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html?lang=ja){target="_blank"}。
>* [データ管理ライセンス使用権限のベストプラクティス](https://experienceleague.adobe.com/en/docs/experience-platform/landing/license/data-management-best-practices#data-management-best-practices){target="_blank"}
