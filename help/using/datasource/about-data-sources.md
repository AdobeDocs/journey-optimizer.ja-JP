---
title: データソースについて
description: データソースの設定方法を学ぶ
feature: Data Sources
topic: Administration
role: Admin
level: Intermediate
exl-id: e0cb261f-7cf7-42de-8e56-576492e3b5cc
source-git-commit: 7138e1f031bd26caf9379c3ff19d79ac29442bc6
workflow-type: tm+mt
source-wordcount: '288'
ht-degree: 100%

---

# データソースについて {#concept_s1s_dqt_52b}

>[!CONTEXTUALHELP]
>id="jo_datasources"
>title="データソースについて"
>abstract="データソースの設定は、常に技術ユーザーが実行します。データソースを設定すると、システムへの接続を定義して、ジャーニーで使用される（条件定義、アクションのパラメーターとパーソナライゼーションデータ、カスタム待機定義、タイムゾーン定義に対する）追加情報を取得できます。"

データソース設定を使用すると、システムへの接続を定義して、ジャーニーにおいて次の目的でジャーニーで使用される追加情報を取得できます。

* [条件の定義](../building-journeys/condition-activity.md)
* [アクション](../action/action.md)のパラメーターとパーソナライゼーションデータ
* [カスタムの待機の定義](../building-journeys/wait-activity.md#custom)
* [タイムゾーンの定義](../building-journeys/timezone-management.md)

ジャーニーがイベントペイロードからのローカルデータのみを活用する場合、この設定は必要ありません。例えば、ジャーニーがイベントと、そのイベントのデータのみを使用するメッセージアクティビティのみで構成される場合、データソースを設定する必要はありません。

データソースには次の 2 種類があります。

* リアルタイム顧客プロファイルサービスへの接続を定義する、事前設定済みの Adobe Experience Platform データソース。これは組み込みのデータソースです。[このページ](../datasource/adobe-experience-platform-data-source.md)を参照してください。
* 外部システムへの接続を定義できる外部データソース。これは作成可能なデータソースです。[このページ](../datasource/external-data-sources.md)を参照してください。

各データソースについて、フィールドグループを使用して取得する情報を定義します。フィールドグループは、データソースから取得できるフィールドのセットです。[このページ](../datasource/configure-data-sources.md#define-field-groups)を参照してください。

>[!NOTE]
>
>スキーマ間の関係がデータソースでサポートされるようになりました。

Adobe Experience Platform データソースと外部データソースの設定方法と、ジャーニーでデータを検索および使用する方法について詳しくは、この[チュートリアルビデオ](https://experienceleague.adobe.com/docs/journey-orchestration-learn/tutorials/configure-data-sources.html?lang=ja){target=&quot;_blank&quot;}をご覧ください。
