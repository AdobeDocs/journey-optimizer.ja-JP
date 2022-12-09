---
solution: Journey Optimizer
product: journey optimizer
title: 関連するオプティマイザーリソースに対する操作の監査
description: 旅のオプティマイザーリソースに対して実行されたアクションを追跡する方法について説明します。
feature: Monitoring
role: User
level: Intermediate
exl-id: 759b014a-c834-4331-bffd-5bc159ec555d
source-git-commit: 63c52f04da9fd1a5fafc36ffb5079380229f885e
workflow-type: tm+mt
source-wordcount: '289'
ht-degree: 0%

---

# 関連するオプティマイザーリソースに対する操作の監査 {#track-changes}

## 監査ログについて {#audit-logs}

このような旅により、システムのユーザーが実行した操作は、journeys、メッセージ、ランディングページなどの様々なサービスと機能によって識別できます。

これにより、システムで実行されたアクティビティの可視性が向上します。問題が解決され、ビジネスにおける規制や企業データ管理方針の順守が容易になります。

各アクションは、Adobe エクスペリエンスプラットフォームでアクセス可能な「監査ログ」にメタデータと共に記録されます。 監査ログの詳細については、「Adobe エクスペリエンス統合ガイド ](https://experienceleague.adobe.com/docs/experience-platform/landing/governance-privacy-security/audit-logs/overview.html) 」を [ 参照してください。

![](assets/audit-logs.png)

## 監査ログによってキャプチャされたイベントタイプ {#events}

以下の表は、監査ログによって、旅オプティマイザーのリソースが記録されるアクションを示しています。

>[!NOTE]
>
>監査ログに記録されているすべてのアクションのリストは、Adobe エクスペリエンスプラットフォーム ](https://experienceleague.adobe.com/docs/experience-platform/landing/governance-privacy-security/audit-logs/overview.html#category) で [ 利用できます。

| リソース | アクション |
|-----------|------------------|
| AJO キャンペーン | 作成/削除/更新/アクティブ化/停止 |
| AJO チャネル全般設定 | 作成/削除/更新 |
| AJO IP プールの管理 | 作成/削除/更新 |
| AJO ランディングページ | 作成、削除、更新、パブリッシュ、未発行 |
| AJO ランディングページの HTML テンプレート | 作成/削除/更新 |
| AJO ランディングページのプリセット | 作成/削除/更新 |
| AJO ランディングページサブドメイン | 作成/削除/更新 |
| AJO メッセージの表示 | 作成/削除/更新/パブリッシュ |
| AJO メッセージプリセット | 作成/削除/更新 |
| AJO PTR レコード | 作成/削除/更新 |
| AJO 保存された式テンプレート | 作成/削除/更新 |
| AJO SMS API の資格情報 | 作成/削除/更新 |
| AJO サブドメイン | 作成/削除/更新 |
| AJO 抑制リスト | CSV の作成/削除/ダウンロード |
| フィールドグループ | 作成/削除/更新 |
| 旅 | 作成/削除/更新/停止/パブリッシュ |
| 旅のカスタムアクション | 作成/削除/更新 |
| 「旅のデータソース」 | 作成/削除/更新 |
| 旅イベント | 作成/削除/更新 |
| メッセージ頻度ルール | 作成/削除/更新 |
| ランク付け方針 | 作成/削除/更新 |
