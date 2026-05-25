---
solution: Journey Optimizer
product: journey optimizer
title: ロイヤルティデータとデータセット
description: Adobe Experience Platformのプロファイルデータとデータセットのロイヤルティの課題が必要とする理由、データセットの有効期間（TTL）が顧客維持に与える影響をご紹介します。
feature: Journeys
topic: Content Management
role: Admin, Developer
level: Intermediate
hide: true
badge: label="Private Beta" type="Informative"
mini-toc-levels: 1
exl-id: a7c4e1b2-8f3d-4a6c-9e0b-1d2e3f4a5b6c
source-git-commit: 894dd7f811e87a8551f92654e5b913a459c1382e
workflow-type: tm+mt
source-wordcount: '497'
ht-degree: 6%

---

# ロイヤルティデータとデータセット {#loyalty-data-and-datasets}

>[!BEGINSHADEBOX]

**ロイヤルティの課題に関するドキュメント**

[ロイヤルティに関する課題を解決](get-started.md)

+++課題の創出と管理

* [課題とタスクへのアクセスと管理](access-loyalty-challenges.md)
* [課題の創出](create-challenges.md)
* [タスクの作成](create-tasks.md)
* [ロイヤルティチャレンジのパフォーマンスを監視する](loyalty-reporting.md)

+++

+++設定と統合

<!-- * [Configure loyalty challenges](loyalty-admin.md) -->
* **ロイヤルティデータとデータセット** ◀︎ **現在の状態**
* [ロイヤルティチャレンジ API リファレンス](https://developer.adobe.com/journey-optimizer-apis/references/loyalty-challenges){target="_blank"}

+++

>[!ENDSHADEBOX]

>[!AVAILABILITY]
>
>この機能は現在&#x200B;**プライベートベータ版**&#x200B;です。 リリースサイクルと可用性フェーズについて詳しくは、[Journey Optimizer リリースサイクル](../rn/releases.md)を参照してください。

## 概要 {#overview}

ロイヤルティの課題は、ID、プロファイル属性、エクスペリエンスイベント、オーディエンスをAdobe Adobe Experience Platformに依存します。 このページでは、課題を作成したり、ロイヤルティチャレンジ APIを使用したりする前に、**有効期間（TTL）**&#x200B;がリテンションにどのように影響するかを説明します。

Journey Optimizer プログラムの設定（報酬フルフィルメントとイベントマッピング）については、Adobe管理者にお問い合わせください。 REST エンドポイントと認証については、[ ロイヤルティチャレンジ API リファレンス ](https://developer.adobe.com/journey-optimizer-apis/references/loyalty-challenges){target="_blank"}を参照してください。

## Adobe Experience Platform data {#aep-data}

### プロファイル属性 {#profile-attributes}

**[!DNL XDM Individual Profile]** クラスのプロファイルを使用して、オーディエンス、パーソナライゼーション、レポートに挑戦します。 ロイヤルティの課題に使用するID [名前空間](https://experienceleague.adobe.com/ja/docs/experience-platform/identity/features/namespaces){target="_blank"}と、プロファイルデータ内のメンバーの識別方法を一致させます。

プロファイル（ポイント、階層、プログラム、ステータス、および関連フィールド）の標準ロイヤルティ属性の場合は、Experience Platform **[ロイヤルティの詳細](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/field-groups/profile/loyalty-details){target="_blank"}** スキーマフィールドグループを使用します。 このフィールドグループは、`loyalty` オブジェクトとそのプロパティ （例：`points`、`tier`、`program`、および`status`）を定義します。

➡️ [ ロイヤルティの詳細スキーマフィールドグループ ](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/field-groups/profile/loyalty-details){target="_blank"}

### エクスペリエンスイベント {#experience-events}

**[!UICONTROL 購入]**、**[!UICONTROL 支出]**&#x200B;および&#x200B;**[!UICONTROL カスタムイベント]** タスクは、Adobe Experience Platformに取り込まれたエクスペリエンスイベントによって異なります。 **[!UICONTROL カスタムイベント]** タスクの場合、タスクビルダーで選択する前に、管理者が一致するイベント定義（識別子パス、オプションのXDM スキーマ ID、スキーマ、トランスフォーマ）を設定する必要があります。

イベントペイロードでロイヤルティチャレンジの設定と同じID名前空間を使用することで、進行状況を正しいプロファイルに起因させることができます。

### オーディエンスとレポート {#audiences-reporting}

マーケターは、チャレンジの実施要件を設定する際に、プラットフォーム [ オーディエンス ](../audience/about-audiences.md)を選択します。 ロイヤルティレポートダッシュボードでは、Adobe Customer Journey Analyticsを使用します。 [ ロイヤルティチャレンジのパフォーマンスを監視する方法について説明します](loyalty-reporting.md)

## データセットの有効期間（TTL） {#dataset-ttl}

ロイヤルティの課題：Adobe Experience Platformのデータセット（プログラム用に作成されたイベントおよびパーソナライゼーション関連のデータセットを含む）に、運用データとレポートデータを保存します。 データセット **有効期間（TTL）**&#x200B;は、データレイク内およびプロファイルストア内でデータを保持する期間を制御します。

Journey Optimizerでは、システム生成の多くのデータセットにTTL ガードレールを適用します。 ロイヤルティ関連のデータセットは、サンドボックスと同じプラットフォーム維持モデルに従います。

➡️ [Journey Optimizerのデータセットの有効期間（TTL）ガードレール ](../data/datasets-ttl.md)

>[!NOTE]
>
>組織レベルのロイヤルティ設定には、ロイヤルティメタデータサービスを通じて管理されるアーカイブ設定と保持設定（アーカイブ期間など）を含めることができます。 プライベートベータ版のリテンションを調整する必要がある場合は、Adobe管理者と調整してください。

<!-- For UI-based setup (reward providers, event definitions, product inventory, and exclusions), see [Configure loyalty challenges](loyalty-admin.md). -->
