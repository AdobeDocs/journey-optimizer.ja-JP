---
solution: Journey Optimizer
product: journey optimizer
title: ジャーニーでのオーディエンスの使用
description: 「オーディエンスを読み取り」アクティビティを設定および使用して、 [!DNL Adobe Experience Platform]  オーディエンスの個人をジャーニーに参加させる方法を説明します。
feature: Journeys, Activities, Audiences
topic: Content Management
role: User
level: Intermediate
keywords: アクティビティ，ジャーニー，オーディエンスの読み取り，オーディエンス，セグメント，バッチ，エントリポイント，トリガー, スケジュール，オーディエンスの選定
exl-id: 7b27d42e-3bfe-45ab-8a37-c55b231052ee
version: Journey Orchestration
source-git-commit: d7d9c371f4b0d8b4ea51e1f23eb9a2f665711fce
workflow-type: tm+mt
source-wordcount: '3435'
ht-degree: 63%

---

# ジャーニーでのオーディエンスの使用 {#segment-trigger-activity}

「オーディエンスを読み取り」アクティビティを使用して、定義されたオーディエンスでジャーニーを開始します。 オーディエンスとその実行日時を選択し、[条件](#audience-targeting-in-journeys)、タイマー、アクションを使用して、各プロファイルのパスをパーソナライズします。

## オーディエンスを読み取りアクティビティについて {#about-segment-trigger-activity}

>[!CONTEXTUALHELP]
>id="ajo_journey_read_segment"
>title="「オーディエンスを読み取り」アクティビティ"
>abstract="選択した [!DNL Adobe Experience Platform] オーディエンスのすべての認定済みプロファイルをこのジャーニーに追加します。 1 回またはスケジュールに従って実行します。"

「**オーディエンスを読み取り**」アクティビティは、選択した[!DNL Adobe Experience Platform] オーディエンスのすべてのプロファイルをジャーニーに追加するジャーニーエントリポイントアクティビティです。 エントリは1回または定期的に実行できます。 APIおよび技術参照では、このアクティビティはセグメントトリガーまたはオーディエンスベースのジャーニーエントリとも呼ばれます。

**オーディエンスの読み取りとオーディエンスの選定を使用するタイミング**

| 次の場合に&#x200B;**オーディエンスの読み取り**&#x200B;を使用 | 次の場合に&#x200B;**[Audience Qualification](audience-qualification-events.md)**&#x200B;を使用 |
|----------------------------|-----------------------------------------------------------------------|
| ジャーニーを1回または1回のスケジュール（バッチ）で実行する場合。 | 顧客プロファイルは、適格なリードをリアルタイムで獲得するために必要です。 |
| オーディエンスはバッチ評価されます（毎日のスナップショットなど）。 | オーディエンスは、ストリーミングベースまたはイベントベースです。 |
| オーディエンスの評価とジャーニー入力の間に遅延が発生しても問題ありません。 | プロファイルが適格になったら、すぐにエントリする必要があります。 |

**主要な制限：** ジャーニーごとに1つの読み取りオーディエンス （最初のアクティビティにする必要があります）、アクティビティごとに1つのオーディエンス、組織ごとに最大5つの同時読み取りオーディエンス実行、サンドボックスごとに1秒あたり20,000件のプロファイル、12時間のジョブタイムアウト。 [ ガードレールと制限事項](../start/guardrails.md#read-segment-g)の詳細。

**前提条件：**&#x200B;構築および評価される[!DNL Adobe Experience Platform]のオーディエンス（リアライズ済みステータス）、ジャーニー用に選択された個人ベースのID名前空間、および繰り返し実行の場合、[のスケジューリングとスループットの制限](../start/guardrails.md#read-segment-g)について理解する。

例えば、`Luma app opening and checkout` オーディエンスの構築[ ユースケースで作成された](../audience/about-audiences.md) オーディエンスは、エントリポイントとして使用できます。 条件、タイマー、イベント、アクションを使用して、適格なすべてのプロファイルがジャーニーにエントリし、個別のパスを進みます。

➡️ [この機能をビデオで確認](#video)


>[!CAUTION]
>
>* オーディエンスを読み取りアクティビティを使用する前に、[ガードレールと制限のトピックに目を通してください](#must-read)。

## アクティビティの設定 {#configuring-segment-trigger-activity}

**オーディエンス** （必須）、**名前空間** （必須）、**読み取り率** （必須、デフォルトは5,000/秒）、**スケジュール** （ジャーニー実行時）を設定します。 オプションで&#x200B;**ラベル**&#x200B;と&#x200B;**補足識別子**&#x200B;を追加します。 以下の手順では、各設定について説明します。

### アクティビティを追加してオーディエンスを選択 {#add-activity-and-select-audience}

>[!CONTEXTUALHELP]
>id="ajo_journey_read_segment_label"
>title="ラベル"
>abstract="レポートモードとテストモードのログでこのアクティビティを識別するオプションのラベル。"

>[!CONTEXTUALHELP]
>id="ajo_journey_read_segment_audience"
>title="オーディエンス"
>abstract="プロファイルがこのジャーニーにエントリする [!DNL Adobe Experience Platform] オーディエンスを選択します。"

>[!CONTEXTUALHELP]
>id="ajo_journey_read_segment_namespace"
>title="名前空間"
>abstract="ジャーニーにエントリする個人の識別に使用する ID （メール、ECID など）を選択します。 デフォルトでは、このフィールドには、最後に使用した名前空間が事前に入力されています。"

1. **[!UICONTROL オーケストレーション]**&#x200B;カテゴリを展開し、**[!UICONTROL オーディエンスをを読み取り]**&#x200B;アクティビティをキャンバスにドロップします。

   アクティビティは、ジャーニーの最初のステップとして配置する必要があります。

1. アクティビティに&#x200B;**[!UICONTROL ラベル]**&#x200B;を追加します（オプション）。 オプションのラベルを使用すると、レポートとテストモードのログのアクティビティを特定できます。

1. 「**[!UICONTROL オーディエンス]**」フィールドで、ジャーニーにエントリする [!DNL Adobe Experience Platform] オーディエンスを選択し、「**[!UICONTROL 保存]**」をクリックします。[セグメント定義](../audience/creating-a-segment-definition.md)を使用して生成された [!DNL Adobe Experience Platform] オーディエンスを選択できます。

   >[!NOTE]
   >
   >さらに、[!DNL Adobe Experience Platform] オーディエンスコンポジション [を使用して作成された](../audience/get-started-audience-orchestration.md)人のオーディエンスをターゲットにすることができます。
   >また、CSV ファイル [からアップロードされた](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html?lang=ja#import-audience){target="_blank"} オーディエンスをターゲットにすることもできます。
   >[Journey Optimizer でオーディエンスを生成およびターゲットにする方法の詳細情報](../audience/about-audiences.md)。

   リストに表示される列は、カスタマイズして並べ替えることができます。

   ![利用可能な[!DNL Adobe Experience Platform] オーディエンス ](assets/read-segment-selection.png)を表示するオーディエンス選択インターフェイス

   オーディエンスが追加されると、「**[!UICONTROL コピー]**」ボタンを使用して、オーディエンスの名前と ID をコピーできます。

   `{"name":"Luma app opening and checkout","id":"8597c5dc-70e3-4b05-8fb9-7e938f5c07a3"}`

   ![オーディエンス名と ID を JSON 形式でコピーする「コピー」ボタン](assets/read-segment-copy.png)

   >[!NOTE]
   >
   >オーディエンスの参加ステータスが&#x200B;**適合**&#x200B;の個人のみが、ジャーニーにエントリします。オーディエンスの評価方法について詳しくは、[セグメント化サービスのドキュメント](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html?lang=ja#interpret-segment-results){target="_blank"}を参照してください。

1. 「**[!UICONTROL 名前空間]**」フィールドで、個人の識別に使用する名前空間を選択します。デフォルトでは、このフィールドには、最後に使用した名前空間が事前に入力されています。 [名前空間の詳細情報](../event/about-creating.md#select-the-namespace)。

   >[!NOTE]
   >
   >様々な ID の中から選択した ID（名前空間）を持たないオーディエンスに属する個人は、ジャーニーにエントリできません。ユーザーベースの ID 名前空間のみ選択できます。名前空間を参照テーブルに対して定義した場合（例：ProductID 名前空間を Product 参照に対して定義した場合）、その名前空間を&#x200B;**名前空間**&#x200B;ドロップダウンリストで使用することはできません。

### 補足識別子 {#read-audience-supplemental-id}

オプションで、**補足識別子**&#x200B;を使用して、プロファイル IDに加えてセカンダリ ID （注文IDや予約IDなど）のコンテキストでジャーニーを実行できます。 これにより、補足識別子が異なる場合に、同じプロファイルの複数のエントリを許可します。

[ ジャーニーで補足識別子を使用する方法について説明します](supplemental-identifier.md)。 オーディエンスジャーニーを読み取る場合、補足IDはプロファイル属性である必要があります。補足IDを使用する場合、読み取り率は1秒あたり500 プロファイルに制限されます。

### ガードレールとレコメンデーション {#must-read}

**オーディエンスの読み取り** アクティビティに関するすべてのガードレールと制限（同時実行、スループット、アクティビティごとに1人のオーディエンス、ジョブタイムアウト、再試行など）は、[ ガードレールと制限](../start/guardrails.md#read-segment-g)に一覧表示されます。

**レコメンデーション**

* ベストプラクティスとして、信頼できる一貫性のあるカウントを得るために、**オーディエンスを読み取り** アクティビティでバッチオーディエンスを使用します。 「オーディエンスを読み取り」は、バッチのユースケース向けに設計されています。ユースケースでリアルタイムデータが必要な場合は、代わりに[ オーディエンスの選定](audience-qualification-events.md) アクティビティを使用してください。
* [CSV ファイルから読み込まれた](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html?lang=ja#import-audience)オーディエンスや、[構成ワークフロー](../audience/get-started-audience-orchestration.md)から生成されたオーディエンスは、「**オーディエンスを読み取り**」アクティビティで選択できます。これらのオーディエンスは、「**オーディエンスの選定**」アクティビティでは使用できません。
* オーディエンスのスナップショットのタイミング、バッチセグメント化の完了ウィンドウ、およびジャーニーが常に最新のデータで実行されることを確認する方法については、[ タイミングとデータの伝達](#timing-and-data-propagation)を参照してください。 定期的なジャーニーの場合は、最新のオーディエンススナップショットの準備が整うまで自動的に実行を遅らせるために、「**[!UICONTROL トリガーをバッチオーディエンスの評価]**」オプションを有効にすることを検討してください。 [詳細情報](#schedule)

>[!CAUTION]
>
>[リアルタイム顧客プロファイルデータとセグメント化のガードレール](https://experienceleague.adobe.com/docs/experience-platform/profile/guardrails.html?lang=ja){target="_blank"}は、[!DNL Adobe Journey Optimizer] にも適用されます。

**次：** [読み取り率](#profile-entry-and-reading-rate)と[ スケジュール ](#schedule)を設定してから、[ テストして公開](#testing-publishing)します。

### プロファイルのエントリと読み取り率 {#profile-entry-and-reading-rate}

>[!CONTEXTUALHELP]
>id="ajo_journey_read_segment_reading_rate"
>title="読み取り率"
>abstract="1 秒あたりにジャーニーにエントリするプロファイルの最大数（500 ～ 20,000）。 初期設定は 5,000 です。"

**[!UICONTROL 読み取り率]**&#x200B;を設定します（必須）。 これは、1 秒あたりにジャーニーにエントリできるプロファイルの最大数です。このレートは、このアクティビティにのみ適用され、ジャーニーの他のアクティビティには適用されません。例えば、カスタムのアクションに対してスロットルレートを定義する場合は、Throttling API を使用する必要があります。この[ページ](../configuration/throttling.md)を参照してください。

この値は、ジャーニーバージョンのペイロードに格納されます。デフォルト値は、1 秒あたり 5,000 プロファイルです。この値は、1 秒あたり 500～20,000 プロファイルの範囲で変更できます。

>[!NOTE]
>
>サンドボックスあたりの全体的な読み取り率は、1 秒あたり 20,000 プロファイルに設定されています。したがって、同じサンドボックスで同時に実行されるすべての「オーディエンスを読み取り」の読み取り率は、合計で 1 秒あたり最大 20,000 プロファイルになります。このキャップは変更できません。ジャーニーの処理率とスループットについて詳しくは、[この節](entry-management.md#journey-processing-rate)を参照してください。

### ジャーニーのスケジュール {#schedule}

>[!CONTEXTUALHELP]
>id="ajo_journey_read_segment_scheduler_start_date"
>title="開始日時"
>abstract="このジャーニーをいつ開始するかを定義します。"

>[!CONTEXTUALHELP]
>id="ajo_journey_read_segment_scheduler_repeat_until"
>title="繰り返しの期限"
>abstract="繰り返し実行の終了日を定義します。"

>[!CONTEXTUALHELP]
>id="ajo_journey_read_segment_scheduler_repeat_every"
>title="繰り返し間隔"
>abstract="ジャーニーの実行頻度（毎日、毎週など）。"

>[!CONTEXTUALHELP]
>id="ajo_journey_read_segment_scheduler_incremental_read"
>title="増分読み取り"
>abstract="最初の実行後、オーディエンスに追加された新しいプロファイルのみがジャーニーにエントリします。"

>[!CONTEXTUALHELP]
>id="ajo_journey_read_segment_scheduler_force_reentrance"
>title="再エントリを強制する"
>abstract="新しいオーディエンスが読み取られる前に、ジャーニーのすべての参加者をクリアします。"

>[!CONTEXTUALHELP]
>id="ajo_journey_read_segment_scheduler_synchronize_audience"
>title="バッチオーディエンス評価の後にトリガー"
>abstract="バッチオーディエンスが新たに評価された後にのみジャーニーを実行します。"

>[!CONTEXTUALHELP]
>id="ajo_journey_read_segment_scheduler_synchronize_audience_wait_time"
>title="新しいオーディエンス評価の待機時間"
>abstract="ジャーニーが新しいオーディエンスデータを待つ時間（1～6 時間、分または時間）。"

デフォルトでは、ジャーニーは 1 回実行されるように設定されています。ジャーニーを実行する特定の日付／時刻と頻度を定義するには、次の手順に従います。

>[!NOTE]
>
>**ジャーニーステータスと91日間のグローバル タイムアウト：**
>
>* **ワンショット** ジャーニーの実行後、読み取りオーディエンスのジャーニーは&#x200B;**終了** ステータスに91日（[ ジャーニーグローバルタイムアウト ](journey-properties.md#global_timeout)）移動します。
>* **繰り返し**&#x200B;終了日のないオーディエンスジャーニーを読み取る&#x200B;**ジャーニーが公開されている限り、ライブ**&#x200B;を維持します。 **完了** ステータスに移行します。**最後に発生した**&#x200B;の実行から91日後です。
>* 91日間のタイムアウトは、ジャーニーを流れる個々の&#x200B;**プロファイル**&#x200B;に適用されます（プロファイルがアクティブであり続けることができる最大時間）。ジャーニーのライブステータスには適用されません。
>* 91日間の&#x200B;**レポートウィンドウ**&#x200B;は別の概念です。UIには、約91日間のパフォーマンスデータが表示されます。 古いデータはUIではアクセスできませんが、ジャーニーは引き続き実行されます。 [詳細情報](journey-properties.md#global_timeout)

1. **[!UICONTROL オーディエンスを読み取り]**&#x200B;アクティビティのプロパティで、「**[!UICONTROL ジャーニースケジュールを編集]**」を選択します。

   ![オーディエンスを読み取りアクティビティのプロパティの「ジャーニースケジュールを編集」ボタン](assets/read-segment-schedule.png)

1. ジャーニーのプロパティが表示されます。**[!UICONTROL スケジューラータイプ]**&#x200B;ドロップダウンリストで、ジャーニーを実行する頻度を選択します。

   ![頻度オプション（1 回、毎日、毎週、毎月）を含むスケジューラータイプドロップダウン](assets/read-segment-schedule-list.png)

繰り返しジャーニーの場合は、ジャーニーへのプロファイルのエントリを管理するのに役立つ特定のオプションを使用できます。各オプションについて詳しくは、以下の節を展開してください。

![オーディエンスの読み取りの繰り返しオプション：増分読み取り、再エントリを適用、バッチ後にトリガー](assets/read-audience-options.png)

+++**[!UICONTROL 増分読み取り]**

繰り返しの&#x200B;**オーディエンスを読み取り**&#x200B;を含んだジャーニーが初めて実行されると、オーディエンス内のすべてのプロファイルがジャーニーにエントリします。このオプションを使用すると、最初の実行後、ジャーニーの前回の実行以降にオーディエンスにエントリした個人のみをターゲットにすることができます。

このオプションを使用すると、システムは [!DNL Adobe Experience Platform] のセグメント化サービスによって実行された前回のオーディエンス評価ジョブの時点から **24 時間**&#x200B;前まで遡って確認します。

セグメント化が完了すると、プロファイルスナップショットのエクスポートジョブが開始され、Journey Optimizer が新しいプロファイルを検出して処理できるようになります。これらの 2 つのジョブの間にジャーニーがスケジュールされている場合、増分読み取りでは、ジャーニーの前回の実行以降にオーディエンスのメンバーになったプロファイルは取得されません。

プロファイルが欠落するリスクを最小限に抑えるには：
* 「**[!UICONTROL バッチオーディエンス評価の後にトリガー]**」オプションを有効にすると、発生した経過時間に関係なく、最後に成功したジャーニー実行時までルックバック期間を延長できます
* 毎日のバッチセグメント化ジョブが完了した後にジャーニーが適切に実行されるようにスケジュールします（通常 2～3 時間のバッファー）
* すぐにプロファイルを組み込む必要がある緊急のユースケースでは、代わりにストリーミングオーディエンスでの[オーディエンスの選定](audience-qualification-events.md)アクティビティの使用を考慮します

>[!CAUTION]
>
>ジャーニーで[ カスタムアップロードオーディエンス ](../audience/about-audiences.md#about-segments)をターゲットにしている場合、プロファイルは、このオプションが繰り返しジャーニーで有効になっている場合にのみ、最初の繰り返しで取得されます。 これらのオーディエンスは固定されています。

+++

+++**[!UICONTROL 繰り返し時に再エントリを強制する]**

このオプションを使用すると、ジャーニーにまだ存在するすべてのプロファイルを、次回の実行時に自動的に終了させることができます。

例えば、毎日の繰り返しジャーニーで2日間待機している場合、このオプションを有効にすると、プロファイルは次のジャーニー実行に移動します。 これは、次の実行オーディエンスに属しているかどうかを問わず、次の日に実行されます。

このジャーニーでのプロファイルの存続期間が繰り返し頻度よりも長くなる可能性がある場合は、プロファイルがジャーニーを終了できるようにするために、このオプションをアクティブ化しないでください。

+++

+++**[!UICONTROL バッチオーディエンス評価の後にトリガー]**

毎日スケジュールされ、バッチオーディエンスをターゲティングするジャーニーの場合、バッチセグメント化ジョブからの新しいオーディエンスデータを待機するジャーニーの時間枠を最大 6 時間まで定義できます。セグメント化ジョブが時間枠内に完了すると、ジャーニーがトリガーされます。それ以外の場合は、次回の実行までジャーニーはスキップされます。このオプションにより、正確かつ最新のオーディエンスデータを使用してジャーニーが実行されます。

例えば、毎日午後 6 時にジャーニーがスケジュールされている場合、ジャーニーの実行前に待機する分数または時間数を指定できます。午後 6 時にジャーニーが起動すると、新しいオーディエンス、つまり前回のジャーニー実行時に使用されたオーディエンスよりも新しいオーディエンスがないか確認します。指定した時間枠内で、新しいオーディエンスが検出されるとすぐにジャーニーが実行されます。新しいオーディエンスが検出されない場合、その日のジャーニーの実行はスキップされます。

+++

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

## ジャーニーのテストと公開 {#testing-publishing}

**[!UICONTROL オーディエンスを読み取り]**&#x200B;アクティビティを使用すると、単一プロファイルでジャーニーをテストできます。

それには、テストモードを有効にします。

![テストプロファイルの選択を含むオーディエンスを読み取りアクティビティのテストモードインターフェイス](assets/read-segment-test-mode.png)

通常どおりにテストモードを設定し実行します。[ジャーニーのテスト方法を学ぶ](testing-the-journey.md)。

テストを実行したら、「**[!UICONTROL ログを表示]**」ボタンを使用して、テスト結果を確認できます。詳しくは、[この節](testing-the-journey.md#viewing_logs)を参照してください。

![オーディエンス実行結果とプロファイルフローを示すテストログ](assets/read-segment-log.png)

テストが正常に完了すると、ジャーニーを公開できます（[ジャーニーの公開](../building-journeys/publish-journey.md)を参照）。オーディエンスに属する個人は、ジャーニーのプロパティの「**[!UICONTROL スケジューラー]**」セクションで指定された日時にジャーニーにエントリします。

>[!NOTE]
>
>繰り返しのオーディエンスベースジャーニーの場合、ジャーニーは、最後の実行が完了すると自動的にクローズします。終了日時が指定されていない場合は、新しいエントリに対するジャーニーを手動でクローズして終了する必要があります。

## ジャーニーにおけるオーディエンスのターゲティング {#audience-targeting-in-journeys}

オーディエンスベースのジャーニーは、常に&#x200B;**オーディエンスを読み取り** アクティビティで開始し、[!DNL Adobe Experience Platform] オーディエンスに属する個人を取得します。 これらのプロファイルは、1回または定期的に読み取られます。

ジャーニーにエントリした後、属性または行動でセグメント化、母集団の一部を除外、または分岐を結合（和集合）するなど、**条件** アクティビティを使用してオーケストレーションします。 以下の節では、各パターンについて説明します。

**セグメント化**

条件を使用して、**条件**&#x200B;アクティビティでセグメント化を実行できます。例えば、VIP 顧客は特定のパス、VIP 以外の顧客は別のパスに沿って進むようにすることができます。

セグメント化は以下に基づいて実行できます。

* データソースのデータ
* ジャーニーデータのイベント部分のコンテキスト（例：ある人物が 1 時間前に受け取ったメッセージをクリックしたか）
* 日付（例：ある人物がジャーニーを経験したのは 6 月だったか？）。
* 時間（例：その人物のタイムゾーンで午前中か？）
* ジャーニーに流入するオーディエンスを割合に基づいて分割するアルゴリズム（例：90% - 10%、コントロール母集団を除外）

![VIP パスと VIP 以外のパスへのオーディエンスのセグメント化の条件アクティビティ](assets/read-segment-audience1.png)

>[!NOTE]
>
>**[!UICONTROL オーディエンスを読み取り]**&#x200B;アクティビティで「毎日」のスケジューラータイプを使用する場合、新しいオーディエンスデータを待機するジャーニーの時間枠を定義できます。これにより、正確なターゲティングが確保され、バッチセグメント化ジョブの遅延によって発生する問題を防ぐことができます。[詳しくは、ジャーニーのスケジュール方法を参照してください](#schedule)

**除外**

セグメント化に使用するのと同じ&#x200B;**条件**&#x200B;アクティビティ（上記を参照）を使用すると、母集団の一部を除外することもできます。例えば、VIP を除外するには、そのユーザーを終了ステップ直前の分岐に送ります。

この除外は、母集団のカウントを目的として、または複数のステップから成るジャーニーに従って、オーディエンスの取得直後に発生する可能性があります。

![終了アクティビティを使用した除外分岐を含むジャーニーパス](assets/read-segment-audience2.png)

**和集合**

ジャーニーを使用すると、セグメント化の後に、N 個の分岐を作成および結合できます。その結果、2 つのオーディエンスを同じエクスペリエンスに戻すことができます。

例えば、VIP の顧客と VIP 以外の顧客は、ジャーニーで 10 日間別々のエクスペリエンスを経た後で、同じパスに戻ることができます。結合した後、セグメント化や除外を実行してオーディエンスを再度分割できます。

![和集合を使用したセグメント化の後に再度結合されるジャーニーパス](assets/read-segment-audience3.png)

## トラブルシューティング {#audience-count-mismatch}

このセクションでは、**オーディエンスサイズの不一致** （入力するプロファイル数が予想よりも少ない）、**処理されたプロファイル数がゼロ** （オーディエンスの警告を読み取るか、エントリなし）、**遅延または欠落したエントリ** （タイミングとデータの伝達）を解決するのに役立ちます。

>[!NOTE]
>
>オーディエンスを読み取りアクティビティを実行すると、システムではオーディエンスの書き出し操作のライフサイクルを追跡する内部イベント（`segmentExportJob` イベントと呼ばれる）が生成されます。これらのイベントは、個々のプロファイルごとではなく、アクティビティレベルで記録され、監視やトラブルシューティングの目的でクエリを実行できます。詳しくは、[オーディエンスを読み取りイベントのクエリ](../reports/query-examples.md#read-segment-queries)を参照してください。

**問題を検索：**

| 症状 | に移動 |
|---------|--------|
| オーディエンスサイズよりも入力されたプロファイル数が少ない（またはそれ以上） | [ タイミングとデータの伝達](#timing-and-data-propagation)、[ データの検証と監視](#data-validation-and-monitoring) |
| オーディエンスの読み取りがゼロのプロファイルを処理しました。アラートが実行されました | [処理されたプロファイルがゼロです](#zero-profiles-processed) |
| バッチオーディエンスのエントリが遅延または欠落している | [ タイミングとデータの伝達](#timing-and-data-propagation) |
| セグメントのジョブのステータスまたは名前空間を確認する必要があります | [ データの検証と監視](#data-validation-and-monitoring) |

### プロファイルが処理されていません {#zero-profiles-processed}

**オーディエンスの読み取り** アクティビティがプロファイルを処理していない場合（例：[ オーディエンスの読み取りアラート ](../reports/alerts.md#alert-read-audiences)）:

1. **オーディエンスが空かどうかを確認する** - [!DNL Adobe Experience Platform]で、オーディエンスサイズとプロファイルが&#x200B;**Realized** ステータスであることを確認します。 空のオーディエンスまたは未評価のオーディエンスは、エントリが0になります。
2. **名前空間を確認** - オーディエンスの読み取りアクティビティで選択した名前空間は、オーディエンスのプロファイルに存在する必要があります。 このIDのないプロファイルはジャーニーにエントリできません。 [名前空間の詳細情報](../event/about-creating.md#select-the-namespace)。
3. **アラートの確認と再試行** – 失敗は&#x200B;**アラート**&#x200B;で報告されます。 システムは、10分ごとに最大1時間、書き出しジョブの作成を再試行します。 [再試行とアラートの詳細](#read-audience-retry)。

これらのチェック後も問題が解決しない場合は、「[ タイミングとデータの伝播](#timing-and-data-propagation)」および「[ データの検証と監視](#data-validation-and-monitoring)」を参照して、バッチと設定の原因を確認してください。

### タイミングとデータの生成 {#timing-and-data-propagation}

* **バッチセグメント化ジョブの完了**：バッチオーディエンスの場合、ジャーニーを実行する前に、毎日のバッチセグメント化ジョブが完了し、スナップショットが更新されていることを確認します。バッチオーディエンスは、セグメント化ジョブの完了から約 **2 時間**&#x200B;後に使用できます。詳しくは、[オーディエンスの評価方法](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html?lang=ja#evaluate-segments){target="_blank"}を参照してください。

* **データ取り込みのタイミング**：ジャーニーの実行前にプロファイルデータ取り込みが完全に完了していることを確認します。プロファイルがジャーニーの開始直前に取り込まれた場合、まだオーディエンスに反映されていないことがあります。[ [!DNL Adobe Experience Platform]での](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html?lang=ja){target="_blank"} データ取り込みについて詳しく説明します。

* **「バッチオーディエンス評価の後にトリガー」を使用**：バッチオーディエンスを使用する毎日のスケジュール済みジャーニーの場合は、「**[!UICONTROL バッチオーディエンス評価の後にトリガー]**」オプションを有効にすることを考慮します。これにより、ジャーニーは実行される前に最新のオーディエンスデータ（最大 6 時間）を待機するようになります。 [詳しくは、スケジュール設定を参照してください。](#schedule)

* **待機アクティビティを追加**：最近取り込まれたデータを持つストリーミングオーディエンスの場合は、データの生成とプロファイルの選定の時間を確保するために、ジャーニーの開始時に&#x200B;**待機**&#x200B;アクティビティを追加することを考慮します。[待機アクティビティの詳細情報](wait-activity.md)

* **`inAudience()`条件のタイミング：** オーディエンスの読み取りジャーニー内の条件ノードで`inAudience()`を使用すると、プロファイルのバッチ投影からセグメントメンバーシップが読み取られます。 この投影内のデータは、取り込み後&#x200B;**2時間**&#x200B;以内に更新されます。 伝播タイミングのシナリオについて詳しくは、[inAudience関数のドキュメント ](functions/functioninaudience.md#propagation-timing)を参照してください。

### データ検証 {#data-validation-and-monitoring}

* **セグメント化ジョブの状態を確認**: [!DNL Adobe Experience Platform] [監視ダッシュボード ](https://experienceleague.adobe.com/docs/experience-platform/dataflows/ui/monitor-segments.html?lang=ja){target="_blank"}でバッチ セグメント化ジョブの完了時間を監視します。 オーディエンスデータの準備が整ったかどうかを検証するために使用します。

* **結合ポリシーを確認**：オーディエンスに対して設定された結合ポリシーが、異なるソースからのプロファイルデータを組み合わせる場合の予想される動作と一致していることを確認します。[ [!DNL Adobe Experience Platform]の](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/overview.html?lang=ja){target="_blank"}結合ポリシーについて詳しく説明します。

* **セグメント定義を確認**：セグメント定義が正しく設定され、予想されるすべての選定条件が含まれていることを確認します。詳しくは、[オーディエンスの作成](../audience/creating-a-segment-definition.md)を参照してください。特に注意すべき点：
   * イベントのタイムスタンプに基づいてプロファイルを除外する場合がある時間ベースの条件
   * 最近更新されたデータに依存する属性の選定
   * ストリーミングとバッチの評価方法

* **名前空間の設定を検証**：**オーディエンスを読み取り**&#x200B;アクティビティで選択された名前空間が、オーディエンス内のプロファイルで使用されるプライマリ ID と一致していることを確認します。選択された名前空間のないプロファイルは、ジャーニーにエントリしません。詳しくは、[ID 名前空間](../event/about-creating.md#select-the-namespace)を参照してください。

### ベストプラクティス

* **セグメント化の後にジャーニーをスケジュール**：バッチオーディエンスの場合、通常のバッチセグメント化ジョブの完了時間から 2～3 時間以上後にジャーニーの実行をスケジュールします。[ジャーニーのスケジュールの詳細情報](#schedule)

* **リアルタイムのユースケースにストリーミングオーディエンスを使用**：即時のプロファイルの選定とジャーニーのエントリが必要な場合は、バッチオーディエンスでの&#x200B;**オーディエンスを読み取り**&#x200B;の代わりに、ストリーミングオーディエンスで[オーディエンスの選定](audience-qualification-events.md)アクティビティを使用します。

* **最初に小規模なオーディエンスでテスト**：大規模なジャーニーを開始する前に、小規模なサブセットでテストして、カウントが期待値と一致することを検証します。[ジャーニーのテスト方法の詳細情報](testing-the-journey.md)

* **定期的に監視**：オーディエンスサイズとジャーニーエントリ指標の定期的な監視を設定し、不一致を早期に検出します。詳しくは、[ジャーニーの処理率とエントリ管理](entry-management.md)を参照してください。

### サポートに連絡するタイミング

上記の手順を実行した後もカウントの不一致またはプロファイルがゼロの実行が保持される場合は、Adobe サポートにお問い合わせください。 準備ができました：オーディエンス名/ID、ジャーニー名/ID、スケジュールされた実行時間、サンドボックス、および不一致の簡単な説明（例：「オーディエンスは10Kが確認されたことを示し、2Kのみが[日付]にジャーニーにエントリしました」）。

## 再試行 {#read-audience-retry}

再試行は、エクスポートジョブの取得中に、オーディエンストリガージャーニー（**オーディエンスを読み取り**&#x200B;または&#x200B;**ビジネスイベント**&#x200B;で始まる）にデフォルトで適用されます。エクスポートジョブの作成中にエラーが発生した場合、最大 1 時間、10 分ごとに再試行が行われます。それ以降は失敗と見なされます。したがって、これらのタイプのジャーニーは、スケジュールされた時間から最大 1 時間後に実行できます。

失敗した&#x200B;**オーディエンスの読み取り**&#x200B;トリガーがキャプチャされ、**アラート**&#x200B;に表示されます。 **オーディエンスの読み取りアラート**&#x200B;は、**オーディエンスの読み取り** アクティビティが、スケジュールされた実行時間から10分後にプロファイルを処理しなかった場合に警告します。 このエラーは、技術的な問題または空のオーディエンスが原因で発生する可能性があります。 技術的な問題が原因で失敗した場合でも、問題の種類によっては再試行が発生する可能性があります。 例えば、書き出しジョブの作成に失敗した場合、10分ごとに最大1時間再試行します。 [詳細情報](../reports/alerts.md#alert-read-audiences)

オーディエンスの読み取りのガードレール（再試行とスループットの制限を含む）の完全なリストについては、[ ガードレールと制限](../start/guardrails.md#read-segment-g)を参照してください。

## 関連トピック

* [オーディエンスを作成](../audience/about-audiences.md)
* [オーディエンスの選定アクティビティ](audience-qualification-events.md)
* [ジャーニーの補足識別子の使用](supplemental-identifier.md)
* [ガードレールと制限](../start/guardrails.md#read-segment-g)
* [ジャーニー処理率とエントリ管理](entry-management.md)
* [ジャーニーのテスト](testing-the-journey.md)
* [ジャーニーの公開](../building-journeys/publish-journey.md)

## チュートリアルビデオ {#video}

「オーディエンスを読み取り」アクティビティによってトリガーされるジャーニーに適用可能なユースケースを理解します。バッチベースのジャーニーを構築する方法と適用するベストプラクティスについて説明します。

>[!VIDEO](https://video.tv.adobe.com/v/3424997?quality=12)
