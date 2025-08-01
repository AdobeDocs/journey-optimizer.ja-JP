---
solution: Journey Optimizer
product: journey optimizer
title: Journey Optimizer ビルトインの役割
description: ビルトインの役割の詳細情報
feature: Access Management
topic: Administration
role: Admin, User
level: Intermediate
keywords: 権限, オーサリング, メッセージ
exl-id: 5a968bd8-cf76-4242-aa80-3cfb3d551511
source-git-commit: ee2e07353762a81aadd3d63580c528f617599623
workflow-type: tm+mt
source-wordcount: '1175'
ht-degree: 100%

---

# ビルトインの役割 {#ootb-product-profiles}

ビルトインの役割は、ユーザーがインターフェイス内の特定の機能やオブジェクトにアクセスできるようにするための、一連の単一権限です。役割を構築するために利用可能な権限のリストについては、[このページ](ootb-permissions.md)を参照してください。

## [!DNL Content Library Manager] {#content-library-manager}

**[!DNL Content Library Manager]** の役割では、**[!UICONTROL コンテンツテンプレート]**&#x200B;メニューへのアクセスのみが許可されます。この役割に割り当てられたユーザーは、ジャーニーやキャンペーンにアクセスせずにコンテンツを作成するテンプレートライブラリにのみアクセスできます。

この役割には、次の権限が含まれます。

| 機能 | 権限 |
|-|-|
| Journey Optimizer ライブラリ | <ul><li>**[!DNL Manage library items]**：コンテンツテンプレートやフラグメントを含む、Journey Optimizer ライブラリの項目の読み取り、作成、編集、削除。</li><li>**[!DNL Manage simulate content]**：プレビューおよび配達確認用に「**[!UICONTROL コンテンツをシミュレート]**」オプションへのアクセス。</li><li>**[!DNL Publish Fragment]**：コンテンツフラグメントを公開します。</li></ul> |
| 意思決定管理 | <ul><li>**[!DNL Manage decisions]**：決定エンティティの読み取り、作成、編集、削除を行う。</li><li>**[!DNL Manage ranking strategies]**：カスタムレポートの読み取り、作成、編集および削除、アクション機能の使用。</li></ul> |
| Adobe Experience Platform | <ul><li>**[!DNL Manage merge policies]**：結合ポリシーの読み取り、作成、編集、削除。</li><li>**[!DNL Manage profiles]**：プロファイルの読み取り、作成、編集、削除。</li><li> **[!DNL Manage segments]**：セグメント定義の読み取り、作成、編集、削除。</li><li>**[!DNL View datasets]**：データセットへの読み取り専用アクセス。</li><li>**[!DNL View schemas]**：スキーマへの読み取り専用アクセス。</li></ul> |

## [!DNL Decisioning manager] {#decisioning-manager}

**[!DNL Decisioning manager]** の役割では、**[!UICONTROL 意思決定管理]**&#x200B;メニューへのアクセスのみが許可されます。この役割に割り当てられたユーザーは、決定の管理、表示および公開のみを実行できます。

この役割には、次の権限が含まれます。

| 機能 | 権限 |
|-|-|
| 意思決定管理 | <ul><li>**[!DNL Manage decisions]**：決定エンティティの読み取り、作成、編集、削除を行う。</li><li>**[!DNL Manage ranking strategies]**：カスタムレポートの読み取り、作成、編集および削除、アクション機能の使用。</li><li>**[!DNL View decisions]**：決定エンティティへの読み取り専用アクセス。</li><li>**[!DNL Publish decisions]**：決定アクティビティのアクティブ化または非アクティブ化。</li><!--li>**[!DNL Manage Experience decisions]**: read, create, edit, and delete Decisioning entities.</li--></ul> |

## [!DNL Campaign Administrator] {#campaign-administrator}

**[!DNL Campaign Administrator]** の役割を使用すると、管理メニューでキャンペーンおよび意思決定管理を管理および公開できます。

この役割には、次の権限が含まれます。

| リソース | 権限 |
|-|-|
| キャンペーン | <ul><li> **[!DNL Manage campaigns]**：キャンペーンの読み取り、作成、編集、削除。</li><li>**[!DNL Publish campaigns]**：キャンペーンの公開。</li><li>**[!DNL View campaigns report]**：キャンペーンレポートの読み取りおよび編集。</li></ul> |
| チャネル設定 | <ul> <li>**[!DNL Export suppression list]**：抑制リストを CSV ファイルとして書き出すためのアクセス権。</li> <li>**[!DNL Manage alerts]**：キャンペーン、メッセージ、権限に関するアラートの有効化／無効化。</li> <li>**[!DNL Manage IP pools]**：IP プールの読み取り、作成、編集、削除。</li> <li>**[!DNL Manage landing page settings]**：ランディングページ設定の読み取り、作成、編集、削除。</li> <li>**[!DNL Manage messages general settings]**：メッセージの一般設定の読み取り、作成、編集、削除。</li> <li>**[!DNL Manage messages presets]**：コンテンツのブランディングの読み取り、作成、編集、削除。</li> <li>**[!DNL Manage PTR records]**：PTR レコードの読み取りと編集。</li> <li>**[!DNL Manage SMS settings]**：SMS 設定の読み取り、作成、編集、削除。</li> <li>**[!DNL Manage subdomains delegation]**：サブドメインデリゲーションの読み取り、作成、編集、削除。</li> <li>**[!DNL Manage suppression rules]**：抑制ルールの読み取り、作成、編集、削除へのアクセス。</li> <li>**[!DNL View PTR records]**：PTR レコードへの読み取り専用アクセス。</li> <li>**[!DNL View suppression list]**：ローカル抑制リストの読み取り、書き出し。</li> </ul> |
| 意思決定管理 | <ul><li>**[!DNL Manage decisions]**：決定の読み取り、作成、編集、削除。</li><li>**[!DNL Manage ranking strategies]**：ランキング戦略を読み取り、作成、編集および削除します。</li></ul> |
| Adobe Experience Platform | <ul> <li>**[!DNL Manage merge policies]**：結合ポリシーの読み取り、作成、編集、削除。</li> <li>**[!DNL Manage profiles]**：プロファイルの読み取り、作成、編集、削除。</li> <li>**[!DNL Manage segments]**：セグメント定義の読み取り、作成、編集、削除。</li> <li>**[!DNL View datasets]**：データセットへの読み取り専用アクセス。</li> <li>**[!DNL Read Identity namespace]**：ID 名前空間への読み取り専用アクセス。</li> <li>**[!DNL View schemas]**：スキーマへの読み取り専用アクセス。</li> <li>**[!DNL Sandbox]**：サンドボックスへのアクセスの許可。</li> </ul> |

## [!DNL Campaign Approver] {#campaign-approver}

**[!DNL Campaign Approver]** の役割を使用すると、ユーザーは配信を承認および公開できます。後から **[!DNL Campaigns]** レポートで配信の成功を確認できます。

| リソース | 権限 |
|-|-|
| キャンペーン | <ul><li>**[!DNL Manage campaigns]**：キャンペーンの読み取り、作成、編集、削除。</li><li>**[!DNL Publish campaigns]**：キャンペーンの公開。</li><li>**[!DNL View campaigns report]**：キャンペーンレポートの読み取り、編集。</li></ul> |
| 意思決定管理 | <ul><li>**[!DNL Manage decisions]**：決定エンティティの読み取り、作成、編集、削除を行う。</li><li>**[!DNL Manage ranking strategies]**：カスタムメッセージレポートの読み取り、作成、編集、削除を行い、アクション機能を使用する。</li></ul> |
| Adobe Experience Platform | <ul><li>**[!DNL Manage merge policies]**：結合ポリシーの読み取り、作成、編集、削除。</li><li>**[!DNL Manage segments]**：セグメント定義の読み取り、作成、編集、削除。</li><li>**[!DNL Manage profiles]**：プロファイルの読み取り、作成、編集、削除。</li><li>**[!DNL View datasets]**：データセットへの読み取り専用アクセス。</li><li>**[!DNL View schemas]**：スキーマへの読み取り専用アクセス。</li></ul> |
| チャネル設定 | <ul><li>**[!DNL View messages presets]**：メッセージプリセットへの読み取り専用アクセス。</li></ul> |

## [!DNL Campaign Manager] {#campaign-manager}

**[!DNL Campaign Manager]** の役割を持つユーザーは、**[!UICONTROL キャンペーン]**&#x200B;と、**[!UICONTROL キャンペーン]**&#x200B;にリンクされたすべての機能を作成および編集できますが、公開はできません。

この役割には、次の権限が含まれます。

| リソース | 権限 |
|-|-|
| キャンペーン | <ul><li>**[!DNL Manage campaigns]**：キャンペーンの読み取り、作成、編集、削除。</li><li>**[!DNL View campaigns report]**：ジャーニーレポートの読み取り、編集。</li></ul> |
| 意思決定管理 | <ul><li>**[!DNL Manage decisions]**：決定エンティティの読み取り、作成、編集、削除を行う。</li><li>**[!DNL Manage ranking strategies]**：カスタムメッセージレポートの読み取り、作成、編集、削除を行い、アクション機能を使用する。</li></ul> |
| Adobe Experience Platform | <ul><li>**[!DNL Manage merge policies]**：結合ポリシーの読み取り、作成、編集、削除。</li><li>**[!DNL Manage profiles]**：プロファイルの読み取り、作成、編集、削除。</li><li> **[!DNL Manage segments]**：セグメント定義の読み取り、作成、編集、削除。</li><li>**[!DNL View datasets]**：データセットへの読み取り専用アクセス。</li><li>**[!DNL View schemas]**：スキーマへの読み取り専用アクセス。</li></ul> |
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
| ジャーニー | <ul> <li>**[!DNL Manage journeys]**：ジャーニーの読み取り、作成、編集、削除。</li> <li>**[!DNL Manage journeys events, data sources and actions]**：イベント、ソース、アクションの読み取り、作成、編集、削除。</li> <li>**[!DNL Publish journeys]**：ジャーニーの公開。</li> <li>**[!DNL View journeys report]**：ジャーニーレポートの読み取り、編集。</li> </ul> |
| チャネル設定 | <ul> <li>**[!DNL Manage alerts]**：ジャーニーおよび使用権限に関するアラートの有効化／無効化。</li> <li>**[!DNL Manage IP pools]**：IP プールの読み取り、作成、編集、削除。</li> <li>**[!DNL Manage Landing page settings]**：ランディングページのサブドメインとランディングページのプリセットの作成、編集、削除。</li> <li>**[!DNL Manage messages general settings]**：メッセージの一般設定の読み取り、作成、編集、削除。</li> <li>**[!DNL Manage messages presets]**：コンテンツのブランディングの読み取り、作成、編集、削除。</li> <li>**[!DNL Manage PTR records]**：PTR レコードの読み取りと編集。</li> <li>**[!DNL Manage SMS settings]**：SMS チャネルを有効にする必要な API 資格情報と SMS チャネル設定の作成、編集、削除。</li> <li>**[!DNL Manage subdomains delegation]**：サブドメインデリゲーションの読み取り、作成、編集、削除。</li> <li>**[!DNL Manage suppression rules]**：抑制ルールの読み取り、作成、編集、削除へのアクセス。</li> <li>**[!DNL View PTR records]**：PTR レコードへの読み取り専用アクセス。</li> <li>**[!DNL View suppression list]**：ローカル抑制リストの読み取り、書き出し。</li> </ul> |
| 意思決定管理 | <ul> <li>**[!DNL Manage decisions]**：決定の読み取り、作成、編集、削除。</li> <li>**[!DNL Manage ranking strategies]**：ランキング戦略を読み取り、作成、編集および削除します。</li> </ul> |
| Adobe Experience Platform | <ul> <li>**[!DNL Manage merge policies]**：結合ポリシーの読み取り、作成、編集、削除。</li> <li>**[!DNL Manage profiles]**：プロファイルの読み取り、作成、編集、削除。</li> <li>**[!DNL Manage segments]**：セグメント定義の読み取り、作成、編集、削除。</li> <li>**[!DNL View datasets]**：データセットへの読み取り専用アクセス。</li> <li>**[!DNL Read Identity namespace]**：ID 名前空間への読み取り専用アクセス。</li> <li>**[!DNL View schemas]**：スキーマへの読み取り専用アクセス。</li> <li>**[!DNL Sandbox]**：サンドボックスへのアクセスの許可。</li> </ul> |
| Journey Optimizer ライブラリ | <ul> <li>**[!DNL Manage Library Items]**：[!DNL Journey Optimizer] ライブラリ内の保存済み式の追加、削除。</li> </ul> |
| データガバナンス | <ul> <li>**[!DNL Manage data usage policies]**：データ使用ポリシーの読み取り、作成、編集、削除。</li> <li>**[!DNL Manage usage label]**：使用ラベルの読み取り、作成、削除</li> <li>**[!DNL View data usage policies]**：データ使用ポリシーへの読み取り専用アクセス。</li> <li>**[!DNL View user activity log]**：監査ログの読み取り、書き出し。</li> </ul> |

## [!DNL Journey Approver] {#journey-approver}

**[!DNL Journey Approver]** の役割を使用すると、ユーザーは配信を承認および公開できます。後から **[!DNL Journey]** レポートで配信の成功を確認できます。

この役割には、次の権限が含まれます。

| リソース | 権限 |
|-|-|
| ジャーニー | <ul><li>**[!DNL Manage journeys]**：ジャーニーの読み取り、作成、編集、削除。</li><li>**[!DNL Publish journey]**：ジャーニーの公開。</li><li>**[!DNL View journeys events, data sources and actions]**：ジャーニーイベント、ジャーニーカスタムアクション、ジャーニーデータソースへの読み取り専用アクセス。</li><li>**[!DNL View journeys report]**:ジャーニーレポートの読み取り、編集。</li></ul> |
| 意思決定管理 | <ul><li>**[!DNL Manage decisions]**：決定エンティティの読み取り、作成、編集、削除を行う。</li><li>**[!DNL Manage ranking strategies]**：カスタムレポートの読み取り、作成、編集および削除、アクション機能の使用。</li></ul> |
| Adobe Experience Platform | <ul><li>**[!DNL Manage merge policies]**：結合ポリシーの読み取り、作成、編集、削除。</li><li>**[!DNL Manage profiles]**：プロファイルの読み取り、作成、編集、削除。</li><li>**[!DNL Manage segments]**：セグメント定義の読み取り、作成、編集、削除。</li><li>**[!DNL View datasets]**：データセットへの読み取り専用アクセス。</li><li>**[!DNL View schemas]**：スキーマへの読み取り専用アクセス。</li></ul> |
| チャネル設定 | <ul><li>**[!DNL View channel configurations]**：チャネル設定への読み取り専用アクセス。</li></ul> |

## [!DNL Journey Manager] {#journey-manager}

**[!DNL Journey Manager]** の役割を持つユーザーは、**[!UICONTROL ジャーニー]**&#x200B;と、**[!UICONTROL ジャーニー]**&#x200B;にリンクされたすべての機能を作成および編集できますが、公開はできません。

この役割には、次の権限が含まれます。

| リソース | 権限 |
|-|-|
| ジャーニー | <ul><li>**[!DNL Manage journeys]**：ジャーニーの読み取り、作成、編集、削除。</li><li>**[!DNL View journeys events]**：ジャーニーイベント、ジャーニーカスタムアクション、ジャーニーデータソースへの読み取り専用アクセス。</li><li>**[!DNL View journeys report]**：ジャーニーレポートの読み取り、編集。</li></ul> |
| 意思決定管理 | <ul><li>**[!DNL Manage decisions]**：決定エンティティの読み取り、作成、編集、削除を行う。</li><li>**[!DNL Manage ranking strategies]**：カスタムレポートの読み取り、作成、編集および削除、アクション機能の使用。</li></ul> |
| Adobe Experience Platform | <ul><li>**[!DNL Manage merge policies]**：結合ポリシーの読み取り、作成、編集、削除。</li><li>**[!DNL Manage profiles]**：プロファイルの読み取り、作成、編集、削除。</li><li> **[!DNL Manage segments]**：セグメント定義の読み取り、作成、編集、削除。</li><li>**[!DNL View datasets]**：データセットへの読み取り専用アクセス。</li><li>**[!DNL View schemas]**：スキーマへの読み取り専用アクセス。</li></ul> |
| チャネル設定 | <ul><li>**[!DNL View channel configurations]**：チャネル設定への読み取り専用アクセス。</li></ul> |

## [!DNL Journey Viewer] {#journey-viewer}

**[!DNL Journey viewer]** の役割を持つユーザーは、**[!UICONTROL ジャーニー]**&#x200B;および&#x200B;**[!UICONTROL 意思決定管理]**&#x200B;の機能に読み取り専用でアクセスできます。

この役割に割り当てられたユーザーは、編集または公開はできません。

この役割には、次の権限が含まれます。

| リソース | 権限 |
|-|-|
| ジャーニー | <ul><li>**[!DNL View journeys]**：ジャーニーへの読み取り専用アクセス。</li><li>**[!DNL View journeys event, data sources, actions]**：ジャーニーイベントおよびデータソースへの読み取り専用アクセス。</li><li>**[!DNL View journeys report]**：ジャーニーレポートへの読み取り専用アクセス。</li></ul> |
| 意思決定管理 | <ul><li>**[!DNL View decisions]**：決定エンティティへの読み取り専用アクセス。</li></ul> |

<!--
## [!DNL Orchestrated Campaign Administrators] {#orchestrated-campaign-administrator}

The **[!DNL Orchestrated Campaign Administrator]** role allows the administration menus with the possibility to manage and publish Orchestrated Campaigns. 

This role includes the following permissions:

| Resources | Permissions|
|-|-|
|Orchestrated Campaigns| <ul><li> **[!DNL Manage orchestrated campaigns]**: read, create, edit, and delete orchestrated campaigns.</li><li>**[!DNL Publish orchestrated campaigns]**: publish orchestrated campaigns.</li><li>**[!DNL View orchestrated campaigns report]**: read and edit orchestrated campaigns report.</li></ul>|
|Messages| <ul><li>**[!DNL Manage messages]**: read, create, edit, and delete messages.</li><li>**[!DNL Manage messages preview and test]**: preview and test messages before sending.</li><li>**[!DNL Publish messages]**: publish messages.</li><li>**[!DNL View messages report]**: view and edit message reports.</li></ul>|
|Channel configurations|<ul><li>**[!DNL Export suppression list]**: access to export suppression list as a CSV file.</li> <li>**[!DNL Manage alerts]**: enable/disable alerts for campaigns, messages and entitlements.</li> <li>**[!DNL Manage custom dashboards]**: read, create, edit, and delete custom dashboards.</li><li>**[!DNL Manage IP pools]**: read, create, edit, and delete ip pool.</li> <li>**[!DNL Manage landing page settings]**: read, create, edit, and delete landing page settings.</li> <li>**[!DNL Manage messages general settings]**: read, create, edit, and delete message general settings.</li> <li>**[!DNL Manage messages presets]**: read, create, edit, and delete content branding.</li> <li>**[!DNL Manage orchestrated campaign administrator]**: Read, create, edit and delete links and reconciliations between Adobe Experience Platform Profiles and Relational store entities.</li><li>**[!DNL Manage PTR records]**: read and edit PTR records.</li> <li>**[!DNL Manage SMS settings]**: read, create, edit, and delete SMS settings.</li> <li>**[!DNL Manage subdomains delegation]**: read, create, edit, and delete subdomain delegation.</li> <li>**[!DNL Manage suppression rules]**: access read, create, edit and delete suppression rules.</li> <li>**[!DNL View PTR records]**: read-only access to PTR records.</li> <li>**[!DNL View suppression list]**: read and export local suppression list.</li> </ul>|
|Decision management|<ul><li>**[!DNL Manage decisions]**: read, create, edit, and delete decisions.</li><li>**[!DNL Manage ranking strategies]**: read, create, edit, and delete ranking strategies.</li></ul>|
|Adobe Experience Platform|<ul> <li>**[!DNL Manage merge policies]**: read, create, edit, and delete merge policies.</li> <li>**[!DNL Manage profiles]**: read, create, edit, and delete profiles.</li> <li>**[!DNL Manage segments]**: read, create, edit, and delete segment definitions.</li> <li>**[!DNL View datasets]**: read-only access to datasets.</li> <li>**[!DNL View Identity namespace]**: read-only access to identity namespace.</li> <li>**[!DNL View schemas]**: read-only access to schemas.</li> <li>**[!DNL View sandbox]**: grant access to sandboxes.</li> </ul>|

## [!DNL Orchestrated Campaign Approver] {#orchestrated-campaign-approver}

The **[!DNL Orchestrated Campaign Approver]** role allows users to publish Orchestrated campaigns. 

This role includes the following permissions:

| Resources | Permissions|
|-|-|
|Orchestrated campaigns| <ul><li>**[!DNL Manage orchestrated campaigns]**: read, create, edit, and delete campaigns.</li><li>**[!DNL Publish orchestrated campaigns]**: publish campaigns.</li><li>**[!DNL View orchestrated campaigns report]**: read orchestrated campaign reports.</li></ul>|
|Messages| <ul><li>**[!DNL Manage messages]**: read, create, edit, and delete messages.</li><li>**[!DNL Manage messages preview and test]**: preview and test messages before sending.</li><li>**[!DNL Publish messages]**: publish messages.</li><li>**[!DNL View messages report]**: view and edit message reports.</li></ul>|
|Decision management| <ul><li>**[!DNL Manage decisions]**: read, create, edit, and delete decisioning entities.</li><li>**[!DNL Manage ranking strategies]**: read, create, edit, and delete custom messages reports and use action features.</li></ul>|
|Adobe Experience Platform|<ul> <li>**[!DNL Manage segments]**: read, create, edit, and delete segment definitions.</li> <li>**[!DNL Manage profiles]**: read, create, edit, and delete profiles.</li> <li>**[!DNL View datasets]**: read-only access to datasets.</li> <li>**[!DNL View schemas]**: read-only access to schemas.</li> <li>**[!DNL Manage merge policies]**: read, create, edit, and delete merge policies.</li> <li>**[!DNL Enable AI Assistant]**: enable or access AI-powered campaign and audience features.</li>  <li>**[!DNL View operational insights]**: read-only access to system-level insights and monitoring dashboards.</li></ul>|
|Channel configurations|<ul><li>**[!DNL Manage custom dashboards]**: create, edit, and delete custom dashboards.</li> <li>**[!DNL View messages presets]**: read-only access to messages presets.</li><li>**[!DNL View orchestrated campaigns admin]**: Read-only access to links and reconciliations between Adobe Experience Platform Profiles and Relational store entities section.</li> </ul>|

## [!DNL Orchestrated Campaign Manager] {#orchestrated-campaign-manager}

The **[!DNL Orchestrated Campaign Manager]** role allows users to create and edit **[!UICONTROL Orchestrated campaigns]** and every capability linked to **[!UICONTROL Orchestrated campaigns]** but will not be able to publish them.

This role includes the following permissions:

| Resources | Permissions|
|-|-|
|Orchestrated campaigns| <ul><li>**[!DNL Manage orchestrated campaigns]**: read, create, edit, and delete campaigns.</li><li>**[!DNL View orchestrated campaigns report]**: read orchestrated campaigns report.</li></ul>|
|Messages| <ul><li>**[!DNL Manage messages]**: read, create, edit, and delete messages.</li><li>**[!DNL Manage messages preview and test]**: preview and test messages before sending.</li><li>**[!DNL View messages report]**: view and edit message reports.</li></ul>|
|Decision management| <ul><li>**[!DNL Manage decisions]**: read, create, edit, and delete decisioning entities.</li><li>**[!DNL Manage ranking strategies]**: read, create, edit, and delete custom messages reports and use action features.</li></ul>|
|Adobe Experience Platform| <ul><li>**[!DNL Enable AI Assistant]**: enable or access AI-powered campaign and audience features.</li> <li>**[!DNL Manage merge policies]**: read, create, edit, and delete merge policies.</li><li>**[!DNL Manage profiles]**: read, create, edit, and delete profiles.</li><li> **[!DNL Manage segments]**: read, create, edit, and delete segment definitions.</li><li>**[!DNL View datasets]**: read-only access to datasets.</li>  <li>**[!DNL View operational insights]**: read-only access to system-level insights and monitoring dashboards.</li><li>**[!DNL View schemas]**: read-only access to schemas.</li></ul>|
|Channel configurations| <ul><li>**[!DNL Manage custom dashboards]**: create, edit, and delete custom dashboards.</li><li>**[!DNL View messages presets]**: read-only access to messages presets.</li><li>**[!DNL View orchestrated campaigns admin]**: Read-only access to links and reconciliations between Adobe Experience Platform Profiles and Relational store entities section.</li></ul>|

## [!DNL Orchestrated Campaign Viewer] {#orchestrated-campaign-viewer}

The **[!DNL Campaign Viewer]** role allows read-only access to the **[!UICONTROL Orchestrated campaigns]** capabilities. 

Users assigned to this role will not be able to edit or publish. 

This role includes the following permissions:

| Resources | Permissions|
|-|-|
|Orchestrated campaigns| <ul><li>**[!DNL View orchestrated campaigns]**: read-only access to campaigns.</li><li>**[!DNL View orchestrated campaigns report]**: read-only access to campaigns reports.</li></ul>|
|Messages|<ul><li>**[!DNL View messages]**: view messages.</li><li>**[!DNL View messages report]**: view and edit message reports.</li></ul>|
|Decision management| <ul><li>**[!DNL View decisions]**: read-only access to decisions entities.</li></ul>|
|Adobe Experience Platform| <ul><li>**[!DNL Enable AI Assistant]**: enable or access AI-powered campaign and audience features.</li> <li>**[!DNL View operational insights]**: read-only access to system-level insights and monitoring dashboards.</li></ul>|
|Channel configurations| <ul><li>**[!DNL Manage custom dashboards]**: create, edit, and delete custom dashboards.</li><li>**[!DNL View orchestrated campaigns admin]**: Read-only access to links and reconciliations between Adobe Experience Platform Profiles and Relational store entities section.</li></ul>|

-->