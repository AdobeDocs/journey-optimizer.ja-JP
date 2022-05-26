---
title: Journey Optimizerリソースに対する監査アクション
description: Journey Optimizerリソースで実行されたアクションを追跡する方法について説明します。
feature: Monitoring
role: User
level: Intermediate
source-git-commit: 336a2a4d28ce1738cc664861291fdc1f39b3ab29
workflow-type: tm+mt
source-wordcount: '297'
ht-degree: 1%

---

# Journey Optimizerリソースに対する監査アクション {#track-changes}

## 監査ログについて {#audit-logs}

Journey Optimizerを使用すると、ジャーニー、メッセージ、ランディングページなど、様々なサービスや機能でシステム内のユーザーが実行したアクションを識別できます。

これにより、システムで実行されるアクティビティの可視性を高め、問題をトラブルシューティングし、ビジネスが規制や企業データ管理ポリシーに準拠できるようにします。

各アクションは、メタデータと共に、Adobe Experience Platformでアクセス可能な「監査ログ」に記録されます。 UI または API での監査ログの表示方法や管理方法など、監査ログについて詳しくは、 [Adobe Experience Platform ドキュメント](https://experienceleague.adobe.com/docs/experience-platform/landing/governance-privacy-security/audit-logs/overview.html).

![](assets/audit-logs.png)

## 監査ログによってキャプチャされるイベントタイプ {#events}

次の表に、監査ログでJourney Optimizerリソースが記録されるアクションの概要を示します。

>[!NOTE]
>
>監査ログでキャプチャされるアクションの完全なリストは、 [Adobe Experience Platform ドキュメント](https://experienceleague.adobe.com/docs/experience-platform/landing/governance-privacy-security/audit-logs/overview.html#category).

| リソース | アクション |
|-----------|------------------|
| フィールドグループ | 作成/削除/更新 |
| AJO サブドメイン | 作成/削除/更新 |
| CJM 抑制リスト | CSV の作成/削除/ダウンロード |
| AJO メッセージプリセット | 作成/削除/更新 |
| AJO PTR レコード | 作成/削除/更新 |
| ランキング戦略 | 作成/削除/更新 |
| ジャーニーのカスタムアクション | 作成/削除/更新 |
| AJO ランディングページHTMLテンプレート | 作成/削除/更新 |
| AJO IP プール | 作成/削除/更新 |
| AJO ランディングページサブドメイン | 作成/削除/更新 |
| AJO SMS API の資格情報 | 作成/削除/更新 |
| AJO ランディングページプリセット | 作成/削除/更新 |
| ジャーニーデータソース | 作成/削除/更新 |
| ジャーニーイベント | 作成/削除/更新 |
| AJO が保存した式テンプレート | 作成/削除/更新 |
| メッセージ頻度ルール | 作成/削除/更新 |
| AJO ランディングページ | 作成/削除/更新/公開/非公開 |
| ジャーニー | 作成/削除/更新/停止/公開 |
| AJO メッセージ | 作成/削除/更新/公開 |
| AJO チャネルの一般設定 | 作成/削除/更新 |
