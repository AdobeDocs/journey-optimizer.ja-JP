---
title: データソースについて
description: データソースの設定方法を学ぶ
feature: Data Sources
topic: Administration
role: Admin
level: Intermediate
exl-id: e0cb261f-7cf7-42de-8e56-576492e3b5cc
source-git-commit: 1fa91a841d4f941f2c5bd1efd4a06ac8a9938bc7
workflow-type: ht
source-wordcount: '313'
ht-degree: 100%

---

# データソースについて {#about-data-sources}

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

ジャーニーがイベントペイロードからのローカルデータのみを活用する場合、この設定は必要ありません。例えば、ジャーニーがイベントと、そのイベントのデータのみを使用するメッセージアクティビティのみで構成される場合、データソースを設定する必要はありません。

データソースには次の 2 種類があります。

* リアルタイム顧客プロファイルサービスへの接続を定義する、事前設定済みの Adobe Experience Platform データソース。これはビルトインのデータソースです。[このページ](../datasource/adobe-experience-platform-data-source.md)を参照してください。
* 外部システムへの接続を定義できる外部データソース。これは作成可能なデータソースです。[このページ](../datasource/external-data-sources.md)を参照してください。

各データソースについて、フィールドグループを使用して取得する情報を定義します。フィールドグループは、データソースから取得できるフィールドのセットです。[このページ](../datasource/configure-data-sources.md#define-field-groups)を参照してください。

>[!NOTE]
>
>スキーマ間の関係がデータソースでサポートされるようになりました。

Adobe Experience Platform データソースと外部データソースの設定方法と、ジャーニーでデータを検索および使用する方法について詳しくは、この[チュートリアルビデオ](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/journey-configuration/configure-data-sources.html?lang=ja){target=&quot;_blank&quot;}をご覧ください。

## ハウツービデオ {#video}

データソースとは何かを理解し、Experience Platform と外部データソースを設定する方法を説明します。

>[!VIDEO](https://video.tv.adobe.com/v/334256?quality=12)

