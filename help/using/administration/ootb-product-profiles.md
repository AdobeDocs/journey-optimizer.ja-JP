---
solution: Journey Optimizer
product: journey optimizer
title: 製品に組み込まれているプロファイル
description: 組み込み製品プロファイルについて
feature: Access Management
topic: Administration
role: Admin
level: Intermediate
exl-id: 5a968bd8-cf76-4242-aa80-3cfb3d551511
source-git-commit: d17e64e03d093a8a459caef2fb0197a5710dfb7d
workflow-type: tm+mt
source-wordcount: '1104'
ht-degree: 0%

---

# 製品に組み込まれているプロファイル {#ootb-product-profiles}


## メッセージに関連する権限について{#message-permissions}

Adobe の旅オプティマイザーにより、新しいインラインオーサリング機能がリリースされました。この機能を使用すると、旅またはキャンペーンから直接メッセージを作成して作成することができます。

この機能により、次のようにアクセス許可が影響を受けます。

| 権限の名前 | に追加されます。 |
|:-:|:-:|
| **[!DNL View Messages]** | **[!DNL View Journeys]** |
| **[!DNL View Message reports]** | **[!DNL View Journeys Report]** |
| **[!DNL Manage Messages]** | **[!DNL Manage Journey]** |
| **[!DNL Publish Messages]** | **[!DNL Publish Journeys]** |
| **[!DNL Manage Messages Preview and Test]** | **[!DNL Manage Journeys]** |

**7月 25** 日以降、メッセージに **** アクセスしてトランジションを有効にすることができます。また、それをテンプレートとして保存することもできます。

**9月 6** 日の間、メッセージ **に関連する権限が削除され、メッセージに** アクセスできなくなりました。

>[!WARNING]
>
>ユーザーが製品プロファイルに **[!DNL Message Manager]** 割り当てられている場合のみ、そのユーザーが製品プロファイルを使用 **[!DNL Journey manager]** してコンテンツの編集を続行できるようにするには、新しい製品プロファイルを割り当てる必要があります。


## [!DNL Campaign Administrator] {#campaign-administrator}

**[!DNL Campaign Administrator]**&#x200B;製品プロファイルを使用すると、管理メニューに、キャンペーンや意思決定管理を管理および公開することができます。

この製品プロファイルには、次の権限が含まれています。

|機能 |権限 |
|-|-|
|キャンペーン | <ul><li> **[!DNL Manage campaigns]**: キャンペーンの読み取り、作成、編集および削除を行います。</li><li>**[!DNL Publish campaigns]**: キャンペーンをパブリッシュします。</li><li>**[!DNL View campaigns report]**: キャンペーンレポートの表示と編集を参照してください。</li></ul>|
|管理 |<ul><li>**[!DNL Manage subdomains delegation]**: サブドメイン委任の読み取り、作成、編集および削除を行います。</li><li>**[!DNL Manage IP pools]**: ip プールの読み取り、作成、編集および削除を行います。</li><li>**[!DNL Manage PTR records]**: PTR レコードの読み取りと編集を行います。</li><li>**[!DNL View PTR records]**: PTR レコードには読み取り専用のアクセスが許可されています。</li><li> **[!DNL Manage messages general settings]**: メッセージ全般設定の読み取り、作成、編集および削除を行います。</li><li>**[!DNL Manage messages presets]**: コンテンツのブランディングの読み取り、作成、編集および削除を行います。</li><li>**[!DNL Manage suppression rules]**: 抑制ルールの読み取り、作成、編集および削除を行います。</li><li>**[!DNL Export suppression list]**: CSV ファイルとして書き出し抑制リストにアクセスします。</li><li>**[!DNL View suppression list]**: 局所抑制リストの読み取りと書き出しを行います。</li><li>**[!DNL Manage alerts]**: キャンペーン、メッセージ、権限に関するアラートの有効化と無効化を行います。</li><li>**[!DNL Manage landing page settings]**: ランディングページの設定を読み取り、作成、編集、削除します。</li><li>**[!DNL Manage SMS settings]**「SMS 設定の読み取り、作成、編集および削除」を参照してください。</li></ul>|
|意思決定管理 |<ul><li>**[!DNL Manage decisions]**: 決定の読み取り、作成、編集、および削除を行います。</li><li>**[!DNL Manage ranking strategies]**: ランク付けストラテジの読み取り、作成、編集および削除を行います。</li></ul>|
|Adobe エクスペリエンス Platform |<ul><li>**[!DNL Sandbox]**: サンドボックスへのアクセスを許可します。</li><li>**[!DNL Manage segments]**「セグメントの読み取り、作成、編集および削除」を参照してください。</li><li>**[!DNL Manage profiles]**: プロファイルの読み取り、作成、編集および削除を行います。</li><li>**[!DNL Read datasets]**: 読み取り専用のデータセットへのアクセスを許可します。</li><li>**[!DNL Read schemas]**: スキーマに読み取り専用でアクセスします。</li><li>**[!DNL Read Identity namespace]**: アイデンティティ名前空間への読み取り専用アクセス。</li><li>**[!DNL Manage merge policies]**: マージポリシーの読み取り、作成、編集および削除を行います。</li></ul>|

## [!DNL Campaign Approver] {#campaign-approver}

製品プロファイルを使用すると、 **[!DNL Campaign Approver]** ユーザーは配信を承認してパブリッシュすることができます。 これにより、後でレポートを使用して **[!DNL Campaigns]** 配信が成功したかどうかを確認することができます。

|機能 |権限 |
|-|-|
|キャンペーン | <ul><li>**[!DNL Manage campaigns]**: キャンペーンの読み取り、作成、編集および削除を行います。</li><li>**[!DNL Publish campaigns]**: キャンペーンをパブリッシュします。</li><li>**[!DNL View Campaigns report]**: 「先読みレポートの編集」を参照してください。</li></ul>|
|意思決定管理 | <ul><li>**[!DNL Manage decisions]**: decisioning エンティティの読み取り、作成、編集および削除を行います。</li><li>**[!DNL Manage ranking strategies]**: カスタムメッセージの読み取り、作成、編集、および削除レポートを使用して、操作の機能を使用します。</li></ul>|
|Adobe エクスペリエンス Platform | <ul><li>**[!DNL Manage segments]**「セグメントの読み取り、作成、編集および削除」を参照してください。</li><li>**[!DNL Manage profiles]**: プロファイルの読み取り、作成、編集および削除を行います。</li><li>**[!DNL Read datasets]**: 読み取り専用のデータセットへのアクセスを許可します。</li><li>**[!DNL Read schemas]**: スキーマに読み取り専用でアクセスします。</li><li>**[!DNL Manage merge policies]**: マージポリシーの読み取り、作成、編集および削除を行います。</li></ul>|
|管理 | <ul><li>**[!DNL View messages presets]**: メッセージプリセットには読み取り専用のアクセスを許可します。</li></ul>|

## [!DNL Campaign Manager] {#campaign-manager}

ユーザーは製品プロファイルを使用して、に **[!UICONTROL Campaigns]** リンクされた **[!DNL Campaign Manager]** すべての機能を作成および編集 **[!UICONTROL Campaigns]** できますが、パブリッシュすることはできません。

この製品プロファイルには、次の権限が含まれています。

|機能 |権限 |
|-|-|
|キャンペーン | <ul><li>**[!DNL Manage campaigns]**: キャンペーンの読み取り、作成、編集および削除を行います。</li><li>**[!DNL View campaigns report]**: 「旅レポートの編集」を参照してください。</li></ul>|
|意思決定管理 | <ul><li>**[!DNL Manage decisions]**: decisioning エンティティの読み取り、作成、編集および削除を行います。</li><li>**[!DNL Manage ranking strategies]**: カスタムメッセージの読み取り、作成、編集、および削除レポートを使用して、操作の機能を使用します。</li></ul>|
|Adobe エクスペリエンス Platform | <ul><li> **[!DNL Manage segments]**「セグメントの読み取り、作成、編集および削除」を参照してください。</li><li>**[!DNL Manage profiles]**: プロファイルの読み取り、作成、編集および削除を行います。</li><li>**[!DNL Read datasets]**: 読み取り専用のデータセットへのアクセスを許可します。</li><li>**[!DNL Read schemas]**: スキーマに読み取り専用でアクセスします。</li><li>**[!DNL Manage merge policies]**: マージポリシーの読み取り、作成、編集および削除を行います。</li></ul>|
|管理 | <ul><li>**[!DNL View messages presets]**: メッセージプリセットには読み取り専用のアクセスを許可します。</li></ul>|

## [!DNL Campaign Viewer] {#campaign-viewer}

**[!DNL Campaign Viewer]**&#x200B;製品プロファイルには、および **[!UICONTROL Decision management]** 機能への **[!UICONTROL Campaigns]** 読み取り専用アクセスが許可されています。

この製品プロファイルに割り当てられているユーザーは、編集またはパブリッシュすることはできません。

この製品プロファイルには、次の権限が含まれています。

|機能 |権限 |
|-|-|
|キャンペーン | <ul><li>**[!DNL View campaigns]**: キャンペーンへの読み取り専用のアクセスを許可します。</li><li>**[!DNL View campaigns report]**: キャンペーンレポートへの読み取り専用アクセス。</li></ul>|
|意思決定管理 | <ul><li>**[!DNL View decisions]**: 意思決定エンティティへの読み取り専用アクセス。</li></ul>|

## [!DNL Journey Administrator] {#journey-administrator}

**[!DNL Journey Administrator]**&#x200B;製品プロファイルを使用すると、管理メニューに Journeys と意思決定管理を管理してパブリッシュすることができます。

この製品プロファイルには、次の権限が含まれています。

|機能 |権限 |
|-|-|
|Journeys | <ul><li> **[!DNL Manage journeys]**: 読み取り、作成、編集、および削除の journeys を参照してください。</li><li>**[!DNL Publish journeys]**: journeys をパブリッシュします。</li><li>**[!DNL Manage journeys events, data sources and actions]**: イベント、ソースまたはアクションの読み取り、作成、編集および削除を行います。</li><li>**[!DNL View journeys report]**: journeys レポートの読み取りと編集を行います。</li></ul>|
|管理 |<ul><li>**[!DNL Manage subdomains delegation]**: サブドメイン委任の読み取り、作成、編集および削除を行います。</li><li>**[!DNL Manage IP pools]**: ip プールの読み取り、作成、編集および削除を行います。</li><li>**[!DNL Manage PTR records]**: PTR レコードの読み取りと編集を行います。</li><li>**[!DNL View PTR records]**: PTR レコードには読み取り専用のアクセスが許可されています。</li><li>**[!DNL Manage channel surfaces]**: コンテンツのブランディングの読み取り、作成、編集および削除を行います。</li><li>**[!DNL Manage Landing page settings]**: ランディングページのサブドメインとランディングページのプリセットを作成、編集、削除します。</li><li> **[!DNL Manage messages general settings]**: メッセージ全般設定の読み取り、作成、編集および削除を行います。</li><li>**[!DNL Manage SMS settings]**: SMS チャネルを有効にするために必要な API 資格情報と SMS チャンネルサーフェスを作成、編集、削除します。</li><li>**[!DNL Manage suppression rules]**: 抑制ルールの読み取り、作成、編集および削除を行います。</li><li>**[!DNL View suppression list]**: 局所抑制リストの読み取りと書き出しを行います。</li><li>**[!DNL Manage alerts]**: journeys および権限についてのアラートを有効または無効にします。</li></ul>|
|意思決定管理 |<ul><li>**[!DNL Manage decisions]**: 決定の読み取り、作成、編集、および削除を行います。</li><li>**[!DNL Manage ranking strategies]**: ランク付けストラテジの読み取り、作成、編集および削除を行います。</li></ul>|
|Adobe エクスペリエンス Platform |<ul><li>**[!DNL Sandbox]**: サンドボックスへのアクセスを許可します。</li><li>**[!DNL Manage segments]**「セグメントの読み取り、作成、編集および削除」を参照してください。</li><li>**[!DNL Manage profiles]**: プロファイルの読み取り、作成、編集および削除を行います。</li><li>**[!DNL Read datasets]**: 読み取り専用のデータセットへのアクセスを許可します。</li><li>**[!DNL Read schemas]**: スキーマに読み取り専用でアクセスします。</li><li>**[!DNL Read Identity namespace]**: アイデンティティ名前空間への読み取り専用アクセス。</li><li>**[!DNL Manage merge policies]**: マージポリシーの読み取り、作成、編集および削除を行います。</li></ul>|
|旅のオプティマイザーライブラリ |<ul><li>**[!DNL Manage Library Items]**: ライブラリに [!DNL Journey Optimizer] 保存されたエクスプレッションを追加および削除します。</li></ul>|

## [!DNL Journey Approver] {#journey-approver}

製品プロファイルを使用すると、 **[!DNL Journey Approver]** ユーザーは配信を承認してパブリッシュすることができます。 これにより、後でレポートを使用して **[!DNL Journey]** 配信が成功したかどうかを確認することができます。

この製品プロファイルには、次の権限が含まれています。

|機能 |権限 |
|-|-|
|Journeys | <ul><li>**[!DNL Manage journeys]**: 読み取り、作成、編集、および削除の journeys を参照してください。</li><li>**[!DNL Publish journey]**: journeys をパブリッシュします。</li><li>**[!DNL View journeys events, data sources and actions]**: 旅イベントに対する読み取り専用アクセス、カスタムアクションおよび旅データソースソース</li><li>**[!DNL View journeys report]**: 「先読みレポートの編集」を参照してください。</li></ul>|
|意思決定管理 | <ul><li>**[!DNL Manage decisions]**: decisioning エンティティの読み取り、作成、編集および削除を行います。</li><li>**[!DNL Manage ranking strategies]**: カスタムレポートの読み取り、作成、編集および削除、およびアクション機能の使用を行います。</li></ul>|
|Adobe エクスペリエンス Platform | <ul><li>**[!DNL Manage segments]**「セグメントの読み取り、作成、編集および削除」を参照してください。</li><li>**[!DNL Manage profiles]**: プロファイルの読み取り、作成、編集および削除を行います。</li><li>**[!DNL Read datasets]**: 読み取り専用のデータセットへのアクセスを許可します。</li><li>**[!DNL Read schemas]**: スキーマに読み取り専用でアクセスします。</li><li>**[!DNL Manage merge policies]**: マージポリシーの読み取り、作成、編集および削除を行います。</li></ul>|
|管理 | <ul><li>**[!DNL View channel surfaces]**: チャンネルサーフェスへの読み取り専用アクセス。</li></ul>|

## [!DNL Journey Manager] {#journey-manager}

ユーザーは製品プロファイルを使用して、に **[!UICONTROL Journeys]** リンクされた **[!DNL Journey Manager]** すべての機能を作成および編集 **[!UICONTROL Journeys]** できますが、パブリッシュすることはできません。

この製品プロファイルには、次の権限が含まれています。

|機能 |権限 |
|-|-|
|Journeys | <ul><li>**[!DNL Manage journeys]**: 読み取り、作成、編集、および削除の journeys を参照してください。</li><li>**[!DNL View journeys events]**: 旅イベントに対する読み取り専用アクセス、カスタムアクションおよび旅データソースソース</li><li>**[!DNL View journeys report]**: 「旅レポートの編集」を参照してください。</li></ul>|
|意思決定管理 | <ul><li>**[!DNL Manage decisions]**: decisioning エンティティの読み取り、作成、編集および削除を行います。</li><li>**[!DNL Manage ranking strategies]**: カスタムレポートの読み取り、作成、編集および削除、およびアクション機能の使用を行います。</li></ul>|
|Adobe エクスペリエンス Platform | <ul><li> **[!DNL Manage segments]**「セグメントの読み取り、作成、編集および削除」を参照してください。</li><li>**[!DNL Manage profiles]**: プロファイルの読み取り、作成、編集および削除を行います。</li><li>**[!DNL Read datasets]**: 読み取り専用のデータセットへのアクセスを許可します。</li><li>**[!DNL Read schemas]**: スキーマに読み取り専用でアクセスします。</li><li>**[!DNL Manage merge policies]**: マージポリシーの読み取り、作成、編集および削除を行います。</li></ul>|
|管理 | <ul><li>**[!DNL View channel surfaces]**: チャンネルサーフェスへの読み取り専用アクセス。</li></ul>|

## [!DNL Journey Viewer] {#journey-viewer}

**[!DNL Journey viewer]**&#x200B;製品プロファイルには、および **[!UICONTROL Decision management]** 機能への **[!UICONTROL Journeys]** 読み取り専用アクセスが許可されています。

この製品プロファイルに割り当てられているユーザーは、編集またはパブリッシュすることはできません。

この製品プロファイルには、次の権限が含まれています。

|機能 |権限 |
|-|-|
|Journeys | <ul><li>**[!DNL View journeys]**: journeys には読み取り専用のアクセスが許可されています。</li><li>**[!DNL View journeys event, data sources, actions]**: journeys イベントおよびデータソースへの読み取り専用のアクセスを許可します。</li><li>**[!DNL View journeys report]**: journeys レポートには読み取り専用のアクセスが許可されています。</li></ul>|
|意思決定管理 | <ul><li>**[!DNL View decisions]**: 意思決定エンティティへの読み取り専用アクセス。</li></ul>|

## [!DNL Decisioning manager] {#decisioning-manager}

**[!DNL Decisioning manager]**&#x200B;製品プロファイルではメニューのみが **[!UICONTROL Decision management]** 表示されます。この製品プロファイルに割り当てられているユーザーは、決定の管理、表示および公開のみを行うことができます。

この製品プロファイルには、次の権限が含まれています。

|機能 |権限 |
|-|-|
|意思決定管理 | <ul><li>**[!DNL Manage decisions]**: decisioning エンティティの読み取り、作成、編集および削除を行います。</li><li>**[!DNL View decisions]**: decisioning エンティティへの読み取り専用のアクセスを許可します。</li><li>**[!DNL Manage ranking strategies]**: カスタムレポートの読み取り、作成、編集および削除、およびアクション機能の使用を行います。</li><li>**[!DNL Publish decisions]**: decisioning アクティビティをアクティブまたは非アクティブにします。</li></ul>|
