---
title: 組み込みの製品プロファイル
description: 組み込みの製品プロファイルの詳細
feature: Control Groups
topic: Administration
role: Admin
level: Intermediate
exl-id: 5a968bd8-cf76-4242-aa80-3cfb3d551511
source-git-commit: bbeecbacb4838dfb0794d5625eb2774cf4b983ef
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# ビルトインの製品プロファイル {#ootb-product-profiles}

## [!DNL Journey Administrator] {#journey-administrator}

この **[!DNL Journey Administrator]** 製品プロファイルを使用すると、管理メニューで、メッセージ、メッセージおよび決定管理をジャーニーおよび公開できます。

この製品プロファイルには、次の権限が含まれます：

|機能|権限|
|-|-|
|ジャーニー| <ul><li> **[!DNL Manage journeys]**:ジャーニーの読み取り、作成、編集、削除を行います。</li><li>**[!DNL Publish journeys]**:ジャーニーを公開します。</li><li>**[!DNL Manage journeys events, data sources and actions]**:イベント、ソース、アクションの読み取り、作成、編集、削除</li><li>**[!DNL View journeys report]**:ジャーニーレポートを読み取り、編集します。</li></ul>|
|メッセージ|<ul><li> **[!DNL Manage messages]**:メッセージのプレビューを読み取り、作成、編集し、テスト/配達確認を送信します。</li><li>**[!DNL Manage messages preview and test]**:メッセージを公開します。</li><li>**[!DNL Publish messages]**:メッセージのプレビューを読み取り、作成および編集し、テスト/配達確認を送信します。</li><li>**[!DNL View messages report]**:メッセージレポートを読み取り、編集します。</li></ul>|
|管理|<ul><li>**[!DNL Manage subdomains delegation]**:サブドメインデリゲーションの読み取り、作成、編集および削除</li><li>**[!DNL Manage IP pools]**:ip プールを読み取り、作成、編集、削除します。</li><li>**[!DNL Manage PTR records]**:PTR レコードを読み取り、作成、編集、削除します。</li><li>**[!DNL View PTR records]**:PTR レコードへの読み取り専用アクセス</li><li> **[!DNL Manage messages general settings]**:メッセージの一般設定の読み取り、作成、編集、削除</li><li>**[!DNL Manage messages presets]**:コンテンツのブランディングを読み取り、作成、編集および削除します。</li><li>**[!DNL Manage suppression rules]**:抑制ルールの読み取り、作成、編集および削除にアクセスします。</li><li>**[!DNL View suppression list]**:ローカル抑制リストの読み取りと書き出しを行います。</li><li>**[!DNL Manage alerts]**:ジャーニー、メッセージ、権限に関するアラートを有効/無効にします。</li></ul>|
|意思決定管理|<ul><li>**[!DNL Manage decisions]**:決定の読み取り、作成、編集および削除</li><li>**[!DNL Manage ranking strategies]**:カスタムメッセージレポートの読み取り、作成、編集、削除、およびアクション機能の使用</li></ul>|
|Adobe Experience Platform|<ul><li>**[!DNL Sandbox]**:サンドボックスへのアクセス権を付与する。</li><li>**[!DNL Manage segments]**:セグメントの読み取り、作成、編集、削除</li><li>**[!DNL Manage profiles]**:プロファイルの読み取り、作成、編集、削除</li><li>**[!DNL Read datasets]**:データセットへの読み取り専用アクセス</li><li>**[!DNL Read schemas]**:スキーマへの読み取り専用アクセス</li><li>**[!DNL Read Identity namespace]**:id 名前空間への読み取り専用アクセス</li><li>**[!DNL Manage merge policies]**:結合ポリシーの読み取り、作成、編集、削除</li></ul>|

## [!DNL Journey Approver] {#journey-approver}

この **[!DNL Journey Approver]** 製品プロファイルを使用すると、ユーザーは配信を承認して公開できます。 後で、 **[!DNL Message]** および **[!DNL Journey]** レポート。

この製品プロファイルには、次の権限が含まれます：

|機能|権限|
|-|-|
|ジャーニー| <ul><li>**[!DNL Manage journeys]**:ジャーニーの読み取り、作成、編集、削除を行います。</li><li>**[!DNL Publish journey]**:ジャーニーを公開します。</li><li>**[!DNL View journeys events, data sources and actions]**:ジャーニーイベント、ジャーニーカスタムアクション、ジャーニーデータソースへの読み取り専用アクセス</li><li>**[!DNL View journeys report]**:ジャーニーレポートを読み取り、編集します。</li></ul>|
|メッセージ| <ul><li>**[!DNL Manage messages]**:メッセージの読み取り、作成、編集、削除を行います。</li><li>**[!DNL Publish messages]** メッセージを公開します。</li><li>**[!DNL Manage messages preview and test]**:メッセージのプレビューを読み取り、作成および編集し、テスト/配達確認を送信します。</li><li>**[!DNL View messages report]**:メッセージレポートの読み取り、作成、編集、削除を行います。</li></ul>|
|意思決定管理| <ul><li>**[!DNL Manage decisions]**:判定エンティティの読み取り、作成、編集、削除を行います。</li><li>**[!DNL Manage ranking strategies]**:カスタムメッセージレポートの読み取り、作成、編集、削除、およびアクション機能の使用</li></ul>| |Adobe Experience Platform| <ul><li>**[!DNL Manage segments]**:セグメントの読み取り、作成、編集、削除</li><li>**[!DNL Manage profiles]**:プロファイルの読み取り、作成、編集、削除</li><li>**[!DNL Read datasets]**:データセットへの読み取り専用アクセス</li><li>**[!DNL Read schemas]**:スキーマへの読み取り専用アクセス</li><li>**[!DNL Manage merge policies]**:結合ポリシーの読み取り、作成、編集、削除</li></ul>|
|管理| <ul><li>**[!DNL View messages presets]**:メッセージプリセットへの読み取り専用アクセス</li></ul>|

## [!DNL Journey Manager] {#journey-manager}

この **[!DNL Journey Manager]** 製品プロファイルを使用すると、ユーザーは **[!UICONTROL ジャーニー]** そしてリンクされたすべての能力 **[!UICONTROL ジャーニー]** ただし、公開できません。

この製品プロファイルには、次の権限が含まれます：

|機能|権限|
|-|-|
|ジャーニー| <ul><li>**[!DNL Manage journeys]**:ジャーニーの読み取り、作成、編集、削除を行います。</li><li>**[!DNL View journeys events]**:ジャーニーイベント、ジャーニーカスタムアクション、ジャーニーデータソースへの読み取り専用アクセス</li><li>**[!DNL View journeys report]**:ジャーニーレポートを読み取り、編集します。</li></ul>|
|メッセージ| <ul><li>**[!DNL Manage messages]**:メッセージの読み取り、作成、編集、削除を行います。</li><li> **[!DNL Manage messages preview and test]**:メッセージのプレビューを読み取り、作成および編集し、テスト/配達確認を送信します。</li><li>**[!DNL View messages report]**:メッセージレポートの読み取り、作成、編集、削除を行います。</li></ul>|
|意思決定管理| <ul><li>**[!DNL Manage decisions]**:判定エンティティの読み取り、作成、編集、削除を行います。</li><li>**[!DNL Manage ranking strategies]**:カスタムメッセージレポートの読み取り、作成、編集、削除、およびアクション機能の使用</li></ul>| |Adobe Experience Platform| <ul><li> **[!DNL Manage segments]**:セグメントの読み取り、作成、編集、削除</li><li>**[!DNL Manage profiles]**:プロファイルの読み取り、作成、編集、削除</li><li>**[!DNL Read datasets]**:データセットへの読み取り専用アクセス</li><li>**[!DNL Read schemas]**:スキーマへの読み取り専用アクセス</li><li>**[!DNL Manage merge policies]**:結合ポリシーの読み取り、作成、編集、削除</li></ul>|
|管理| <ul><li>**[!DNL View messages presets]**:メッセージプリセットへの読み取り専用アクセス</li></ul>|

## [!DNL Journey viewer] {#journey-viewer}

この **[!DNL Journey viewer]** 製品プロファイルを使用すると、 **[!UICONTROL ジャーニー]**, **[!UICONTROL 目標]**, **[!UICONTROL メッセージ]** および **[!UICONTROL 決定管理]** 機能

この製品プロファイルに割り当てられたユーザーは、編集または公開はできません。

この製品プロファイルには、次の権限が含まれます。

|機能|権限|
|-|-|
|ジャーニー| <ul><li>**[!DNL View journeys]**:ジャーニーへの読み取り専用アクセス</li><li>**[!DNL View journeys event, data sources, actions]**:ジャーニーイベントおよびデータソースへの読み取り専用アクセス</li><li>**[!DNL View journeys report]**:ジャーニーレポートへの読み取り専用アクセス</li></ul>|
|メッセージ| <ul><li>**[!DNL View messages]**:メッセージへの読み取り専用アクセス</li><li>**[!DNL View messages report]**:メッセージレポートへの読み取り専用アクセス</li></ul>|
|意思決定管理| <ul><li>**[!DNL View decisions]**:決定エンティティへの読み取り専用アクセス権。</li></ul>|

## [!DNL Message Manager] {#message-manager}

この **[!DNL Message Manager]** 製品プロファイルを使用すると、ユーザーは **[!UICONTROL メッセージ]** および **[!UICONTROL 決定管理]** ただし、公開できません。

この製品プロファイルには、次の権限が含まれます：

|機能|権限|
|-|-|
|ジャーニー| <ul><li>**[!DNL View journeys]**:ジャーニーへの読み取り専用アクセス</li><li>**[!DNL View Journeys events, data sources and actions]**:ジャーニーイベント、ジャーニーカスタムアクション、ジャーニーデータソースへの読み取り専用アクセス</li></ul>|
|メッセージ| <ul><li>**[!DNL Manage messages]**:メッセージの読み取り、作成、編集、削除を行います。</li><li>**[!DNL Manage messages preview and test]**:メッセージのプレビューを読み取り、作成および編集し、テスト/配達確認を送信します。</li><li> **[!DNL View messages report]**:メッセージレポートの読み取り、作成、編集、削除を行います。</li></ul>|
|意思決定管理| <ul><li>**[!DNL Manage decisions]**:判定エンティティの読み取り、作成、編集、削除を行います。</li></ul>| |Adobe Experience Platform| <ul><li>**[!DNL Read profiles]**:プレビューおよびテスト用のプロファイルへの読み取り専用アクセス</li><li>**[!DNL Read datasets]**:データセットへの読み取り専用アクセス</li><li>**[!DNL Read schemas]**:スキーマへの読み取り専用アクセス</li><li>**[!DNL Manage merge policies]**:結合ポリシーの読み取り、作成、編集、削除</li></ul>|
|管理| <ul><li>**[!DNL View messages presets]**:メッセージプリセットへの読み取り専用アクセス</li></ul>|

## [!DNL Decisioning manager] {#decisioning-manager}

この **[!DNL Decisioning manager]** 製品プロファイルで許可されるのは **[!UICONTROL 決定管理]** メニュー この製品プロファイルに割り当てられたユーザーは、決定の管理、表示および公開のみを実行できます。

この製品プロファイルには、次の権限が含まれます。

|機能 |権限|
|-|-|
|意思決定管理| <ul><li>**[!DNL Manage decisions]**:判定エンティティの読み取り、作成、編集、削除を行います。</li><li>**[!DNL View decisions]**:判定エンティティへの読み取り専用アクセス</li><li>**[!DNL Manage ranking strategies]**:カスタムメッセージレポートの読み取り、作成、編集、削除、およびアクション機能の使用</li><li>**[!DNL Publish decisions]**:判定アクティビティをアクティブ化または非アクティブ化する。</li></ul>|
