---
solution: Journey Optimizer
product: journey optimizer
title: ビルトインの役割
description: ビルトインの権限について学ぶ
feature: Access Management
topic: Administration
role: Admin, User
level: Intermediate
keywords: 権限, オーサリング, メッセージ
exl-id: 5d014017-ca7c-4206-b783-989677ec0e1c
source-git-commit: 2a5db6950ac82fd18deb2e4009c9a43247444d6a
workflow-type: tm+mt
source-wordcount: '989'
ht-degree: 99%

---

# ビルトインの権限 {#ootb-permissions}

ビルトインの権限は、「**[!UICONTROL 役割]**」に割り当てることができる様々な権限を表します。これにより、Journey Optimizer へのユーザーアクセスを微調整します。高レベルの権限には、[このページ](high-low-permissions.md)で詳しく説明されている低レベルの権限が含まれます。

| 機能 | 権限 |
|-|-|
| AI アシスタント | **[!DNL Generate content]**：Journey Optimizer の AI アシスタントへのアクセス。 |
| キャンペーン | **[!DNL Approve & publish Campaigns]**：ポリシーが適用された際にキャンペーンを承認および公開する権限。</br>**[!DNL Manage campaigns]**：キャンペーンの読み取り、作成、編集、削除。</br>**[!DNL Publish campaigns]**：キャンペーンを公開する権限。</br>**[!DNL View campaigns]**：キャンペーンへの読み取り専用アクセス。</br>**[!DNL View campaigns report]**：キャンペーンレポートの読み取り、編集。 |
| チャネル設定 | **[!DNL Export suppression list]**：抑制リストを CSV ファイルとしてエクスポートするためのアクセス権。</br>**[!DNL Manage alerts]**：キャンペーン、メッセージ、権限に関するアラートの有効化／無効化。</br> **[!DNL Manage file routing]**：ファイルルーティング設定の読み取り、作成、編集、削除。</br> **[!DNL Manage IP pools]**：IP プールの読み取り、作成、編集、削除。</br>**[!DNL Manage landing page settings]**：ランディングページ設定の読み取り、作成、編集、削除。</br> **[!DNL Manage messages general settings]**：メッセージの一般設定の読み取り、作成、編集、削除。</br>**[!DNL Manage messages presets]**：コンテンツのブランディングの読み取り、作成、編集、削除。</br>**[!DNL Manage PTR records]**：PTR レコードの読み取りと編集。</br>**[!DNL Manage SMS settings]**：SMS 設定の読み取り、作成、編集、削除。</br>**[!DNL Manage SMS subdomains]**：SMS サブドメインの読み取り、作成、編集、削除。</br> **[!DNL Manage Seedlist]**：シードリストの読み取り、作成、編集、削除。</br> **[!DNL Manage subdomains delegation]**：サブドメインデリゲーションの読み取り、作成、編集、削除。</br>**[!DNL Manage suppression rules]**：抑制ルールの読み取り、作成、編集、削除へのアクセス。</br> **[!DNL View channel surfaces]**：チャネルサーフェスへの読み取り専用アクセス。</br>**[!DNL View file routing]**：ファイルルーティング設定への読み取り専用アクセス。</br>**[!DNL View messages general settings]**：メッセージの一般設定への読み取り専用アクセス。</br> **[!DNL View messages presets]**：メッセージプリセットへの読み取り専用アクセス。</br> **[!DNL View PTR records]**：PTR レコードへの読み取り専用アクセス。</br>**[!DNL View suppression list]**：ローカル抑制リストの読み取り、エクスポート。 |
| ダッシュボード | **[!DNL View license usage dashboards]**：[ライセンス使用状況ダッシュボード](../audience/license-usage.md)を表示する読み取り専用アクセス。</br>**[!DNL Manage custom dashboards]**：新しいダッシュボードの作成と、既存のダッシュボードの編集の許可。</br>**[!DNL Manage standard dashboards]**：カスタムウィジェットを作成し、ウィジェットライブラリを介したウィジェットスキーマを編集できます。</br>**[!DNL View custom dashboards]**：ユーザー定義ダッシュボードへの読み取り専用アクセス。</br>**[!DNL View standard dashboards]**：プロファイル、宛先、オーディエンスの各ダッシュボードへの読み取り専用アクセス。 |
| データ収集 | **[!DNL Manage datastream]**：データストリームの読み取り、作成、編集。</br>**[!DNL View datastream]**：データストリームへの読み取り専用アクセス。 |
| データガバナンス | **[!DNL Manage usage labels]**：ラベルの読み取り、作成、編集、削除。</br>**[!DNL Manage data usage policies]**：データ使用ポリシーの読み取り、作成、編集、削除。</br>**[!DNL View data usage policies]**：組織に属するデータ使用ポリシーに対する読み取り専用アクセス。</br>**[!DNL View user activity log]**：Platform のアクティビティを記録した監査ログを表示する読み取り専用アクセス。 |
| データライフサイクル | **[!DNL Manage data lifecycle]**：データライフサイクルの読み取り、作成、編集、削除。</br>**[!DNL View data lifecycle]**：データライフサイクルに対する読み取り専用アクセス。 |
| データ取り込み | **[!DNL Manage sources]**：ソースの読み取り、作成、編集、無効化。</br>**[!DNL View sources]**：「カタログ」タブでの使用可能なソースおよび「参照」タブでの認証済みのソースへの読み取り専用アクセス。 |
| データ管理 | **[!DNL Data monitoring]**：監視データセットおよびストリームへの読み取り専用アクセス。</br>**[!DNL Manage datasets]**：データセットの読み取り、作成、編集、削除。スキーマへの読み取り専用アクセス</br>**[!DNL View datasets]**：データセットおよびスキーマに対する読み取り専用アクセス。 |
| データモデリング | **[!DNL Manage identity metadata]**：スキーマの ID メタデータの読み取り、作成、編集および削除。</br> **[!DNL Manage relationships]**：スキーマ関係の読み取り、作成、編集、削除。</br>**[!DNL Manage schemas]**：エクスペリエンスデータモデル（XDM）スキーマの読み取り、作成、編集。</br>**[!DNL View schemas]**：スキーマへの読み取り専用アクセス。 |
| 意思決定管理 | **[!DNL Manage decisions]**：決定エンティティの読み取り、作成、編集、削除を行う。</br>**[!DNL Manage offers]**：すべてのオファー、コンポーネント、決定およびコレクションの読み取り、作成、編集、削除。</br>**[!DNL Manage ranking strategies]**：カスタムレポートの読み取り、作成、編集および削除、アクション機能の使用。</br>**[!DNL View decisions]**：オファーエンティティへの読み取り専用アクセス。<!--**[!DNL Manage Experience decisions]**: read, create, edit, and delete Decisioning entities.</br>--> |
| 宛先 | **[!DNL Activate destinations]**：ユーザーが既存の宛先に対してオーディエンスをアクティブ化できるようになります。</br>**[!DNL Activate segment without mapping]**：マッピング手順を表示せずに、ユーザーが既存の宛先に対してオーディエンスをアクティブ化できるようになります。ユーザーは、アクティベーションワークフローでオーディエンスを追加および削除できますが、マッピングされた属性や ID を追加または削除することはできません。</br>**[!DNL Destination authoring]**：Adobe Experience Platform Destination SDK を使用して宛先を作成します。</br>**[!DNL Manage and activate dataset destination]**：データセットエクスポートフローを読み取り、作成、編集および無効化。作成済みのアクティブなデータセットに対してデータもアクティブ化する機能。</br>**[!DNL Manage destinations]**：宛先アクティブ化フローと宛先アカウントの読み取り、作成および削除。</br>**[!DNL View destinations]**：「カタログ」タブの使用可能な宛先と「参照」タブの認証済みの宛先への読み取り専用アクセス。 |
| ID 管理 | **[!DNL Manage identity namespaces]**：ID 名前空間の読み取り、作成および編集。</br>**[!DNL Manage identity settings]**：ID 設定の読み取り、作成および編集。</br>**[!DNL View identity namespaces]**：ID 名前空間への読み取り専用アクセス。</br>**[!DNL View identity settings]**：ID 設定への読み取り専用アクセス。</br>**[!DNL View identity graph]**：ID グラフへの読み取り専用アクセス。 |
| IP ウォームアップ設定 | **[!DNL Manage IP warmup plans]**：IP ウォームアッププランを読み取り、作成、編集します。</br>**[!DNL View IP warmup plans]**：IP ウォームアッププランへの読み取り専用アクセス。</br>**[!DNL View IP warmup reports]**：IP ウォームアップレポートの読み取りおよび編集。 |
| Journey Optimizer ライブラリ | **[!DNL Manage Library Items]**：[!DNL Journey Optimizer] ライブラリ内の保存済み式の追加、削除。</br>**[!DNL Simulate content]**：プレビューおよび配達確認用に「コンテンツをシミュレート」オプションへのアクセス。</br>**[!DNL Publish fragments]**：コンテンツフラグメントを公開します。 |
| Journey Optimizer ルール | **[!DNL Manage frequency rules]**：メッセージ頻度ルールへのアクセス、作成、編集、削除。</br>**[!DNL View frequency rules]**：ルールへの読み取り専用アクセス。 |
| ジャーニー | **[!DNL Approve & publish Journeys]**：ポリシーが適用された際にジャーニーを承認および公開する権限。</br> **[!DNL Manage journeys]**：ジャーニーの読み取り、作成、編集、一時停止、停止、削除。 ジャーニーにアクセスして管理するには、この権限を **[!DNL View journeys events, data sources and actions]** と組み合わせます。</br>**[!DNL Manage journeys events, data sources and actions]**：イベント、ソース、アクションの読み取り、作成、編集、削除。</br>**[!DNL Publish journeys]**：ジャーニーの公開。</br>**[!DNL View journeys]**：ジャーニーへの読み取り専用アクセス。</br>**[!DNL View journeys events, data sources and actions]**：ジャーニーイベント、ジャーニーカスタムアクション、ジャーニーデータソースへの読み取り専用アクセス。</br>**[!DNL View journeys report]**：ジャーニーレポートの読み取りと編集。</br> |
| メッセージ | **[!DNL Manage messages]**：メッセージの読み取り、作成、編集、削除。</br>**[!DNL Manage messages preview and test]**：ポリシーが適用された際にメッセージを承認および公開する権限。</br>**[!DNL Publish messages]**：メッセージを公開する権限。</br>**[!DNL View messages]**：メッセージへの読み取り専用アクセス。</br>**[!DNL View messages report]**：メッセージレポートの読み取り、編集。 |
| 調整されたキャンペーン | **[!DNL Manage orchestrated campaigns]**：調整されたキャンペーンの読み取り、作成、編集、削除。</br>**[!DNL Manage orchestrated campaigns admin]**：Adobe Experience Platform プロファイルとリレーショナルストアエンティティ間のリンクと紐付けの読み取り、作成、編集、削除。</br>**[!DNL Publish orchestrated campaigns]**：調整されたキャンペーンの公開。</br>**[!DNL View orchestrated campaigns admin]**：Adobe Experience Platform プロファイルとリレーショナルストアエンティティ間のリンクと紐付けの読み取り、編集。</br>**[!DNL View orchestrated campaigns]**：調整されたキャンペーンの読み取り、編集。</br>**[!DNL View orchestrated campaigns report]**：調整されたキャンペーンレポートの読み取り、編集。 |
| プロファイル管理 | **[!DNL Evaluate a segment to an audience]**：セグメント定義を評価して、オーディエンスのプロファイルを生成します。</br>**[!DNL Export audience segments]**：評価済みのデータセットセグメントをオーディエンスセットにエクスポートします。</br>**[!DNL Manage merge policies]**：結合ポリシーの読み取り、作成、編集、削除。</br>**[!DNL Manage profiles]**：顧客プロファイルに使用するデータセットへの読み取り、作成、編集、削除。使用可能なプロファイルへの読み取り専用アクセス</br>**[!DNL View merge policies]**：使用可能な結合ポリシーへの読み取り専用アクセス。</br>**[!DNL View profiles]**：使用可能なプロファイルへの読み取り専用アクセス。</br>**[!DNL View segments]**：使用可能なオーディエンスへの読み取り専用アクセス。 |
| クエリサービス | **[!DNL Manage queries]**：Platform データの構造化 SQL クエリの読み取り、作成、編集、削除。</br>**[!DNL Manage query service integration]**：クエリサービスアクセスの有効期限が切れていない資格情報を作成、更新および削除。 |
| レポート | **[!DNL View channel reports]**：チャネルレポートの読み取り、編集。 |
| サンドボックス管理 | **[!DNL Export sandboxes]**：サンドボックスをエクスポートする機能。</br>**[!DNL Manage packages]**：パッケージの読み取り、作成、編集、および削除。</br>**[!DNL Manage sandboxes]**：サンドボックスの読み取り、作成、編集、削除。</br>**[!DNL View sandboxes]**：組織に属するサンドボックスへの読み取り専用アクセス。</br>**[!DNL Reset sandboxes]**：サンドボックスをリセットする機能。 |
| サンドボックス管理 | **[!DNL Export sandboxes]**：サンドボックスをエクスポートする機能。</br>**[!DNL Manage packages]**：パッケージの読み取り、作成、編集、および削除。</br>**[!DNL Manage sandboxes]**：サンドボックスの読み取り、作成、編集、削除。</br>**[!DNL View sandboxes]**：組織に属するサンドボックスへの読み取り専用アクセス。</br>**[!DNL Reset sandboxes]**：サンドボックスをリセットする機能。 |
| 翻訳サービス | **[!DNL Manage translation projects]**：翻訳プロジェクトの読み取り、作成、編集、削除。</br>**[!DNL View translation projects]**：翻訳プロジェクトへの読み取り専用アクセス。</br>**[!DNL Manage translation tasks]**：翻訳タスクの読み取り、作成、編集、削除。</br>**[!DNL View translation tasks]**：翻訳タスクへの読み取り専用アクセス。</br> **[!DNL Manage translation reviews]**：翻訳レビューの読み取り、作成、編集、削除。</br>**[!DNL View translation reviews]**：翻訳レビューへの読み取り専用アクセス。</br>**[!DNL Manage translation in house]**：社内翻訳の読み取り、作成、編集、削除。</br>**[!DNL View translation in house]**：社内翻訳への読み取り専用アクセス。</br>**[!DNL Manage translation settings]**：翻訳設定の読み取り、作成、編集、削除。 |

{style="table-layout:fixed"}

