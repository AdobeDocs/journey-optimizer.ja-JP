---
title: 権限レベル
description: 高レベルおよび低レベル権限について学ぶ
topic: Administration
role: Admin
level: Intermediate
exl-id: 1b286f9d-43ef-4b80-b4ee-136da857bb95
source-git-commit: ad24f1ed5b3480385cb8cab471f638e289bf5094
workflow-type: tm+mt
source-wordcount: '1050'
ht-degree: 55%

---

# 権限レベル {#high-low-permissions}

![](../assets/do-not-localize/permissions.png)

各製品プロファイルは、ユーザーが様々な機能にアクセスできる権限で構成されています。
権限は次の 2 つのタイプに分けることができます。

* **高レベル権限**:は、割り当て可能な様々な権限を表します **[!UICONTROL 製品プロファイル]** 内 [!DNL Admin console]例： **[!DNL Publish journeys]** および **[!DNL Manage subdomains delegation]**. 高レベル権限は、低レベル権限を含みます。

* **低レベル権限**：高レベル権限から取得される様々な権限を表します。

例えば、 **[!DNL Journey administrator]** 製品プロファイルが割り当てられます **[!DNL Manage journeys]** 権限。 この権限により、ジャーニー管理者がジャーニーの書き込み、読み取りおよび削除ができる低レベル権限が生じます。

## ジャーニー機能 {#journey-capability}

### [!DNL Manage journeys] 権限 {#manage-journeys}

この **[!DNL Manage journeys]** 高レベルの権限を持つユーザーは、新しいジャーニーの作成、既存のアクションの編集/削除、およびジャーニーキャンバスでジャーニーフローの構築に使用されるオブジェクトへのアクセスが可能です。

これには、次の低レベル権限が含まれます。

* Journey Optimizer 固有：

   * journeys.read
   * journeys.write
   * journeys.delete
   * messages.read

* Adobe Experience Platform 固有：

   * segments.read
   * profiles.read
   * datasets.read
   * schemas.read

### [!DNL Publish journeys] 権限 {#publish-journeys}

この **[!DNL Publish journeys]** 高レベル権限を持つユーザーは、ジャーニーを公開できます。

これには、次の低レベル権限が含まれます。

* Journey Optimizer 固有：
   * journeys.publish
   * journeys.read

### [!DNL View journeys] 権限 {#view-journeys}

この **[!DNL View journeys]** 高レベル権限を持つユーザーは、ジャーニーを参照および表示できます。

これには、次の低レベル権限が含まれます。

* Journey Optimizer 固有：
   * journeys.read

* Adobe Experience Platform 固有：
   * segments.read
   * profiles.read

### [!DNL Manage journeys events, data sources and actions] 権限 {#manage-journeys-events}

この **[!DNL Manage journeys events, data sources and actions]** 高レベル権限を持つユーザーは、イベントとデータの設定をおこなうことができます。

これには、次の低レベル権限が含まれます。

* Journey Optimizer 固有：
   * journeys_events.read
   * journeys_events.write
   * journeys_events.delete
   * journeys_data_sources.read
   * journeys_data_sources.write
   * journeys_data_sources.delete
   * journeys_actions.read
   * journeys_actions.write
   * journeys_actions.delete

* Adobe Experience Platform 固有：
   * schemas.read
   * datasets.read
   * identity_namespace.read

### [!DNL View journeys events, data sources and actions] 権限 {#view-journeys-event}

この **[!DNL View journeys events, data sources and actions]** 高レベル権限を持つユーザーは、ジャーニーフローでイベントとデータを使用できます。

これには、次の低レベル権限が含まれます。

* Journey Optimizer 固有：
   * journeys_events.read
   * journeys_data_sources.read
   * journeys_actions.read

* Adobe Experience Platform 固有：
   * schemas.read
   * datasets.read
   * identity_namespace.read

### [!DNL View journeys report] 権限 {#view-journeys-report}

この **[!DNL View journeys report]** 高レベルの権限を持つユーザーは、読み取り専用のジャーニーレポートを使用できます。

これには、次の低レベル権限が含まれます。

* Journey Optimizer 固有：
   * journeys_report.read
   * messages_report.read

* Adobe Experience Platform 固有：
   * datasets.read
   * queries.read
   * queries.write
   * queries.delete

## メッセージ機能 {#message-capability}

### [!DNL Manage messages] 権限 {#manage-messages}

この **[!DNL Manage messages]** 高レベル権限を持つユーザーは、メッセージの作成と編集/削除ができます。

これには、次の低レベル権限が含まれます。

* Journey Optimizer 固有：
   * messages.write
   * messages.read
   * messages.delete
   * messages_presets.read

* Adobe Experience Platform 固有：
   * segments.read
   * schemas.read

### [!DNL Manage messages preview and test] 権限 {#mange-messages-preview}

この **[!DNL Manage messages preview and test]** 高レベル権限を持つユーザーは、パーソナライズされたメッセージをプレビューできます。

これには、次の低レベル権限が含まれます。

* Journey Optimizer 固有：
   * messages.publish
   * messages_preview_and_test.write
   * messages.publish

* Adobe Experience Platform 固有：
   * profiles.read
   * profiles.write
   * schemas.read
   * datasets.write
   * datasets.read
   * identity_namespace.read
   * segments.read
   * queries.write
   * merge_policies.read

### [!DNL Publish messages] 権限 {#publish-messages}

この **[!DNL Publish messages]** 高レベル権限を持つユーザーは、メッセージを公開できます。

これには、次の低レベル権限が含まれます。

* Journey Optimizer 固有：
   * messages.publish

* Adobe Experience Platform 固有：
   * profiles.read
   * schemas.read
   * datasets.read

### [!DNL View messages] 権限 {#view-messages}

この **[!DNL View messages]** 高レベル権限を持つユーザーは、メッセージの読み取りのみ可能です。

これには、次の低レベル権限が含まれます。

* Journey Optimizer 固有：
   * messages.read
   * messages_presets.read

* Adobe Experience Platform 固有：
   * schemas.read
   * segments.read

### [!DNL View messages report] 権限 {#view-message-reports}

この **[!DNL View messages report]** 高レベル権限を持つユーザーは、電子メールおよびプッシュレポートを読み取り専用で使用できます。

これには、次の低レベル権限が含まれます。

* Journey Optimizer 固有：
   * messages_report.read
   * datasets.read
   * queries.read
   * queries.write
   * queries.delete
   * journey.read

## 意思決定管理機能
 {#decisions-permissions}

### [!DNL Manage decisions] 権限 {#manage-decisioning}

この **[!DNL Manage decisions]** 高レベルの権限を持つユーザーは、新規作成や既存の編集/削除が可能です **[!DNL Activity entities]**&#x200B;を管理し、判定をおこなうためにこれらのアクティビティで使用されるオブジェクトを管理します。

これには、次の低レベル権限が含まれます。

* 意思決定管理固有：

   * activities.read
   * activities.write
   * activities.delete
   * offers.read
   * offers.write
   * offers.delete
   * placements.read
   * placements.write
   * placements.delete
   * ranking_strategy.read

* Adobe Experience Platform 固有：
   * datasets.read
   * datasets.write
   * datasets.delete
   * schemas.read
   * profile.read
   * segments.read

### [!DNL View decisions] 権限 {#view-decisions}

この **[!DNL View decisions]** 高レベル権限を持つユーザーは、既存のアクティビティと関連するビジネスオブジェクトを使用して意思決定をおこなうことができます。

これには、次の低レベル権限が含まれます。

* 意思決定管理固有：

   * activities.read
   * offers.read
   * placements.read
   * ranking_strategy.read

* Adobe Experience Platform 固有：
   * schemas.read
   * segment.read
   * datasets.read
   * datasets.write
   * datasets.delete

### [!DNL Publish offers decisioning] 権限 {#publish-decisions}

この **[!DNL Publish offers decisioning]** 高レベル権限を持つユーザーは、オファーアクティビティの承認/承認取消にアクセスできます。

これには、次の低レベル権限が含まれます。

* 意思決定管理固有：

   * offers_activity.read
   * offers.read
   * offers.write
   * offers.delete
   * placements.read
   * placements.write
   * placements.delete
   * ranking_strategy.read

* Adobe Experience Platform 固有：
   * schemas.read
   * segment.read
   * datasets.read
   * profiles.read

### [!DNL Manage ranking strategies] 権限 {#manage-decisions}

この **[!DNL Manage ranking strategies]** 高レベル権限を持つユーザーは、カスタムメッセージレポートの読み取り、作成、編集、削除を行い、アクション機能を使用できます。

これには、次の低レベル権限が含まれます。

* 意思決定管理固有：

   * ranking_strategy.read
   * ranking_strategy.write
   * ranking_strategy.delete
   * activities.read
   * offers.read
   * placements.read

## 管理機能 {#administration-permissions}

### [!DNL Manage subdomains delegation] 権限 {#manage-subdomain}

この **[!DNL Manage subdomains delegation]** 高レベル権限を持つユーザーは、サブドメインの委任（IP プールを含む）を作成、編集および削除できます。

これには、次の低レベル権限が含まれます。

* subdomains_delegation.read
* subdomains_delegation.write
* subdomains_delegation.delete

### [!DNL Manage PTR records] 権限 {#manage-ptr}

この **[!DNL Manage PTR records]** 高レベル権限を持つユーザーは、サブドメインに基づいて設定された PTR レコードの読み取りと編集が可能です。

これには、次の低レベル権限が含まれます。

* PTR_records.read
* PTR_records.write
* subdomains_delegation.read

### [!DNL View PTR records] 権限 {#view-ptr}

この **[!DNL View PTR records]** 高レベル権限を持つユーザーは、サブドメインに基づいて設定された PTR レコードを表示できます。

これには、次の低レベル権限が含まれます。

* PTR_records.read
* subdomains_delegation.read

### [!DNL Manage IP pools] 権限 {#manage-ip-pools}

この **[!DNL Manage IP pools]** 高レベル権限を持つユーザーは、アフィニティ定義を作成、編集および削除できます。

これには、次の低レベル権限が含まれます。

* IP_pools.read
* IP_pools.write
* IP_pools.delete

### [!DNL Manage messages general settings] 権限 {#manage-message-settings}

この **[!DNL Manage messages general settings]** 高レベル権限を持つユーザーは、サンドボックスレベルでグローバル設定を作成、編集および削除できます。

これには、次の低レベル権限が含まれます。

* Journey Optimizer 固有：
   * messages_general_settings.read
   * messages_general_settings.write
   * messages_general_settings.delete
* Adobe Experience Platform 固有：
   * schemas.read

### [!DNL View messages general settings] 権限 {#view-message-settings}

この **[!DNL View messages general settings]** 高レベル権限を持つユーザーは、実行アドレスなどのメッセージの一般設定を表示できます。

これには、次の低レベル権限が含まれます。

* Journey Optimizer 固有：
   * messages_general_settings.read
* Adobe Experience Platform 固有：
   * schemas.read

### [!DNL Manage messages presets] 権限 {#manage-message-presets}

この **[!DNL Manage messages presets]** 高レベル権限を持つユーザーは、サンドボックスレベルでチャネルをまたいでメッセージプリセットを作成、編集および削除できます。

これには、次の低レベル権限が含まれます。

* Journey Optimizer 固有：
   * messages_presets.read
   * messages_presets.write
   * messages_presets.delete
   * subdomains_delegation.read
   * IP_pools.read
   * mobile_setting.read（Adobe Experience Platform Launch から）

### [!DNL View messages presets] 権限 {#view-message-presets}

この **[!DNL View messages presets]** 高レベル権限を持つユーザーは、メッセージの作成時に使用するメッセージプリセットを知るために、メッセージプリセットを表示できます。

これには、次の低レベル権限が含まれます。

* messages_presets.read
* subdomains_delegation.read
* IP_pools.read
* mobile_setting.read(Adobe Experience Platform Data Collection から )

### [!DNL Manage suppression] 権限 {#manage-suppression}

この **[!DNL Manage suppression]** 高レベル権限を使用すると、ユーザーは、電子メールアドレスが抑制リストに追加される前にバウンス数を定義したり、抑制リストに対するエントリの追加や削除をおこなうことができます。

これには、次の低レベル権限が含まれます。

* suppression_rules.read
* suppression_rules.write
* suppression_rules.delete
* suppression_list.write
* suppression_list.delete

### [!DNL View suppression list] 権限 {#view-suppression-list}

この **[!DNL View suppression list]** 高レベル権限を持つユーザーは、抑制リストのコンテンツと設定を表示できます。

これには、次の低レベル権限が含まれます。

* Journey Optimizer 固有：
   * suppression_list.view

* Adobe Experience Platform 固有：
   * profiles.read
   * datasets.read

### [!DNL Export suppression list] 権限 {#export-suppression-list}

この **[!DNL Export suppression list]** 高レベル権限を持つユーザーは、抑制リストを CSV ファイルとしてダウンロードできます。

これには、次の低レベル権限が含まれます。

* Journey Optimizer 固有：
   * suppression_list.export

* Adobe Experience Platform 固有：
   * profiles.read
   * datasets.read
