---
product: journey optimizer
title: inAudience 関数
description: Adobe Experience Platform inAudience 関数について説明します
feature: Journeys
role: Developer
level: Experienced
keywords: inAudience, 関数, 式, ジャーニー, オーディエンス, セグメント化
exl-id: 8417af75-6e97-4ad4-86b4-3ecd264a5560
version: Journey Orchestration
source-git-commit: 4f653c0bd3f6998dd54deeae996b7b0427a1744e
workflow-type: ht
source-wordcount: '600'
ht-degree: 100%

---

# inAudience 関数 {#inAudience}

`inAudience` 関数は、ジャーニー内の個人が特定のオーディエンスに属しているかどうかを確認できる Adobe Experience Platform 関数です。この強力な関数により、オーディエンスメンバーシップに基づいてパーソナライズされたジャーニーパスを作成し、カスタマーエクスペリエンス内での高度なセグメント化とターゲティングが可能になります。

`inAudience` 関数は、次の操作が必要な場合に使用します。

* オーディエンスメンバーシップに基づいてジャーニーパスを分岐。[詳細情報](../condition-activity.md#using-a-segment)
* プロファイルが特定のセグメントに属しているかどうかに応じて条件付きロジックを適用
* パーソナライズされたエクスペリエンスで特定の顧客グループをターゲット
* ジャーニー条件内でリアルタイムのオーディエンスのパーティシペーションを評価
* 複数のオーディエンスチェックを組み合わせて、複雑なターゲティングルールを作成

この関数は、オーディエンスメンバーシップをリアルタイムで評価し、ブール値を返すので、決定ノードや条件式に最適です。オーディエンスは [Adobe Experience Platform](https://platform.adobe.com/audience/overview){target="_blank"} で定義および管理され（詳しくは、Journey Optimizer での[オーディエンスの操作](../../audience/about-audiences.md)を参照）、式エディターでは、オーディエンスを正確に参照できるようにオートコンプリートの候補が表示されます。

**オーディエンスステータス：**

オーディエンスには次の 2 つのパーティシペーションステータスがあります。

* **実現済み**：個人がオーディエンス定義を選定し、アクティブなメンバーです
* **退出済み**：個人がオーディエンスから退出し、選定しなくなりました

**実現済み**&#x200B;ステータスの個人のみがアクティブなオーディエンスメンバーと見なされます。関数が `true` を返す場合、個人がステータスを実現したことが確認され、`false` を返す場合、退出済みステータスが示されます。オーディエンス評価について詳しくは、[セグメント化サービスのドキュメント](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html?lang=ja#interpret-segment-results){target="_blank"}を参照してください。

+++構文

`inAudience(<parameter>)`

+++

+++パラメーター

| パラメーター | 説明 | タイプ |
|--- |--- |--- |
| オーディエンス | オーディエンス名 | `<string>` |

**重要な制約：**

* オーディエンス名は、文字列定数にする必要があります
* フィールド参照や式は使用できません
* 1 回のジャーニーで最大 100 個のオーディエンスを取得できます

+++

+++シグネチャと戻り値のタイプ

`inAudience(<string>)`

次のブール値を返します。
* `true`：個人はオーディエンスのメンバーです（実現済みステータス）

* `false`：個人はオーディエンスのメンバーではありません（退出済みステータス）

+++

+++例

`inAudience("men over 50")`

ジャーニーインスタンス内の個人が「50 歳以上の男性」という名前の Adobe Experience Platform オーディエンスに属している場合、**true** を返します。それ以外の場合は **false** を返します。

**実用的なユースケース：**

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

ジャーニーで `inAudience` 関数を使用する際は、次のガードレールと制限に注意してください。

**オーディエンス取得の制限：**
* 1 回のジャーニー内で最大 100 個のオーディエンスを取得できます
* 式エディターでは、使用可能なオーディエンスのオートコンプリートリストが表示されるので、正しく参照できます

**パラメーター制約：**
* オーディエンス名は、文字列定数にする必要があります
* フィールド参照と式は、パラメーターとしてサポートされていません

**オーディエンス名の変更：**
* Adobe Experience Platform で既存のオーディエンスの名前を変更しても、ジャーニー式内のそのオーディエンスへの参照は自動的に更新されません
* 条件ノードで `inAudience('oldAudienceName')` が使用されている場合は、新しい名前を使用するように式を手動で編集する必要があります。
* オーディエンス名を更新しないと、ジャーニー条件が破られ、ジャーニーの動作が不正確になる場合があります

**結合ポリシーの考慮事項：**
* `inAudience` 関数で複数のオーディエンスを使用する際、結合ポリシーとの不一致により、エラーやアラートが発生する場合があります。
* 結合ポリシーの動作について詳しくは、[ジャーニーのプロパティ](../journey-properties.md)を参照してください

## 関連トピック

Adobe Journey Optimizer でのオーディエンスの使用について詳しくは、以下を参照してください。

* **[オーディエンスについて](../../audience/about-audiences.md)** - Adobe Experience Platform および Journey Optimizer でのオーディエンスの仕組み（作成方法や管理方法を含む）について説明します
* **[オーディエンスを読み取りアクティビティ](../read-audience.md)** - オーディエンスを使用してジャーニーエントリをトリガーし、すべてのオーディエンスメンバーをジャーニーにエントリさせます
* **[オーディエンスの選定イベント](../audience-qualification-events.md)** - オーディエンスからプロファイルのエントリと退出をリッスンして、ジャーニーアクションをリアルタイムでトリガーします
* **[条件でのオーディエンスの使用](../condition-activity.md#using-a-segment)** - 条件アクティビティを使用して、オーディエンスメンバーシップに基づいて条件付きジャーニーパスを作成します
* **[ジャーニーのプロパティ - 結合ポリシー](../journey-properties.md)** - inAudience 関数を使用して複数のオーディエンスを使用する際の結合ポリシーの仕組みについて説明します

