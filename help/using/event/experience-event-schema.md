---
title: ジャーニーイベント用の ExperienceEvent スキーマについて
description: ジャーニーイベント用の ExperienceEvent スキーマについて学ぶ
source-git-commit: 55b9e5d8ed259ec6ed7746e835691d7d6261a8a4
workflow-type: ht
source-wordcount: '317'
ht-degree: 100%

---

# [!DNL Journey Optimizer] イベントの ExperienceEvent スキーマについて

![](../assets/do-not-localize/badge.png)

[!DNL Journey Optimizer] イベントは、ストリーミング取得を介して Adobe Experience Platform に送信される XDM エクスペリエンスイベントです。

そのため、[!DNL Journey Optimizer] のイベントを設定するための重要な前提条件は、Adobe Experience Platform の Experience Data Model（または XDM）と XDM Experience Data スキーマの作成方法、および XDM 形式のデータを Adobe Experience Platform にストリーミングする方法に精通していることです。

## [!DNL Journey Optimizer] イベントのスキーマ要件

[!DNL Journey Optimizer] のイベントを設定する最初の手順は、イベントを表す XDM スキーマと、Adobe Experience Platform でイベントのインスタンスを記録するために作成されたデータセットを確実に用意することです。イベント用データセットは必ずしも必要ではありませんが、特定のデータセットにイベントを送信すると、ユーザーのイベント履歴を保持して後から参照および分析できるので便利です。イベントに適したスキーマとデータセットがまだない場合は、これらのタスクの両方を Adobe Experience Platform の Web インターフェイスで実行できます。

![](../assets/schema1.png)

[!DNL Journey Optimizer] イベントに使用される XDM スキーマは、以下の要件を満たす必要があります。

* スキーマは、XDM ExperienceEvent クラスである必要があります。

   ![](../assets/schema2.png)

* システム生成イベントの場合、スキーマにオーケストレーション eventID Mixin を含める必要があります。[!DNL Journey Optimizer] はこのフィールドを使用して、ジャーニーで使用されるイベントを識別します。

   ![](../assets/schema3.png)

* イベントの件名を識別するための ID フィールドを宣言します。ID が指定されていない場合は、ID マップを使用できます。この方法は推奨されません。

   ![](../assets/schema4.png)

* このデータを後からジャーニーで参照できるようにする場合は、プロファイルのスキーマとデータセットをマークします。

   ![](../assets/schema5.png)

   ![](../assets/schema6.png)

* ユーザーに関する情報、イベントの生成元のデバイス、場所、イベントに関連するその他の有意義な状況など、イベントに含めたいその他のコンテキストデータを取り込むためのデータフィールドを自由に含めることができます。

   ![](../assets/schema7.png)

   ![](../assets/schema8.png)
