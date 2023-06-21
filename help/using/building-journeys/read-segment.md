---
solution: Journey Optimizer
product: journey optimizer
title: ジャーニーでのセグメントの使用
description: ジャーニーでのセグメントの使用方法を学ぶ
feature: Journeys
topic: Content Management
role: User
level: Intermediate
keywords: アクティビティ, ジャーニー, 読み取り, セグメント, プラットフォーム
exl-id: 7b27d42e-3bfe-45ab-8a37-c55b231052ee
source-git-commit: a278b217882f2646e106600e110226941e7e4f10
workflow-type: tm+mt
source-wordcount: '1337'
ht-degree: 81%

---

# ジャーニーでのセグメントの使用 {#segment-trigger-activity}

## 「セグメントを読み取り」アクティビティの追加 {#about-segment-trigger-actvitiy}

>[!CONTEXTUALHELP]
>id="ajo_journey_read_segment"
>title="「セグメントを読み取り」アクティビティ"
>abstract="セグメントの読み取りアクティビティを使用すると、Adobe Experience Platform セグメントに属するすべての個人をジャーニーにエントリさせることができます。ジャーニーへのエントリは、1 回きりと定期的のいずれも可能です。"

**セグメントを読み取り**&#x200B;アクティビティを使用すると、セグメントのすべての個人をジャーニーにエントリさせることができます。ジャーニーへのエントリは、1 回きりと定期的のいずれも可能です。

例として、[セグメントの作成](../segment/about-segments.md)のユースケースで作成した「Luma アプリのオープンとチェックアウト」セグメントを見てみましょう。セグメントの読み取りアクティビティを使用すると、このセグメントに属するすべての個人をジャーニーがエントリし、すべてのジャーニー機能 （条件、タイマー、イベント、アクション）を活用したカスタムジャーニーの流れに沿うようにします。

>[!NOTE]
>
>「セグメントを読み取り」アクティビティを使用するジャーニーの場合、同時に開始できるジャーニーの最大数があります。 再試行はシステムによって実行されますが、たとえば 5 ～10 分間隔で時間を分散させて、5 つを超えるジャーニー（読み取りセグメント、スケジュール済み、または「できるだけ早く」開始）を同時に開始することは避けてください。
>
>エクスペリエンスイベントフィールドグループは、「セグメントを読み取り」、セグメントの選定またはビジネスイベントアクティビティで始まるジャーニーでは使用できません。

### アクティビティの設定 {#configuring-segment-trigger-activity}

セグメントの読み取りアクティビティを設定する手順は次のとおりです。

1. **[!UICONTROL オーケストレーション]**&#x200B;カテゴリを展開し、「**[!UICONTROL セグメントを読み取り]**」アクティビティをキャンバスにドロップします。

   アクティビティは、ジャーニーの最初のステップとして配置する必要があります。

1. アクティビティに&#x200B;**[!UICONTROL ラベル]**&#x200B;を追加します（オプション）。

1. 「**[!UICONTROL セグメント]**」フィールドで、ジャーニーにエントリする Adobe Experience Platform セグメントを選択し、「**[!UICONTROL 保存]**」をクリックします。

   リストに表示される列はカスタマイズして並べ替えることができます。

   >[!NOTE]
   >
   >**実現**&#x200B;および&#x200B;**既存**&#x200B;のセグメント参加ステータスを持つ個人のみが個人のみがジャーニーにエントリします。セグメントの評価方法について詳しくは、[セグメント化サービスのドキュメント](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html?lang=ja#interpret-segment-results){target="_blank"}を参照してください。

   ![](assets/read-segment-selection.png)

   セグメントが追加されると、「**[!UICONTROL コピー]**」ボタンを使用して、セグメントの名前と ID をコピーできます。

   `{"name":"Luma app opening and checkout",”id":"8597c5dc-70e3-4b05-8fb9-7e938f5c07a3"}`

   ![](assets/read-segment-copy.png)

1. **[!UICONTROL 名前空間]**&#x200B;フィールドで、個人の識別に使用する名前空間を選択します。デフォルトでは、このフィールドには、最後に使用した名前空間が事前に入力されています。 [名前空間の詳細情報](../event/about-creating.md#select-the-namespace)。

   >[!NOTE]
   >
   >異なる ID の中から選択した ID（名前空間）を持たないセグメントに属する個人は、ジャーニーにエントリできません。ユーザーベースの ID 名前空間のみ選択できます。参照テーブルの名前空間を定義した場合（製品参照用の製品 ID 名前空間など）、**名前空間**&#x200B;ドロップダウンリストでは使用できません。

1. 「**[!UICONTROL スロットルレート]**」フィールドを、「セグメントを読み取り」アクティビティのスループット限度に設定します。

   この値は、ジャーニーバージョンのペイロードに格納されます。デフォルト値は、1 秒あたり 5,000 メッセージです。この値は、1 秒あたり 500 から 20,000 メッセージの範囲で変更できます。

   >[!NOTE]
   >
   >サンドボックスあたりの全体的なスロットルレートは、1 秒あたり 20,000 メッセージに設定されています。したがって、同じサンドボックスで同時に実行されるすべての読み取りセグメントのスロットルレートは、合計で 1 秒あたり最大 20,000 メッセージになります。この上限は変更できません。

1. **[!UICONTROL セグメントを読み取り]**&#x200B;アクティビティを使用すると、セグメントがジャーニーにエントリする時間を指定できます。これをおこなうには、 **[!UICONTROL ジャーニースケジュールを編集]** ジャーニーのプロパティにアクセスするためのリンク。次に、 **[!UICONTROL スケジューラータイプ]** フィールドに入力します。

   ![](assets/read-segment-schedule.png)

   デフォルトでは、セグメントは&#x200B;**[!UICONTROL 早急に]**&#x200B;ジャーニーにエントリします。セグメントを特定の日時にまたは繰り返しジャーニーにエントリさせる場合は、リストから目的の値を選択します。

   >[!NOTE]
   >
   >「**[!UICONTROL スケジュール]**」セクションは、「**[!UICONTROL セグメントを読み取り]**」アクティビティがキャンバスにドロップされた場合にのみ使用できます。

   ![](assets/read-segment-schedule-list.png)

   定期的な **セグメントを読み取り** が初めて実行されると、セグメント内のすべてのプロファイルがジャーニーにエントリします。 以下を使用： **増分読み取り** 最初の発生後に、ジャーニーの最後の実行以降にセグメントにエントリした個人のみをターゲットにするオプション。

   の有効化 **繰り返し時に再入力を強制** 「 」オプションを使用すると、次回の実行時に、ジャーニーに現在存在するすべてのプロファイルを自動的に削除できます。 例えば、毎日の繰り返しジャーニーに 2 日間の待機がある場合、このオプションを有効にすると、次回実行されるオーディエンスに含まれるかどうかに関係なく、プロファイルは、常に後続のジャーニー実行（翌日）に移動します。 ただし、このジャーニーのプロファイルの期間が繰り返し頻度を超える可能性がある場合は、このオプションを有効にしないで、プロファイルがジャーニーを完了できるようにすることをお勧めします。

<!--

### Segment filters {#segment-filters}

[!CONTEXTUALHELP]
>id="jo_segment_filters"
>title="About segment filters"
>abstract="You can choose to target only the individuals who entered or exited a specific segment during a specific time window. For example, you can decide to only retrieve all the customers who entered the VIP segment since last week."

You can choose to target only the individuals who entered or exited a specific segment during a specific time window. For example, you can decide to only retrieve all the customers who entered the VIP segment since last week. Only the new VIP customers will be targeted. All the customers who were already part of the VIP segment before will be excluded.

To activate this mode, click the **Segment Filters** toggle. Two fields are displayed:

**Segment membership**: choose whether you want to listen to segment entrances or exits. 

**Lookback window**: define when you want to start to listen to entrances or exits. This lookback window is expressed in hours, starting from the moment the journey is triggered.  If you set this duration to 0, the journey will target all members of the segment. For recurring journeys, it will take into account all entrances/exits since the last time the journey was triggered.

-->

>[!NOTE]
>
>ワンショット **セグメントを読み取り** ジャーニーが **完了** ジャーニーの実行後 30 日後にステータスが変更された場合。 スケジュール済み **セグメントの読み取り**&#x200B;の場合、最後の値を実行してから 30 日経過します。

### ジャーニーのテストと公開 {#testing-publishing}

この **[!UICONTROL セグメントを読み取り]** 「 」アクティビティを使用すると、単一のプロファイルまたはセグメントに適合するプロファイルの中から選択した 100 個のランダムテストプロファイルで、ジャーニーをテストできます。

これをおこなうには、 **テストモード**.次に、左側のパネルから目的のオプションを選択します。

![](assets/read-segment-test-mode.png)

その後、 **テストモード** いつも通り [ジャーニーのテスト方法を学ぶ](testing-the-journey.md)。方法を学ぶ

テストが実行されると、「**[!UICONTROL ログを表示]**」ボタンを使用し、選択したテストオプションに従ってテスト結果を確認できます。

* **[!UICONTROL 一度に 1 つのプロファイル]**：テストログには、単一テストモードを使用した場合と同じ情報が表示されます。詳しくは、[この節](testing-the-journey.md#viewing_logs)を参照してください。

* **[!UICONTROL 一度に最大 100 個のプロファイル]**：テストログでは、Adobe Experience Platform からのセグメント書き出しの進行状況と、ジャーニーにエントリしたすべての人の個人の進行状況を追跡できます。

  最大 100 個のプロファイルを一度に使用してジャーニーをテストした場合、視覚的なフローを使用してジャーニー内の個人の進行状況を追跡することはできません。

  ![](assets/read-segment-log.png)

テストが正常に完了すると、ジャーニーを公開できます（[ジャーニーの公開](publishing-the-journey.md)を参照）。セグメントに属する個人は、ジャーニーのプロパティの「**[!UICONTROL スケジューラー]**」セクションで指定された日時にジャーニーにエントリします。

>[!NOTE]
>
>繰り返しセグメントベースのジャーニーの場合、ジャーニーは、最後の処理が実行されると自動的にクローズします。終了日時が指定されていない場合は、新しいエントリに対するジャーニーを手動でクローズして終了する必要があります。

## セグメントベースのジャーニーでのオーディエンスのターゲティング

セグメントベースのジャーニーは常に、Adobe Experience Platform セグメントに属する個人を取得する「**セグメントを読み取り**」アクティビティで開始します。

セグメントに属するオーディエンスは、1 回のみ、または定期的に取得されます。

ジャーニーへのエントリ後、オーディエンスオーケストレーションのユースケースを作成し、最初のセグメントの個人をジャーニーの異なる分岐に誘導することができます。

**セグメント化**

条件を使用して、**条件**&#x200B;アクティビティでセグメント化を実行できます。例えば、VIP 顧客は特定のパス、VIP 以外の顧客は別のパスに沿って進むようにすることができます。

セグメント化は以下に基づいて実行できます。

* データソースのデータ
* ジャーニーデータのイベント部分のコンテキスト（例：ある人物が 1 時間前に受け取ったメッセージをクリックしたか）
* 日付（例：ある人物がジャーニーを経験したのは 6 月だったか？）。
* 時間（例：ある人物のタイムゾーンでは朝か？）
* ジャーニーを経験しているオーディエンスを割合に基づいて分割するアルゴリズム（例：90% - 10%、コントロール母集団を除く）。

![](assets/read-segment-audience1.png)

**除外**

セグメント化に使用するのと同じ&#x200B;**条件**&#x200B;アクティビティ（上記を参照）を使用すると、母集団の一部を除外することもできます。例えば、VIP を除外するには、そのユーザーを終了ステップ直前の分岐に送ります。

この除外は、セグメントの取得直後に発生する可能性があります。これは、母集団のカウント目的や、複数手順のジャーニーに沿ったものです。

![](assets/read-segment-audience2.png)

**結合**

ジャーニーを使用すると、セグメント化の後に、N 個の分岐を作成および結合できます。

その結果、2 つのオーディエンスを同じエクスペリエンスに戻すことができます。

例えば、VIP と非 VIP の顧客は、ジャーニーで 10 日間別々のエクスペリエンスをした後で、同じパスに戻ることができます。

結合した後、セグメント化や除外を実行してオーディエンスを再度分割できます。

![](assets/read-segment-audience3.png)
