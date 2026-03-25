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
source-git-commit: a422cad5349de0ad87aa3a11ce923e04e862a63c
workflow-type: tm+mt
source-wordcount: '645'
ht-degree: 54%

---

# データソースの基本を学ぶ {#about-data-sources}

>[!CONTEXTUALHELP]
>id="ajo_journey_data_source_list"
>title="データソースについて"
>abstract="データソースの設定は、常に技術ユーザーが実行します。データソースを設定すると、システムへの接続を定義して、ジャーニーで使用される（条件定義、アクションのパラメーターとパーソナライゼーションデータ、カスタム待機定義、タイムゾーン定義に対する）追加情報を取得できます。"

>[!TIP]
>Journey Optimizerを初めて利用する場合？ データ ソースを設定する前に、スキーマ、データセット、ID、データ フローを理解するには、[&#x200B; データ管理の概要](../data/gs-data.md)から始めます。

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

## データアクセス戦略の選択 {#data-access-strategy}

データソースを設定する前に、自社のユースケースに最も適したアプローチを検討してください。 3つのオプションが利用可能で、それぞれ永続性、プロファイルの充実、再利用性の観点から異なるトレードオフがあります。 これらのオプションについて詳しくは、[Journey Optimizerの高度なジャーニーのベストプラクティス &#x200B;](https://experienceleague.adobe.com/en/perspectives/best-practices-for-advanced-journeys-in-journey-optimizer){target="_blank"}を参照してください。

**オプション 1 — カスタムアクションを使用した外部データへのアクセス（データレイクなし）**

Experience Platform Data Lakeにデータを保持することなく、ジャーニーランタイムで外部APIに直接接続できます。 次の場合に最適：

* データは、ジャーニーのコンテキスト内でのみ有用であり、他の場所では必要ありません。
* 外部システムには、必要な属性を返すAPI エンドポイントを通じてアクセスできます。

[&#x200B; カスタムアクション &#x200B;](../action/action.md)と[&#x200B; カスタムアクション応答](../action/action-response.md)の詳細を説明します。

**オプション 2 — データレイク内のデータセット。プロファイル**&#x200B;に対して有効になっていません

データセットにデータを取り込み、リアルタイムの顧客プロファイルに貢献することなく、コンテキストに即したイベントデータにもとづいてジャーニーをトリガーし、パーソナライズできます。 次の場合に最適：

* レコードには、Experience Platformに既に保存されているプロファイルにアクセスできるID フィールドが含まれています。
* Journey Optimizerの外部でオーディエンスを作成したりIDをつなぎ合わせたりする場合、データは必要ありません。

**オプション 3 — データレイクのプロファイル対応データセット**

データを[&#x200B; プロファイル対応データセット &#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/catalog/datasets/user-guide#enable-profile){target="_blank"}に取り込み、オーディエンスを作成し、ID グラフを充実させ、複数のジャーニーおよびRT-CDPの宛先をまたいでデータを活用します。 次の場合に最適：

* このデータは、Journey Optimizer以外のチャネルで使用されるオーディエンス定義に役立ちます。
* データには、より豊富でステッチされたプロファイルフラグメントに貢献する複数のIDが含まれています。

| | データはデータレイクに保持されます | プロファイルに対するデータセットの有効化 |
| --- | --- | --- |
| **オプション 1** — カスタムアクションによる外部データ | × | × |
| **オプション 2** — プロファイルでデータセットが有効になっていません | ○ | × |
| **オプション 3** — プロファイル対応データセット | ○ | ○ |

Adobe Experience Platform データソースと外部データソースの設定方法、およびデータを特定してジャーニーで使用する方法について詳しくは、この[チュートリアルビデオ](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/journey-configuration/configure-data-sources.html?lang=ja){target="_blank"}を参照してください。

## チュートリアルビデオ {#video}

データソースとは何かを理解し、Experience Platform と外部データソースを設定する方法を説明します。

>[!VIDEO](https://video.tv.adobe.com/v/334256?quality=12)

