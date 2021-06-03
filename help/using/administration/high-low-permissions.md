---
title: 権限レベル
description: 高レベルおよび低レベルの権限について説明します
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
source-git-commit: 917dc621afc7b7137d8556987967966d23fae4c9
workflow-type: tm+mt
source-wordcount: '1168'
ht-degree: 0%

---

# 権限レベル{#high-low-permissions}

![](../assets/do-not-localize/permissions.png)

各製品プロファイルは、ユーザーが様々な機能にアクセスできる権限で構成されています。
次の2つのタイプに分けることができます。

* **高レベルの権限**:は、公開ジャーニーやサブドメインデリゲーシ **[!UICONTROL ョンの管]** 理など、 [!DNL Admin console]で製品プロファイルに割り当て **[!UICONTROL ることができる様々]** な権限を表します ****。高レベルの権限は、低レベルの権限を含みます。

* **低レベルの権限**:は、高レベルの権限から取得される様々な権限を表します。

例えば、**[!UICONTROL ジャーニー管理者]**&#x200B;製品プロファイルに、**[!UICONTROL ジャーニーの管理]**&#x200B;権限が割り当てられます。 この権限により、ジャーニー管理者がジャーニーの書き込み、読み取り、削除をおこなえる低レベルの権限が生じます。

## ジャーニー機能{#journey-capability}

### ジャーニー権限の管理{#manage-journeys}

**[!UICONTROL ジャーニーの管理]**&#x200B;の高レベル権限を使用すると、新しいジャーニーの作成や、既存のジャーニーの編集/削除、ジャーニーキャンバスでジャーニーフローの構築に使用されるオブジェクトへのアクセスができます。

これには、次の低レベル権限が含まれます。

* Journey Optimizer固有：

   * journeys.read
   * journeys.write
   * journeys.delete
   * messages.read

* Adobe Experience Platform固有：

   * segments.read
   * profiles.read
   * datasets.read
   * schemas.read

### ジャーニーの公開権限{#publish-journeys}

**[!UICONTROL ジャーニーの公開]**&#x200B;の高レベル権限を使用すると、ユーザーはジャーニーを公開できます。

これには、次の低レベル権限が含まれます。

* Journey Optimizer固有：
   * journeys.publish
   * journeys.read

### ジャーニー権限{#view-journeys}の表示

**[!UICONTROL ジャーニー]**&#x200B;の高レベル権限を使用すると、ユーザーはジャーニーを参照および表示できます。

これには、次の低レベル権限が含まれます。

* Journey Optimizer固有：
   * journeys.read

* Adobe Experience Platform固有：
   * segments.read
   * profiles.read

### ジャーニーイベント、データソース、アクションの権限を管理します。{#manage-journeys-events}

**[!UICONTROL ジャーニーイベント、データソース、アクションの管理]**&#x200B;の高レベル権限を使用すると、イベントとデータの設定を行うことができます。

これには、次の低レベル権限が含まれます。

* Journey Optimizer固有：
   * journeys_events.read
   * journeys_events.write
   * journeys_events.delete
   * journeys_data_sources.read
   * journeys_data_sources.write
   * journeys_data_sources.delete
   * journeys_actions.read
   * journeys_actions.write
   * journeys_actions.delete
* Adobe Experience Platform固有：
   * schemas.read
   * datasets.read
   * identity_namespace.read

### ジャーニーイベント、データソース、アクションの権限を表示{#view-journeys-event}

**[!UICONTROL ジャーニーイベント、データソース、アクションの表示]**&#x200B;の高レベル権限を使用すると、ユーザーはジャーニーフローでイベントとデータを使用できます。

これには、次の低レベル権限が含まれます。

* Journey Optimizer固有：
   * journeys_events.read
   * journeys_data_sources.read
   * journeys_actions.read

* Adobe Experience Platform固有：
   * schemas.read
   * datasets.read
   * identity_namespace.read

### ジャーニーレポートの権限{#view-journeys-report}を表示

**[!UICONTROL ジャーニーレポート]**&#x200B;の高レベル権限を持つユーザーは、読み取り専用のジャーニーレポートを作成できます。

これには、次の低レベル権限が含まれます。

* Journey Optimizer固有：
   * journeys_report.read
   * messages_report.read

* Adobe Experience Platform固有：
   * datasets.read
   * queries.read
   * queries.write
   * queries.delete

## メッセージ機能{#message-capability}

### メッセージの管理権限{#manage-messages}

**[!UICONTROL メッセージの管理]**&#x200B;の高レベル権限を使用すると、ユーザーはメッセージを作成および編集/削除できます。

これには、次の低レベル権限が含まれます。

* Journey Optimizer固有：
   * messages.write
   * messages.read
   * messages.delete
   * messages_presets.read

* Adobe Experience Platform固有：
   * segments.read
   * schemas.read

### メッセージのプレビューとテストの権限を管理します{#mange-messages-preview}

**[!UICONTROL メッセージのプレビューおよびテストの管理]**&#x200B;の高レベル権限を使用すると、パーソナライズされたメッセージをプレビューできます。

これには、次の低レベル権限が含まれます。

* Journey Optimizer固有：
   * messages.publish
   * messages_preview_and_test.write
   * messages.publish

* Adobe Experience Platform固有：
   * profiles.read
   * profiles.write
   * schemas.read
   * datasets.write
   * datasets.read
   * identity_namespace.read
   * segments.read
   * queries.write
   * merge_policies.read

### メッセージの公開権限{#publish-messages}

**[!UICONTROL メッセージの公開]**&#x200B;の高レベル権限を使用すると、ユーザーはメッセージを公開できます。

これには、次の低レベル権限が含まれます。

* Journey Optimizer固有：
   * messages.publish

* Adobe Experience Platform固有：
   * profiles.read
   * schemas.read
   * datasets.read

### メッセージの表示権限{#view-messages}

**[!UICONTROL メッセージの表示]**&#x200B;の高レベル権限を持つユーザーは、メッセージの読み取りのみ可能です。

これには、次の低レベル権限が含まれます。

* Journey Optimizer固有：
   * messages.read
   * messages_presets.read

* Adobe Experience Platform固有：
   * schemas.read
   * segments.read

### メッセージレポートの権限{#view-message-reports}の表示

**[!UICONTROL メッセージレポート]**&#x200B;の表示権限を持つユーザーは、読み取り専用の電子メールおよびプッシュレポートを実行できます。

これには、次の低レベル権限が含まれます。

* Journey Optimizer固有：
   * messages_report.read
   * datasets.read
   * queries.read
   * queries.write
   * queries.delete
   * journey.read

## 判定管理機能{#decisions-permissions}

### 決定権限の管理{#manage-decisioning}

**[!UICONTROL 意思決定を管理]**&#x200B;大まかな権限を持つユーザーは、新しい&#x200B;**[!UICONTROL アクティビティエンティティ]**&#x200B;の作成や編集、削除を行えるほか、これらのアクティビティで使用されるオブジェクトを管理できます。

これには、次の低レベル権限が含まれます。

* 判定管理固有：
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

* Adobe Experience Platform固有：
   * datasets.read
   * datasets.write
   * datasets.delete
   * schemas.read
   * profile.read
   * segments.read

### 表示決定権限{#view-decisions}

**[!UICONTROL 意思決定を表示]**&#x200B;する高レベルの権限を持つユーザーは、既存のアクティビティと関連するビジネスオブジェクトを使用して意思決定をおこなうことができます。

これには、次の低レベル権限が含まれます。

* 判定管理固有：
   * activities.read
   * offers.read
   * placements.read
   * ranking_strategy.read

* Adobe Experience Platform固有：
   * schemas.read
   * segment.read
   * datasets.read
   * datasets.write
   * datasets.delete

### オファー判定権限の公開{#publish-decisions}

**[!UICONTROL オファー判定]**&#x200B;の公開の高レベル権限を使用すると、ユーザーはオファーアクティビティの承認/未承認にアクセスできます。

これには、次の低レベル権限が含まれます。

* 判定管理固有：
   * offers_activity.read
   * offers.read
   * offers.write
   * offers.delete
   * placements.read
   * placements.write
   * placements.delete
   * ranking_strategy.read

* Adobe Experience Platform固有：
   * schemas.read
   * segment.read
   * datasets.read
   * profiles.read

### ランキング戦略の権限{#manage-decisions}の管理

**[!UICONTROL ランキング戦略の管理]**&#x200B;の高レベル権限を使用すると、カスタムメッセージレポートの読み取り、作成、編集、削除や、アクション機能の使用が可能になります。

これには、次の低レベル権限が含まれます。

* 判定管理固有：
   * ranking_strategy.read
   * ranking_strategy.write
   * ranking_strategy.delete
   * activities.read
   * offers.read
   * placements.read

## 管理機能{#administration-permissions}

### サブドメインのデリゲーション権限を管理します{#manage-subdomain}

**[!UICONTROL サブドメインデリゲーションの管理]**&#x200B;の高レベル権限を使用すると、サブドメインデリゲーション（IPプールを含む）を作成、編集および削除できます。

これには、次の低レベル権限が含まれます。

* subdomains_delegation.read
* subdomains_delegation.write
* subdomains_delegation.delete

### PTRレコードのアクセス許可{#view-ptr}の表示

**[!UICONTROL View PTR records]**&#x200B;高レベル権限を使用すると、サブドメインに基づいて構成され、次の低レベル権限を含むPTRレコードを表示できます。

* PTR_records.read
* subdomains_delegation.read

### IPプールのアクセス許可{#manage-ip-pools}を管理します

**[!UICONTROL IPプールの管理]**&#x200B;の高レベル権限を使用すると、アフィニティ定義の作成、編集、削除を行うことができます。

これには、次の低レベル権限が含まれます。

* IP_pools.read
* IP_pools.write
* IP_pools.delete

### メッセージの全般設定の権限{#manage-message-settings}を管理します

**[!UICONTROL メッセージの一般設定を管理]**&#x200B;高レベル権限を使用すると、サンドボックスレベルでグローバル設定を作成、編集、削除できます。

これには、次の低レベル権限が含まれます。

* Journey Optimizer固有：
   * messages_general_settings.read
   * messages_general_settings.write
   * messages_general_settings.delete

* Adobe Experience Platform固有：
   * schemas.read

### メッセージの一般設定のアクセス許可{#view-message-settings}を表示

**[!UICONTROL メッセージの一般設定]**&#x200B;の高レベル権限を使用すると、抑制ルールや実行アドレスなどのメッセージの一般設定を表示できます。

これには、次の低レベル権限が含まれます。

* Journey Optimizer固有：
   * messages_general_settings.read
* Adobe Experience Platform固有：
   * schemas.read

### メッセージプリセットの権限{#manage-message-presets}の管理

**[!UICONTROL メッセージプリセットの管理]**&#x200B;の高レベル権限を使用すると、ユーザーはサンドボックスレベルでチャネル間でメッセージプリセットを作成、編集および削除できます。

これには、次の低レベル権限が含まれます。

* Journey Optimizer固有：
   * messages_presets.read
   * messages_presets.write
   * messages_presets.delete
   * subdomains_delegation.read
   * IP_pools.read
   * mobile_setting.read (Adobe Experience Platform Launchから)

### メッセージプリセットの権限{#view-message-presets}の表示

「**[!UICONTROL メッセージプリセットを表示]**」の高レベル権限を使用すると、メッセージの作成時に使用するメッセージプリセットを知るために、メッセージプリセットを表示できます。

これには、次の低レベル権限が含まれます。

* messages_presets.read
* subdomains_delegation.read
* IP_pools.read
* mobile_setting.read (Adobe Experience Platform Launchから)

### 抑制ルールの権限を管理{#manage-suppression-rules}

**[!UICONTROL 抑制ルールの管理]**&#x200B;の高レベル権限を使用すると、ユーザーの電子メールアドレスが抑制リストに追加される前に、バウンス数を定義できます。

これには、次の低レベル権限が含まれます。

* suppression_rules.read
* suppression_rules.write
* suppression_rules.delete

### 表示抑制リストの権限{#view-suppresion-list}

**[!UICONTROL 表示抑制リスト]**&#x200B;の高レベル権限を使用すると、メッセージプリセットや一般的なメッセージ設定などのメッセージ設定を表示できます。

これには、次の低レベル権限が含まれます。

* Journey Optimizer固有：
   * suppression_list.view
* Adobe Experience Platform固有：
   * profiles.read
   * datasets.read

### 書き出し抑制リストの権限{#export-suppression-list}

**[!UICONTROL 書き出し抑制リスト]**&#x200B;の高レベル権限を使用すると、メッセージプリセットや一般的なメッセージ設定などのメッセージ設定を行うことができます。

これには、次の低レベル権限が含まれます。

* Adobe Experience Platform固有：
   * profiles.read
   * datasets.read
