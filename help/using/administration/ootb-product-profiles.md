---
solution: Journey Optimizer
product: journey optimizer
title: Journey Optimizer 組み込みの役割
description: 組み込みの役割の詳細情報
feature: Access Management
topic: Administration
role: Admin, User
level: Intermediate
keywords: 権限, オーサリング, メッセージ
exl-id: 5a968bd8-cf76-4242-aa80-3cfb3d551511
source-git-commit: b9208544b08b474db386cce3d4fab0a4429a5f54
workflow-type: tm+mt
source-wordcount: '1175'
ht-degree: 97%

---

# 組み込みの役割 {#ootb-product-profiles}

組み込みの役割は、ユーザーがインターフェイス内の特定の機能やオブジェクトにアクセスできるようにするための、一連の単一権限です。役割を構築するために利用可能な権限のリストについては、[このページ](ootb-permissions.md)を参照してください。

## [!DNL Campaign Administrator] {#campaign-administrator}

**[!DNL Campaign Administrator]** の役割を使用すると、管理メニューでキャンペーンおよび意思決定管理を管理および公開できます。

この役割には、次の権限が含まれます。

| リソース | 権限 |
|-|-|
| キャンペーン | <ul><li> **[!DNL Manage campaigns]**：キャンペーンの読み取り、作成、編集、削除。</li><li>**[!DNL Publish campaigns]**：キャンペーンの公開。</li><li>**[!DNL View campaigns report]**：キャンペーンレポートの読み取りおよび編集。</li></ul> |
| チャネル設定 | <ul><li>**[!DNL Manage subdomains delegation]**：サブドメインデリゲーションの読み取り、作成、編集、削除。</li><li>**[!DNL Manage IP pools]**：IP プールの読み取り、作成、編集、削除。</li><li>**[!DNL Manage PTR records]**：PTR レコードの読み取りと編集。</li><li>**[!DNL View PTR records]**：PTR レコードへの読み取り専用アクセス。</li><li> **[!DNL Manage messages general settings]**：メッセージの一般設定の読み取り、作成、編集、削除。</li><li>**[!DNL Manage messages presets]**：コンテンツのブランディングの読み取り、作成、編集、削除。</li><li>**[!DNL Manage suppression rules]**：抑制ルールの読み取り、作成、編集、削除へのアクセス。</li><li>**[!DNL Export suppression list]**：抑制リストを CSV ファイルとして書き出すためのアクセス権。</li><li>**[!DNL View suppression list]**：ローカル抑制リストの読み取り、書き出し。</li><li>**[!DNL Manage alerts]**：キャンペーン、メッセージ、権限に関するアラートの有効化／無効化。</li><li>**[!DNL Manage landing page settings]**：ランディングページ設定の読み取り、作成、編集、削除。</li><li>**[!DNL Manage SMS settings]**：SMS 設定の読み取り、作成、編集、削除。</li></ul> |
| 意思決定管理 | <ul><li>**[!DNL Manage decisions]**：決定の読み取り、作成、編集、削除。</li><li>**[!DNL Manage ranking strategies]**：ランキング戦略を読み取り、作成、編集および削除します。</li></ul> |
| Adobe Experience Platform | <ul><li>**[!DNL Sandbox]**：サンドボックスへのアクセスの許可。</li><li>**[!DNL Manage segments]**：セグメント定義の読み取り、作成、編集、削除。</li><li>**[!DNL Manage profiles]**：プロファイルの読み取り、作成、編集、削除。</li><li>**[!DNL Read datasets]**：データセットへの読み取り専用アクセス。</li><li>**[!DNL Read schemas]**：スキーマへの読み取り専用アクセス。</li><li>**[!DNL Read Identity namespace]**：ID 名前空間への読み取り専用アクセス。</li><li>**[!DNL Manage merge policies]**：結合ポリシーの読み取り、作成、編集、削除。</li></ul> |

## [!DNL Campaign Approver] {#campaign-approver}

**[!DNL Campaign Approver]** の役割を使用すると、ユーザーは配信を承認および公開できます。後から **[!DNL Campaigns]** レポートで配信の成功を確認できます。

| リソース | 権限 |
|-|-|
| キャンペーン | <ul><li>**[!DNL Manage campaigns]**：キャンペーンの読み取り、作成、編集、削除。</li><li>**[!DNL Publish campaigns]**：キャンペーンの公開。</li><li>**[!DNL View Campaigns report]**:ジャーニーレポートの読み取り、編集。</li></ul> |
| 意思決定管理 | <ul><li>**[!DNL Manage decisions]**：決定エンティティの読み取り、作成、編集、削除を行う。</li><li>**[!DNL Manage ranking strategies]**：カスタムメッセージレポートの読み取り、作成、編集、削除を行い、アクション機能を使用する。</li></ul> |
| Adobe Experience Platform | <ul><li>**[!DNL Manage segments]**：セグメント定義の読み取り、作成、編集、削除。</li><li>**[!DNL Manage profiles]**：プロファイルの読み取り、作成、編集、削除。</li><li>**[!DNL Read datasets]**：データセットへの読み取り専用アクセス。</li><li>**[!DNL Read schemas]**：スキーマへの読み取り専用アクセス</li><li>**[!DNL Manage merge policies]**：結合ポリシーの読み取り、作成、編集、削除。</li></ul> |
| チャネル設定 | <ul><li>**[!DNL View messages presets]**：メッセージプリセットへの読み取り専用アクセス。</li></ul> |

## [!DNL Campaign Manager] {#campaign-manager}

**[!DNL Campaign Manager]** の役割を持つユーザーは、**[!UICONTROL キャンペーン]**&#x200B;と、**[!UICONTROL キャンペーン]**&#x200B;にリンクされたすべての機能を作成および編集できますが、公開はできません。

この役割には、次の権限が含まれます。

| リソース | 権限 |
|-|-|
| キャンペーン | <ul><li>**[!DNL Manage campaigns]**：キャンペーンの読み取り、作成、編集、削除。</li><li>**[!DNL View campaigns report]**：ジャーニーレポートの読み取り、編集。</li></ul> |
| 意思決定管理 | <ul><li>**[!DNL Manage decisions]**：決定エンティティの読み取り、作成、編集、削除を行う。</li><li>**[!DNL Manage ranking strategies]**：カスタムメッセージレポートの読み取り、作成、編集、削除を行い、アクション機能を使用する。</li></ul> |
| Adobe Experience Platform | <ul><li> **[!DNL Manage segments]**：セグメント定義の読み取り、作成、編集、削除。</li><li>**[!DNL Manage profiles]**：プロファイルの読み取り、作成、編集、削除。</li><li>**[!DNL Read datasets]**：データセットへの読み取り専用アクセス。</li><li>**[!DNL Read schemas]**：スキーマへの読み取り専用アクセス</li><li>**[!DNL Manage merge policies]**：結合ポリシーの読み取り、作成、編集、削除。</li></ul> |
| チャネル設定 | <ul><li>**[!DNL View messages presets]**：メッセージプリセットへの読み取り専用アクセス。</li></ul> |

## [!DNL Campaign Viewer] {#campaign-viewer}

**[!DNL Campaign Viewer]** の役割を持つユーザーは、**[!UICONTROL キャンペーン]**&#x200B;および&#x200B;**[!UICONTROL 意思決定管理]**&#x200B;の機能に読み取り専用でアクセスできます。

この役割に割り当てられたユーザーは、編集または公開はできません。

この役割には、次の権限が含まれます。

| リソース | 権限 |
|-|-|
| キャンペーン | <ul><li>**[!DNL View campaigns]**：キャンペーンへの読み取り専用アクセス。</li><li>**[!DNL View campaigns report]**：キャンペーンレポートへの読み取り専用アクセス。</li></ul> |
| 意思決定管理 | <ul><li>**[!DNL View decisions]**：決定エンティティへの読み取り専用アクセス。</li></ul> |

## [!DNL Journey Administrator] {#journey-administrator}

**[!DNL Journey Administrator]** の役割を持つユーザーは、管理メニューでジャーニーおよび意思決定管理を管理および公開できます。

この役割には、次の権限が含まれます。

| リソース | 権限 |
|-|-|
| ジャーニー | <ul><li> **[!DNL Manage journeys]**：ジャーニーの読み取り、作成、編集、削除。</li><li>**[!DNL Publish journeys]**：ジャーニーの公開。</li><li>**[!DNL Manage journeys events, data sources and actions]**：イベント、ソース、アクションの読み取り、作成、編集、削除。</li><li>**[!DNL View journeys report]**：ジャーニーレポートの読み取り、編集。</li></ul> |
| チャネル設定 | <ul><li>**[!DNL Manage subdomains delegation]**：サブドメインデリゲーションの読み取り、作成、編集、削除。</li><li>**[!DNL Manage IP pools]**：IP プールの読み取り、作成、編集、削除。</li><li>**[!DNL Manage PTR records]**：PTR レコードの読み取りと編集。</li><li>**[!DNL View PTR records]**：PTR レコードへの読み取り専用アクセス。</li><li>**[!DNL Manage messages presets]**：コンテンツのブランディングの読み取り、作成、編集、削除。</li><li>**[!DNL Manage Landing page settings]**：ランディングページのサブドメインとランディングページのプリセットの作成、編集、削除。</li><li> **[!DNL Manage messages general settings]**：メッセージの一般設定の読み取り、作成、編集、削除。</li><li>**[!DNL Manage SMS settings]**:SMS チャネルを有効にするために必要な API 認証情報と SMS チャネル設定の作成、編集、削除。</li><li>**[!DNL Manage suppression rules]**：抑制ルールの読み取り、作成、編集、削除へのアクセス。</li><li>**[!DNL View suppression list]**：ローカル抑制リストの読み取り、書き出し。</li><li>**[!DNL Manage alerts]**：ジャーニーおよび使用権限に関するアラートの有効化／無効化。</li></ul> |
| 意思決定管理 | <ul><li>**[!DNL Manage decisions]**：決定の読み取り、作成、編集、削除。</li><li>**[!DNL Manage ranking strategies]**：ランキング戦略を読み取り、作成、編集および削除します。</li></ul> |
| Adobe Experience Platform | <ul><li>**[!DNL Sandbox]**：サンドボックスへのアクセスの許可。</li><li>**[!DNL Manage segments]**：セグメント定義の読み取り、作成、編集、削除。</li><li>**[!DNL Manage profiles]**：プロファイルの読み取り、作成、編集、削除。</li><li>**[!DNL Read datasets]**：データセットへの読み取り専用アクセス。</li><li>**[!DNL Read schemas]**：スキーマへの読み取り専用アクセス。</li><li>**[!DNL Read Identity namespace]**：ID 名前空間への読み取り専用アクセス。</li><li>**[!DNL Manage merge policies]**：結合ポリシーの読み取り、作成、編集、削除。</li></ul> |
| Journey Optimizer ライブラリ | <ul><li>**[!DNL Manage Library Items]**：[!DNL Journey Optimizer] ライブラリ内の保存済み式の追加、削除。</li></ul> |
| データガバナンス | <ul><li>**[!DNL Manage usage label]**：使用ラベルの読み取り、作成、削除</li><li>**[!DNL Manage data usage policies]**：データ使用ポリシーの読み取り、作成、編集、削除。</li><li>**[!DNL View data usage policies]**：データ使用ポリシーへの読み取り専用アクセス。</li><li>**[!DNL View user activity log]**：監査ログの読み取り、書き出し。</li></ul> |

## [!DNL Journey Approver] {#journey-approver}

**[!DNL Journey Approver]** の役割を使用すると、ユーザーは配信を承認および公開できます。後から **[!DNL Journey]** レポートで配信の成功を確認できます。

この役割には、次の権限が含まれます。

| リソース | 権限 |
|-|-|
| ジャーニー | <ul><li>**[!DNL Manage journeys]**：ジャーニーの読み取り、作成、編集、削除。</li><li>**[!DNL Publish journey]**：ジャーニーの公開。</li><li>**[!DNL View journeys events, data sources and actions]**：ジャーニーイベント、ジャーニーカスタムアクション、ジャーニーデータソースへの読み取り専用アクセス。</li><li>**[!DNL View journeys report]**:ジャーニーレポートの読み取り、編集。</li></ul> |
| 意思決定管理 | <ul><li>**[!DNL Manage decisions]**：決定エンティティの読み取り、作成、編集、削除を行う。</li><li>**[!DNL Manage ranking strategies]**：カスタムレポートの読み取り、作成、編集および削除、アクション機能の使用。</li></ul> |
| Adobe Experience Platform | <ul><li>**[!DNL Manage segments]**：セグメント定義の読み取り、作成、編集、削除。</li><li>**[!DNL Manage profiles]**：プロファイルの読み取り、作成、編集、削除。</li><li>**[!DNL Read datasets]**：データセットへの読み取り専用アクセス。</li><li>**[!DNL Read schemas]**：スキーマへの読み取り専用アクセス</li><li>**[!DNL Manage merge policies]**：結合ポリシーの読み取り、作成、編集、削除。</li></ul> |
| チャネル設定 | <ul><li>**[!DNL View channel configurations]**：チャネル設定への読み取り専用アクセス。</li></ul> |

## [!DNL Journey Manager] {#journey-manager}

**[!DNL Journey Manager]** の役割を持つユーザーは、**[!UICONTROL ジャーニー]**&#x200B;と、**[!UICONTROL ジャーニー]**&#x200B;にリンクされたすべての機能を作成および編集できますが、公開はできません。

この役割には、次の権限が含まれます。

| リソース | 権限 |
|-|-|
| ジャーニー | <ul><li>**[!DNL Manage journeys]**：ジャーニーの読み取り、作成、編集、削除。</li><li>**[!DNL View journeys events]**：ジャーニーイベント、ジャーニーカスタムアクション、ジャーニーデータソースへの読み取り専用アクセス。</li><li>**[!DNL View journeys report]**：ジャーニーレポートの読み取り、編集。</li></ul> |
| 意思決定管理 | <ul><li>**[!DNL Manage decisions]**：決定エンティティの読み取り、作成、編集、削除を行う。</li><li>**[!DNL Manage ranking strategies]**：カスタムレポートの読み取り、作成、編集および削除、アクション機能の使用。</li></ul> |
| Adobe Experience Platform | <ul><li> **[!DNL Manage segments]**：セグメント定義の読み取り、作成、編集、削除。</li><li>**[!DNL Manage profiles]**：プロファイルの読み取り、作成、編集、削除。</li><li>**[!DNL Read datasets]**：データセットへの読み取り専用アクセス。</li><li>**[!DNL Read schemas]**：スキーマへの読み取り専用アクセス</li><li>**[!DNL Manage merge policies]**：結合ポリシーの読み取り、作成、編集、削除。</li></ul> |
| チャネル設定 | <ul><li>**[!DNL View channel configurations]**：チャネル設定への読み取り専用アクセス。</li></ul> |

## [!DNL Journey Viewer] {#journey-viewer}

**[!DNL Journey viewer]** の役割を持つユーザーは、**[!UICONTROL ジャーニー]**&#x200B;および&#x200B;**[!UICONTROL 意思決定管理]**&#x200B;の機能に読み取り専用でアクセスできます。

この役割に割り当てられたユーザーは、編集または公開はできません。

この役割には、次の権限が含まれます。

| リソース | 権限 |
|-|-|
| ジャーニー | <ul><li>**[!DNL View journeys]**：ジャーニーへの読み取り専用アクセス。</li><li>**[!DNL View journeys event, data sources, actions]**：ジャーニーイベントおよびデータソースへの読み取り専用アクセス。</li><li>**[!DNL View journeys report]**：ジャーニーレポートへの読み取り専用アクセス。</li></ul> |
| 意思決定管理 | <ul><li>**[!DNL View decisions]**：決定エンティティへの読み取り専用アクセス。</li></ul> |

## [!DNL Decisioning manager] {#decisioning-manager}

**[!DNL Decisioning manager]** の役割では、**[!UICONTROL 意思決定管理]**&#x200B;メニューへのアクセスのみが許可されます。この役割に割り当てられたユーザーは、決定の管理、表示および公開のみを実行できます。

この役割には、次の権限が含まれます。

| 機能 | 権限 |
|-|-|
| 意思決定管理 | <ul><li>**[!DNL Manage decisions]**：決定エンティティの読み取り、作成、編集、削除を行う。</li><li>**[!DNL View decisions]**：決定エンティティへの読み取り専用アクセス。</li><li>**[!DNL Manage ranking strategies]**：カスタムレポートの読み取り、作成、編集および削除、アクション機能の使用。</li><li>**[!DNL Publish decisions]**：決定アクティビティのアクティブ化または非アクティブ化。</li><!--li>**[!DNL Manage Experience decisions]**: read, create, edit, and delete Experience decisioning entities.</li--></ul> |

## [!DNL Content Library Manager] {#content-library-manager}

**[!DNL Content Library Manager]** の役割では、**[!UICONTROL コンテンツテンプレート]**&#x200B;メニューへのアクセスのみが許可されます。この役割に割り当てられたユーザーは、ジャーニーやキャンペーンにアクセスせずにコンテンツを作成するテンプレートライブラリにのみアクセスできます。

この役割には、次の権限が含まれます。

| 機能 | 権限 |
|-|-|
| Journey Optimizer ライブラリ | <ul><li>**[!DNL Manage library items]**：コンテンツテンプレートやフラグメントを含む、Journey Optimizer ライブラリの項目の読み取り、作成、編集、削除。</li><li>**[!DNL Manage simulate content]**：プレビューおよび配達確認用に「**[!UICONTROL コンテンツをシミュレート]**」オプションへのアクセス。</li><li>**[!DNL Publish Fragment]**：コンテンツフラグメントを公開します。</li></ul> |
| 意思決定管理 | <ul><li>**[!DNL Manage decisions]**：決定エンティティの読み取り、作成、編集、削除を行う。</li><li>**[!DNL Manage ranking strategies]**：カスタムレポートの読み取り、作成、編集および削除、アクション機能の使用。</li></ul> |
| Adobe Experience Platform | <ul><li> **[!DNL Manage segments]**：セグメント定義の読み取り、作成、編集、削除。</li><li>**[!DNL Manage profiles]**：プロファイルの読み取り、作成、編集、削除。</li><li>**[!DNL Read datasets]**：データセットへの読み取り専用アクセス。</li><li>**[!DNL Read schemas]**：スキーマへの読み取り専用アクセス</li><li>**[!DNL Manage merge policies]**：結合ポリシーの読み取り、作成、編集、削除。</li></ul> |