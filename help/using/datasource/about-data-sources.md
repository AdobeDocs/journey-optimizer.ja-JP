---
solution: Journey Optimizer
product: journey optimizer
title: データソースについて
description: データソースの設定方法について説明します。
feature: Data Sources
topic: Administration
role: Admin
level: Intermediate
exl-id: e0cb261f-7cf7-42de-8e56-576492e3b5cc
source-git-commit: 0b19af568b33d29f4b35deeab6def17919cfe824
workflow-type: tm+mt
source-wordcount: '309'
ht-degree: 0%

---

# データソースについて {#about-data-sources}

>[!CONTEXTUALHELP]
>id="ajo_journey_data_source_list"
>title="データソースについて"
>abstract="データソースの設定は、テクニカルユーザーによって常に実行されます。 データソースの構成では、システムへの接続を定義して、journeys で使用されるその他の情報を取得することができます。このためには、操作、カスタム待ちの定義、タイムゾーン定義などの、条件定義、パラメーター、パーソナル化データが含まれます。"

データソース設定を使用すると、journeys で使用されるその他の情報を取得するための、システムへの接続を定義することができます。

* [条件の定義](../building-journeys/condition-activity.md)
* アクション内の [ パラメーターとパーソナル化データ](../action/action.md)
* [カスタム待機の定義](../building-journeys/wait-activity.md#custom)
* [タイムゾーン定義](../building-journeys/timezone-management.md)

➡️ [ ビデオでのこの機能の検出](#video)

Journeys がイベントペイロードから送られるローカルデータのみを利用する場合は、この設定は必要ありません。 例えば、イベントの後にイベントのデータのみを使用するチャンネルアクションアクティビティーがある場合は、データソースを設定する必要はありません。

データソースには、次の2種類があります。

* 事前に設定されている Adobe エクスペリエンスプラットフォームデータソースには、リアルタイムカスタマープロファイルサービスへの接続が定義されています。 これは、データソースとして組み込まれています。 このページ ](../datasource/adobe-experience-platform-data-source.md) を参照してください [ 。
* 外部システムへの接続を定義するために使用できる外部データソース。 このようなテンプレートを作成することができます。 このページ ](../datasource/external-data-sources.md) を参照してください [ 。

データソースごとに、フィールドグループを使用して取得する情報を定義します。 フィールドグループには、データソースから取得できるフィールドのセットがあります。 このページ ](../datasource/configure-data-sources.md#define-field-groups) を参照してください [ 。

>[!NOTE]
>
>データソースでは、スキーマリレーションシップはサポートされていません。

Adobe エクスペリエンス Platform のデータソースと外部データソースの設定方法、およびデータの検索と使用方法について詳しくは、 [ ](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/journey-configuration/configure-data-sources.html) 「target = &quot;_blank&quot;}」を参照してください。

## 操作方法のビデオ {#video}

データソースの概要と、エクスペリエンスプラットフォームと外部データソースを設定する方法について説明します。

>[!VIDEO](https://video.tv.adobe.com/v/334256?quality=12)

