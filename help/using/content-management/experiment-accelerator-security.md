---
solution: Journey Optimizer
product: journey optimizer
title: Journey Optimizer Experimentation Accelerator
description: Journey Optimizer Experimentation Acceleratorを使用した AI でのデータ使用
feature: Experimentation
topic: Content Management
role: User
level: Beginner
keywords: コンテンツ, 実験, 複数, オーディエンス, 処理
exl-id: b7c00cdc-430c-40a2-90c9-6dd891d2563b
source-git-commit: 61ae9196f699c3b6aa1d9a5bb2259d36aaebc0e3
workflow-type: tm+mt
source-wordcount: '439'
ht-degree: 1%

---

# Journey Optimizer Experimentation Acceleratorを使用した AI でのデータ使用{#experiment-accelerator-security}

**Adobe Journey Optimizer Journey Optimizer Experimentation Accelerator** を使用すると、インサイトを自動的に見つけ、実験および実験プログラムを改善する機会を推奨できます。 ソリューションでは、AI と機械学習を活用して、これらの推奨事項を提供します。 このステートメントでは、顧客データが **Journey Optimizer Experimentation Accelerator** でどのように使用されるかを明確にします。

## Journey Optimizer Experimentation Acceleratorではどのようなデータを使用しますか？

現在、**Journey Optimizer Experimentation Accelerator** で使用されるデータには次の 3 種類があります。

* **実験メタデータ**：実験名、実験に使用されるオーディエンスの定義および実験の処理（名前、分割パーセンテージ、実験の提供先の場所またはサーフェスなど）。

* **処理のパフォーマンス**：人数、成功指標の平均、各処理の標準偏差。

* **処理の内容**：レンダリングされたHTMLと、web サイト上のユーザーに表示される処理のスクリーンショット。

## Journey Optimizer Experimentation Acceleratorはこのデータに対して何を行いますか？

**Journey Optimizer Experimentation Accelerator** は、処理ごとにコンテンツを受け取り、コンテンツの数学的表現などの埋め込みを作成してから、それらの埋め込みを処理のパフォーマンスに関連付けます。 このプロセスを使用すると、今後の使用のために最も効果が高いコンテンツ属性を抽出できます。 これらの属性は、Adobeでホストされる大規模言語モデルに入力され、人間が読み取れるステートメントに変換されて、インサイトを生み出し、オポチュニティを提案するために使用されます。

## 使用されるデータに対してJourney Optimizer Experimentation Acceleratorにはどのような制限がありますか？

各顧客は、特定の組織とサンドボックスに割り当てられています。 サンドボックスごとに専用モデルのトレーニングが実施されます。 サンドボックスを削除すると、関連するすべてのデータ、シグナルおよびモデルが完全に削除されます。

* 顧客データは、その顧客からのモデルのトレーニングや微調整にのみ使用します。

* お客様を混ぜてモデルをトレーニングしたり、微調整したりすることはありません。

## Adobe モデルまたは AI はブランドのユーザーエクスペリエンスを自動的に変更しますか？

いいえ。**Journey Optimizer Experimentation Accelerator** 変更対象とその変更方法に関する推奨事項のみを作成します。 Journey Optimizerまたは Target を使用してエクスペリエンスを変更する権限を持つユーザーのみが、これらのレコメンデーションに基づいてアクションを実行できます。 すべてのレコメンデーションは、プッシュする前にレビューおよび編集できます。

## データやシステムの安定性に対するリスクはありますか？

**Journey Optimizer Experimentation Accelerator** は、データのみを取り込んで分析し、将来のテストのためのインサイトと推奨事項を生成します。 テスト設定を変更するアクセス権はありません。 ツールで生成されたすべての提案は、Target とJourney Optimizerに送信されて実装され、顧客の現在のアクティビティに影響を与えません。
