---
solution: Journey Optimizer
product: journey optimizer
title: Journey Optimizer リソースに対する監査アクション
description: Journey Optimizer リソースで実行されたアクションを追跡する方法について説明します。
feature: Monitoring
role: User
level: Intermediate
exl-id: 759b014a-c834-4331-bffd-5bc159ec555d
TQID: https://experienceleague.adobe.com/Usk3qin9P4IZlKw-gEI4zaKO-aRtaKq9-0GMVlOecjA
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2:
  - id: aeebb91a-f216-4d5f-8da1-3a7e6f696ed0
  - id: bb359667-ec7d-4d4b-8663-5850fc219d32
subfeature_v2:
  - id: a9cf78bf-e9e4-4836-85a5-b6b3cf93bf56
  - id: f365ec33-2b99-4b7f-b4ee-c743dd7f615f
  - id: c8d5f2ce-ba44-43e9-a2bf-94a3d7d85ec3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 4e89993a998268ae2810c949d0669bf6dc458dd6
workflow-type: ht
source-wordcount: 380
ht-degree: 100%

---

# Journey Optimizer リソースに対する監査アクション {#track-changes}

>[!BEGINSHADEBOX]

**このページ：** Journey Optimizer リソースに対するユーザーアクションを記録する監査ログを確認します。これにより、可視性を向上させ、問題をトラブルシューティングし、規制およびデータスチュワードシップポリシーへの準拠を実証できます。

>[!ENDSHADEBOX]

## 監査ログについて {#audit-logs}

>[!IMPORTANT]
>
>監査ログを表示、エクスポートするには、**[!DNL View User Activity Log]** 権限を付与されている必要があります。 [詳細情報](../administration/ootb-product-profiles.md)

Journey Optimizer を使用すると、ジャーニー、メッセージ、ランディングページなど、様々なサービスや機能に対してシステム内のユーザーが実行したアクションを識別できます。

これにより、システムで実行されるアクティビティの可視性の向上、問題のトラブルシューティング、ビジネスの規制や企業データ管理ポリシーへの準拠が可能になります。

各アクションは、メタデータと共に、Adobe Experience Platform でアクセス可能な「監査ログ」に記録されます。 UI または API での監査ログの表示方法や管理方法など、監査ログについて詳しくは、[Adobe Experience Platform ドキュメント](https://experienceleague.adobe.com/docs/experience-platform/landing/governance-privacy-security/audit-logs/overview.html?lang=ja)を参照してください。

![](assets/audit-logs.png)

## 監査ログで記録されるイベントタイプ {#events}

監査ログで Journey Optimizer リソースが記録されるアクションの概要を次の表に示します。 監査ログで記録されるアクションの一覧については、[Adobe Experience Platform ドキュメント](https://experienceleague.adobe.com/docs/experience-platform/landing/governance-privacy-security/audit-logs/overview.html?lang=ja#category)を参照してください。

>[!NOTE]
>
>**意思決定管理**&#x200B;に関連する監査ログは、「**[!UICONTROL ログをダウンロード]**」ボタンを使用してダウンロードできる CSV ファイルからのみ表示されます。

| リソース | アクション |
|-----------|------------------|
| AJO キャンペーン | 作成／削除／更新／アクティベート／停止 |
| AJO チャネルの一般設定 | 作成／削除／更新 |
| AJO IP プール | 作成／削除／更新 |
| AJO ランディングページ | 作成／削除／更新／公開／非公開 |
| AJO ランディングページ HTML テンプレート | 作成／削除／更新 |
| AJO ランディングページプリセット | 作成／削除／更新 |
| AJO ランディングページサブドメイン | 作成／削除／更新 |
| AJO メッセージプリセット | 作成／削除／更新 |
| AJO PTR レコード | 作成／削除／更新 |
| AJO で保存された式テンプレート | 作成／削除／更新 |
| AJO SMS API 資格情報 | 作成／削除／更新 |
| AJO サブドメイン | 作成／削除／更新 |
| AJO 抑制リスト | CSV の作成／削除／ダウンロード |
| フィールドグループ | 作成／削除／更新 |
| ジャーニー | 作成／削除／更新／停止／公開 |
| ジャーニーのカスタムアクション | 作成／削除／更新 |
| ジャーニーデータソース | 作成／削除／更新 |
| ジャーニーイベント | 作成／削除／更新 |
| ジャーニーフラグメント | 作成／削除／更新／アクティブ化／アーカイブ |
| メッセージ頻度ルール | 作成／削除／更新 |
| ランキング戦略 | 作成／削除／更新 |
