---
solution: Journey Optimizer
product: journey optimizer
title: データソースの基本を学ぶ
description: データソースの開始方法について学ぶ
feature: Journeys, Data Sources
topic: Administration
role: Developer, Admin
level: Intermediate, Experienced
keywords: データ, ソース, ジャーニー, プラットフォーム
exl-id: e0cb261f-7cf7-42de-8e56-576492e3b5cc
source-git-commit: 302db58525a7b2648bb9c44bc9b42da787ca9c43
workflow-type: tm+mt
source-wordcount: '615'
ht-degree: 56%

---

# データソースの基本を学ぶ {#about-data-sources}

>[!CONTEXTUALHELP]
>id="ajo_journey_data_source_list"
>title="データソースについて"
>abstract="データソースの設定は、常に技術ユーザーが実行します。データソースを設定すると、システムへの接続を定義して、ジャーニーで使用される（条件定義、アクションのパラメーターとパーソナライゼーションデータ、カスタム待機定義、タイムゾーン定義に対する）追加情報を取得できます。"

データソース設定を使用すると、システムへの接続を定義して、ジャーニーにおいて次の目的でジャーニーで使用される追加情報を取得できます。

* [条件の定義](../building-journeys/condition-activity.md)
* [アクション](../action/action.md)のパラメーターとパーソナライゼーションデータ
* [カスタムの待機の定義](../building-journeys/wait-activity.md#custom)
* [タイムゾーンの定義](../building-journeys/timezone-management.md)

➡️ [この機能をビデオで確認](#video)

ジャーニーがイベントペイロードからのローカルデータのみを活用する場合、この設定は必要ありません。例えば、ジャーニーがイベントと、そのイベントのデータのみを使用する後続のチャネルアクションアクティビティで構成される場合、データソースを設定する必要はありません。

データソースには次の 2 種類があります。

* リアルタイム顧客プロファイルサービスへの接続を定義する、**事前設定済み**&#x200B;の Adobe Experience Platform データソース。これはビルトインのデータソースです。[このページ](../datasource/adobe-experience-platform-data-source.md)を参照してください。
* 外部システムへの接続を定義できる&#x200B;**外部**&#x200B;データソース。これは作成可能なデータソースです。[このページ](../datasource/external-data-sources.md)を参照してください。

>[!NOTE]
>
>応答がサポートされるようになったので、外部データソースのユースケースでは、データソースの代わりにカスタムアクションを使用する必要があります。応答について詳しくは、この[節](../action/action-response.md)を参照してください。

各データソースについて、フィールドグループを使用して取得する情報を定義します。フィールドグループは、データソースから取得できるフィールドのセットです。[このページ](../datasource/configure-data-sources.md#define-field-groups)を参照してください。

>[!NOTE]
>
>スキーマの関係は、データ ソースではサポートされていません。

## データアクセス戦略を選択 {#data-access-strategy}

データソースを設定する前に、ユースケースに最適なアプローチを検討してください。 永続性、プロファイルのエンリッチメントおよび再利用性に関して、それぞれ異なるトレードオフを持つ 3 つのオプションを使用できます。 これらのオプションについて詳しくは、[Journey Optimizerの高度なジャーニーのベストプラクティス &#x200B;](https://experienceleague.adobe.com/ja/perspectives/best-practices-for-advanced-journeys-in-journey-optimizer){target="_blank"} を参照してください。

**オプション 1 - カスタムアクションを使用して外部データにアクセス（データレイクなし）**

Experience Platform Data Lake にデータを保持することなく、ジャーニー実行時に外部 API に直接接続します。 次の場合に最適です。

* データは、ジャーニーコンテキスト内でのみ役立ち、他の場所では必要ありません。
* 外部システムには、必要な属性を返す API エンドポイントを通じてアクセスできます。

詳しくは、[&#x200B; カスタムアクション &#x200B;](../action/action.md) および [&#x200B; カスタムアクション応答 &#x200B;](../action/action-response.md) を参照してください。

**オプション 2 - データレイクのデータセットで、プロファイルに対して有効になっていない**

リアルタイム顧客プロファイルに貢献することなく、データセットにデータを取り込み、コンテキストイベントデータに基づいてジャーニーをトリガーおよびパーソナライズします。 次の場合に最適です。

* レコードには、Experience Platformに既に保存されているプロファイルにアクセスするために使用可能な ID フィールドが含まれています。
* Journey Optimizer外でのオーディエンスの作成や ID のステッチには、データは必要ありません。

**オプション 3 - データレイクのプロファイルが有効なデータセット**

プロファイル対応データセットにデータを取り込むことで、オーディエンスの作成、ID グラフのエンリッチメント、複数のジャーニーや RT-CDP 宛先にわたるデータの活用を行います。 次の場合に最適です。

* このデータは、Journey Optimizer以外のチャネルで使用されるオーディエンス定義に役立ちます。
* データには、ステッチされた豊富なプロファイルフラグメントに貢献する複数の ID が含まれています。

| | データレイクに保持されるデータ | プロファイルに対して有効なデータセット |
| --- | --- | --- |
| **オプション 1** - カスタムアクションを使用した外部データ | × | × |
| **オプション 2** - プロファイルに対してデータセットが有効になっていない | ○ | × |
| **オプション 3** - プロファイルが有効なデータセット | ○ | ○ |

Adobe Experience Platform データソースと外部データソースの設定方法、およびデータを特定してジャーニーで使用する方法について詳しくは、この[チュートリアルビデオ](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/journey-configuration/configure-data-sources.html?lang=ja){target="_blank"}を参照してください。

## チュートリアルビデオ {#video}

データソースとは何かを理解し、Experience Platform と外部データソースを設定する方法を説明します。

>[!VIDEO](https://video.tv.adobe.com/v/3416779?captions=jpn&quality=12)

