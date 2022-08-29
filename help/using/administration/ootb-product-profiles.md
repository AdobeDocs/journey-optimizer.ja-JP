---
title: ビルトインの製品プロファイル
description: ビルトインの製品プロファイルの詳細
feature: Access Management
topic: Administration
role: Admin
level: Intermediate
exl-id: 5a968bd8-cf76-4242-aa80-3cfb3d551511
source-git-commit: 3afef10461ce29b811cb20a2c8c4e94f452daf1f
workflow-type: tm+mt
source-wordcount: '1125'
ht-degree: 75%

---

# ビルトインの製品プロファイル {#ootb-product-profiles}


## メッセージに関連する権限について{#message-permissions}

Adobe Journey Optimizerは、新しいインラインオーサリング機能をリリースしました。この機能を使用すると、ジャーニーやキャンペーンから直接メッセージを作成し、オーサリングできます。 この新機能の詳細は、 [このページを参照してください。](../rn/inline-messages.md).

この機能は次の権限に影響を与えます。

| 権限の名前 | 上位の権限 |
|:-:|:-:|
| **[!DNL View Messages]** | **[!DNL View Journeys]** |
| **[!DNL View Message reports]** | **[!DNL View Journeys Report]** |
| **[!DNL Manage Messages]** | **[!DNL Manage Journey]** |
| **[!DNL Publish Messages]** | **[!DNL Publish Journeys]** |
| **[!DNL Manage Messages Preview and Test]** | **[!DNL Manage Journeys]** |

**7 月 25 日以降**、 **メッセージ** は引き続き使用可能です。これは、トランジションを有効にするためにメッセージにアクセスでき、テンプレートとして保存できるためです。

**9 月 6 日現在**、 **メッセージ** が削除され、メッセージにアクセスできなくなります。

>[!WARNING]
>
>ユーザーが **[!DNL Message Manager]** 製品プロファイルのみ（なし） **[!DNL Journey manager]** 製品プロファイルを編集する場合、コンテンツの編集を続行するには、新しい製品プロファイルを割り当てる必要があります。


## [!DNL Campaign Administrator] {#campaign-administrator}

この **[!DNL Campaign Administrator]** 製品プロファイルを使用すると、管理メニューでキャンペーンと決定管理を管理および公開できます。

この製品プロファイルには、次の権限が含まれます：

|機能 |権限| |-|-| |キャンペーン| <ul><li> **[!DNL Manage campaigns]**:キャンペーンの読み取り、作成、編集、削除を行います。</li><li>**[!DNL Publish campaigns]**:キャンペーンを公開します。</li><li>**[!DNL View campaigns report]**:キャンペーンレポートを読み取り、編集します。</li></ul>|
|管理|<ul><li>**[!DNL Manage subdomains delegation]**：サブドメインデリゲーションの読み取り、作成、編集、削除。</li><li>**[!DNL Manage IP pools]**：IP プールの読み取り、作成、編集、削除。</li><li>**[!DNL Manage PTR records]**：PTR レコードの読み取りと編集。</li><li>**[!DNL View PTR records]**：PTR レコードへの読み取り専用アクセス。</li><li> **[!DNL Manage messages general settings]**：メッセージの一般設定の読み取り、作成、編集、削除。</li><li>**[!DNL Manage messages presets]**：コンテンツのブランディングの読み取り、作成、編集、削除。</li><li>**[!DNL Manage suppression rules]**：抑制ルールの読み取り、作成、編集、削除へのアクセス。</li><li>**[!DNL Export suppression list]**:抑制リストを CSV ファイルとして書き出すためのアクセス権。</li><li>**[!DNL View suppression list]**：ローカル抑制リストの読み取り、書き出し。</li><li>**[!DNL Manage alerts]**:キャンペーン、メッセージおよび権利に関するアラートの有効化/無効化</li><li>**[!DNL Manage landing page settings]**:ランディングページの設定を読み取り、作成、編集、削除します。</li><li>**[!DNL Manage SMS settings]**:SMS 設定を読み取り、作成、編集および削除します。</li></ul>|
|意思決定管理|<ul><li>**[!DNL Manage decisions]**：決定の読み取り、作成、編集、削除。</li><li>**[!DNL Manage ranking strategies]**：ランキング戦略を読み取り、作成、編集および削除します。</li></ul>|
|Adobe Experience Platform|<ul><li>**[!DNL Sandbox]**：サンドボックスへのアクセスの許可。</li><li>**[!DNL Manage segments]**：セグメントの読み取り、作成、編集、削除。</li><li>**[!DNL Manage profiles]**：プロファイルの読み取り、作成、編集、削除。</li><li>**[!DNL Read datasets]**：データセットへの読み取り専用アクセス。</li><li>**[!DNL Read schemas]**：スキーマへの読み取り専用アクセス。</li><li>**[!DNL Read Identity namespace]**：ID 名前空間への読み取り専用アクセス。</li><li>**[!DNL Manage merge policies]**：結合ポリシーの読み取り、作成、編集、削除。</li></ul>|

## [!DNL Campaign Approver] {#campaign-approver}

**[!DNL Campaign Approver]** 製品プロファイルを使用すると、ユーザーは配信を承認および公開できます。後から **[!DNL Campaigns]** レポートで配信の成功を確認できます。

|機能 |権限| |-|-| |キャンペーン| <ul><li>**[!DNL Manage campaigns]**:キャンペーンの読み取り、作成、編集、削除を行います。</li><li>**[!DNL Publish campaigns]**:キャンペーンを公開します。</li><li>**[!DNL View Campaigns report]**:ジャーニーレポートの読み取り、編集。</li></ul>|
|意思決定管理| <ul><li>**[!DNL Manage decisions]**：決定エンティティの読み取り、作成、編集、削除を行う。</li><li>**[!DNL Manage ranking strategies]**：カスタムメッセージレポートの読み取り、作成、編集、削除を行い、アクション機能を使用する。</li></ul>| |Adobe Experience Platform| <ul><li>**[!DNL Manage segments]**：セグメントの読み取り、作成、編集、削除。</li><li>**[!DNL Manage profiles]**：プロファイルの読み取り、作成、編集、削除。</li><li>**[!DNL Read datasets]**：データセットへの読み取り専用アクセス。</li><li>**[!DNL Read schemas]**：スキーマへの読み取り専用アクセス</li><li>**[!DNL Manage merge policies]**：結合ポリシーの読み取り、作成、編集、削除。</li></ul>|
|管理| <ul><li>**[!DNL View messages presets]**：メッセージプリセットへの読み取り専用アクセス。</li></ul>|

## [!DNL Campaign Manager] {#campaign-manager}

この **[!DNL Campaign Manager]** 製品プロファイルを使用すると、ユーザーは **[!UICONTROL キャンペーン]** そしてリンクされたすべての能力 **[!UICONTROL キャンペーン]** ただし、公開できません。

この製品プロファイルには、次の権限が含まれます：

|機能 |権限| |-|-| |キャンペーン| <ul><li>**[!DNL Manage campaigns]**:キャンペーンの読み取り、作成、編集、削除を行います。</li><li>**[!DNL View campaigns report]**：ジャーニーレポートの読み取り、編集。</li></ul>|
|意思決定管理| <ul><li>**[!DNL Manage decisions]**：決定エンティティの読み取り、作成、編集、削除を行う。</li><li>**[!DNL Manage ranking strategies]**：カスタムメッセージレポートの読み取り、作成、編集、削除を行い、アクション機能を使用する。</li></ul>| |Adobe Experience Platform| <ul><li> **[!DNL Manage segments]**：セグメントの読み取り、作成、編集、削除。</li><li>**[!DNL Manage profiles]**：プロファイルの読み取り、作成、編集、削除。</li><li>**[!DNL Read datasets]**：データセットへの読み取り専用アクセス。</li><li>**[!DNL Read schemas]**：スキーマへの読み取り専用アクセス</li><li>**[!DNL Manage merge policies]**：結合ポリシーの読み取り、作成、編集、削除。</li></ul>|
|管理| <ul><li>**[!DNL View messages presets]**：メッセージプリセットへの読み取り専用アクセス。</li></ul>|

## [!DNL Campaign Viewer] {#campaign-viewer}

この **[!DNL Campaign Viewer]** 製品プロファイルを使用すると、 **[!UICONTROL キャンペーン]** および **[!UICONTROL 決定管理]** 機能

この製品プロファイルに割り当てられたユーザーは、編集または公開はできません。

この製品プロファイルには、次の権限が含まれます。

|機能 |権限| |-|-| |キャンペーン| <ul><li>**[!DNL View campaigns]**:キャンペーンへの読み取り専用アクセス</li><li>**[!DNL View campaigns report]**:キャンペーンレポートへの読み取り専用アクセス</li></ul>|
|意思決定管理| <ul><li>**[!DNL View decisions]**：決定エンティティへの読み取り専用アクセス。</li></ul>|

## [!DNL Journey Administrator] {#journey-administrator}

**[!DNL Journey Administrator]** 製品プロファイルを使用すると、管理メニューでジャーニーおよび意思決定管理を管理および公開できます。

この製品プロファイルには、次の権限が含まれます：

|機能|権限|
|-|-|
|ジャーニー| <ul><li> **[!DNL Manage journeys]**：ジャーニーの読み取り、作成、編集、削除。</li><li>**[!DNL Publish journeys]**：ジャーニーの公開。</li><li>**[!DNL Manage journeys events, data sources and actions]**：イベント、ソース、アクションの読み取り、作成、編集、削除。</li><li>**[!DNL View journeys report]**：ジャーニーレポートの読み取り、編集。</li></ul>|
|管理|<ul><li>**[!DNL Manage subdomains delegation]**：サブドメインデリゲーションの読み取り、作成、編集、削除。</li><li>**[!DNL Manage IP pools]**：IP プールの読み取り、作成、編集、削除。</li><li>**[!DNL Manage PTR records]**：PTR レコードの読み取りと編集。</li><li>**[!DNL View PTR records]**：PTR レコードへの読み取り専用アクセス。</li><li>**[!DNL Manage channel surfaces]**：コンテンツのブランディングの読み取り、作成、編集、削除。</li><li>**[!DNL Manage Landing page settings]**:ランディングページのサブドメインとランディングページのプリセットを作成、編集および削除します。</li><li> **[!DNL Manage messages general settings]**：メッセージの一般設定の読み取り、作成、編集、削除。</li><li>**[!DNL Manage SMS settings]**:SMS チャネルを有効にするために必要な API 資格情報と SMS チャネル面を作成、編集および削除します。</li><li>**[!DNL Manage suppression rules]**：抑制ルールの読み取り、作成、編集、削除へのアクセス。</li><li>**[!DNL View suppression list]**：ローカル抑制リストの読み取り、書き出し。</li><li>**[!DNL Manage alerts]**：ジャーニーおよび使用権限に関するアラートの有効化／無効化。</li></ul>|
|意思決定管理|<ul><li>**[!DNL Manage decisions]**：決定の読み取り、作成、編集、削除。</li><li>**[!DNL Manage ranking strategies]**：ランキング戦略を読み取り、作成、編集および削除します。</li></ul>| |Adobe Experience Platform|<ul><li>**[!DNL Sandbox]**：サンドボックスへのアクセスの許可。</li><li>**[!DNL Manage segments]**：セグメントの読み取り、作成、編集、削除。</li><li>**[!DNL Manage profiles]**：プロファイルの読み取り、作成、編集、削除。</li><li>**[!DNL Read datasets]**：データセットへの読み取り専用アクセス。</li><li>**[!DNL Read schemas]**：スキーマへの読み取り専用アクセス。</li><li>**[!DNL Read Identity namespace]**：ID 名前空間への読み取り専用アクセス。</li><li>**[!DNL Manage merge policies]**：結合ポリシーの読み取り、作成、編集、削除。</li></ul>| |Journey Optimizer ライブラリ|<ul><li>**[!DNL Manage Library Items]**：[!DNL Journey Optimizer] ライブラリ内の保存済み式の追加、削除。</li></ul>|

## [!DNL Journey Approver] {#journey-approver}

**[!DNL Journey Approver]** 製品プロファイルを使用すると、ユーザーは配信を承認および公開できます。後から **[!DNL Journey]** レポートで配信の成功を確認できます。

この製品プロファイルには、次の権限が含まれます：

|機能|権限|
|-|-|
|ジャーニー| <ul><li>**[!DNL Manage journeys]**：ジャーニーの読み取り、作成、編集、削除。</li><li>**[!DNL Publish journey]**：ジャーニーの公開。</li><li>**[!DNL View journeys events, data sources and actions]**：ジャーニーイベント、ジャーニーカスタムアクション、ジャーニーデータソースへの読み取り専用アクセス。</li><li>**[!DNL View journeys report]**:ジャーニーレポートの読み取り、編集。</li></ul>|
|意思決定管理| <ul><li>**[!DNL Manage decisions]**：決定エンティティの読み取り、作成、編集、削除を行う。</li><li>**[!DNL Manage ranking strategies]**：カスタムレポートの読み取り、作成、編集および削除、アクション機能の使用。</li></ul>| |Adobe Experience Platform| <ul><li>**[!DNL Manage segments]**：セグメントの読み取り、作成、編集、削除。</li><li>**[!DNL Manage profiles]**：プロファイルの読み取り、作成、編集、削除。</li><li>**[!DNL Read datasets]**：データセットへの読み取り専用アクセス。</li><li>**[!DNL Read schemas]**：スキーマへの読み取り専用アクセス</li><li>**[!DNL Manage merge policies]**：結合ポリシーの読み取り、作成、編集、削除。</li></ul>|
|管理| <ul><li>**[!DNL View channel surfaces]**：チャネルサーフェスへの読み取り専用アクセス。</li></ul>|

## [!DNL Journey Manager] {#journey-manager}

**[!DNL Journey Manager]** 製品プロファイルを使用すると、ユーザーは&#x200B;**[!UICONTROL ジャーニー]**&#x200B;と、**[!UICONTROL ジャーニー]**&#x200B;にリンクされたすべての機能を作成および編集できますが、公開はできません。

この製品プロファイルには、次の権限が含まれます：

|機能|権限|
|-|-|
|ジャーニー| <ul><li>**[!DNL Manage journeys]**：ジャーニーの読み取り、作成、編集、削除。</li><li>**[!DNL View journeys events]**：ジャーニーイベント、ジャーニーカスタムアクション、ジャーニーデータソースへの読み取り専用アクセス。</li><li>**[!DNL View journeys report]**：ジャーニーレポートの読み取り、編集。</li></ul>|
|意思決定管理| <ul><li>**[!DNL Manage decisions]**：決定エンティティの読み取り、作成、編集、削除を行う。</li><li>**[!DNL Manage ranking strategies]**：カスタムレポートの読み取り、作成、編集および削除、アクション機能の使用。</li></ul>| |Adobe Experience Platform| <ul><li> **[!DNL Manage segments]**：セグメントの読み取り、作成、編集、削除。</li><li>**[!DNL Manage profiles]**：プロファイルの読み取り、作成、編集、削除。</li><li>**[!DNL Read datasets]**：データセットへの読み取り専用アクセス。</li><li>**[!DNL Read schemas]**：スキーマへの読み取り専用アクセス</li><li>**[!DNL Manage merge policies]**：結合ポリシーの読み取り、作成、編集、削除。</li></ul>|
|管理| <ul><li>**[!DNL View channel surfaces]**：チャネルサーフェスへの読み取り専用アクセス。</li></ul>|

## [!DNL Journey Viewer] {#journey-viewer}

**[!DNL Journey viewer]** 製品プロファイルを使用すると、**[!UICONTROL ジャーニー]**&#x200B;および&#x200B;**[!UICONTROL 意思決定管理]**&#x200B;などの機能に読み取り専用でアクセスできます。

この製品プロファイルに割り当てられたユーザーは、編集または公開はできません。

この製品プロファイルには、次の権限が含まれます。

|機能|権限|
|-|-|
|ジャーニー| <ul><li>**[!DNL View journeys]**：ジャーニーへの読み取り専用アクセス。</li><li>**[!DNL View journeys event, data sources, actions]**：ジャーニーイベントおよびデータソースへの読み取り専用アクセス。</li><li>**[!DNL View journeys report]**：ジャーニーレポートへの読み取り専用アクセス。</li></ul>|
|意思決定管理| <ul><li>**[!DNL View decisions]**：決定エンティティへの読み取り専用アクセス。</li></ul>|

## [!DNL Decisioning manager] {#decisioning-manager}

**[!DNL Decisioning manager]** 製品プロファイルでは、**[!UICONTROL 意思決定管理]**&#x200B;メニューのみが許可されます。この製品プロファイルに割り当てられたユーザーは、決定の管理、表示および公開のみを実行できます。

この製品プロファイルには、次の権限が含まれます。

|機能 |権限|
|-|-|
|意思決定管理| <ul><li>**[!DNL Manage decisions]**：決定エンティティの読み取り、作成、編集、削除。</li><li>**[!DNL View decisions]**：決定エンティティへの読み取り専用アクセス。</li><li>**[!DNL Manage ranking strategies]**：カスタムレポートの読み取り、作成、編集および削除、アクション機能の使用。</li><li>**[!DNL Publish decisions]**：決定アクティビティのアクティブ化または非アクティブ化。</li></ul>|
