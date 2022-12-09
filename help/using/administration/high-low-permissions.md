---
solution: Journey Optimizer
product: journey optimizer
title: アクセス許可レベル
description: 高レベルと低レベルの権限について説明します。
topic: Administration
role: Admin
level: Intermediate
exl-id: 1b286f9d-43ef-4b80-b4ee-136da857bb95
source-git-commit: 2160d52f24af50417cdcf8c6ec553b746a544c2f
workflow-type: tm+mt
source-wordcount: '834'
ht-degree: 0%

---

# アクセス許可レベル {#high-low-permissions}

![](assets/do-not-localize/permissions.png)

各製品プロファイルは、様々な機能にアクセスするための権限で構成されています。これらは、次の2つのタイプに分けることができます。

* **高レベルのアクセス許可** : や **[!DNL Manage subdomains delegation]** などので [!DNL Admin console] **[!DNL Publish journeys]** に **[!UICONTROL Product profile]** 割り当てられるさまざまなアクセス許可を指定します。高レベルのアクセス許可は、低レベルのアクセス許可を網羅します。

* **「低レベル」アクセス** 許可: 高レベルのアクセス許可から取得されたさまざまなアクセス許可を表します。

例えば、 **[!DNL Journey administrator]** 製品プロファイルにはパーミッションが割り当てら **[!DNL Manage journeys]** れています。 このアクセス許可によって、記録された管理者が journeys の作成、読み取り、削除を実行できるようにするための下位レベルの権限が与えられます。

## 旅機能 {#journey-capability}

### [!DNL Manage journeys] 許可 {#manage-journeys}

高レベルの **[!DNL Manage journeys]** 権限を使用すると、ユーザーは新しい Journeys を作成して、既存のを編集または削除することができます。また、旅のフローを構築するために、これらのオブジェクトに対して使用されているオブジェクトにアクセスすることもできます。

このファイルには、次の下位レベルの権限が含まれています。

* 次のような旅のオプティマイザー:

   * journeys.read
   * journeys.write
   * journeys.delete
   * messages.read

* Adobe エクスペリエンスプラットフォーム特有の機能:

   * segments.read
   * profiles.read
   * datasets.read
   * schemas.read

### [!DNL Publish journeys] 許可 {#publish-journeys}

高レベルの権限を使用すると、 **[!DNL Publish journeys]** journeys を公開することができます。

このファイルには、次の下位レベルの権限が含まれています。

* 次のような旅のオプティマイザー:
   * journeys.publish
   * journeys.read

### [!DNL View journeys] 許可 {#view-journeys}

高レベルの権限を使用すると、 **[!DNL View journeys]** journeys を参照したり表示したりすることができます。

このファイルには、次の下位レベルの権限が含まれています。

* 次のような旅のオプティマイザー:
   * journeys.read

* Adobe エクスペリエンスプラットフォーム特有の機能:
   * segments.read
   * profiles.read

### [!DNL Manage journeys events, data sources and actions] 許可 {#manage-journeys-events}

高レベルの権限を使用すると、 **[!DNL Manage journeys events, data sources and actions]** ユーザーがイベントおよびデータの設定を行うことができます。

このファイルには、次の下位レベルの権限が含まれています。

* 次のような旅のオプティマイザー:
   * journeys_events を参照してください。
   * journeys_events の作成
   * journeys_events を削除します。
   * journeys_data_sources を参照してください。
   * journeys_data_sources の作成
   * journeys_data_sources を削除します。
   * journeys_actions を参照してください。
   * journeys_actions の作成
   * journeys_actions を削除します。

* Adobe エクスペリエンスプラットフォーム特有の機能:
   * schemas.read
   * datasets.read
   * identity_namespace を参照してください。

### [!DNL View journeys events, data sources and actions] 許可 {#view-journeys-event}

高レベルの **[!DNL View journeys events, data sources and actions]** 権限を使用すると、ユーザーは旅の過程でイベントやデータを使用することができます。

このファイルには、次の下位レベルの権限が含まれています。

* 次のような旅のオプティマイザー:
   * journeys_events を参照してください。
   * journeys_data_sources を参照してください。
   * journeys_actions を参照してください。

* Adobe エクスペリエンスプラットフォーム特有の機能:
   * schemas.read
   * datasets.read
   * identity_namespace を参照してください。

### [!DNL View journeys report] 許可 {#view-journeys-report}

高レベルの権限を使用すると、ユーザーは読み取り専用の **[!DNL View journeys report]** 旅レポートを作成できます。

このファイルには、次の下位レベルの権限が含まれています。

* 次のような旅のオプティマイザー:
   * journeys_report を参照してください。
   * messages_report を参照してください。

* Adobe エクスペリエンスプラットフォーム特有の機能:
   * datasets.read
   * queries.read
   * queries.write
   * queries.delete

## 意思決定管理機能 {#decisions-permissions}

### [!DNL Manage decisions] 許可 {#manage-decisioning}

高レベルの権限を **[!DNL Manage decisions]** 使用すると、ユーザーは新規作成し、既存 **[!DNL Activity entities]** の編集/削除を行うことができます。また、これらの操作で使用するオブジェクトを管理して、決定を行うこともできます。

このファイルには、次の下位レベルの権限が含まれています。

* 意思決定管理に関する具体的な事項:
   * activities.read
   * activities.write
   * activities.delete
   * offers.read
   * offers.write
   * offers.delete
   * placements.read
   * placements.write
   * placements.delete
   * ranking_strategy を参照してください。

* Adobe エクスペリエンスプラットフォーム特有の機能:
   * datasets.read
   * datasets.write
   * datasets.delete
   * schemas.read
   * profile.read
   * segments.read

### [!DNL View decisions] 許可 {#view-decisions}

高レベルの **[!DNL View decisions]** 権限を使用すると、ユーザーは既存の操作と関連するビジネスオブジェクトを使用して、決定を行うことができます。

このファイルには、次の下位レベルの権限が含まれています。

* 意思決定管理に関する具体的な事項:
   * activities.read
   * offers.read
   * placements.read
   * ranking_strategy を参照してください。

* Adobe エクスペリエンスプラットフォーム特有の機能:
   * schemas.read
   * segment.read
   * datasets.read
   * datasets.write
   * datasets.delete

### [!DNL Publish offers decisioning] 許可 {#publish-decisions}

高レベルの権限を使用すると、ユーザーは提示された **[!DNL Publish offers decisioning]** 利用状況にアクセスすることができます。

このファイルには、次の下位レベルの権限が含まれています。

* 意思決定管理に関する具体的な事項:
   * offers_activity を参照してください。
   * offers.read
   * offers.write
   * offers.delete
   * placements.read
   * placements.write
   * placements.delete
   * ranking_strategy を参照してください。

* Adobe エクスペリエンスプラットフォーム特有の機能:
   * schemas.read
   * segment.read
   * datasets.read
   * profiles.read

### [!DNL Manage ranking strategies] 許可 {#manage-ranking-strategies}

高レベルの権限を使用すると、 **[!DNL Manage ranking strategies]** ユーザーはランク付け方針を読み取り、作成、編集、削除することができます。

このファイルには、次の下位レベルの権限が含まれています。

* 意思決定管理に関する具体的な事項:
   * ranking_strategy を参照してください。
   * ranking_strategy の作成
   * ranking_strategy を削除します。
   * activities.read
   * offers.read
   * placements.read

## 管理機能 {#administration-permissions}

### [!DNL Manage subdomains delegation] 許可 {#manage-subdomain}

高レベルの権限を使用すると、 **[!DNL Manage subdomains delegation]** ユーザーはサブドメインを作成、編集、削除できます。この機能を使用して IP プールを作成することもできます。

このファイルには、次の下位レベルの権限が含まれています。

* subdomains_delegation を参照してください。
* subdomains_delegation の作成
* subdomains_delegation を削除します。

### [!DNL Manage PTR records] 許可 {#manage-ptr}

高レベルの **[!DNL Manage PTR records]** アクセス許可によって、ユーザーは、サブドメインに基づいて構成されている PTR レコードを読み取り、編集することができます。

このファイルには、次の下位レベルの権限が含まれています。

* PTR_records を参照してください。
* PTR_records の作成
* subdomains_delegation を参照してください。

### [!DNL View PTR records] 許可 {#view-ptr}

高レベルの **[!DNL View PTR records]** 権限を使用すると、サブドメインに基づいて設定されている PTR レコードを表示できます。

このファイルには、次の下位レベルの権限が含まれています。

* PTR_records を参照してください。
* subdomains_delegation を参照してください。

### [!DNL Manage IP pools] 許可 {#manage-ip-pools}

高レベルの権限を **[!DNL Manage IP pools]** 使用すると、ユーザーはアフィニティ定義を作成、編集、および削除することができます。

このファイルには、次の下位レベルの権限が含まれています。

* IP_pools を参照してください。
* IP_pools の作成
* IP_pools を削除します。

<!--
### [!DNL Manage messages general settings] permission {#manage-message-settings}

The **[!DNL Manage messages general settings]** high-level permission allows users to create, edit and delete global settings at the sandbox level.

It includes the following low-level permissions: 

* Journey Optimizer specific: 
  * messages_general_settings.read
  * messages_general_settings.write
  * messages_general_settings.delete
* Adobe Experience Platform specific:
  * schemas.read

### [!DNL View messages general settings] permission {#view-message-settings}

The **[!DNL View messages general settings]** high-level permission allows users to view messages general settings such as the execution address.

It includes the following low-level permissions:

* Journey Optimizer specific: 
  * messages_general_settings.read
* Adobe Experience Platform specific: 
  * schemas.read
-->

### [!DNL Manage channel surface] 許可 {#manage-channel-surface}

高レベルの権限を使用すると、 **[!DNL Manage channel surface]** ユーザーは、チャネル間でサンドボックスレベルのチャンネルを作成、編集、削除することができます。

このファイルには、次の下位レベルの権限が含まれています。

* 次のような旅のオプティマイザー:
   * messages_presets を参照してください。
   * messages_presets の作成
   * messages_presets を削除します。
   * subdomains_delegation を参照してください。
   * IP_pools を参照してください。
   * mobile_setting (Adobe エクスペリエンスプラットフォームの起動から)

### [!DNL View channel surface] 許可 {#view-channel-surface}

高レベルの権限を使用すると、ユーザーはチャンネルサーフェスを表示して **[!DNL View channel surface]** 、どのチャンネルサーフェスを使用するかを確認することができます。

このファイルには、次の下位レベルの権限が含まれています。

* messages_presets を参照してください。
* subdomains_delegation を参照してください。
* IP_pools を参照してください。
* mobile_setting ます (Adobe エクスペリエンスプラットフォームデータコレクションからの読み取り)。

### [!DNL Manage suppression] 許可 {#manage-suppression}

高レベルの権限を **[!DNL Manage suppression]** 使用すると、抑制リストに電子メールアドレスを追加する前に、ユーザーがバウンスの回数を定義することができます。また、抑制リストとの間でエントリを追加したり削除したりすることもできます。

このファイルには、次の下位レベルの権限が含まれています。

* suppression_rules を参照してください。
* suppression_rules の作成
* suppression_rules を削除します。
* suppression_list の作成
* suppression_list を削除します。

### [!DNL View suppression list] 許可 {#view-suppression-list}

高レベルの **[!DNL View suppression list]** 権限を使用すると、抑制リストのコンテンツと設定を表示することができます。

このファイルには、次の下位レベルの権限が含まれています。

* 次のような旅のオプティマイザー:
   * suppression_list を表示します。

* Adobe エクスペリエンスプラットフォーム特有の機能:
   * profiles.read
   * datasets.read

### [!DNL Export suppression list] 許可 {#export-suppression-list}

高レベルのアクセス許可に **[!DNL Export suppression list]** よって、ユーザーは抑制リストを CSV ファイルとしてダウンロードできます。

このファイルには、次の下位レベルの権限が含まれています。

* 次のような旅のオプティマイザー:
   * suppression_list 書き出し

* Adobe エクスペリエンスプラットフォーム特有の機能:
   * profiles.read
   * datasets.read

### [!DNL Manage landing page settings] 許可 {#manage-landing-page-settings}

高レベルの権限を使用すると、ユーザーは、ランディングページのサブドメインと事前設定の **[!DNL Manage landing page settings]** 設定を読み取り、作成、編集することができます。

このファイルには、次の下位レベルの権限が含まれています。

* 次のような旅のオプティマイザー:
   * landing_page_subdomain を参照してください。
   * landing_page_subdomain の作成
   * landing_page_subdomain を削除します。
   * landing_page_preset を参照してください。
   * landing_page_preset の作成
   * landing_page_preset を削除します。

### [!DNL Manage frequency rules] 許可 {#manage-frequency-rules}

高レベルの権限を使用すると、頻度ルールの **[!DNL Manage frequency rules]** 読み取り、作成、編集、削除、アクティブ化、非アクティブ化を行うことができます。

このファイルには、次の下位レベルの権限が含まれています。

* 次のような旅のオプティマイザー:
   * frequency_rules を参照してください。
   * frequency_rules の作成
   * frequency_rules を削除します。

### [!DNL View frequency rules] 許可 {#view-frequency-rules}

高レベルの権限を使用すると、 **[!DNL View frequency rules]** ユーザーは頻度ルールを表示することができます。

このファイルには、次の下位レベルの権限が含まれています。

* 次のような旅のオプティマイザー:
   * frequency_rules を参照してください。
