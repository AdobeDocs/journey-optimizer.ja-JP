---
title: ジャーニーイベント用の ExperienceEvent スキーマについて
description: ジャーニーイベント用の ExperienceEvent スキーマについて学ぶ
feature: スキーマ
topic: 管理
role: Admin
level: Intermediate
source-git-commit: e965372e3640b92f672bf03098c8e4fb487dfc7d
workflow-type: tm+mt
source-wordcount: '774'
ht-degree: 41%

---

# [!DNL Journey Optimizer] イベントの ExperienceEvent スキーマについて

[!DNL Journey Optimizer] イベントは、ストリーミング取得を介して Adobe Experience Platform に送信される XDM エクスペリエンスイベントです。

そのため、[!DNL Journey Optimizer] のイベントを設定するための重要な前提条件は、Adobe Experience Platform の Experience Data Model（または XDM）と XDM Experience Data スキーマの作成方法、および XDM 形式のデータを Adobe Experience Platform にストリーミングする方法に精通していることです。

## [!DNL Journey Optimizer] イベントのスキーマ要件

[!DNL Journey Optimizer] のイベントを設定する最初の手順は、イベントを表す XDM スキーマと、Adobe Experience Platform でイベントのインスタンスを記録するために作成されたデータセットを確実に用意することです。イベント用データセットは必ずしも必要ではありませんが、特定のデータセットにイベントを送信すると、ユーザーのイベント履歴を保持して後から参照および分析できるので便利です。イベントに適したスキーマとデータセットがまだない場合は、これらのタスクの両方を Adobe Experience Platform の Web インターフェイスで実行できます。

![](../assets/schema1.png)

[!DNL Journey Optimizer] イベントに使用される XDM スキーマは、以下の要件を満たす必要があります。

* スキーマは、XDM ExperienceEvent クラスである必要があります。

   ![](../assets/schema2.png)

* システム生成イベントの場合、オーケストレーション eventID フィールドグループがスキーマに含まれている必要があります。[!DNL Journey Optimizer] はこのフィールドを使用して、ジャーニーで使用されるイベントを識別します。

   ![](../assets/schema3.png)

* イベントの件名を識別するための ID フィールドを宣言します。ID が指定されていない場合は、ID マップを使用できます。この方法は推奨されません。

   ![](../assets/schema4.png)

* このデータを後からジャーニーで参照できるようにする場合は、プロファイルのスキーマとデータセットをマークします。

   ![](../assets/schema5.png)

   ![](../assets/schema6.png)

* ユーザーに関する情報、イベントの生成元のデバイス、場所、イベントに関連するその他の有意義な状況など、イベントに含めたいその他のコンテキストデータを取り込むためのデータフィールドを自由に含めることができます。

   ![](../assets/schema7.png)

   ![](../assets/schema8.png)

## スキーマの関係の活用{#leverage_schema_relationships}

Adobe Experience Platformでは、あるデータセットを別のデータセットのルックアップテーブルとして使用するために、スキーマ間の関係を定義できます。

ブランドデータモデルに、購入をキャプチャするスキーマがあるとします。 また、製品カタログのスキーマもあります。 製品IDを購入スキーマに取り込み、関係を使用して、製品カタログからより完全な製品詳細を検索できます。 これにより、例えば、ノートパソコンを購入したすべての顧客に対して、すべてのノートパソコンIDを明示的にリストアウトしたり、トランザクションシステムですべての製品の詳細を取り込んだりする必要がなく、セグメントを作成できます。

関係を定義するには、ソーススキーマに専用のフィールド（この場合は購入スキーマの製品IDフィールド）が必要です。 このフィールドは、宛先スキーマの製品IDフィールドを参照する必要があります。 プロファイルに対してソーステーブルと宛先テーブルを有効にし、宛先スキーマには、プライマリIDとして定義された共通フィールドが必要です。

次に、製品IDがプライマリIDとして定義されたプロファイルに対して有効な製品カタログスキーマを示します。

![](../assets/schema9.png)

次に、製品IDフィールドで定義された関係を持つ購入スキーマを示します。

![](../assets/schema10.png)

>[!NOTE]
>
>スキーマの関係について詳しくは、[Experience Platformのドキュメント](https://experienceleague.adobe.com/docs/platform-learn/tutorials/schemas/configure-relationships-between-schemas.html?lang=en)を参照してください。

Journey Optimizerでは、リンクされたテーブルのすべてのフィールドを活用できます。

* 単一イベントを設定する場合、[詳細を表示](../event/experience-event-schema.md#unitary_event_configuration)
* ジャーニーで条件を使用する場合、[詳細を表示](../event/experience-event-schema.md#journey_conditions_using_event_context)
* メッセージのパーソナライゼーションで、[詳細を表示](../event/experience-event-schema.md#message_personalization)
* カスタムアクションのパーソナライゼーションで、[詳細を表示](../event/experience-event-schema.md#custom_action_personalization_with_journey_event_context)

### 単一イベントの設定{#unitary_event_configuration}

リンクされたスキーマフィールドは、単一のイベント設定で使用できます。

* イベント設定画面の「イベントスキーマ」フィールドを参照する際。
* （システム生成イベントの条件を定義する場合）

![](../assets/schema11.png)

リンクされたフィールドは使用できません。

* イベントキーの数式
* イベントid条件（ルールベースのイベント）
* ビジネスイベント（後日）

単一イベントの設定方法については、この[ページ](../event/about-creating.md)を参照してください。

### ジャーニーコンテキストを使用したイベント条件{#journey_conditions_using_event_context}

条件作成のジャーニー（式エディター）で使用するイベントにリンクされたルックアップテーブルのデータを使用できます。

ジャーニーに条件を追加し、式を編集し、式エディターでイベントノードを展開します。

![](../assets/schema12.png)

ジャーニー条件の定義方法については、この[ページ](../building-journeys/condition-activity.md)を参照してください。

### メッセージのパーソナライズ{#message_personalization}

リンクされたフィールドは、メッセージをパーソナライズする際に使用できます。 関連するフィールドは、ジャーニーからメッセージに渡されるコンテキストで表示されます。

![](../assets/schema14.png)

コンテキストジャーニー情報を使用してメッセージをパーソナライズする方法については、[ページ](../personalization/personalization-use-case.md)を参照してください。

### ジャーニーイベントコンテキストを使用したカスタムアクションのパーソナライゼーション{#custom_action_personalization_with_journey_event_context}

リンクされたフィールドは、ジャーニーのカスタムアクションアクティビティのアクションパラメーターを設定する際に使用できます。

![](../assets/schema13.png)

カスタムアクションの使用方法については、この[ページ](../building-journeys/using-custom-actions.md)を参照してください。
