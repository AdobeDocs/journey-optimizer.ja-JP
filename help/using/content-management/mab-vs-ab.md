---
title: 実験レポートで使用される統計計算
description: A/B テストとマルチアームバンディットの比較の詳細
feature: A/B Testing, Experimentation
role: User
level: Experienced
source-git-commit: 397fad9c95e0c11c0496ab5c9adfb6f8169de4f6
workflow-type: tm+mt
source-wordcount: '506'
ht-degree: 3%

---

# A/B とマルチアームバンディット実験の比較 {#mab-vs-ab}

<!--
>[!CONTEXTUALHELP]
>id="ajo_ab_test_mab"
>title="Experiment type"
>abstract="Experiment type determines how traffic is allocated between treatments during your test. Choose the method that best aligns with your goals:</br>
>
>* **A/B Experiment**: Splits traffic as you define between treatments and measures performance until results are statistically significant. Best for learning which treatment performs better in a controlled comparison.
>
>* **Multi-armed Bandit**: Shifts traffic toward higher-performing treatments as data is collected, balancing speed and optimization. Useful when you want to maximize conversions during the experiment.
>
>* **Bring your own Multi-armed Bandit**: Use your own algorithm to decide traffic allocation, giving you flexibility if you have a custom model or strategy."
-->

このページでは、**A/B** 実験と **マルチアームバンディット** 実験を詳細に比較し、それぞれの強み、制限、各アプローチが最も効果的なシナリオについて説明します。

## A/B {#ab-test}

従来の A/B 実験では、処理をまたいでトラフィックを均等に分割し、実験が終了するまでこの配分を維持します。 統計的優位差に達すると、勝者処理が識別され、その後スケールされます。

### メリット

従来の A/B 実験の主な強みは次のとおりです。

* **統計的厳密**

  固定設計により、明確に定義されたエラー率と信頼区間が提供されます。

  仮説テストのフレームワーク（95% の信頼性など）を使用すると、適用と解釈が容易になります。

  適切な処理能力を持つ実験を行うと、偽陽性の可能性が低くなります。

* **シンプルさ**

  この方法は、設計と実行が簡単です。

  結果は、技術者以外の関係者に明確に伝えることができます。

* **包括的なデータ収集**

  各治療は十分な暴露を受けるため、勝者バリアントだけでなくパフォーマンスの低い代替策の分析も可能になります。

  この追加情報は、長期的な戦略的決定に情報を提供できます。

* **バイアス制御**

  固定配分は、「勝者の呪い」や平均への回帰などの偏りに対する感受性を軽減します。

### 制限事項

従来の A/B 実験の主な制限は次のとおりです。

* **商談コスト**

  トラフィックの大部分は劣悪な処理に向けられており、テスト中のコンバージョンや売上高を減らす可能性があります。

  勝者の処理は、実験が終了するまで実装できません。

* **固定期間要件**

  季節性、市場の変化などの外部条件が途中で変化した場合でも、テストは通常、事前に指定された範囲で実行する必要があります。

  実験中の適応は限られています。

## マルチアームバンディット {#mab-experiment}

マルチアームバンディットアルゴリズムは、適応配分を使用します。証拠が蓄積されると、より多くのトラフィックがパフォーマンスの高い処理に向けられます。 目的は、最終結果にのみ焦点を当てるのではなく、実験中に累積報酬を最大化することです。

### メリット

マルチアームバンディット方式の主な強みは次のとおりです。

* **最適化の迅速化**

  早期に有望な治療を優先し、試験中の全体的なパフォーマンスを向上させます。

* **適応性**

  割り当ては、データが収集されるたびに継続的に更新されるので、マルチアームバンディットは動的環境に適しています。

* **機会費用の削減**

  不十分な処理は迅速に段階的に廃止され、無駄なトラフィックが最小限に抑えられます。

* **連続試験の適切性**

  トラフィックにコストがかかる進行中の実験やコンテキストに効果的です。

### 制限事項

マルチアームバンディット方式の主な制限事項は次のとおりです。

* **統計的保証の脆弱性**

  従来の仮説テストは適用が難しく、ルールを停止する方法もはっきりしません。

* **透明性の低下**

  アダプティブ配分は、関係者への説明が困難な場合があります。

* **不良な待遇に関する限定的情報**

  弱い治療はほとんど曝露を受けず、診断的なinsightが制限される。

* **実装の複雑さ**

  高度なアルゴリズムとインフラストラクチャが必要であり、設定ミスの可能性が高くなります。

## A/B バンディットとマルチアームバンディットのどちらを使用するか

| シナリオ | 推奨される方法 |
|-|-|
| 探索的テストまたは研究主導のテストを実行している場合 | A/B |
| 広告、レコメンデーションなど、常時稼動のキャンペーンを実行している | 多腕バンディット |
| テスト中にコンバージョンを最大化する | 多腕バンディット |
| 明確で確信に満ちたインサイトが必要 | A/B |
| 季節によるシフトなど、迅速な適応が必要 | 多腕バンディット |
| トラフィックが限られており、投資回収率を迅速に最適化したい場合 | 多腕バンディット |
| トラフィックが多く、学習に時間がかかる場合 | A/B |
| 関係者は、明確な決定点を必要としている | A/B |

