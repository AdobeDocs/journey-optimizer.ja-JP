---
title: 権限レベル
description: 高レベルおよび低レベル権限について学ぶ
page-status-flag: never-activated
uuid: null
contentOwner: null
products: null
audience: administrators
content-type: reference
topic-tags: null
discoiquuid: null
internal: n
snippet: y
exl-id: 85fd386a-45fa-4f9a-89d1-cecc0749b90d
feature: コントロール母集団
topic: 管理
role: Administrator
level: Intermediate
source-git-commit: b58c5b527e594c03f3b415549e6b7cd15b050139
workflow-type: tm+mt
source-wordcount: '1171'
ht-degree: 100%

---

# 権限レベル {#high-low-permissions}

![](../assets/do-not-localize/permissions.png)

各製品プロファイルは、ユーザーが様々な機能にアクセスできる権限で構成されています。
権限は次の 2 つのタイプに分けることができます。

* **高レベル権限**：**[!UICONTROL ジャーニーの公開]**&#x200B;や&#x200B;**[!UICONTROL サブドメインのデリゲーションの管理]**&#x200B;など、[!DNL Admin console] で&#x200B;**[!UICONTROL 製品プロファイル]**&#x200B;に割り当てることができる様々な権限を表します。高レベル権限は、低レベル権限を含みます。

* **低レベル権限**：高レベル権限から取得される様々な権限を表します。

例えば、**[!UICONTROL ジャーニー管理者]**&#x200B;製品プロファイルには、**[!UICONTROL ジャーニーの管理]**&#x200B;権限が割り当てられます。 この権限により、ジャーニー管理者がジャーニーの書き込み、読み取りおよび削除ができる低レベル権限が生じます。

## ジャーニー機能 {#journey-capability}

### ジャーニー管理の権限 {#manage-journeys}

**[!UICONTROL ジャーニーの管理]**&#x200B;の高レベル権限を持つユーザーは、新しいジャーニーの作成や、既存のジャーニーの編集／削除、ジャーニーキャンバスでジャーニーフローの構築に使用されるオブジェクトへのアクセスができます。

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

### ジャーニーの公開権限 {#publish-journeys}

**[!UICONTROL ジャーニーの公開]**&#x200B;の高レベル権限を持つユーザーは、ジャーニーを公開できます。

これには、次の低レベル権限が含まれます。

* Journey Optimizer 固有：
   * journeys.publish
   * journeys.read

### ジャーニーの表示権限 {#view-journeys}

**[!UICONTROL ジャーニーの表示]**&#x200B;の高レベル権限を持つユーザーは、ジャーニーを参照および表示できます。

これには、次の低レベル権限が含まれます。

* Journey Optimizer 固有：
   * journeys.read

* Adobe Experience Platform 固有：
   * segments.read
   * profiles.read

### ジャーニーイベント、データソース、アクションの管理権限 {#manage-journeys-events}

**[!UICONTROL ジャーニーイベント、データソース、アクションの管理]**&#x200B;の高レベル権限を持つユーザーは、イベントとデータの設定を行うことができます。

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

### ジャーニーイベント、データソース、アクションの表示権限 {#view-journeys-event}

**[!UICONTROL ジャーニーイベント、データソース、アクションの表示]**&#x200B;の高レベル権限を持つユーザーは、ジャーニーフローでイベントとデータを使用できます。

これには、次の低レベル権限が含まれます。

* Journey Optimizer 固有：
   * journeys_events.read
   * journeys_data_sources.read
   * journeys_actions.read

* Adobe Experience Platform 固有：
   * schemas.read
   * datasets.read
   * identity_namespace.read

### ジャーニーレポートの表示権限 {#view-journeys-report}

**[!UICONTROL ジャーニーレポートの表示]**&#x200B;の高レベル権限を持つユーザーは、ジャーニーレポートを読み取ることのみが可能です。

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

### メッセージの管理権限 {#manage-messages}

**[!UICONTROL メッセージの管理]**&#x200B;の高レベル権限を持つユーザーは、メッセージを作成および編集／削除できます。

これには、次の低レベル権限が含まれます。

* Journey Optimizer 固有：
   * messages.write
   * messages.read
   * messages.delete
   * messages_presets.read

* Adobe Experience Platform 固有：
   * segments.read
   * schemas.read

### メッセージのプレビューとテストの管理権限 {#mange-messages-preview}

**[!UICONTROL メッセージのプレビューおよびテストの管理]**&#x200B;の高レベル権限を持つユーザーは、パーソナライズされたメッセージをプレビューできます。

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

### メッセージの公開権限 {#publish-messages}

**[!UICONTROL メッセージの公開]**&#x200B;の高レベル権限を持つユーザーは、メッセージを公開できます。

これには、次の低レベル権限が含まれます。

* Journey Optimizer 固有：
   * messages.publish

* Adobe Experience Platform 固有：
   * profiles.read
   * schemas.read
   * datasets.read

### メッセージの表示権限 {#view-messages}

**[!UICONTROL メッセージの表示]**&#x200B;の高レベル権限を持つユーザーは、メッセージの読み取りのみ可能です。

これには、次の低レベル権限が含まれます。

* Journey Optimizer 固有：
   * messages.read
   * messages_presets.read

* Adobe Experience Platform 固有：
   * schemas.read
   * segments.read

### メッセージレポートの表示権限 {#view-message-reports}

**[!UICONTROL メッセージレポートの表示]**&#x200B;の高レベル権限を持つユーザーは、読み取り専用のメールおよびプッシュレポートが許可されます。

これには、次の低レベル権限が含まれます。

* Journey Optimizer 固有：
   * messages_report.read
   * datasets.read
   * queries.read
   * queries.write
   * queries.delete
   * journey.read

## 決定管理機能 {#decisions-permissions}

### 決定の管理権限 {#manage-decisioning}

**[!UICONTROL 決定管理]**&#x200B;の高レベル権限を持つユーザーは、既存の&#x200B;**[!UICONTROL アクティビティエンティティ]**&#x200B;の編集／削除、新規作成をおこなえるほか、これらのアクティビティで使用されるオブジェクトを管理し、決定することができます。

これには、次の低レベル権限が含まれます。

* 決定管理固有：
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

### 決定の表示権限 {#view-decisions}

**[!UICONTROL 決定を表示]**&#x200B;の高レベル権限を持つユーザーは、既存のアクティビティと関連するビジネスオブジェクトを使用して意思決定をおこなうことができます。

これには、次の低レベル権限が含まれます。

* 決定管理固有：
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

### オファー決定の公開権限 {#publish-decisions}

**[!UICONTROL オファー決定の公開]**&#x200B;の高レベル権限を持つユーザーは、オファーアクティビティを承認／未承認する権限を持ちます。

これには、次の低レベル権限が含まれます。

* 決定管理固有：
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

### ランキング戦略の管理権限 {#manage-decisions}

**[!UICONTROL ランキング戦略の管理]**&#x200B;の高レベル権限を持つユーザーは、カスタムメッセージレポートの読み取り、作成、編集および削除や、アクション機能を使用できます。

これには、次の低レベル権限が含まれます。

* 決定管理固有：
   * ranking_strategy.read
   * ranking_strategy.write
   * ranking_strategy.delete
   * activities.read
   * offers.read
   * placements.read

## 管理機能 {#administration-permissions}

### サブドメインのデリゲーション管理権限 {#manage-subdomain}

**[!UICONTROL サブドメインのデリゲーション管理]**&#x200B;の高レベル権限を持つユーザーは、サブドメインのデリゲーション（IP プールを含む）の作成、編集および削除ができます。

これには、次の低レベル権限が含まれます。

* subdomains_delegation.read
* subdomains_delegation.write
* subdomains_delegation.delete

### PTR レコードのアクセス表示権限 {#view-ptr}

**[!UICONTROL PTR レコードの表示]**&#x200B;の高レベル権限を持つユーザーは、サブドメインに基づいて構成された、次の低レベル権限を含む PTR レコードを表示できます。

* PTR_records.read
* subdomains_delegation.read

### IP プールの管理権限 {#manage-ip-pools}

**[!UICONTROL IP プールの管理]**&#x200B;の高レベル権限を持つユーザーは、アフィニティ定義を作成、編集および削除できます。

これには、次の低レベル権限が含まれます。

* IP_pools.read
* IP_pools.write
* IP_pools.delete

### メッセージの一般設定の管理権限 {#manage-message-settings}

**[!UICONTROL メッセージの一般設定の管理]**&#x200B;の高レベル権限をを持つユーザーは、サンドボックスレベルでグローバル設定を作成、編集および削除できます。

これには、次の低レベル権限が含まれます。

* Journey Optimizer 固有：
   * messages_general_settings.read
   * messages_general_settings.write
   * messages_general_settings.delete

* Adobe Experience Platform 固有：
   * schemas.read

### メッセージの一般設定の表示権限 {#view-message-settings}

**[!UICONTROL メッセージの一般設定の表示]**&#x200B;の高レベル権限を持つユーザーは、抑制ルールや実行アドレスなどの、メッセージの一般設定を表示できます。

これには、次の低レベル権限が含まれます。

* Journey Optimizer 固有：
   * messages_general_settings.read
* Adobe Experience Platform 固有：
   * schemas.read

### メッセージプリセットの管理権限 {#manage-message-presets}

**[!UICONTROL メッセージプリセットの管理]**&#x200B;の高レベル権限を持つユーザーは、サンドボックスレベルでチャネル間のメッセージプリセットを作成、編集および削除できます。

これには、次の低レベル権限が含まれます。

* Journey Optimizer 固有：
   * messages_presets.read
   * messages_presets.write
   * messages_presets.delete
   * subdomains_delegation.read
   * IP_pools.read
   * mobile_setting.read（Adobe Experience Platform Launch から）

### メッセージプリセットの表示権限 {#view-message-presets}

**[!UICONTROL メッセージプリセットの表示]**&#x200B;の高レベル権限を持つユーザーは、メッセージの作成時にどのメッセージプリセットを使うべきか理解できるように、メッセージプリセットを表示できます。

これには、次の低レベル権限が含まれます。

* messages_presets.read
* subdomains_delegation.read
* IP_pools.read
* mobile_setting.read（Adobe Experience Platform Launch から）

### 抑制ルールの管理権限 {#manage-suppression-rules}

**[!UICONTROL 抑制ルールの管理]**&#x200B;の高レベル権限を持つユーザーは、自身のメールアドレスが抑制リストに追加される前に、バウンス数を定義できます。

これには、次の低レベル権限が含まれます。

* suppression_rules.read
* suppression_rules.write
* suppression_rules.delete

### 抑制リストの表示権限 {#view-suppresion-list}

**[!UICONTROL 抑制リストの表示]**&#x200B;の高レベル権限を持つユーザーは、メッセージプリセットや一般的なメッセージ設定などのメッセージ設定を表示できます。

これには、次の低レベル権限が含まれます。

* Journey Optimizer 固有：
   * suppression_list.view
* Adobe Experience Platform 固有：
   * profiles.read
   * datasets.read

### 抑制リストの書き出し権限 {#export-suppression-list}

**[!UICONTROL 抑制リストの書き出し]**&#x200B;の高レベル権限を持つユーザーは、メッセージプリセットや一般的なメッセージ設定などのメッセージ設定を行うことができます。

これには、次の低レベル権限が含まれます。

* Adobe Experience Platform 固有：
   * profiles.read
   * datasets.read
