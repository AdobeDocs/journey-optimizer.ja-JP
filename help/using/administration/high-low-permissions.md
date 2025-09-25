---
solution: Journey Optimizer
product: journey optimizer
title: 権限レベル
description: ユーザーが様々な機能にアクセスできるようになる高レベルおよび低レベルの権限について説明します。
topic: Administration
feature: Access Management
role: Admin, Architect, Developer
level: Experienced
keywords: 権限, 高レベル, 低レベル, プロファイル, Admin Console
exl-id: 1b286f9d-43ef-4b80-b4ee-136da857bb95
source-git-commit: 2a5db6950ac82fd18deb2e4009c9a43247444d6a
workflow-type: tm+mt
source-wordcount: '1303'
ht-degree: 97%

---

# 権限レベル {#high-low-permissions}


各役割は、ユーザーが様々な機能にアクセスできる権限で構成されています。

権限は次の 2 つのタイプに分けることができます。

* **上位の権限**：**[!DNL Publish journeys]** や **[!DNL Manage subdomains delegation]** など、**[!UICONTROL 役割]**&#x200B;に割り当てることができる様々な権限を表します。高レベルの権限は、低レベルの権限を含みます。高レベルの権限について詳しくは、[このページ](ootb-permissions.md)を参照してください。

* **低レベルの権限**：高レベルの権限から取得される様々な権限を表します。

例えば、**[!DNL Journey administrator]** の役割には、**[!DNL Manage journeys]** 権限が割り当てられます。この権限により、ジャーニー管理者に対してジャーニーの書き込み、読み取りおよび削除を許可する低レベルの権限が生じます。

![](assets/do-not-localize/permissions.png){width="70%"}


## ジャーニーリソース {#journey-capability}

* 「**[!DNL Manage journeys]**」という高レベルの権限を持つユーザーは、既存のジャーニーの編集/削除/停止/一時停止、新規作成を行なえるほか、ジャーニーキャンバスでジャーニーフローの構築に使用されるオブジェクトへアクセスできます。

  +++ この権限には、次の低レベルの権限が含まれます。  

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

  +++

* 「**[!DNL Publish journeys]**」という高レベルの権限を持つユーザーは、ジャーニーを公開できます。

  +++ この権限には、次の低レベルの権限が含まれます。  
   * Journey Optimizer 固有：
      * journeys.publish
      * journeys.read

  +++

* 「**[!DNL View journeys]**」という高レベルの権限を持つユーザーは、ジャーニーを参照および表示できます。

  +++ この権限には、次の低レベルの権限が含まれます。  

   * Journey Optimizer 固有：
      * journeys.read

   * Adobe Experience Platform 固有：
      * segments.read
      * profiles.read

  +++

* 「**[!DNL Manage journeys events, data sources and actions]**」という高レベルの権限を持つユーザーは、イベントとデータの設定を行うことができます。

  +++ この権限には、次の低レベルの権限が含まれます。  

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

  +++

* 「**[!DNL View journeys events, data sources and actions]**」という高レベルの権限を持つユーザーは、ジャーニーフローでイベントとデータを使用できます。

  +++ この権限には、次の低レベルの権限が含まれます。  

   * Journey Optimizer 固有：
      * journeys_events.read
      * journeys_data_sources.read
      * journeys_actions.read

   * Adobe Experience Platform 固有：
      * schemas.read
      * datasets.read
      * identity_namespace.read

  +++

* 「**[!DNL View journeys report]**」という高レベルの権限を持つユーザーは、ジャーニーレポートに対する読み取り専用のアクセス権を持ちます。

  +++ この権限には、次の低レベルの権限が含まれます。  

   * Journey Optimizer 固有：
      * journeys_report.read
      * messages_report.read

   * Adobe Experience Platform 固有：
      * datasets.read
      * queries.read
      * queries.write
      * queries.delete

  +++

## Journey Optimizer ルールリソース {#journey-rules-capability}

* 「**[!DNL Manage frequency rules]**」という高レベルの権限を持つユーザーは、頻度ルールの読み取り、作成、編集、削除およびアクティブ化／非アクティブ化を行うことができます。

  +++ この権限には、次の低レベルの権限が含まれます。  

   * Journey Optimizer 固有：
      * frequency_rules.read
      * frequency_rules.write
      * frequency_rules.delete

  +++

* 「**[!DNL View frequency rules]**」という高レベルの権限を持つユーザーは、頻度ルールを表示できます。

  +++ この権限には、次の低レベルの権限が含まれます。  

   * Journey Optimizer 固有：
      * frequency_rules.read

  +++

## キャンペーンリソース {#campaign-capability}

* 「**[!DNL Export suppression list]**」という高レベルの権限を持つユーザーは、抑制リストを CSV ファイルとしてダウンロードできます。

  +++ この権限には、次の低レベルの権限が含まれます。 

   * Journey Optimizer 固有：
      * suppression_list.export

   * Adobe Experience Platform 固有：
      * profiles.read
      * datasets.read

  +++

* 「**[!DNL Manage campaigns]**」という高レベルの権限を持つユーザーは、キャンペーンを新規作成および編集／削除できます。

  +++ この権限には、次の低レベルの権限が含まれます。  

   * Journey Optimizer 固有：

      * campaign.read
      * campaign.write
      * campaign.delete
     <!--* experiments.read
      * experiments.write
      * experiments.delete-->

  +++

* 「**[!DNL Publish campaigns]**」という高レベルの権限を持つユーザーは、キャンペーンを公開できます。

  +++ この権限には、次の低レベルの権限が含まれます。

   * Journey Optimizer 固有：

      * campaign-read
      * campaign-publish
        <!--* experiments.activate-->

  +++

* 「**[!DNL View campaigns report]**」という高レベルの権限を持つユーザーは、キャンペーンレポートを読み取り、編集できます。

  +++ この権限には、次の低レベルの権限が含まれます。  

   * Journey Optimizer 固有：
      * campaign.read
      * campaign-report.read
     <!--* experiments.read
      * experiments_report.read-->

  +++

## 意思決定管理リソース {#decisions-permissions}

* 「**[!DNL Manage decisions]**」という高レベルの権限を持つユーザーは、既存の **[!DNL Activity entities]** の編集／削除、新規作成を行なえるほか、これらのアクティビティで使用されるオブジェクトを管理し、決定することができます。

  +++ この権限には、次の低レベルの権限が含まれます。  

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

  +++

* 「**[!DNL View decisions]**」という高レベルの権限を持つユーザーは、既存のアクティビティと関連するビジネスオブジェクトを使用して意思決定を行うことができます。

  +++ この権限には、次の低レベルの権限が含まれます。  

   * 意思決定管理固有：

      * activities.read
      * offers.read
      * placements.read
      * ranking_strategy.read

   * Adobe Experience Platform 固有：
      * schemas.read
      * segment.read
      * datasets.read

  +++

* 「**[!DNL Manage offers]**」という高レベルの権限を持つユーザーは、すべてのオファー、コンポーネントを作成、編集および削除し、決定およびコレクションを読み取ることができます。

  +++ この権限には、次の低レベルの権限が含まれます。  

   * 意思決定管理固有：

      * offers_activity.read
      * offers.read
      * offers.Write
      * offers.Delete
      * placements.Read
      * placements.Write
      * placements.Delete
      * ranking_strategy.read

   * Adobe Experience Platform 固有：
      * schemas.read
      * segment.read
      * datasets.read
      * profiles.read

  +++

* 「**[!DNL Manage ranking strategies]**」という高レベルの権限を持つユーザーは、ランキング戦略の読み取り、作成、編集、削除を行うことができます。

  +++ この権限には、次の低レベルの権限が含まれます。  

   * 意思決定管理固有：

      * ranking_strategy.read
      * ranking_strategy.write
      * ranking_strategy.delete
      * activities.read
      * offers.read
      * placements.read

  +++

## チャネル設定リソース {#administration-permissions}

<!--
* **[!DNL Manage Experience decisions]** high-level permission allows users to read, create, edit, and delete Decisioning entities.

  +++ This permission includes the following low-level permissions:  

  * Experience decisions specific:
    * ranking_strategy.read
    * offeritem.read
    * offeritem.write
    * offeritem.delete
    * itemCollection.read
    * itemCollection.write
    * itemCollection.delete
    * SelectionStrategy.read
    * SelectionStrategy.write
    * SelectionStrategy.delete
    * Decisionpolicy.read
    * Decisionpolicy.write
    * Decisionpolicy.delete
  +++
-->

* 「**[!DNL Manage file routing]**」という高レベルの権限を持つユーザーは、ファイルルーティング設定の作成、編集および削除を行うことができます。

  +++ この権限には、次の低レベルの権限が含まれます。  
   * Journey Optimizer 固有：

      * file_routing.read
      * file_routing.write
      * file_routing.delete

  +++

* 「**[!DNL Manage IP pools]**」という高レベルの権限を持つユーザーは、アフィニティ定義の作成、編集および削除を行うことができます。

  +++ この権限には、次の低レベルの権限が含まれます。  
   * Journey Optimizer 固有：
      * IP_pools.read
      * IP_pools.write
      * IP_pools.delete

  +++

* 「**[!DNL Manage landing page settings]**」という高レベルの権限を持つユーザーは、ランディングページのサブドメインとプリセット設定の読み取り、作成および編集を行うことができます。

  +++ この権限には、次の低レベルの権限が含まれます。 

   * Journey Optimizer 固有：

      * landing_page_subdomain.read
      * landing_page_subdomain.write
      * landing_page_subdomain.delete
      * landing_page_preset.read
      * landing_page_preset.write
      * landing_page_preset.delete

  +++

* 「**[!DNL Manage messages general settings]**」という高レベルの権限を持つユーザーは、サンドボックスレベルでグローバル設定の作成、編集および削除を行うことができます。

  +++ この権限には、次の低レベルの権限が含まれます。  

   * Journey Optimizer 固有：
      * messages_general_settings.read
      * messages_general_settings.write
      * messages_general_settings.delete

   * Adobe Experience Platform 固有：
      * schemas.read

  +++

* 「**[!DNL Manage messages presets]**」という高レベルの権限を持つユーザーは、チャネルをまたぐチャネル設定の読み取り、作成、編集および削除をサンドボックスレベルで行うことができます。

  +++ この権限には、次の低レベルの権限が含まれます。 

   * Journey Optimizer 固有：
      * messages_presets.read
      * messages_presets.write
      * messages_presets.delete
      * subdomains_delegation.read
      * IP_pools.read

   * データ収集固有：
      * Mobile_setting.read <!--(from Adobe Experience Platform Launch)-->

  +++

* 「**[!DNL Manage PTR records]**」という高レベルの権限を持つユーザーは、サブドメインに基づいて設定された PTR レコードの読み取りと編集を行うことができます。

  +++ この権限には、次の低レベルの権限が含まれます。 

   * Journey Optimizer 固有：
      * PTR_records.read
      * PTR_records.write
      * subdomains_delegation.read

  +++

* 「**[!DNL Manage Seedlist]**」という高レベルの権限を持つユーザーは、シードリストの読み取り、作成、編集、削除を行うことができます。

  +++ この権限には、次の低レベルの権限が含まれます。 

   * Journey Optimizer 固有：
      * seedlist.read
      * seedlist.write
      * seedlist.delete

  +++

* 「**[!DNL Manage SMS subdomains]**」という高レベルの権限を持つユーザーは、SMS サブドメインの読み取り、作成、編集、削除を行うことができます。

  +++ この権限には、次の低レベルの権限が含まれます。 

   * Journey Optimizer 固有：
      * sms_subdomains.read
      * sms_subdomains.write
      * sms_subdomains.delete

  +++

* 「**[!DNL Manage subdomains delegations]**」という高レベルの権限を持つユーザーは、サブドメインのデリゲーション（IP プールを含む）の作成、編集および削除を行うことができます。

  +++ この権限には、次の低レベルの権限が含まれます。  
   * Journey Optimizer 固有：

      * subdomains_delegation.read
      * subdomains_delegation.write
      * subdomains_delegation.delete

  +++

* 「**[!DNL Manage suppression]**」という高レベルの権限を持つユーザーは、メールアドレスが抑制リストに追加されるまでのバウンス数を定義できるほか、抑制リストに対するエントリの追加や削除も行うことができます。

  +++ この権限には、次の低レベルの権限が含まれます。  
   * Journey Optimizer 固有：
      * suppression_rules.read
      * suppression_rules.write
      * suppression_rules.delete
      * suppression_list.write
      * suppression_list.delete

  +++

* 「**[!DNL View file routing]**」という高レベルの権限を持つユーザーは、ファイルルーティング設定を表示できます。

  +++ この権限には、次の低レベルの権限が含まれます。  
   * Journey Optimizer 固有：

      * file_routing.read

  +++

* 「**[!DNL View messages general settings]**」という高レベルの権限を持つユーザーは、メッセージの一般設定（実行アドレスなど）を表示できます。

  +++ この権限には、次の低レベルの権限が含まれます。 

   * Journey Optimizer 固有：
      * messages_general_settings.read

   * Adobe Experience Platform 固有：
      * schemas.read

  +++

* 「**[!DNL View messages presets]**」という高レベルの権限を持つユーザーは、メッセージプリセットを表示できます。

  +++ この権限には、次の低レベルの権限が含まれます。 

   * Journey Optimizer 固有：
      * messages_presets.read
      * subdomains_delegation.read
      * IP_pools.read

   * データ収集固有：
      * Mobile_setting.read

  +++

* 「**[!DNL View PTR records]**」という高レベルの権限を持つユーザーは、サブドメインに基づいて設定された PTR レコードを表示できます。

  +++ この権限には、次の低レベルの権限が含まれます。 
   * Journey Optimizer 固有：

      * PTR_records.read
      * subdomains_delegation.read

  +++

<!--
### [!DNL View channel configuration] permission {#view-channel-surface}

The **[!DNL View channel configuration]** high-level permission allows users to view channel configurations in order to know which channel configurations to use. 
  +++ This permission includes the following low-level permissions:  

* messages_presets.read
* subdomains_delegation.read
* IP_pools.read
* mobile_setting.read (from Adobe Experience Platform Data Collection)
-->


* 「**[!DNL View suppression list]**」という高レベルの権限を持つユーザーは、抑制リストの内容と設定を表示できます。

  +++ この権限には、次の低レベルの権限が含まれます。  

   * Journey Optimizer 固有：
      * suppression_list.view

   * Adobe Experience Platform 固有：
      * profiles.read
      * datasets.read

  +++

<!--
### Manage web subdomain permission {#web-subdomain}

The **[!DNL Manage web subdomain]** high-level permission allows users to read, create, edit, and delete web subdomains.

  +++ This permission includes the following low-level permissions: 
-->

## AI アシスタントリソース {#ai-permissions}

* **[!DNL Generate content]** の高レベルの権限により、ユーザーは Journey Optimizer の AI アシスタントにアクセスできます。

  +++ これには、次の下位レベルの権限が含まれます。  

   * Journey Optimizer 固有：
      * AI アシスタント生成コンテンツ

  +++

## 調整されたキャンペーンリソース {#ai-orchestrated-campaign}

* **[!DNL Manage orchestrated campaigns]** の上位権限を持つユーザーは、調整されたキャンペーンを新規作成および編集／削除できます。

  +++ この権限には、次の低レベルの権限が含まれます。  

   * Journey Optimizer 固有：

      * orchestrated_campaigns.read
      * orchestrated_campaigns.write
      * orchestrated_campaigns.delete
      * cjm-web-subdomain.read
      * cjm-message.read
      * cjm-message.write
      * cjm-message.delete
      * cjm-library-item.read
      * cjm-message-general-setting.read
      * cjm-message-preset.read
      * cjm-message-preview-test.write
      * experiment.read
      * experiment.write
      * experiment.delete

   * Adobe Experience Platform 固有：

      * identity-graph.read
      * segments.read
      * profiles.read
      * datasets.read
      * schemas.read
      * sandboxes.view

  +++

* **[!DNL Manage orchestrated campaigns admin]** の上位権限を持つユーザーは、Adobe Experience Platform プロファイルとリレーショナルストアエンティティ間のリンクと紐付けを新規作成および編集／削除できます。

  +++ この権限には、次の低レベルの権限が含まれます。  

   * Journey Optimizer 固有：

      * cjm-orchestrated-campaign-admin.read
      * cjm-orchestrated-campaign-admin.write
      * cjm-orchestrated-campaign-admin.delete

  +++

* **[!DNL Publish orchestrated campaigns]** の上位権限を持つユーザーは、調整されたキャンペーンを公開できます。

  +++ この権限には、次の低レベルの権限が含まれます。

   * Journey Optimizer 固有：

      * cjm-orchestrated-campaign.read
      * cjm-orchestrated-campaign.publish
      * cjm-web-subdomain.read
      * cjm-message.read
      * cjm-message.publish
      * cjm-library-item.read

   * Adobe Experience Platform 固有：

      * sandboxes.view

  +++

* **[!DNL View orchestrated campaigns]** の上位権限を持つユーザーは、調整されたキャンペーンとそのコンテンツを表示できます。

  +++ この権限には、次の低レベルの権限が含まれます。  

   * Journey Optimizer 固有：

      * cjm-orchestrated-campaign.read
      * cjm-message.read
      * cjm-library-item.read
      * cjm-message-general-setting.read
      * cjm-message-preset.read
      * experiment.read

   * Adobe Experience Platform 固有：

      * sandboxes.view
      * segments.read
      * profiles.read

  +++

* **[!DNL View orchestrated campaigns admin]** の上位権限を持つユーザーは、管理設定を表示できますが、設定を編集することはできません。

  +++ この権限には、次の低レベルの権限が含まれます。  

   * Journey Optimizer 固有：

      * cjm-orchestrated-campaign-admin.read

  +++

* **[!DNL View orchestrated campaigns report]** の上位権限を持つユーザーは、調整されたキャンペーンのパフォーマンスをライブレポートとビジネスレポートの両方で表示できます。

  +++ この権限には、次の低レベルの権限が含まれます。  

   * Journey Optimizer 固有：

      * cjm-orchestrated-campaign-reports.read
      * cjm-message-report.read
      * cjm-channel-report.read
      * cjm-orchestrated-campaign.read
      * cjm-message.read
      * cjm-library-item.read
      * experiment.read
      * experiment-report.read

   * Adobe Experience Platform 固有：

      * sandboxes.view
      * datasets.read
      * queries.read
      * queries.write
      * queries.delete

  +++
