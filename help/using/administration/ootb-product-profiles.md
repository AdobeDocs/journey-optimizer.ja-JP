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
TQID: https://experienceleague.adobe.com/LkOCFOSH-AzwWMoteNN-XI3R2yYkO5iBrVwMtobd4iI
product_v2: id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2: id: bb359667-ec7d-4d4b-8663-5850fc219d32id: b856530c-d60b-42d8-a19d-df2dfd7fe62a
subfeature_v2: []
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2: id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adebid: e1e0219c-f879-479f-8427-888ed2a6e9c2id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: c46ce04b47a3576e6373cbe788f2bbccf6ddbed0
workflow-type: tm+mt
source-wordcount: 2684
ht-degree: 76%

---

# ビルトインの役割 {#ootb-product-profiles}

>[!BEGINSHADEBOX]

**このページでは、**&#x200B;組み込みの役割と、それぞれに含まれる権限について説明します。これにより、ユーザーの責任に合った既製のレベルのアクセス権をすばやく付与できます。

>[!ENDSHADEBOX]

ビルトインの役割は、ユーザーがインターフェイス内の特定の機能やオブジェクトにアクセスできるようにするための、一連の単一権限です。 役割を構築するために利用可能な権限のリストについては、[このページ](ootb-permissions.md)を参照してください。


## [!DNL Campaign Administrator] {#campaign-administrator}

**[!DNL Campaign Administrator]** の役割を使用すると、管理メニューでキャンペーンおよび意思決定管理を管理および公開できます。

この役割には、次の権限が含まれます。

| リソース | 権限 |
|-|-|
| Adobe Experience Platform | <ul> <li>**[!DNL Manage merge policies]**：結合ポリシーの読み取り、作成、編集、削除。</li> <li>**[!DNL Manage profiles]**：プロファイルの読み取り、作成、編集、削除。</li> <li>**[!DNL Manage segments]**：セグメント定義の読み取り、作成、編集、削除。</li> <li>**[!DNL View datasets]**：データセットへの読み取り専用アクセス。</li> <li>**[!DNL Read Identity namespace]**：ID 名前空間への読み取り専用アクセス。</li> <li>**[!DNL View schemas]**：スキーマへの読み取り専用アクセス。</li> <li>**[!DNL Sandbox]**：サンドボックスへのアクセスの許可。</li> </ul> |
| キャンペーン | <ul><li> **[!DNL Manage campaigns]**：キャンペーンの読み取り、作成、編集、削除。</li><li>**[!DNL Publish campaigns]**：キャンペーンの公開。</li><li>**[!DNL View campaigns report]**：キャンペーンレポートの読み取りおよび編集。</li></ul> |
| チャネル設定 | <ul> <li>**[!DNL Export suppression list]**：抑制リストを CSV ファイルとしてエクスポートするためのアクセス権。</li> <li>**[!DNL Manage alerts]**：キャンペーン、メッセージ、権限に関するアラートの有効化／無効化。</li> <li>**[!DNL Manage IP pools]**：IP プールの読み取り、作成、編集、削除。</li> <li>**[!DNL Manage landing page settings]**：ランディングページ設定の読み取り、作成、編集、削除。</li> <li>**[!DNL Manage messages general settings]**：メッセージの一般設定の読み取り、作成、編集、削除。</li> <li>**[!DNL Manage messages presets]**：コンテンツのブランディングの読み取り、作成、編集、削除。</li> <li>**[!DNL Manage PTR records]**：PTR レコードの読み取りと編集。</li> <li>**[!DNL Manage SMS settings]**：SMS 設定の読み取り、作成、編集、削除。</li> <li>**[!DNL Manage subdomains delegation]**：サブドメインデリゲーションの読み取り、作成、編集、削除。</li> <li>**[!DNL Manage suppression rules]**：抑制ルールの読み取り、作成、編集、削除へのアクセス。</li> <li>**[!DNL View PTR records]**：PTR レコードへの読み取り専用アクセス。</li> <li>**[!DNL View suppression list]**：ローカル抑制リストの読み取り、エクスポート。</li> </ul> |
| 意思決定管理 | <ul><li>**[!DNL Manage decisions]**：決定の読み取り、作成、編集、削除。</li><li>**[!DNL Manage ranking strategies]**：ランキング戦略を読み取り、作成、編集および削除します。</li></ul> |

## [!DNL Campaign Approver] {#campaign-approver}

**[!DNL Campaign Approver]** の役割を使用すると、ユーザーは配信を承認および公開できます。 後から **[!DNL Campaigns]** レポートで配信の成功を確認できます。

| リソース | 権限 |
|-|-|
| Adobe Experience Platform | <ul><li>**[!DNL Manage merge policies]**：結合ポリシーの読み取り、作成、編集、削除。</li><li>**[!DNL Manage segments]**：セグメント定義の読み取り、作成、編集、削除。</li><li>**[!DNL Manage profiles]**：プロファイルの読み取り、作成、編集、削除。</li><li>**[!DNL View datasets]**：データセットへの読み取り専用アクセス。</li><li>**[!DNL View schemas]**：スキーマへの読み取り専用アクセス。</li></ul> |
| キャンペーン | <ul><li>**[!DNL Manage campaigns]**：キャンペーンの読み取り、作成、編集、削除。</li><li>**[!DNL Publish campaigns]**：キャンペーンの公開。</li><li>**[!DNL View campaigns report]**：キャンペーンレポートの読み取り、編集。</li></ul> |
| チャネル設定 | <ul><li>**[!DNL View messages presets]**：メッセージプリセットへの読み取り専用アクセス。</li></ul> |
| 意思決定管理 | <ul><li>**[!DNL Manage decisions]**：決定エンティティの読み取り、作成、編集、削除。</li><li>**[!DNL Manage ranking strategies]**：カスタムメッセージレポートの読み取り、作成、編集、削除を行い、アクション機能を使用する。</li></ul> |


## [!DNL Campaign Manager] {#campaign-manager}

**[!DNL Campaign Manager]** の役割を持つユーザーは、**[!UICONTROL キャンペーン]**&#x200B;と、**[!UICONTROL キャンペーン]**&#x200B;にリンクされたすべての機能を作成および編集できますが、公開はできません。

この役割には、次の権限が含まれます。

| リソース | 権限 |
|-|-|
| Adobe Experience Platform | <ul><li>**[!DNL Manage merge policies]**：結合ポリシーの読み取り、作成、編集、削除。</li><li>**[!DNL Manage profiles]**：プロファイルの読み取り、作成、編集、削除。</li><li> **[!DNL Manage segments]**：セグメント定義の読み取り、作成、編集、削除。</li><li>**[!DNL View datasets]**：データセットへの読み取り専用アクセス。</li><li>**[!DNL View schemas]**：スキーマへの読み取り専用アクセス。</li></ul> |
| キャンペーン | <ul><li>**[!DNL Manage campaigns]**：キャンペーンの読み取り、作成、編集、削除。</li><li>**[!DNL View campaigns report]**：ジャーニーレポートの読み取り、編集。</li></ul> |
| チャネル設定 | <ul><li>**[!DNL View messages presets]**：メッセージプリセットへの読み取り専用アクセス。</li></ul> |
| 意思決定管理 | <ul><li>**[!DNL Manage decisions]**：決定エンティティの読み取り、作成、編集、削除。</li><li>**[!DNL Manage ranking strategies]**：カスタムメッセージレポートの読み取り、作成、編集、削除を行い、アクション機能を使用する。</li></ul> |

## [!DNL Campaign Viewer] {#campaign-viewer}

**[!DNL Campaign Viewer]** の役割を持つユーザーは、**[!UICONTROL キャンペーン]**&#x200B;および&#x200B;**[!UICONTROL 意思決定管理]**&#x200B;の機能に読み取り専用でアクセスできます。

この役割に割り当てられたユーザーは、編集または公開はできません。

この役割には、次の権限が含まれます。

| リソース | 権限 |
|-|-|
| キャンペーン | <ul><li>**[!DNL View campaigns]**：キャンペーンへの読み取り専用アクセス。</li><li>**[!DNL View campaigns report]**：キャンペーンレポートへの読み取り専用アクセス。</li></ul> |
| 意思決定管理 | <ul><li>**[!DNL View decisions]**：決定エンティティへの読み取り専用アクセス。</li></ul> |

## [!DNL Content Library Manager] {#content-library-manager}

**[!DNL Content Library Manager]** の役割では、**[!UICONTROL コンテンツテンプレート]**&#x200B;メニューへのアクセスのみが許可されます。 この役割に割り当てられたユーザーは、ジャーニーやキャンペーンにアクセスせずにコンテンツを作成するテンプレートライブラリにのみアクセスできます。

この権限には、次の権限が含まれます。

| 機能 | 権限 |
|-|-|
| Adobe Experience Platform | <ul><li>**[!DNL Manage merge policies]**：結合ポリシーの読み取り、作成、編集、削除。</li><li>**[!DNL Manage profiles]**：プロファイルの読み取り、作成、編集、削除。</li><li> **[!DNL Manage segments]**：セグメント定義の読み取り、作成、編集、削除。</li><li>**[!DNL View datasets]**：データセットへの読み取り専用アクセス。</li><li>**[!DNL View schemas]**：スキーマへの読み取り専用アクセス。</li></ul> |
| 意思決定管理 | <ul><li>**[!DNL Manage decisions]**：決定エンティティの読み取り、作成、編集、削除。</li><li>**[!DNL Manage ranking strategies]**：カスタムレポートの読み取り、作成、編集および削除、アクション機能の使用。</li></ul> |
| Journey Optimizer ライブラリ | <ul><li>**[!DNL Manage library items]**：コンテンツテンプレートやフラグメントを含む、Journey Optimizer ライブラリの項目の読み取り、作成、編集、削除。</li><li>**[!DNL Manage simulate content]**：プレビューおよび配達確認用に「**[!UICONTROL コンテンツをシミュレート]**」オプションへのアクセス。</li><li>**[!DNL Publish Fragment]**：コンテンツフラグメントを公開します。</li></ul> |

## [!DNL Decisioning manager] {#decisioning-manager}

**[!DNL Decisioning manager]** の役割では、**[!UICONTROL 意思決定管理]**&#x200B;メニューへのアクセスのみが許可されます。 この役割に割り当てられたユーザーは、決定の管理、表示および公開のみを実行できます。

この権限には、次の権限が含まれます。

| 機能 | 権限 |
|-|-|
| 意思決定管理 | <ul><li>**[!DNL Manage decisions]**：決定エンティティの読み取り、作成、編集、削除。</li><li>**[!DNL Manage ranking strategies]**：カスタムレポートの読み取り、作成、編集および削除、アクション機能の使用。</li><li>**[!DNL View decisions]**：決定エンティティへの読み取り専用アクセス。</li><li>**[!DNL Publish decisions]**：決定アクティビティのアクティブ化または非アクティブ化。</li><!--li>**[!DNL Manage Experience decisions]**: read, create, edit, and delete Decisioning entities.</li--></ul> |

## [!DNL Journey Administrator] {#journey-administrator}

**[!DNL Journey Administrator]** の役割を持つユーザーは、管理メニューでジャーニーおよび意思決定管理を管理および公開できます。

この役割には、次の権限が含まれます。

| リソース | 権限 |
|-|-|
| Adobe Experience Platform | <ul> <li>**[!DNL Manage merge policies]**：結合ポリシーの読み取り、作成、編集、削除。</li> <li>**[!DNL Manage profiles]**：プロファイルの読み取り、作成、編集、削除。</li> <li>**[!DNL Manage segments]**：セグメント定義の読み取り、作成、編集、削除。</li> <li>**[!DNL View datasets]**：データセットへの読み取り専用アクセス。</li> <li>**[!DNL Read Identity namespace]**：ID 名前空間への読み取り専用アクセス。</li> <li>**[!DNL View schemas]**：スキーマへの読み取り専用アクセス。</li> <li>**[!DNL Sandbox]**：サンドボックスへのアクセスの許可。</li> </ul> |
| チャネル設定 | <ul> <li>**[!DNL Manage alerts]**：ジャーニーおよび使用権限に関するアラートの有効化／無効化。</li> <li>**[!DNL Manage IP pools]**：IP プールの読み取り、作成、編集、削除。</li> <li>**[!DNL Manage Landing page settings]**：ランディングページのサブドメインとランディングページのプリセットの作成、編集、削除。</li> <li>**[!DNL Manage messages general settings]**：メッセージの一般設定の読み取り、作成、編集、削除。</li> <li>**[!DNL Manage messages presets]**：コンテンツのブランディングの読み取り、作成、編集、削除。</li> <li>**[!DNL Manage PTR records]**：PTR レコードの読み取りと編集。</li> <li>**[!DNL Manage SMS settings]**：SMS チャネルを有効にする必要な API 資格情報と SMS チャネル設定の作成、編集、削除。</li> <li>**[!DNL Manage subdomains delegation]**：サブドメインデリゲーションの読み取り、作成、編集、削除。</li> <li>**[!DNL Manage suppression rules]**：抑制ルールの読み取り、作成、編集、削除へのアクセス。</li> <li>**[!DNL View PTR records]**：PTR レコードへの読み取り専用アクセス。</li> <li>**[!DNL View suppression list]**：ローカル抑制リストの読み取り、エクスポート。</li> </ul> |
| データガバナンス | <ul> <li>**[!DNL Manage data usage policies]**：データ使用ポリシーの読み取り、作成、編集、削除。</li> <li>**[!DNL Manage usage label]**：使用ラベルの読み取り、作成、削除</li> <li>**[!DNL View data usage policies]**：データ使用ポリシーへの読み取り専用アクセス。</li> <li>**[!DNL View user activity log]**：Experience Platform のアクティビティを記録した監査ログを表示する読み取り専用アクセス。</li> </ul> |
| 意思決定管理 | <ul> <li>**[!DNL Manage decisions]**：決定の読み取り、作成、編集、削除。</li> <li>**[!DNL Manage ranking strategies]**：ランキング戦略を読み取り、作成、編集および削除します。</li> </ul> |
| ジャーニー | <ul> <li>**[!DNL Manage journeys]**: ジャーニーの読み取り、作成、編集、停止（ライブ、テストモード、ドライ実行）および削除。 </li> <li>**[!DNL Manage journeys events, data sources and actions]**：イベント、ソース、アクションの読み取り、作成、編集、削除。</li> <li>**[!DNL Publish journeys]**：公開、テストモードの開始、ドライ実行の開始、ジャーニーの一時停止および再開。 </li> <li>**[!DNL View journeys report]**：ジャーニーレポートの読み取り、編集。</li> </ul> |
| Journey Optimizer ライブラリ | <ul> <li>**[!DNL Manage Library Items]**：[!DNL Journey Optimizer] ライブラリ内の保存済み式の追加、削除。</li> </ul> |

## [!DNL Journey Approver] {#journey-approver}

**[!DNL Journey Approver]** の役割を使用すると、ユーザーは配信を承認および公開できます。 後から **[!DNL Journey]** レポートで配信の成功を確認できます。

この役割には、次の権限が含まれます。

| リソース | 権限 |
|-|-|
| Adobe Experience Platform | <ul><li>**[!DNL Manage merge policies]**：結合ポリシーの読み取り、作成、編集、削除。</li><li>**[!DNL Manage profiles]**：プロファイルの読み取り、作成、編集、削除。</li><li>**[!DNL Manage segments]**：セグメント定義の読み取り、作成、編集、削除。</li><li>**[!DNL View datasets]**：データセットへの読み取り専用アクセス。</li><li>**[!DNL View schemas]**：スキーマへの読み取り専用アクセス。</li></ul> |
| チャネル設定 | <ul><li>**[!DNL View channel configurations]**：チャネル設定への読み取り専用アクセス。</li></ul> |
| 意思決定管理 | <ul><li>**[!DNL Manage decisions]**：決定エンティティの読み取り、作成、編集、削除。</li><li>**[!DNL Manage ranking strategies]**：カスタムレポートの読み取り、作成、編集および削除、アクション機能の使用。</li></ul> |
| ジャーニー | <ul><li>**[!DNL Manage journeys]**: ジャーニーの読み取り、作成、編集、停止（ライブ、テストモード、ドライ実行）および削除。 </li><li>**[!DNL Publish journey]**：公開、テストモードの開始、ドライ実行の開始、ジャーニーの一時停止および再開。 </li><li>**[!DNL View journeys events, data sources and actions]**：ジャーニーイベント、ジャーニーカスタムアクション、ジャーニーデータソースへの読み取り専用アクセス。</li><li>**[!DNL View journeys report]**:ジャーニーレポートの読み取り、編集。</li></ul> |

## [!DNL Journey Manager] {#journey-manager}

**[!DNL Journey Manager]** の役割を持つユーザーは、**[!UICONTROL ジャーニー]**&#x200B;と、**[!UICONTROL ジャーニー]**&#x200B;にリンクされたすべての機能を作成および編集できますが、公開はできません。

この役割には、次の権限が含まれます。

| リソース | 権限 |
|-|-|
| Adobe Experience Platform | <ul><li>**[!DNL Manage merge policies]**：結合ポリシーの読み取り、作成、編集、削除。</li><li>**[!DNL Manage profiles]**：プロファイルの読み取り、作成、編集、削除。</li><li> **[!DNL Manage segments]**：セグメント定義の読み取り、作成、編集、削除。</li><li>**[!DNL View datasets]**：データセットへの読み取り専用アクセス。</li><li>**[!DNL View schemas]**：スキーマへの読み取り専用アクセス。</li></ul> |
| チャネル設定 | <ul><li>**[!DNL View channel configurations]**：チャネル設定への読み取り専用アクセス。</li></ul> |
| 意思決定管理 | <ul><li>**[!DNL Manage decisions]**：決定エンティティの読み取り、作成、編集、削除。</li><li>**[!DNL Manage ranking strategies]**：カスタムレポートの読み取り、作成、編集および削除、アクション機能の使用。</li></ul> |
| ジャーニー | <ul><li>**[!DNL Manage journeys]**: ジャーニーの読み取り、作成、編集、停止（ライブ、テストモード、ドライ実行）および削除。</li><li>**[!DNL View journeys events]**：ジャーニーイベント、ジャーニーカスタムアクション、ジャーニーデータソースへの読み取り専用アクセス。</li><li>**[!DNL View journeys report]**：ジャーニーレポートの読み取り、編集。</li></ul> |

## [!DNL Journey Viewer] {#journey-viewer}

**[!DNL Journey viewer]** の役割を持つユーザーは、**[!UICONTROL ジャーニー]**&#x200B;および&#x200B;**[!UICONTROL 意思決定管理]**&#x200B;の機能に読み取り専用でアクセスできます。

この役割に割り当てられたユーザーは、編集または公開はできません。

この役割には、次の権限が含まれます。

| リソース | 権限 |
|-|-|
| 意思決定管理 | <ul><li>**[!DNL View decisions]**：決定エンティティへの読み取り専用アクセス。</li></ul> |
| ジャーニー | <ul><li>**[!DNL View journeys]**：ジャーニーへの読み取り専用アクセス。</li><li>**[!DNL View journeys event, data sources, actions]**：ジャーニーイベントおよびデータソースへの読み取り専用アクセス。</li><li>**[!DNL View journeys report]**：ジャーニーレポートへの読み取り専用アクセス。</li></ul> |

## [!DNL Orchestrated Campaign Administrators] {#orchestrated-campaign-administrator}

**[!DNL Orchestrated Campaign Administrator]** の役割を持つユーザーは、管理メニューで調整されたキャンペーンを管理および公開できます。

この役割には、次の権限が含まれます。

| リソース | 権限 |
|-|-|
| Adobe Experience Platform | <ul> <li>**[!DNL Enable AI Assistant]**：AI を活用したキャンペーンおよびオーディエンス機能の有効化またはアクセス。</li> <li>**[!DNL Manage merge policies]**：結合ポリシーの読み取り、作成、編集、削除。</li> <li>**[!DNL Manage profiles]**：プロファイルの読み取り、作成、編集、削除。</li> <li>**[!DNL Manage segments]**：セグメント定義の読み取り、作成、編集、削除。</li> <li>**[!DNL View datasets]**：データセットへの読み取り専用アクセス。</li> <li>**[!DNL Read Identity namespace]**：ID 名前空間への読み取り専用アクセス。</li> <li>**[!DNL View schemas]**：スキーマへの読み取り専用アクセス。</li> <li>**[!DNL Sandbox]**：サンドボックスへのアクセスの許可。</li> <li>**[!DNL View operational insights]**：システムレベルのインサイトおよび監視ダッシュボードへの読み取り専用アクセス。</li></ul> |
| チャネル設定 | <ul><li>**[!DNL Export suppression list]**：抑制リストを CSV ファイルとしてエクスポートするためのアクセス権。</li> <li>**[!DNL Manage alerts]**：キャンペーン、メッセージ、権限に関するアラートの有効化／無効化。</li> <li>**[!DNL Manage custom dashboards]**：カスタムダッシュボードの読み取り、作成、編集、削除。</li><li>**[!DNL Manage IP pools]**：IP プールの読み取り、作成、編集、削除。</li> <li>**[!DNL Manage landing page settings]**：ランディングページ設定の読み取り、作成、編集、削除。</li> <li>**[!DNL Manage messages general settings]**：メッセージの一般設定の読み取り、作成、編集、削除。</li> <li>**[!DNL Manage messages presets]**：コンテンツのブランディングの読み取り、作成、編集、削除。</li><li>**[!DNL Manage PTR records]**：PTR レコードの読み取りと編集。</li> <li>**[!DNL Manage SMS settings]**：SMS 設定の読み取り、作成、編集、削除。</li> <li>**[!DNL Manage subdomains delegation]**：サブドメインデリゲーションの読み取り、作成、編集、削除。</li> <li>**[!DNL Manage suppression rules]**：抑制ルールの読み取り、作成、編集、削除へのアクセス。</li> <li>**[!DNL View PTR records]**：PTR レコードへの読み取り専用アクセス。</li> <li>**[!DNL View suppression list]**：ローカル抑制リストの読み取り、エクスポート。</li> </ul> |
| ダッシュボード | <ul> <li>**[!DNL Manage standard dashboard]**：ウィジェットライブラリを使用したカスタムウィジェットおよびウィジェットスキーマの読み取り、作成、編集、削除。</li> </ul> |
| データガバナンス | <ul> <li>**[!DNL View user activity log]**：Experience Platform のアクティビティを記録した監査ログを表示する読み取り専用アクセス。 </li> </ul> |
| データ取り込み | <ul> <li>**[!DNL Manage sources]**：ソースの読み取り、作成、編集、無効化。</li> </ul> |
| データ管理 | <ul> <li>**[!DNL Manage datasets]**：データセットの読み取り、作成、編集、削除。</li> </ul> |
| データモデリング | <ul> <li>**[!DNL Manage schemas]**：スキーマと関連リソースの読み取り、作成、編集、削除。</li> </ul> |
| 意思決定管理 | <ul><li>**[!DNL Manage decisions]**：決定の読み取り、作成、編集、削除。</li><li>**[!DNL Manage ranking strategies]**：ランキング戦略を読み取り、作成、編集および削除します。</li></ul> |
| Journey Optimizer ルール | <ul> <li>**[!DNL View frequency rules]**：頻度ルールへの読み取り専用アクセス。</li><li>**[!DNL Manage frequency rules]**：頻度ルールの読み取り、作成、編集、削除。</li> </ul> |
| メッセージ | <ul><li> **[!DNL Manage Messages]**：メッセージの読み取り、作成、編集、削除。 </li> **[!DNL Manage Messages Preview and Test]**：ポリシーが適用された際のメッセージの承認、公開。</li><li>**[!DNL Publish Messages]**：メッセージの公開。 </li><li>**[!DNL View Messages Report]**：メッセージレポートの読み取り、編集。 <li></ul> |
| オーケストレーションキャンペーン | <ul><li> **[!DNL Manage orchestrated campaigns]**：調整されたキャンペーンの読み取り、作成、編集、削除。</li> <li>**[!DNL Manage orchestrated campaigns admin]**：Adobe Experience Platform プロファイルとリレーショナルストアエンティティ間のリンクと紐付けの読み取り、作成、編集、削除。</li><li>**[!DNL Publish orchestrated campaigns]**：調整されたキャンペーンの公開。</li><li>**[!DNL View orchestrated campaigns report]**：調整されたキャンペーンレポートの読み取り、編集。</li></ul> |

## [!DNL Orchestrated Campaign Approver] {#orchestrated-campaign-approver}

**[!DNL Orchestrated Campaign Approver]** の役割を持つユーザーは、調整されたキャンペーンを公開できます。

| リソース | 権限 |
|-|-|
| Adobe Experience Platform | <ul> <li>**[!DNL Manage segments]**：セグメント定義の読み取り、作成、編集、削除。</li> <li>**[!DNL Manage profiles]**：プロファイルの読み取り、作成、編集、削除。</li> <li>**[!DNL View datasets]**：データセットへの読み取り専用アクセス。</li> <li>**[!DNL View schemas]**：スキーマへの読み取り専用アクセス。</li> <li>**[!DNL Manage merge policies]**：結合ポリシーの読み取り、作成、編集、削除。</li> <li>**[!DNL Enable AI Assistant]**：AI を活用したキャンペーンおよびオーディエンス機能の有効化またはアクセス。</li>  <li>**[!DNL View operational insights]**：システムレベルのインサイトおよび監視ダッシュボードへの読み取り専用アクセス。</li></ul> |
| チャネル設定 | <ul><li>**[!DNL View messages presets]**：メッセージプリセットへの読み取り専用アクセス。</li> <li>**[!DNL Manage custom dashboards]**：カスタムダッシュボードの作成、編集、削除。</li></ul> |
| ダッシュボード | <ul> <li>**[!DNL Manage standard dashboard]**：ウィジェットライブラリを使用したカスタムウィジェットおよびウィジェットスキーマの読み取り、作成、編集、削除。</li> </ul> |
| データガバナンス | <ul> <li>**[!DNL View user activity log]**：Experience Platform のアクティビティを記録した監査ログを表示する読み取り専用アクセス。</li> </ul> |
| 意思決定管理 | <ul><li>**[!DNL Manage decisions]**：決定エンティティの読み取り、作成、編集、削除。</li><li>**[!DNL Manage ranking strategies]**：カスタムメッセージレポートの読み取り、作成、編集、削除を行い、アクション機能を使用する。</li></ul> |
| Journey Optimizer ルール | <ul> <li>**[!DNL View frequency rules]**：頻度ルールへの読み取り専用アクセス。</li></ul> |
| メッセージ | <ul><li> **[!DNL Manage Messages]**：メッセージの読み取り、作成、編集、削除。 </li> **[!DNL Manage Messages Preview and Test]**：ポリシーが適用された際のメッセージの承認、公開。</li><li>**[!DNL Publish Messages]**：メッセージの公開。 </li><li>**[!DNL View Messages Report]**：メッセージレポートの読み取り、編集。 <li></ul> |
| オーケストレーションキャンペーン | <ul><li>**[!DNL Manage orchestrated campaigns]**：調整されたキャンペーンの読み取り、作成、編集、削除。</li><li>**[!DNL Publish orchestrated campaigns]**：調整されたキャンペーンの公開。</li><li>**[!DNL View orchestrated campaigns admin]**：Adobe Experience Platform プロファイルとリレーショナルストアエンティティ間のリンクと紐付けへの読み取り専用アクセス。</li><li>**[!DNL View orchestrated campaigns report]**：調整されたキャンペーンレポートの読み取り、編集。</li></ul> |

## [!DNL Orchestrated Campaign Manager] {#orchestrated-campaign-manager}

**[!DNL Orchestrated Campaign Manager]** の役割を持つユーザーは、**[!UICONTROL 調整されたキャンペーン]**、および&#x200B;**[!UICONTROL 調整されたキャンペーン]**&#x200B;にリンクされたすべての機能を作成および編集できますが、公開はできません。

この役割には、次の権限が含まれます。

| リソース | 権限 |
|-|-|
| Adobe Experience Platform | <ul><li>**[!DNL Enable AI Assistant]**：AI を活用したキャンペーンおよびオーディエンス機能の有効化またはアクセス。</li> <li>**[!DNL Manage merge policies]**：結合ポリシーの読み取り、作成、編集、削除。</li><li>**[!DNL Manage profiles]**：プロファイルの読み取り、作成、編集、削除。</li><li> **[!DNL Manage segments]**：セグメント定義の読み取り、作成、編集、削除。</li><li>**[!DNL View datasets]**：データセットへの読み取り専用アクセス。</li>  <li>**[!DNL View operational insights]**：システムレベルのインサイトおよび監視ダッシュボードへの読み取り専用アクセス。</li><li>**[!DNL View schemas]**：スキーマへの読み取り専用アクセス。</li></ul> |
| チャネル設定 | <ul><li>**[!DNL Manage custom dashboards]**：カスタムダッシュボードの作成、編集、削除。</li><li>**[!DNL View messages presets]**：メッセージプリセットへの読み取り専用アクセス。</li></ul> |
| ダッシュボード | <ul> <li>**[!DNL Manage standard dashboard]**：ウィジェットライブラリを使用したカスタムウィジェットおよびウィジェットスキーマの読み取り、作成、編集、削除。</li> </ul> |
| データガバナンス | <ul> <li>**[!DNL View user activity log]**：Experience Platform のアクティビティを記録した監査ログを表示する読み取り専用アクセス。</li> </ul> |
| 意思決定管理 | <ul><li>**[!DNL Manage decisions]**：決定エンティティの読み取り、作成、編集、削除。</li><li>**[!DNL Manage ranking strategies]**：カスタムメッセージレポートの読み取り、作成、編集、削除を行い、アクション機能を使用する。</li></ul> |
| Journey Optimizer ルール | <ul> <li>**[!DNL View frequency rules]**：頻度ルールへの読み取り専用アクセス。 </li></ul> |
| メッセージ | <ul><li> **[!DNL Manage Messages]**：メッセージの読み取り、作成、編集、削除。 </li> **[!DNL Manage Messages Preview and Test]**：ポリシーが適用された際のメッセージの承認、公開。</li><li>**[!DNL View Messages Report]**：メッセージレポートの読み取り、編集。 </li></ul> |
| オーケストレーションキャンペーン | <ul><li>**[!DNL Manage orchestrated campaigns]**：調整されたキャンペーンの読み取り、作成、編集、削除。</li><li>**[!DNL View orchestrated campaigns report]**：調整されたキャンペーンの読み取り、編集。</li><li>**[!DNL View orchestrated campaigns admin]**：Adobe Experience Platform プロファイルとリレーショナルストアエンティティ間のリンクと紐付けへの読み取り専用アクセス。</li></ul> |

## [!DNL Orchestrated Campaign Viewer] {#orchestrated-campaign-viewer}

**[!DNL Campaign Viewer]** の役割では、**[!UICONTROL 調整されたキャンペーン]**&#x200B;の機能に読み取り専用でアクセスできます。

この役割に割り当てられたユーザーは、編集または公開はできません。

この役割には、次の権限が含まれます。

| リソース | 権限 |
|-|-|
| Adobe Experience Platform | <ul><li>**[!DNL Enable AI Assistant]**：AI を活用したキャンペーンおよびオーディエンス機能の有効化またはアクセス。</li> <li>**[!DNL View operational insights]**：システムレベルのインサイトおよび監視ダッシュボードへの読み取り専用アクセス。</li></ul> |
| チャネル設定 | <ul><li>**[!DNL Manage custom dashboards]**：カスタムダッシュボードの作成、編集、削除。</li></ul> |
| ダッシュボード | <ul> <li>**[!DNL Manage standard dashboard]**：ウィジェットライブラリを使用したカスタムウィジェットおよびウィジェットスキーマの読み取り、作成、編集、削除。</li> </ul> |
| データガバナンス | <ul> <li>**[!DNL View user activity log]**：Experience Platform のアクティビティを記録した監査ログを表示する読み取り専用アクセス。</li> </ul> |
| 意思決定管理 | <ul><li>**[!DNL View decisions]**：決定エンティティへの読み取り専用アクセス。</li></ul> |
| Journey Optimizer ルール | <ul> <li>**[!DNL View frequency rules]**：頻度ルールへの読み取り専用アクセス。</li></ul> |
| オーケストレーションキャンペーン | <ul><li>**[!DNL View orchestrated campaigns]**：調整されたキャンペーンへの読み取り専用アクセス。</li><li>**[!DNL View orchestrated campaigns report]**：調整されたキャンペーンレポートへの読み取り専用アクセス。</li></ul> |

+++ AI ナレッジリファレンス

このセクションには、このトピックに関連する解釈、検索、質問への回答をサポートすることを目的とした構造化された知識が含まれています。

理解を深めるには、この情報をこのページのドキュメントと組み合わせる必要があります。 どちらのソースも単独で使用することを意図していません。このページでは、機能について説明しますが、この節では、用語、意図、適用可能性、および制約の曖昧さを解消するのに役立つ追加のコンテキストを提供します。

* **TL;DR:** Journey Optimizerには、Campaign AdministratorからOrchestrated Campaign Viewerまで、既製の権限セットが組み込まれているため、管理者はゼロからロールを作成することなく、ユーザーの責任に合ったレベルのアクセス権をすばやく付与できます。

**インテント：**

* ユーザーの担当業務に最も適した組み込み役割を特定する
* 各ビルトインロールで実行できる操作と実行できない操作（パブリッシュ権限を含む）を理解する
* ジャーニー、キャンペーン、オーケストレーションされたキャンペーン領域をまたいで役割を比較
* カスタム役割を作成する代わりに、既製の役割を割り当てる
* AI アシスタントへのアクセス権を含む役割を理解する

**用語集：**

* **組み込みの役割**: カスタム設定なしでユーザーに割り当てることができる、事前定義済みの権限とリソース権限のセット *（製品固有）*
* **ジャーニー管理者**: チャネル設定およびデータガバナンス権限&#x200B;*（製品固有）*&#x200B;を含む、ジャーニーと意思決定管理の管理と公開を可能にする組み込みの役割
* **キャンペーン管理者**: チャネル設定&#x200B;*（製品固有）*&#x200B;を含む、キャンペーンと意思決定管理の管理と公開を可能にする組み込みの役割
* **Decisioning manager**：意思決定管理メニューにのみアクセスできる組み込みの役割。決定を管理、表示、公開できます&#x200B;*（製品固有）*
* **コンテンツライブラリマネージャー**: コンテンツテンプレートメニューのみにアクセスできる組み込み役割。ジャーニーまたはキャンペーンにアクセスできません&#x200B;*（製品固有）*
* **テストモード**: ジャーニーの管理およびジャーニーの公開権限で参照されるジャーニー実行モード （ジャーニー管理者はテストモードでジャーニーを停止できます。ジャーニーの公開権限にはテストモードの開始が含まれます） *（製品固有）*
* **ドライラン**: ジャーニーの管理およびジャーニーの公開の権限で参照されているジャーニー実行モードが、テストモード *（製品固有）*&#x200B;と共に表示されます

**用語：**

* 正規名：組み込みロール – バリエーション：すぐに使えるロール、OOTB ロール、製品プロファイル
* 混乱しないでください：「キャンペーン承認者」（キャンペーンの承認と公開が可能）≠「キャンペーンマネージャー」（キャンペーンの作成と編集は可能ですが、公開はできません）
* 「ジャーニー承認者」（ジャーニーを承認および公開できる）≠「ジャーニー管理者」（ジャーニーを作成および編集できますが、公開できません）は混同しないでください
* 混同しないでください。「ジャーニービューア」（ジャーニーおよび意思決定管理への読み取り専用アクセス）≠「キャンペーンビューア」（キャンペーンおよび意思決定管理への読み取り専用アクセス）
* 混乱しないでください：「オーケストレーションされたキャンペーン管理者」（オーケストレーションされたキャンペーンを管理し、AI アシスタントとデータの取り込み/管理を含む）≠「キャンペーン管理者」（標準キャンペーンを管理し、オーケストレーションされたキャンペーン権限を含まない）
* 混乱しないでください：「テストモード」（ジャーニーの管理/ジャーニーの公開を介して停止または開始できるジャーニー実行状態として参照）≠「ドライラン」（同じ権限でも参照される別のジャーニー実行モード）

**FAQ:**

* **Q: ジャーニーを公開できる組み込みロールはどれですか？** — ジャーニー管理者とジャーニー承認者は、ジャーニーを公開できます。
* **Q: ジャーニーマネージャーはジャーニーを公開できますか？**  – いいえ。ジャーニーマネージャーはジャーニーを作成および編集できますが、「ジャーニーを公開」権限はその役割に含まれません。
* **Q：意思決定管理メニューのみにアクセス権を付与する役割はどれですか？** — Decisioning マネージャー。
* **Q: コンテンツテンプレートのみにアクセスできる役割はどれですか？** — コンテンツライブラリマネージャー。
* **Q: AI アシスタントを有効にする権限を含む組み込みロールはどれですか？** - オーケストレーションされたキャンペーン管理者、オーケストレーションされたキャンペーン承認者、オーケストレーションされたキャンペーンマネージャー、およびオーケストレーションされたキャンペーンビューア。

+++
<!-- ai-accordion-version: 1 | source-hash: b9740765 -->




