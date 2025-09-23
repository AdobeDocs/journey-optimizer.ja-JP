---
solution: Journey Optimizer
product: journey optimizer
title: Journey Optimizer Experimentation Accelerator指標
description: 効果的に実験を行い、インサイトを生み出す能力の向上
feature: Experimentation
topic: Content Management
role: User
level: Beginner
keywords: コンテンツ, 実験, 複数, オーディエンス, 処理
hide: true
hidefromtoc: true
exl-id: 74868625-f4ea-44f9-ae2a-8e5fdd22a081
source-git-commit: 70fce6fae4db58c72496945c50155dbd0b4986b4
workflow-type: tm+mt
source-wordcount: '374'
ht-degree: 11%

---

# 指標 {#experiment-accelerator-metrics}

>[!BEGINSHADEBOX]

* [Journey Optimizer Experimentation Acceleratorの概要](experiment-accelerator.md)
* [Journey Optimizer Experimentation Acceleratorを使用した AI でのデータ使用](experiment-accelerator-security.md)
* [Journey Optimizer Experimentation Accelerator ベストプラクティス](experiment-accelerator-best-practices.md)
* [実験の監視](experiment-accelerator-monitor.md)
* **[実験指標](experiment-accelerator-metrics.md)**

>[!ENDSHADEBOX]

**[!UICONTROL 指標]** ページには、Journey Optimizer実験と Target 実験の成功指標が 1 か所で表示され、パフォーマンスのモニタリング、比較、より深いインサイトを得ることができます。

## ダッシュボード {#dashboard}

「**[!UICONTROL 指標]**」タブには、Journey OptimizerとAdobe Targetで使用可能なすべての成功指標が統合ビューに表示されるので、イニシアチブをまたいでパフォーマンスを追跡したり、結果を比較したり、注意が必要な領域をすばやく特定したりするのに役立ちます。

![](assets/do-not-localize/Smock_Filter_18_N.svg) をクリックしてフィルターにアクセスします。ここには、**[!UICONTROL Sourceによるフィルタリング]** または **[!UICONTROL アクティブな実験で使用]** などのコンテキスト固有のオプションがあります。

または、検索バーに名前を入力して、指標をすばやく見つけることもできます。

![](assets/experiment-monitor-metrics.png)

## 指標の詳細 {#metric-details}

### 増分処理の推移

![](assets/experiment-monitor-metrics-2.png)

**[!UICONTROL 増分値の推移]** グラフには、選択した時間範囲内での選択した指標のトレンドを視覚的に分類した値が表示されます。 ドロップダウンメニューを使用して日別ビューと週別ビューを切り替え、精度のレベルを調整します。

クイックリファレンスとして次の要約値を利用できます。

* **[!UICONTROL 合計]**：レポート期間中の選択した指標の累積値。

* **[!UICONTROL 平均]**：選択した時間範囲で計算された指標の代表値。 毎日または毎週の変動のバランスを取ることで、通常のパフォーマンスをより明確に把握し、比較のベースラインとして使用できます。

* **[!UICONTROL コンバージョン率]**：処理を確認した後に目的のアクション（購入、サインアップなど）を完了したプロファイルの割合。

各値には、前期からの変化率が含まれているので、パフォーマンスが改善しているか、低下しているか、安定しているかを簡単に確認できます。

### 実験効果

このセクションには、選択した期間内（過去 90 日間、過去 30 日間または過去 7 日間）のすべてのアクティブな実験が表示され、指標に対する貢献度がハイライト表示されます。

次の指標を使用できます。

* **[!UICONTROL 上昇率]**：ベースラインに対する特定の処理のコンバージョン率の向上率を測定します。

* **[!UICONTROL 信頼性]**：ある処理がベースライン処理と同じであることを示す証拠。[詳細情報](../content-management/experiment-calculations.md#understand-confidence)

* **[!UICONTROL 貢献度]**：特定の実験または処理に起因する可能性のある指標の全体的な変化の割合。相対的な影響が最も大きいイニシアチブを特定できます。
