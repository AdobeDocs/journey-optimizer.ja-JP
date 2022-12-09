---
solution: Journey Optimizer
product: journey optimizer
title: 旅のステップ共有の概要
description: 旅のステップ共有の概要
feature: Reporting
topic: Content Management
role: User
level: Intermediate
exl-id: 07d25f8e-0065-4410-9895-ffa15d6447bb
source-git-commit: 63c52f04da9fd1a5fafc36ffb5079380229f885e
workflow-type: tm+mt
source-wordcount: '467'
ht-degree: 0%

---

# 道報告の作成 {#design-jo-reports}

リアルタイムのレポート ](live-report.md) および組み込みの [ グローバルレポート機能 ](global-report.md) に [ 加えて、パフォーマンスに関するデータが Adobe エクスペリエンスプラットフォームに自動的に送信されるので、 [!DNL Journey Optimizer] 解析用に他のデータと組み合わせることができます。

>[!NOTE]
>
>この機能は、初期設定では、すべてのインスタンスで実行されます。 Step イベントの準備中に作成されたスキーマやデータセットは、修正したり更新することはできません。 デフォルトでは、これらのスキーマおよびデータセットは読み取り専用モードに設定されています。

例えば、複数の電子メールを送信するような旅を設定しているとします。 この機能を使用すると、変換の回数、web サイトで発生した契約数、ストアで発生した取引数などの下流イベントデータとデータを組み合わせる [!DNL Journey Optimizer] ことができます。 このような旅情報は、Adobe エクスペリエンスプラットフォーム上の他のデジタルプロパティまたはオフラインプロパティから組み合わせることによって、パフォーマンスをさらに包括的に示すことができます。

[!DNL Journey Optimizer] によって、1つの旅にかかる各ステップについて、必要なスキーマとストリームがデータセットに Adobe エクスペリエンスプラットフォームに自動的に作成されます。 ステップイベントは、1つのノードから別のノードに移動している個々のノードに対応します。 例えば、イベント、条件、およびアクションが含まれている旅において、3つのステップのイベントが Adobe エクスペリエンスプラットフォームに送られます。

渡される XDM フィールドのリストはすべて包括です。 システムによって生成されたコードや、人間が読めるようなわかりやすい名前を含むものもあります。 例としては、旅アクティビティのラベルやステップのステータス、1つのアクションがタイムアウトした場合、またはエラーが発生した回数などが挙げられます。

>[!CAUTION]
>
>データセットは、リアルタイムプロファイルサービスに対して有効にすることはできません。 トグルがオフになっていることを **[!UICONTROL Profile]** 確認してください。

[!DNL Journey Optimizer] データの発生時に、ストリーミングでデータを送信します。 クエリーサービスを使用して、このデータをクエリーすることができます。 お客様は、次の手順に関連するデータを表示するために、お客様の旅の分析やその他の BI ツールに接続できます。

次のスキーマが作成されます。

* 、旅のメタデータに関連付けられた、旅のステップの [!DNL Journey Orchestration] イベントスキー
* Journeys について説明するための [!DNL Journey Orchestration] 旅フィールドを含む旅スキーマ–旅するメタデータ。

![](assets/sharing1.png)

![](assets/sharing2.png)

次のデータセットが渡されます。

* 「ステップイベントの旅」
* Journeys

![](assets/sharing3.png)

Adobe エクスペリエンスプラットフォームに渡される XDM フィールドのリストは、次のとおりです。

* [ステップイベントフィールドリスト](../reports/sharing-field-list.md)
* [従来のステップのイベントフィールド](../reports/sharing-legacy-fields.md)

## お客様の旅の分析との連携 {#integration-cja}

[!DNL Journey Optimizer]Adobe お客様の旅の _blank 分析 ](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html) に [ ステップイベントをリンクさせることができます。

一般的なワークフローは以下のとおりです。

* [!DNL Customer Journey Analytics] ingests &quot;旅のステップイベント&quot; データセットを定義します。
* **関連付けられた「旅のイベントスキーマ」の「profileID** 」フィールドは、id フィールドとして定義されています。で [!DNL Customer Journey Analytics] は、このデータセットを、人名の識別子と同じ値を持つ他のデータセットにリンクできます。
* このデータセットをで [!DNL Customer Journey Analytics] 使用する場合は、クロスチャネルの旅について詳しくは、「お客様向け旅 ](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/cross-channel.html) の分析について」を [ 参照してください {target = &quot;_blank&quot;}。

