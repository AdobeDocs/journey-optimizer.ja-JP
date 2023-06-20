---
solution: Journey Optimizer
product: journey optimizer
title: 組み込みの役割
description: 組み込みの権限について学ぶ
feature: Access Management
topic: Administration
role: Admin, User
level: Intermediate
keywords: 権限, オーサリング, メッセージ
exl-id: fd7a7564-bf67-4796-8182-0b9b04516f21
source-git-commit: f5b4beb327804c23e58835de3218d67f1ab4e87e
workflow-type: tm+mt
source-wordcount: '731'
ht-degree: 83%

---

# 組み込みの権限 {#ootb-permissions}

| 機能 | 権限 |
|---|---|
| アラート | **[!DNL Manage alerts]**:ジャーニーおよび権限のアラートルールを有効化/無効化します。</br>**[!DNL Resolve alerts]**：トリガーされたアラートの解決の許可。</br>**[!DNL View alerts]**：受信したアラートメッセージの表示と、「アラート」タブへのアクセスの許可。</br>**[!DNL View alerts history]**：受信したアラートの履歴の表示の許可。 |
| キャンペーン | **[!DNL Manage campaigns]**：キャンペーンの読み取り、作成、編集、削除。</br>**[!DNL Publish campaigns]**：キャンペーンを公開する権限。</br>**[!DNL View campaigns]**：キャンペーンへの読み取り専用アクセス。</br>**[!DNL View campaigns report]**：キャンペーンレポートの読み取り、編集。 |
| チャネル設定 | **[!DNL View messages general settings]**:メッセージの一般的な seting への読み取り専用アクセス。</br>**[!DNL Manage web subdomain]**：web サブドメインの読み取り、作成、編集、削除。</br>**[!DNL Manage messages general settings]**：メッセージの一般設定の読み取り、作成、編集、削除。</br>**[!DNL Manage suppression]**：抑制ルールの読み取り、作成、編集、削除。</br>**[!DNL Manage messages presets]**：コンテンツのブランディングの読み取り、作成、編集、削除。</br>**[!DNL View messages presets]**：メッセージプリセットへの読み取り専用アクセス。</br>**[!DNL Manage SMS subdomains]**：SMS サブドメインの読み取り、作成、編集、削除。</br>**[!DNL Manage subdomains delegation]**：サブドメインデリゲーションの読み取り、作成、編集、削除。</br>**[!DNL Manage IP pools]**：IP プールの読み取り、作成、編集、削除。</br>**[!DNL Manage PTR records]**：PTR レコードの読み取りと編集。</br>**[!DNL View PTR records]**：PTR レコードへの読み取り専用アクセス。</br>**[!DNL Manage channel surfaces]**：コンテンツのブランディングの読み取り、作成、編集、削除。</br>**[!DNL Manage Landing page settings]**：ランディングページのサブドメインとランディングページのプリセットの読み取り、作成、編集、削除。</br>**[!DNL Manage SMS settings]**：SMS チャネルを有効にするために必要な API 認証情報と SMS チャネルサーフェスの読み取り、作成、編集、削除。</br>**[!DNL Export suppression list]**：抑制リストを CSV として書き出すためのアクセス権。</br>**[!DNL View suppression list]**：ローカル抑制リストの読み取り、書き出し。 |
| ダッシュボード | **[!DNL View license usage dashboards]**:ライセンス使用状況ダッシュボードへの読み取り専用アクセス </br>**[!DNL Manage custom dashboards]**：新しいダッシュボードの作成と、既存のダッシュボードの編集の許可。</br>**[!DNL View custom dashboards]**：ユーザー定義ダッシュボードへの読み取り専用アクセス。</br>**[!DNL View standard dashboards]**：プロファイル、宛先、セグメントの各ダッシュボードへの読み取り専用アクセス。</br>**[!DNL Manage standard dashboards]**：カスタムウィジェットの作成と、ウィジェットライブラリを介したウィジェットスキーマの編集の許可。 |
| データ収集 | **[!DNL Manage datastream]**:データストリームの読み取り、作成および編集&#x200B;</br>**[!DNL View datastream]**：データストリームへの読み取り専用アクセス。 |
| データガバナンス | **[!DNL Manage usage labels]**:ラベルの読み取り、作成、編集、削除&#x200B;</br>**[!DNL Manage data usage policies]**：データ使用ポリシーの読み取り、作成、編集、削除。</br>**[!DNL View data usage policies]**：組織に属するデータ使用ポリシーに対する読み取り専用アクセス。</br>**[!DNL View user activity log]**：Platform のアクティビティを記録した監査ログを表示する読み取り専用アクセス。 |
| データハイジーン | **[!DNL View data hygiene]**:データの衛生状態に対する読み取り専用アクセス&#x200B;</br>**[!DNL Manage data hygiene]**：データハイジーンの読み取り、作成、編集、削除。 |
| データ取り込み | **[!DNL Manage sources]**:ソースの読み取り、作成、編集、無効化&#x200B;</br>**[!DNL View sources]**：「カタログ」タブでの使用可能なソースおよび「参照」タブでの認証済みのソースへの読み取り専用アクセス。 |
| データ管理 | **[!DNL Manage datasets]**:データセットの読み取り、作成、編集、削除を行います。 スキーマへの読み取り専用アクセス&#x200B;</br>**[!DNL View datasets]**：データセットおよびスキーマに対する読み取り専用アクセス。</br>**[!DNL Data monitoring]**：監視データセットおよびストリームへの読み取り専用アクセス。 |
| データモデリング | **[!DNL Manage schemas]**:Experience Data Model(XDM) スキーマを読み取り、作成および編集します。</br>**[!DNL View schemas]**：スキーマへの読み取り専用アクセス。</br>**[!DNL Manage relationships]**：スキーマ関係の読み取り、作成、編集、削除。</br>**[!DNL Manage identity metadata]**：スキーマの ID メタデータの読み取り、作成、編集、削除。 |
| 意思決定管理 | **[!DNL Manage decisions]**：決定エンティティの読み取り、作成、編集、削除を行う。</br>**[!DNL View decisions]**：オファーエンティティへの読み取り専用アクセス。</br>**[!DNL Manage offers]**：すべてのオファー、コンポーネント、決定およびコレクションの読み取り、作成、編集、削除。</br>**[!DNL Manage ranking strategies]**：カスタムレポートの読み取り、作成、編集および削除、アクション機能の使用。</br> |
| 宛先 | **[!DNL Manage destinations]**:宛先のアクティベーションフローと宛先アカウントを読み取り、作成、削除します。</br>**[!DNL View destinations]**：「カタログ」タブの使用可能な宛先と「参照」タブの認証済みの宛先への読み取り専用アクセス。</br>**[!DNL Activate destinations]**：ユーザーが既存の宛先に対してセグメントをアクティブ化できるようにします。</br>**[!DNL Activate segment without mapping]**：マッピングステップが表示されない状態で、ユーザーがセグメントを既存の宛先に対してアクティブ化できるようにします。ユーザーは、アクティブ化ワークフローでセグメントを追加および削除できますが、マッピングされた属性や ID を追加または削除することはできません。</br>**[!DNL Manage and activate dataset destination]**：データセット書き出しフローを読み取り、作成、編集および無効化。作成済みのアクティブなデータセットに対してデータもアクティブ化する機能。</br>**[!DNL Destination authoring]**：Adobe Experience Platform Destination SDK を使用して宛先を作成します。 |
| ID 管理 | **[!DNL Manage identity namespaces]**:id 名前空間を読み取り、作成および編集します。</br>**[!DNL View identity namespaces]**：ID 名前空間への読み取り専用アクセス。</br>**[!DNL Manage identity settings]**：ID 設定の読み取り、作成および編集。</br>**[!DNL View identity settings]**：ID 設定への読み取り専用アクセス。</br>**[!DNL View identity graph]**：ID グラフへの読み取り専用アクセス。 |
| Journey Optimizer Library | **[!DNL Manage Library Items]**：[!DNL Journey Optimizer] ライブラリ内の保存済み式の追加、削除。</br>**[!DNL Simulate content]**：プレビューおよび配達確認用に「コンテンツをシミュレート」オプションへのアクセス。 |
| Journey Optimizerルール | **[!DNL View frequency rules]**:ルールへの読み取り専用アクセス&#x200B;</br>**[!DNL Manage frequency rules]**：メッセージ頻度ルールへのアクセス、作成、編集、削除。 |
| ジャーニー | **[!DNL Manage journeys]**：ジャーニーの読み取り、作成、編集、削除。</br>**[!DNL View journeys]**：ジャーニーへの読み取り専用アクセス。</br>**[!DNL Publish journeys]**：ジャーニーの公開。</br>**[!DNL Manage journeys events, data sources and actions]**：イベント、ソース、アクションの読み取り、作成、編集、削除。</br>**[!DNL View journeys events, data sources and actions]**：ジャーニーイベント、ジャーニーカスタムアクション、ジャーニーデータソースへの読み取り専用アクセス。</br>**[!DNL View journeys report]**：ジャーニーレポートの読み取り、編集。</br>。 |
| プロファイル管理 | **[!DNL Manage profiles]**:顧客プロファイルに使用するデータセットの読み取り、作成、編集、削除 使用可能なプロファイルへの読み取り専用アクセス&#x200B;</br>**[!DNL View profiles]**：使用可能なプロファイルへの読み取り専用アクセス。</br>**[!DNL Export audience segments]**：評価済みのデータセットセグメントをオーディエンスセットに書き出します。</br>**[!DNL View segments]**：使用可能なセグメントへの読み取り専用アクセス。</br>**[!DNL Evaluate a segment to an audience]**：セグメント定義を評価して、オーディエンスのプロファイルを生成します。</br>**[!DNL Manage merge policies]**：結合ポリシーの読み取り、作成、編集、削除。</br>**[!DNL View merge policies]**：使用可能な結合ポリシーへの読み取り専用アクセス。 |
| クエリサービス | **[!DNL Manage queries]**:Platform データに対する構造化 SQL クエリを読み取り、作成、編集、削除します。</br>**[!DNL Manage query service integration]**：クエリサービスアクセスの有効期限が切れていない認証情報を作成、更新および削除。 |
| サンドボックス管理 | **[!DNL Manage sandboxes]**:サンドボックスの読み取り、作成、編集、削除&#x200B;</br>**[!DNL View sandboxes]**：組織に属するサンドボックスへの読み取り専用アクセス。</br>**[!DNL Reset sandboxes]**：サンドボックスをリセットする機能。</br>**[!DNL Export sandboxes]**:サンドボックスを書き出す機能 |

{style="table-layout:fixed"}
