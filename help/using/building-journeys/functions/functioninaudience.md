---
product: journey optimizer
title: inAudience 関数
description: Adobe Experience Platform inAudience 関数について説明します
feature: Journeys
role: Developer
level: Experienced
keywords: inAudience，関数，式，ジャーニー，オーディエンス，セグメント化
exl-id: 8417af75-6e97-4ad4-86b4-3ecd264a5560
version: Journey Orchestration
source-git-commit: a866442aa073c648d4455754e9945f0dddfb079d
workflow-type: tm+mt
source-wordcount: '598'
ht-degree: 3%

---

# inAudience 関数 {#inAudience}

`inAudience` 関数は、ジャーニー内の個人が特定のオーディエンスに属しているかどうかを確認できるAdobe Experience Platform関数です。 この強力な機能により、オーディエンスメンバーシップに基づいてパーソナライズされたジャーニーパスを作成し、顧客体験内で高度なセグメント化とターゲティングを可能にします。

`inAudience` 関数は、次の場合に使用します。

* [オーディエンスメンバーシップに基づくブランチのジャーニーパス](../condition-activity.md#using-a-segment)
* プロファイルが特定のセグメントに属するかどうかに応じて条件付きロジックを適用します
* エクスペリエンスをパーソナライズした、特定の顧客グループをターゲットにします
* ジャーニー条件内でのリアルタイムオーディエンスの参加の評価
* 複数のオーディエンスチェックを組み合わせて、複雑なターゲティングルールを作成します

この関数は、オーディエンスのメンバーシップをリアルタイムで評価し、ブール値を返すので、決定ノードや条件式に最適です。 オーディエンスは、[Adobe Experience Platform](https://platform.adobe.com/audience/overview){target="_blank"} （Journey Optimizerでの [ オーディエンスの操作 ](../../audience/about-audiences.md) で定義および管理され、式エディターには、オーディエンスを正確に参照するのに役立つオートコンプリート候補が表示されます。

**オーディエンスステータス：**

オーディエンスには、次の 2 つのパーティシペーションのステータスがあります。

* **実現**：個人はオーディエンス定義の対象となり、アクティブなメンバーになります
* **退出**：個人はオーディエンスを離れ、資格を失いました

**実現済み** ステータスの個人のみが、アクティブオーディエンスメンバーと見なされます。 関数が `true` を返す場合、個人が適合済みのステータスであることを確認します。`false` を返す場合、離脱済みのステータスであることを示します。 オーディエンスの評価について詳しくは、[ セグメント化サービスのドキュメント ](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html?lang=ja#interpret-segment-results){target="_blank"} を参照してください。

+++構文

`inAudience(<parameter>)`

+++

+++パラメーター

| パラメーター | 説明 | タイプ |
|--- |--- |--- |
| オーディエンス | オーディエンス名 | `<string>` |

**重要な制約：**

* オーディエンス名は、文字列定数である必要があります
* フィールド参照や式は使用できません
* 1 つのジャーニーで最大 100 個のオーディエンスを取得できます

+++

+++シグネチャと戻り値のタイプ

`inAudience(<string>)`

ブール値を返します。
* `true`：個人がオーディエンスのメンバーである（実現ステータス）

* `false`：個人がオーディエンスのメンバーではない（離脱済みステータス）

+++

+++例

`inAudience("men over 50")`

ジャーニーインスタンス内の個人が「men over 50」という名前のAdobe Experience Platform オーディエンスに属している場合は **true**、それ以外の場合は **false** を返します。

**実用的な使用例：**

```
// Simple audience check in a condition
inAudience("Premium Customers") == true

// Multiple audience evaluation
inAudience("High Value Customers") == true AND inAudience("Active Last 30 Days") == true

// Negation check
inAudience("Unsubscribed") == false
```

+++

## ガードレールと制限 {#guardrails}

ジャーニーで `inAudience` 関数を使用する場合は、次のガードレールおよび制限事項に注意してください。

**オーディエンス取得制限：**
* 1 つのジャーニー内で最大 100 個のオーディエンスを取得できます
* 式エディターには、使用可能なオーディエンスのオートコンプリートリストが表示されるので、オーディエンスを正しく参照するのに役立ちます

**パラメーター制約：**
* オーディエンス名は、文字列定数である必要があります
* フィールド参照と式は、パラメーターとしてはサポートされていません

**オーディエンス名の変更：**
* Adobe Experience Platformで既存のオーディエンスの名前を変更しても、ジャーニー式でそのオーディエンスへの参照が自動的に更新されることはありません
* 条件ノードで `inAudience('oldAudienceName')` を使用する場合は、新しい名前を使用するように式を手動で編集する必要があります
* オーディエンス名を更新しないと、ジャーニー条件が壊れ、ジャーニーの動作が正しくなくなる場合があります

**結合ポリシーに関する考慮事項：**
* `inAudience` 関数で複数のオーディエンスを使用する場合、結合ポリシーとの不一致により、エラーやアラートが発生する可能性があります
* 結合ポリシーの動作の詳細については [](../journey-properties.md)ジャーニープロパティを参照してください

## 関連トピック

Adobe Journey Optimizerでのオーディエンスの使用について詳しくは、以下を参照してください。

* **[オーディエンスについて](../../audience/about-audiences.md)** - Adobe Experience PlatformとJourney Optimizerでのオーディエンスの仕組み（オーディエンスの作成および管理方法を含む）について説明します。
* **[オーディエンスを読み取りアクティビティ](../read-audience.md)** - オーディエンスを使用してジャーニーエントリをトリガーにし、すべてのオーディエンスメンバーをジャーニーにエントリさせます
* **[オーディエンスの選定イベント](../audience-qualification-events.md)** - オーディエンスからトリガージャーニーのアクションへのプロファイルのエントリや離脱をリアルタイムでリッスンします
* **[条件でのオーディエンスの使用](../condition-activity.md#using-a-segment)** – 条件アクティビティを使用して、オーディエンスメンバーシップに基づく条件付きジャーニーパスを作成
* **[ジャーニープロパティ – 結合ポリシー](../journey-properties.md)** - inAudience 関数で複数のオーディエンスを使用する場合の結合ポリシーの仕組みを説明します

