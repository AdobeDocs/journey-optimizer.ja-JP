---
title: 権限レベル
description: 高レベルおよび低レベル権限について学ぶ
topic: Administration
role: Admin
level: Intermediate
exl-id: 1b286f9d-43ef-4b80-b4ee-136da857bb95
source-git-commit: b1c4fb836d34cc6263f804c7a0f700571281b31a
workflow-type: tm+mt
source-wordcount: '1082'
ht-degree: 97%

---

# 権限レベル {#high-low-permissions}

![](../assets/do-not-localize/permissions.png)

各製品プロファイルは、ユーザーが様々な機能にアクセスできる権限で構成されています。
権限は次の 2 つのタイプに分けることができます。

* **高レベルの権限**：**[!DNL Publish journeys]** や **[!DNL Manage subdomains delegation]** など、[!DNL Admin console] で&#x200B;**[!UICONTROL 製品プロファイル]**&#x200B;に割り当てることができる様々な権限を表します。高レベル権限は、低レベル権限を含みます。

* **低レベル権限**：高レベル権限から取得される様々な権限を表します。

例えば、**[!DNL Journey administrator]** 製品プロファイルには、**[!DNL Manage journeys]** 権限が割り当てられます。この権限により、ジャーニー管理者に対してジャーニーの書き込み、読み取りおよび削除を許可する低レベルの権限が生じます。

## ジャーニー機能 {#journey-capability}

### [!DNL Manage journeys] 権限 {#manage-journeys}

「**[!DNL Manage journeys]**」という高レベルの権限を持つユーザーは、新しいジャーニーの作成や、既存のジャーニーの編集／削除を行い、ジャーニーキャンバスでジャーニーフローの構築に使用されるオブジェクトへアクセスできます。

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

「**[!DNL Publish journeys]**」という高レベルの権限を持つユーザーは、ジャーニーを公開できます。

これには、次の低レベル権限が含まれます。

* Journey Optimizer 固有：
   * journeys.publish
   * journeys.read

### [!DNL View journeys] 権限 {#view-journeys}

「**[!DNL View journeys]**」という高レベルの権限を持つユーザーは、ジャーニーを参照および表示できます。

これには、次の低レベル権限が含まれます。

* Journey Optimizer 固有：
   * journeys.read

* Adobe Experience Platform 固有：
   * segments.read
   * profiles.read

### [!DNL Manage journeys events, data sources and actions] 権限 {#manage-journeys-events}

「**[!DNL Manage journeys events, data sources and actions]**」という高レベルの権限を持つユーザーは、イベントとデータの設定を行うことができます。

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

「**[!DNL View journeys events, data sources and actions]**」という高レベルの権限を持つユーザーは、ジャーニーフローでイベントとデータを使用できます。

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

**[!DNL View journeys report]** 高レベルの権限を持つユーザーは、ジャーニーレポートに対する読み取り専用のアクセス権を持ちます。

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

「**[!DNL Manage messages]**」という高レベルの権限を持つユーザーは、メッセージを作成および編集／削除できます。

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

「**[!DNL Manage messages preview and test]**」という高レベルの権限を持つユーザーは、パーソナライズされたメッセージをプレビューできます。

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

「**[!DNL Publish messages]**」という高レベルの権限を持つユーザーは、メッセージを公開できます。

これには、次の低レベル権限が含まれます。

* Journey Optimizer 固有：
   * messages.publish

* Adobe Experience Platform 固有：
   * profiles.read
   * schemas.read
   * datasets.read

### [!DNL View messages] 権限 {#view-messages}

「**[!DNL View messages]**」という高レベルの権限を持つユーザーは、メッセージに対する読み取り専用のアクセス権を持ちます。

これには、次の低レベル権限が含まれます。

* Journey Optimizer 固有：
   * messages.read
   * messages_presets.read

* Adobe Experience Platform 固有：
   * schemas.read
   * segments.read

### [!DNL View messages report] 権限 {#view-message-reports}

「**[!DNL View messages report]**」という高レベルの権限を持つユーザーは、メールおよびプッシュレポートに対する読み取り専用のアクセス権を持ちます。

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

「**[!DNL Manage decisions]**」という高レベルの権限を持つユーザーは、既存の **[!DNL Activity entities]** の編集／削除、新規作成を行なえるほか、これらのアクティビティで使用されるオブジェクトを管理し、決定することができます。

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

「**[!DNL View decisions]**」という高レベルの権限を持つユーザーは、既存のアクティビティと関連するビジネスオブジェクトを使用して意思決定を行うことができます。

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

「**[!DNL Publish offers decisioning]**」という高レベルの権限を持つユーザーは、オファーアクティビティを承認／未承認するアクセス権を持ちます。

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

「**[!DNL Manage ranking strategies]**」という高レベルの権限を持つユーザーは、カスタムメッセージレポートの読み取り、作成、編集および削除を行い、アクション機能を使用できます。

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

「**[!DNL Manage subdomains delegation]**」という高レベルの権限を持つユーザーは、サブドメインのデリゲーション（IP プールを含む）の作成、編集および削除を行うことができます。

これには、次の低レベル権限が含まれます。

* subdomains_delegation.read
* subdomains_delegation.write
* subdomains_delegation.delete

### [!DNL Manage PTR records] 権限 {#manage-ptr}

「**[!DNL Manage PTR records]**」という高レベルの権限を持つユーザーは、サブドメインに基づいて設定された PTR レコードの読み取りと編集を行うことができます。

これには、次の低レベル権限が含まれます。

* PTR_records.read
* PTR_records.write
* subdomains_delegation.read

### [!DNL View PTR records] 権限 {#view-ptr}

「**[!DNL View PTR records]**」という高レベルの権限を持つユーザーは、サブドメインに基づいて設定された PTR レコードを表示できます。

これには、次の低レベル権限が含まれます。

* PTR_records.read
* subdomains_delegation.read

### [!DNL Manage IP pools] 権限 {#manage-ip-pools}

「**[!DNL Manage IP pools]**」という高レベルの権限を持つユーザーは、アフィニティ定義の作成、編集および削除を行うことができます。

これには、次の低レベル権限が含まれます。

* IP_pools.read
* IP_pools.write
* IP_pools.delete

### [!DNL Manage messages general settings] 権限 {#manage-message-settings}

**[!DNL Manage messages general settings]** 高レベルの権限を持つユーザーは、サンドボックスレベルでグローバル設定の作成、編集および削除を行うことができます。

これには、次の低レベル権限が含まれます。

* Journey Optimizer 固有：
   * messages_general_settings.read
   * messages_general_settings.write
   * messages_general_settings.delete
* Adobe Experience Platform 固有：
   * schemas.read

### [!DNL View messages general settings] 権限 {#view-message-settings}

「**[!DNL View messages general settings]**」という高レベルの権限を持つユーザーは、メッセージの一般設定（実行アドレスなど）を表示できます。

これには、次の低レベル権限が含まれます。

* Journey Optimizer 固有：
   * messages_general_settings.read
* Adobe Experience Platform 固有：
   * schemas.read

### [!DNL Manage messages presets] 権限 {#manage-message-presets}

「**[!DNL Manage messages presets]**」という高レベルの権限を持つユーザーは、チャネルをまたぐメッセージプリセットの作成、編集および削除をサンドボックスレベルで行うことができます。

これには、次の低レベル権限が含まれます。

* Journey Optimizer 固有：
   * messages_presets.read
   * messages_presets.write
   * messages_presets.delete
   * subdomains_delegation.read
   * IP_pools.read
   * mobile_setting.read（Adobe Experience Platform Launch から）

### [!DNL View messages presets] 権限 {#view-message-presets}

「**[!DNL View messages presets]**」という高レベルの権限を持つユーザーは、メッセージの作成時にどのメッセージプリセットを使用すればよいか把握するために、メッセージプリセットを表示できます。

これには、次の低レベル権限が含まれます。

* messages_presets.read
* subdomains_delegation.read
* IP_pools.read
* mobile_setting.read（Adobe Experience Platform データ収集から）

### [!DNL Manage suppression] 権限 {#manage-suppression}

**[!DNL Manage suppression]** 高レベル権限を持つユーザーは、メールアドレスが抑制リストに追加されるまでのバウンス数を定義できるほか、抑制リストに対するエントリの追加や削除も行うことができます。

これには、次の低レベル権限が含まれます。

* suppression_rules.read
* suppression_rules.write
* suppression_rules.delete
* suppression_list.write
* suppression_list.delete

### [!DNL View suppression list] 権限 {#view-suppression-list}

**[!DNL View suppression list]** 高レベル権限を持つユーザーは、抑制リストの内容と設定を表示できます。

これには、次の低レベル権限が含まれます。

* Journey Optimizer 固有：
   * suppression_list.view

* Adobe Experience Platform 固有：
   * profiles.read
   * datasets.read

### [!DNL Export suppression list] 権限 {#export-suppression-list}

**[!DNL Export suppression list]** 高レベル権限を持つユーザーは、抑制リストを CSV ファイルとしてダウンロードできます。

これには、次の低レベル権限が含まれます。

* Journey Optimizer 固有：
   * suppression_list.export

* Adobe Experience Platform 固有：
   * profiles.read
   * datasets.read

## Journey Optimizer Library 機能 {library-permissions}

### ライブラリ項目を管理 {#library-items}

この **[!DNL Manage Library Items]** 高レベル権限を持つユーザーは、 [!DNL Journey Optimizer] ライブラリ。

これには、次の低レベル権限が含まれます。

* library_item.create
* ibrary_item.delete
