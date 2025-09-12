---
solution: Journey Optimizer
product: journey optimizer
title: 実験アクセラレータ
description: Experimentation Acceleratorを使用した AI でのデータ使用
feature: Experimentation
topic: Content Management
role: User
level: Beginner
keywords: コンテンツ, 実験, 複数, オーディエンス, 処理
hide: true
hidefromtoc: true
source-git-commit: 50dcdd30e21fe1b12d502a2b9c478f4ceb546c49
workflow-type: tm+mt
source-wordcount: '436'
ht-degree: 1%

---

# Experimentation Acceleratorを使用した AI でのデータ使用{#experiment-accelerator-security}

>[!BEGINSHADEBOX]

* [Experimentation Acceleratorの概要](experiment-accelerator.md)
* [Experimentation Acceleratorを使用した AI でのデータ使用](experiment-accelerator-security.md)
* [Experimentation Accelerator ベストプラクティス](experiment-accelerator-best-practices.md)
* [実験の監視](experiment-accelerator-monitor.md)
* [実験指標](experiment-accelerator-metrics.md)

>[!ENDSHADEBOX]

**Adobe Journey Optimizer Experimentation Accelerator** を使用すると、インサイトを自動的に見つけ、実験および実験プログラムを改善する機会を推奨できます。 ソリューションでは、AI と機械学習を活用して、これらの推奨事項を提供します。 このステートメントでは、顧客データが **Experimentation Accelerator** でどのように使用されるかを明確にします。

## 実験アクセラレーターが使用するデータ

現在、**実験アクセラレーター** で使用されるデータには、次の 3 つのタイプがあります。

* **実験メタデータ**：実験名、実験に使用されるオーディエンスの定義および実験の処理（名前、分割パーセンテージ、実験の提供先の場所またはサーフェスなど）。

* **処理のパフォーマンス**：人数、成功指標の平均、各処理の標準偏差。

* **処理の内容**：レンダリングされたHTMLと、web サイト上のユーザーに表示される処理のスクリーンショット。

## 実験アクセラレーターはこのデータに対して何を行いますか？

**実験アクセラレーター** は、処理ごとにコンテンツを受け取り、コンテンツの数学的表現である埋め込みを作成してから、これらの埋め込みを処理のパフォーマンスに関連付けます。 このプロセスを使用すると、今後の使用のために最も効果が高いコンテンツ属性を抽出できます。 これらの属性は、Adobeでホストされる大規模言語モデルに入力され、人間が読み取れるステートメントに変換されて、インサイトを生み出し、オポチュニティを提案するために使用されます。

## 使用されるデータに対してExperimentation Acceleratorにはどのような制限がありますか？

各顧客は、特定の組織とサンドボックスに割り当てられています。 サンドボックスごとに専用モデルのトレーニングが実施されます。 サンドボックスを削除すると、関連するすべてのデータ、シグナルおよびモデルが完全に削除されます。

* 顧客データは、その顧客からのモデルのトレーニングや微調整にのみ使用します。

* お客様を混ぜてモデルをトレーニングしたり、微調整したりすることはありません。

## Adobe モデルまたは AI はブランドのユーザーエクスペリエンスを自動的に変更しますか？

いいえ。**Experimentation Accelerator** 変更対象とその変更方法に関する推奨事項のみを作成します。 Journey Optimizerまたは Target を使用してエクスペリエンスを変更する権限を持つユーザーのみが、これらのレコメンデーションに基づいてアクションを実行できます。 すべてのレコメンデーションは、プッシュする前にレビューおよび編集できます。

## データやシステムの安定性に対するリスクはありますか？

**Experimentation Accelerator** は、データのみを取り込んで分析し、将来のテストのためのインサイトと推奨事項を生成します。 テスト設定を変更するアクセス権はありません。 ツールで生成されたすべての提案は、Target とJourney Optimizerに送信されて実装され、顧客の現在のアクティビティに影響を与えません。
