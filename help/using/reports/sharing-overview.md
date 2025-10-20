---
solution: Journey Optimizer
product: journey optimizer
title: ジャーニーステップ共有の概要
description: ジャーニーステップ共有の概要
feature: Journeys, Reporting
topic: Content Management
role: Engineer, Admin
level: Experienced
exl-id: 29d6b881-35a3-4c62-9e7d-d0aeb206ea77
source-git-commit: 6f7b9bfb65617ee1ace3a2faaebdb24fa068d74f
workflow-type: tm+mt
source-wordcount: '620'
ht-degree: 83%

---

# ジャーニーレポートの作成 {#design-jo-reports}

[!DNL Journey Optimizer] を使用すると、[リアルタイムレポート](live-report.md)やビルトインの[レポート機能](report-gs-cja.md)に加え、ジャーニーのパフォーマンスデータを Adobe Experience Platform に自動的に送信し、他のデータと組み合わせて分析できるようになります。

>[!NOTE]
>
>この機能は、ジャーニーステップのイベントの場合、すべてのインスタンスにおいてデフォルトで有効になっています。ステップイベントのプロビジョニング時に作成されたスキーマやデータセットは、変更も更新もできません。デフォルトでは、これらのスキーマとデータセットは読み取り専用モードです。

例えば、複数のメールを送信するジャーニーを設定したとします。この機能を使用すると、[!DNL Journey Optimizer] のデータをダウンストリームのイベントデータと組み合わせることができます。このようなイベントデータには、発生したコンバージョン数、Web サイトで発生したエンゲージメント、ストアで発生したトランザクション数などがあります。ジャーニー情報を Adobe Experience Platform のデータ（他のデジタルプロパティのデータまたはオフラインプロパティのデータ）と組み合わせて、パフォーマンスをより包括的に把握することができます。

[!DNL Journey Optimizer] は、個人がジャーニーで実行するステップごとに、必要なスキーマとデータセットへのストリームを Adobe Experience Platform に対して自動的に作成します。ステップイベントは、ジャーニーのあるノードから別のノードに移動する個人に対応します。例えば、イベント、条件およびアクションを備えたジャーニーでは、3 つのステップイベントが Adobe Experience Platform に送信されます。

>[!NOTE]
>
>プロファイルレベルのステップイベントに加えて、システムは **オーディエンスを読み取り** アクティビティの内部イベントも生成します。 これらのイベントは `segmentExportJob` イベントと呼ばれ、オーディエンスを読み取りノードのライフサイクル（書き出しジョブの作成、キューへの登録、完了、エラーなど）を記録し、個々のプロファイルではなく、オーディエンスを読み取りアクティビティごとに生成されます。 その結果、これらのイベントにはプロファイル識別子（UPMID）が関連付けられていない場合があります。 これらの内部イベントは、オーディエンスを読み取りのパフォーマンスの監視とトラブルシューティングに役立ち、[serviceEvents の節 ](../reports/sharing-field-list.md#servicevents-field) に記載されているフィールドを使用してクエリできます。 segmentExportJob イベントの操作方法のクエリ例については、[ オーディエンスの読み取りに関連するクエリ ](../reports/query-examples.md#read-segment-queries) を参照してください。

同じノードに対して複数のイベントを作成できる場合があります。例えば、「待機」アクティビティの場合は、次のようになります。

* プロファイルが待機にエントリすると、1 つのイベントが生成される（journeyNodeProcessed 属性が false に等しい）
* プロファイルが離脱すると、1 つのイベントが生成される（journeyNodeProcessed 属性が true に等しい）

渡される XDM フィールドのリストは多岐にわたります。システムで生成されたコードを含むものもあれば、人間が理解できるわかりやすい名前を持つものもあります。例えば、ジャーニーアクティビティやステップステータスのラベルがあります。アクションがタイムアウトした回数や、エラーで終了した回数などです。

>[!CAUTION]
>
>リアルタイムプロファイルサービスの場合は、データセットをオンにできません。**[!UICONTROL プロファイル]**&#x200B;の切り替えがオフになっていることを確認してください。

[!DNL Journey Optimizer] は、発生時にストリーミングでデータを送信します。このデータは、クエリサービスを使用してクエリできます。Customer Journey Analytics またはその他の BI ツールに接続して、これらのステップに関連するデータを表示できます。

次のスキーマが作成されます。

* [!DNL Journey Orchestration] のジャーニーステップイベントスキーマ：ジャーニーメタデータに関連付けられているジャーニーステップイベント。
* [!DNL Journey Orchestration] のジャーニーフィールドを含むジャーニースキーマ：ジャーニーを記述するジャーニーメタデータ。

![](assets/sharing1.png)

![](assets/sharing2.png)

次のデータセットが渡されます。

* ジャーニーステップイベント
* ジャーニー

![](assets/sharing3.png)

Adobe Experience Platform に渡される XDM フィールドのリストについて詳しくは、以下を参照してください。

* [ステップイベントフィールドの一覧](../reports/sharing-field-list.md)
* [従来のステップイベントフィールド](../reports/sharing-legacy-fields.md)

## Customer Journey Analytics との統合 {#integration-cja}

[!DNL Journey Optimizer] のステップイベントは、[Adobe Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=ja){target="_blank"} の他のデータセットにリンクできます。

一般的なワークフローは次のとおりです。

* [!DNL Customer Journey Analytics] は、「ジャーニーステップイベント」データセットを取り込みます。
* 関連する「Journey Orchestration のジャーニーステップイベントスキーマ」の **profileID** フィールドは、ID フィールドとして定義されています。[!DNL Customer Journey Analytics] では、このデータセットを、ユーザーベースの識別情報と同じ値を持つ他のデータセットにリンクできます。
* クロスチャネルジャーニー分析に、このデータセットを [!DNL Customer Journey Analytics] で使用するには、[Customer Journey Analytics のドキュメント](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/cross-channel.html?lang=ja){target="_blank"}を参照してください。

➡️ [Customer Journey Analytics の操作](cja-ajo.md){target="_blank"}
