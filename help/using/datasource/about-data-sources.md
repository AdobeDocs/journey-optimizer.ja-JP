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
TQID: https://experienceleague.adobe.com/eG1QcfpHtxpabUt5e7RZiMIpSAJD6Z6bjO-4wtZEUOg
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2:
  - id: bb359667-ec7d-4d4b-8663-5850fc219d32
  - id: d556b755-390a-43f0-be32-a08cf6236126
  - id: d998adac-2f81-400b-a669-d07bb196e4eb
subfeature_v2:
  - id: dd51b532-b93f-4bcf-8dbf-0d007f593aca
  - id: e30b0a1a-b594-47b8-af94-1e3a2be6df11
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2:
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: e366af78935405cd5acb15269194875098b20914
workflow-type: tm+mt
source-wordcount: 948
ht-degree: 42%

---

# データソースの基本を学ぶ {#about-data-sources}

>[!BEGINSHADEBOX]

**このページ：** データソースの概要と、適切なデータアクセス戦略の選択方法を理解して、条件、パーソナライゼーション、タイミングに関する追加のデータをジャーニーに取り込む方法を説明します。

>[!ENDSHADEBOX]

>[!CONTEXTUALHELP]
>id="ajo_journey_data_source_list"
>title="データソースについて"
>abstract="データソースの設定は、常に技術ユーザーが実行します。 データソースを設定すると、システムへの接続を定義して、ジャーニーで使用される（条件定義、アクションのパラメーターとパーソナライゼーションデータ、カスタム待機定義、タイムゾーン定義に対する）追加情報を取得できます。"

>[!TIP]
>Journey Optimizer のデータ管理を初めて使用しますか？ データ ソースを設定する前に、スキーマ、データセット、ID、データ フローを理解するには、[&#x200B; データ管理の概要](../data/gs-data.md)から始めます。

データソース設定を使用すると、システムへの接続を定義して、ジャーニーにおいて次の目的でジャーニーで使用される追加情報を取得できます。

* [条件の定義](../building-journeys/conditions.md)
* [アクション](../action/action.md)のパラメーターとパーソナライゼーションデータ
* [カスタムの待機の定義](../building-journeys/wait-activity.md#custom)
* [タイムゾーンの定義](../building-journeys/timezone-management.md)

➡️ [この機能をビデオで確認](#video)

ジャーニーがイベントペイロードからのローカルデータのみを活用する場合、この設定は必要ありません。 例えば、ジャーニーがイベントと、そのイベントのデータのみを使用する後続のチャネルアクションアクティビティで構成される場合、データソースを設定する必要はありません。

データソースには次の 2 種類があります。

* リアルタイム顧客プロファイルサービスへの接続を定義する、**事前設定済み**&#x200B;の Adobe Experience Platform データソース。 これはビルトインのデータソースです。 [このページ](../datasource/adobe-experience-platform-data-source.md)を参照してください。
* 外部システムへの接続を定義できる&#x200B;**外部**&#x200B;データソース。 これは作成可能なデータソースです。 [このページ](../datasource/external-data-sources.md)を参照してください。

>[!NOTE]
>
>応答がサポートされるようになったので、外部データソースのユースケースでは、データソースの代わりにカスタムアクションを使用する必要があります。 応答について詳しくは、この[節](../action/action-response.md)を参照してください。

各データソースについて、フィールドグループを使用して取得する情報を定義します。 フィールドグループは、データソースから取得できるフィールドのセットです。 [このページ](../datasource/configure-data-sources.md#define-field-groups)を参照してください。

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

>[!TIP]
>
>このオプションは、両方の質問に&#x200B;**yes**&#x200B;と答える場合に適しています。
>* データはジャーニーのコンテキスト内でのみ有用で、他の場所では必要ないか？ オーディエンスやその他のチャネルにもデータが必要な場合は、オプション 2または3を検討してください。
>* 必要な属性を返すAPI エンドポイントを介して外部システムにアクセスできますか？ そうでない場合は、まずデータをデータレイクに取り込む必要があります。

**オプション 2 — データレイク内のデータセット。プロファイル**&#x200B;に対して有効になっていません

データセットにデータを取り込み、リアルタイムの顧客プロファイルに貢献することなく、コンテキストに即したイベントデータにもとづいてジャーニーをトリガーし、パーソナライズできます。 次の場合に最適：

* レコードには、Experience Platformに既に保存されているプロファイルにアクセスできるID フィールドが含まれています。
* Journey Optimizerの外部でオーディエンスを作成したりIDをつなぎ合わせたりする場合、データは必要ありません。

>[!TIP]
>
>このオプションは、両方の質問に&#x200B;**yes**&#x200B;と答える場合に適しています。
>* レコードには、Experience Platformに既に保存されているプロファイルにアクセスするために使用できるID フィールドが含まれていますか？ そうでない場合、ジャーニーはプロファイルにアクセスして配信することはできません。
>* Journey Optimizer以外で[audience](../audience/about-audiences.md)の作成またはID合成を行う場合、データは不要ですか？ その場合は、代わりにオプション 3を使用してください。

**オプション 3 — データレイクのプロファイル対応データセット**

データを[&#x200B; プロファイル対応データセット &#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/catalog/datasets/user-guide#enable-profile){target="_blank"}に取り込み、オーディエンスを作成し、ID グラフを充実させ、複数のジャーニーおよびRT-CDPの宛先をまたいでデータを活用します。 次の場合に最適：

* このデータは、Journey Optimizer以外のチャネルで使用されるオーディエンス定義に役立ちます。
* データには、より豊富でステッチされたプロファイルフラグメントに貢献する複数のIDが含まれています。

>[!CAUTION]
>
>**プロファイル**&#x200B;のデータセットを有効にする前に、次の領域を評価します。
>* **データ同期** – 取り込みエラーを識別するためのアラートを配置して、外部データベースを同期する必要があります。
>* **[プロファイルガードレール &#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/profile/guardrails){target="_blank"}** — Experience Platformの[一般的なデータ取り込みガードレール &#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/ingestion/guardrails){target="_blank"}に加えて、プロファイル固有のガードレールが適用されます。
>* **IDの整合性** — ソースシステム内のID データは、健全なID グラフを維持するために慎重に計画する必要があります。
>* **データレイクの使用率** – 取り込み前に、全体的なストレージ消費、テーブル関係、およびアドレス可能なプロファイルを評価する必要があります。

| | データはデータレイクに保持されます | プロファイルに対するデータセットの有効化 |
| --- | --- | --- |
| **オプション 1** — カスタムアクションによる外部データ | × | × |
| **オプション 2** — プロファイルでデータセットが有効になっていません | ○ | × |
| **オプション 3** — プロファイル対応データセット | ○ | ○ |

Adobe Experience Platform データソースと外部データソースの設定方法、およびデータを特定してジャーニーで使用する方法について詳しくは、この[チュートリアルビデオ](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/journey-configuration/configure-data-sources.html?lang=ja){target="_blank"}を参照してください。

## チュートリアルビデオ {#video}

データソースとは何かを理解し、Experience Platform と外部データソースを設定する方法を説明します。

>[!VIDEO](https://video.tv.adobe.com/v/334256?quality=12)

