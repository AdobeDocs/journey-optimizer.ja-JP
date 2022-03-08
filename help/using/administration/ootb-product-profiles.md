---
title: ビルトインの製品プロファイル
description: ビルトインの製品プロファイルの詳細
feature: Access Management
topic: Administration
role: Admin
level: Intermediate
exl-id: 5a968bd8-cf76-4242-aa80-3cfb3d551511
source-git-commit: 7da910df3eda84884c7cda56af6ce5dcabc3a3db
workflow-type: tm+mt
source-wordcount: '797'
ht-degree: 77%

---

# ビルトインの製品プロファイル {#ootb-product-profiles}

## [!DNL Journey Administrator] {#journey-administrator}

**[!DNL Journey Administrator]** 製品プロファイルを使用すると、ジャーニー、メッセージおよび意思決定管理を管理および公開できる管理メニューが利用できます。

この製品プロファイルには、次の権限が含まれます：

|機能|権限|
|-|-|
|ジャーニー| <ul><li> **[!DNL Manage journeys]**：ジャーニーの読み取り、作成、編集、削除。</li><li>**[!DNL Publish journeys]**：ジャーニーの公開。</li><li>**[!DNL Manage journeys events, data sources and actions]**：イベント、ソース、アクションの読み取り、作成、編集、削除。</li><li>**[!DNL View journeys report]**：ジャーニーレポートの読み取り、編集。</li></ul>|
|メッセージ|<ul><li> **[!DNL Manage messages]**:メッセージおよびランディングページを読み取り、作成、編集し、テスト/配達確認を送信します。</li><li>**[!DNL Manage messages preview and test]**:メッセージ/ランディングページのプレビューを読み取り、作成、編集し、テスト/配達確認を送信します。</li><li>**[!DNL Publish messages]**:メッセージとランディングページを公開します。</li><li>**[!DNL View messages report]**:メッセージおよびランディングページレポートを読み取り、編集します。</li></ul>|
|管理|<ul><li>**[!DNL Manage subdomains delegation]**：サブドメインデリゲーションの読み取り、作成、編集、削除。</li><li>**[!DNL Manage IP pools]**：IP プールの読み取り、作成、編集、削除。</li><li>**[!DNL Manage PTR records]**：PTR レコードの読み取りと編集。</li><li>**[!DNL View PTR records]**：PTR レコードへの読み取り専用アクセス。</li><li> **[!DNL Manage messages general settings]**：メッセージの一般設定の読み取り、作成、編集、削除。</li><li>**[!DNL Manage messages presets]**：コンテンツのブランディングの読み取り、作成、編集、削除。</li><li>**[!DNL Manage suppression rules]**：抑制ルールの読み取り、作成、編集、削除へのアクセス。</li><li>**[!DNL View suppression list]**：ローカル抑制リストの読み取り、書き出し。</li><li>**[!DNL Manage alerts]**：ジャーニー、メッセージ、権限に関するアラートの有効化／無効化。</li><li>**[!DNL Manage landing page settings]**:ランディングページのサブドメインとプリセット設定を読み取り、作成および編集します。</li></ul>|
|意思決定管理|<ul><li>**[!DNL Manage decisions]**：決定の読み取り、作成、編集、削除。</li><li>**[!DNL Manage ranking strategies]**：カスタムメッセージレポートの読み取り、作成、編集、削除を行い、アクション機能を使用する。</li></ul>|
|Adobe Experience Platform|<ul><li>**[!DNL Sandbox]**：サンドボックスへのアクセスの許可。</li><li>**[!DNL Manage segments]**:セグメントおよび購読リストを読み取り、作成、編集および削除する。</li><li>**[!DNL Manage profiles]**：プロファイルの読み取り、作成、編集、削除。</li><li>**[!DNL Read datasets]**：データセットへの読み取り専用アクセス。</li><li>**[!DNL Read schemas]**：スキーマへの読み取り専用アクセス。</li><li>**[!DNL Read Identity namespace]**：ID 名前空間への読み取り専用アクセス。</li><li>**[!DNL Manage merge policies]**：結合ポリシーの読み取り、作成、編集、削除。</li></ul>|

## [!DNL Journey Approver] {#journey-approver}

**[!DNL Journey Approver]** 製品プロファイルを使用すると、ユーザーは配信を承認および公開できます。 後から **[!DNL Message]** や **[!DNL Journey]** レポートで配信の成功を確認できます。

この製品プロファイルには、次の権限が含まれます：

|機能|権限|
|-|-|
|ジャーニー| <ul><li>**[!DNL Manage journeys]**：ジャーニーの読み取り、作成、編集、削除。</li><li>**[!DNL Publish journey]**：ジャーニーの公開。</li><li>**[!DNL View journeys events, data sources and actions]**：ジャーニーイベント、ジャーニーカスタムアクション、ジャーニーデータソースへの読み取り専用アクセス。</li><li>**[!DNL View journeys report]**:ジャーニーレポートの読み取り、編集。</li></ul>|
|メッセージ| <ul><li>**[!DNL Manage messages]**:メッセージおよびランディングページを読み取り、作成、編集および削除します。</li><li>**[!DNL Publish messages]** メッセージとランディングページを公開します。</li><li>**[!DNL Manage messages preview and test]**:メッセージ/ランディングページのプレビューを読み取り、作成および編集し、テスト/配達確認を送信します。</li><li>**[!DNL View messages report]**:メッセージおよびランディングページレポートを読み取り、編集します。</li></ul>|
|意思決定管理| <ul><li>**[!DNL Manage decisions]**：決定エンティティの読み取り、作成、編集、削除を行う。</li><li>**[!DNL Manage ranking strategies]**：カスタムメッセージレポートの読み取り、作成、編集、削除を行い、アクション機能を使用する。</li></ul>| |Adobe Experience Platform| <ul><li>**[!DNL Manage segments]**:セグメントおよび購読リストを読み取り、作成、編集および削除する。</li><li>**[!DNL Manage profiles]**：プロファイルの読み取り、作成、編集、削除。</li><li>**[!DNL Read datasets]**：データセットへの読み取り専用アクセス。</li><li>**[!DNL Read schemas]**：スキーマへの読み取り専用アクセス</li><li>**[!DNL Manage merge policies]**：結合ポリシーの読み取り、作成、編集、削除。</li></ul>|
|管理| <ul><li>**[!DNL View messages presets]**：メッセージプリセットへの読み取り専用アクセス。</li></ul>|

## [!DNL Journey Manager] {#journey-manager}

**[!DNL Journey Manager]** 製品プロファイルを使用すると、ユーザーは&#x200B;**[!UICONTROL ジャーニー]**&#x200B;と、**[!UICONTROL ジャーニー]**&#x200B;にリンクされたすべての機能を作成および編集できますが、公開はできません。

この製品プロファイルには、次の権限が含まれます：

|機能|権限|
|-|-|
|ジャーニー| <ul><li>**[!DNL Manage journeys]**：ジャーニーの読み取り、作成、編集、削除。</li><li>**[!DNL View journeys events]**：ジャーニーイベント、ジャーニーカスタムアクション、ジャーニーデータソースへの読み取り専用アクセス。</li><li>**[!DNL View journeys report]**：ジャーニーレポートの読み取り、編集。</li></ul>|
|メッセージ| <ul><li>**[!DNL Manage messages]**:メッセージおよびランディングページを読み取り、作成、編集および削除します。</li><li> **[!DNL Manage messages preview and test]**:メッセージ/ランディングページのプレビューを読み取り、作成および編集し、テスト/配達確認を送信します。</li><li>**[!DNL View messages report]**:メッセージおよびランディングページレポートを読み取り、編集します。</li></ul>|
|意思決定管理| <ul><li>**[!DNL Manage decisions]**：決定エンティティの読み取り、作成、編集、削除を行う。</li><li>**[!DNL Manage ranking strategies]**：カスタムメッセージレポートの読み取り、作成、編集、削除を行い、アクション機能を使用する。</li></ul>| |Adobe Experience Platform| <ul><li> **[!DNL Manage segments]**:セグメントおよび購読リストを読み取り、作成、編集および削除する。</li><li>**[!DNL Manage profiles]**：プロファイルの読み取り、作成、編集、削除。</li><li>**[!DNL Read datasets]**：データセットへの読み取り専用アクセス。</li><li>**[!DNL Read schemas]**：スキーマへの読み取り専用アクセス</li><li>**[!DNL Manage merge policies]**：結合ポリシーの読み取り、作成、編集、削除。</li></ul>|
|管理| <ul><li>**[!DNL View messages presets]**：メッセージプリセットへの読み取り専用アクセス。</li></ul>|

## [!DNL Journey viewer] {#journey-viewer}

**[!DNL Journey viewer]** 製品プロファイルを使用すると、**[!UICONTROL ジャーニー]**、**[!UICONTROL 目標]**、**[!UICONTROL メッセージ]**&#x200B;および&#x200B;**[!UICONTROL 意思決定管理]**&#x200B;などの機能に読み取り専用でアクセスできます。

この製品プロファイルに割り当てられたユーザーは、編集または公開はできません。

この製品プロファイルには、次の権限が含まれます。

|機能|権限|
|-|-|
|ジャーニー| <ul><li>**[!DNL View journeys]**：ジャーニーへの読み取り専用アクセス。</li><li>**[!DNL View journeys event, data sources, actions]**：ジャーニーイベントおよびデータソースへの読み取り専用アクセス。</li><li>**[!DNL View journeys report]**：ジャーニーレポートへの読み取り専用アクセス。</li></ul>|
|メッセージ| <ul><li>**[!DNL View messages]**:メッセージおよびランディングページへの読み取り専用アクセス</li><li>**[!DNL View messages report]**:メッセージおよびランディングページレポートへの読み取り専用アクセス</li></ul>|
|意思決定管理| <ul><li>**[!DNL View decisions]**：決定エンティティへの読み取り専用アクセス。</li></ul>|

## [!DNL Message Manager] {#message-manager}

**[!DNL Message Manager]** 製品プロファイルを使用すると、ユーザーは&#x200B;**[!UICONTROL メッセージ]**&#x200B;と&#x200B;**[!UICONTROL 意思決定管理]**&#x200B;を作成および編集できますが、それらを公開することはできません。

この製品プロファイルには、次の権限が含まれます：

|機能|権限|
|-|-|
|ジャーニー| <ul><li>**[!DNL View journeys]**：ジャーニーへの読み取り専用アクセス。</li><li>**[!DNL View Journeys events, data sources and actions]**：ジャーニーイベント、ジャーニーカスタムアクション、ジャーニーデータソースへの読み取り専用アクセス。</li></ul>|
|メッセージ| <ul><li>**[!DNL Manage messages]**:メッセージおよびランディングページを読み取り、作成、編集および削除します。</li><li>**[!DNL Manage messages preview and test]**:メッセージ/ランディングページのプレビューを読み取り、作成および編集し、テスト/配達確認を送信します。</li><li> **[!DNL View messages report]**:メッセージおよびランディングページレポートを読み取り、編集します。</li></ul>|
|意思決定管理| <ul><li>**[!DNL Manage decisions]**：決定エンティティの読み取り、作成、編集、削除。</li></ul>| |Adobe Experience Platform| <ul><li>**[!DNL Read profiles]**：プレビューおよびテスト用のプロファイルの読み取り専用アクセス。</li><li>**[!DNL Read datasets]**：データセットへの読み取り専用アクセス。</li><li>**[!DNL Read schemas]**：スキーマへの読み取り専用アクセス</li><li>**[!DNL Manage merge policies]**：結合ポリシーの読み取り、作成、編集、削除。</li></ul>|
|管理| <ul><li>**[!DNL View messages presets]**：メッセージプリセットへの読み取り専用アクセス。</li></ul>|

## [!DNL Decisioning manager] {#decisioning-manager}

**[!DNL Decisioning manager]** 製品プロファイルでは、**[!UICONTROL 意思決定管理]**&#x200B;メニューのみが許可されます。この製品プロファイルに割り当てられたユーザーは、決定の管理、表示および公開のみを実行できます。

この製品プロファイルには、次の権限が含まれます。

|機能 |権限|
|-|-|
|意思決定管理| <ul><li>**[!DNL Manage decisions]**：決定エンティティの読み取り、作成、編集、削除。</li><li>**[!DNL View decisions]**：決定エンティティへの読み取り専用アクセス。</li><li>**[!DNL Manage ranking strategies]**：カスタムメッセージレポートの読み取り、作成、編集、削除を行い、アクション機能を使用する。</li><li>**[!DNL Publish decisions]**：決定アクティビティのアクティブ化または非アクティブ化。</li></ul>|
