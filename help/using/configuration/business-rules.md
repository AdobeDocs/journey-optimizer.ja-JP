---
solution: Journey Optimizer
product: journey optimizer
title: ビジネスルール
description: ビジネスルールの作成および適用方法を説明します
feature: Rules
topic: Content Management
role: User
level: Intermediate
keywords: メッセージ, 頻度, ルール, プレッシャー
hide: true
hidefromtoc: true
badge: label="ベータ版"
source-git-commit: c1eef06b0edc4e1bcd1b145f8f822295924b205c
workflow-type: tm+mt
source-wordcount: '1426'
ht-degree: 33%

---

# ビジネスルール {#business-rules}

>[!AVAILABILITY]
>
>現在、ビジネスルールは一部のユーザーのみを対象としたベータ版として利用できます。

[!DNL Journey Optimizer] では、過剰に配信を受けているプロファイルをメッセージやアクションから自動的に除外するクロスチャネルルールを設定することで、ユーザーがメッセージを受け取る頻度を制御できます。

例えば、ブランドの場合、顧客に 1 か月に 4 件を超えるマーケティングメッセージを送信しないというルールを設定できます。 これを行うには、頻度ルールを使用して、月別のカレンダー期間に、1 つ以上のチャネルに基づいて送信されるメッセージの件数に上限を設定することができます。

精度を向上させるために、様々なルールセットを作成します。 [!DNL Journey Optimizer] を使用すると、様々なタイプのマーケティングコミュニケーションにフリークエンシーキャップを適用できます。 例えば、ルールセットを作成して、の数を制限できます **プロモーション情報** を顧客に送信し、別のルールセットを作成して数を制限します。 **ニュースレター** がを彼らに送信しました。

>[!NOTE]
>
>ビジネスルールは、ユーザーがブランドからのコミュニケーションの受信を登録解除できる、オプトアウト管理とは異なります。 [詳細情報](../privacy/opt-out.md#opt-out-management)

## ルールセットへのアクセス {#access-rule-sets}

ルールセットは、 **[!UICONTROL 管理]** > **[!UICONTROL ビジネスルール（ベータ版）]** メニュー。 すべてのルールが、作成日順に表示されます。

![](assets/rule-sets-list.png)

ルールセット名をクリックして、そのコンテンツを表示および編集します。 そのルールセットに含まれるすべてのルールが一覧表示されます。

右上のコンテキストメニューを使用すると、次のことが可能です。

* ルールセットの名前と説明を編集
* ルールセットをアクティブ化 –  [詳細を表示する](#activate-rule)
* ルールセットの削除

![](assets/rule-set-example.png)

ルールセットに含まれる各ルールのプロパティ **[!UICONTROL その他のアクション]** ボタンを使用すると、次のことができます。

* ルールの編集
* ルールのアクティブ化 [詳細を表示する](#activate-rule)
* ルールの削除

![](assets/rule-set-example-rules.png)

<!--### Permissions{#permissions-frequency-rules}

To access, create, edit or delete message frequency rules, you must have the **[!UICONTROL Manage frequency rules]** permission. 

Users with the **[!UICONTROL View frequency rules]** permission are able to view rules, but not to modify or delete them.

![](assets/message-rules-access.png)

Learn more about permissions in [this section](../administration/high-low-permissions.md).-->

## ルールセットを作成 {#create-rule-set}

ルールセットを作成するには、次の手順に従います。

1. へのアクセス **[!UICONTROL ルールセット]** リストを選択し、 **[!UICONTROL ルールセットを作成]**.

   ![](assets/rule-sets-create-button.png)

1. ルールセット名を定義し、必要に応じて説明を追加して、 **[!UICONTROL 保存]**.

   ![](assets/rule-sets-create.png)

   >[!NOTE]
   >
   >ルールセット名は一意である必要があります。

1. 次の操作が可能になりました [ルールの定義](#create-new-rule) このルールセットに追加する操作 [アクティベート](#activate-rule) それ。

   >[!NOTE]
   >
   >メッセージに適用するすべてのルールが、ルールセット内でもアクティベートされていることを確認します。

## ルールの作成 {#create-new-rule}

>[!CONTEXTUALHELP]
>id="ajo_rule_sets_category"
>title="メッセージルールカテゴリの選択"
>abstract="アクティブ化してメッセージに適用すると、選択したカテゴリに一致するすべての頻度ルールがこのメッセージに自動的に適用されます。現在、マーケティングカテゴリのみが使用可能です。"

>[!CONTEXTUALHELP]
>id="ajo_rule_sets_capping"
>title="ルールのキャッピングの設定"
>abstract="選択した時間枠内に顧客プロファイルに送信されるメッセージの最大数を指定します。フリークエンシーキャップは、選択したカレンダー期間に基づき、対応する時間枠の開始時にリセットされます。"

>[!CONTEXTUALHELP]
>id="ajo_rule_sets_channel"
>title="ルールを適用するチャネルの定義"
>abstract="少なくとも 1 つのチャネルを選択します。キャッピングは、チャネル間で合計カウントとして適用されます。"

ルールセットにルールを追加するには、次の手順に従います。

1. 作成したルールセットで、 **[!UICONTROL ルールを追加]**.

   ![](assets/rule-sets-create-rule-button.png)

1. ルール名を定義します。

   >[!NOTE]
   >
   >ルールセット名は一意である必要があります。

1. メッセージルールカテゴリを選択します。

   >[!NOTE]
   >
   >現在、**[!UICONTROL マーケティング]**&#x200B;カテゴリのみが使用可能です。

1. **[!UICONTROL 期間]**&#x200B;ドロップダウンリストから、キャッピングを適用する時間枠を選択します。[詳細情報](#frequency-cap)

1. ルールにキャッピングを設定します。キャッピングは、上で選択した内容に応じて、1 か月、1 週間または 1 日に個々のユーザープロファイルに送信できるメッセージの最大数を意味します。

1. このルールに使用するチャネルを選択： **[!UICONTROL 電子メール]**, **[!UICONTROL SMS]**, **[!UICONTROL プッシュ通知]** または **[!UICONTROL ダイレクトメール]**.

   ![](assets/rule-set-channels.png)

   >[!NOTE]
   >
   >ルールを作成するためには、少なくとも 1 つのチャネルを選択する必要があります。

1. 選択したすべてのチャネルに対して合計数としてキャッピングを適用する場合は、複数のチャネルを選択します。

   例えば、キャッピングを 5 に設定し、メールチャネルと SMS チャネルの両方を選択します。 プロファイルが既に、選択した期間の 3 つのマーケティングメールと 2 つのマーケティング SMS を受信している場合、このプロファイルは、マーケティングメールまたは SMS の次回の配信から除外されます。

1. クリック **[!UICONTROL 保存]** をクリックして、ルールの作成を確認します。 メッセージがと共にルールセットに追加されます **[!UICONTROL ドラフト]** ステータス。

   ![](assets/rule-set-rule-created.png)

1. 上記の手順を繰り返して、必要な数のルールをルールセットに追加します。

次に、各ルールをアクティブ化して、メッセージに適用する必要があります。 [詳細情報](#activate-rule)

>[!NOTE]
>
>メッセージで選択できるように、ルールセットもアクティベートされていることを確認します。

### フリークエンシーキャップ {#frequency-cap}

>[!CONTEXTUALHELP]
>id="ajo_rule_sets_duration"
>title="メッセージルールカテゴリの選択"
>abstract="アクティブ化してメッセージに適用すると、選択したカテゴリに一致するすべての頻度ルールがこのメッセージに自動的に適用されます。現在、マーケティングカテゴリのみが使用可能です。"

から **[!UICONTROL 期間]** ドロップダウンリストで、キャッピングを毎月、毎週、毎日に適用するかどうかを選択します。

フリークエンシーキャップは、選択したカレンダーの期間に基づきます。対応する時間枠の開始時にリセットされます。

![](assets/rule-set-capping-duration.png)

各期間のカウンターの有効期限は次のとおりです。

* **[!UICONTROL 毎月]**：フリークエンシーキャップは、その月の最終日の 23:59:59 UTC まで有効です。例えば、1 月の月次有効期限は 1/31 23:59:59 UTC です。

* **[!UICONTROL 毎週]**：フリークエンシーキャップは、暦週が日曜日に始まるため、その週の土曜日 23:59:59 UTC まで有効です。有効期限は、ルールの作成に関係なく設定されます。例えば、木曜日にルールが作成された場合、このルールは土曜日の 23:59:59 まで有効です。

* **[!UICONTROL 日次]**:1 日のフリークエンシーキャップは 23 日まで有効です:59:59 UTC、次の日の開始時に 0 にリセットされます。

### 日別のフリークエンシーキャップ {#daily-frequency-cap}

>[!CAUTION]
>
>毎日のフリークエンシーキャップ ルールの精度を確保するには、を使用します。 [ストリーミングセグメント化](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/streaming-segmentation.html?lang=ja){target="_blank"} は必須です。 オーディエンスの評価方法について詳しくは、[この節](../audience/about-audiences.md#evaluation-method-in-journey-optimizer)を参照してください。

セグメントサイズが 1 時間あたり 6,000 万メッセージの制限を超える場合<!--not clear-->キャンペーンは少なくとも 2 時間離れていることを確認してください。


<!-- Journey example:

* If customer sets a Daily rule under the Global Ruleset for email <= 2/day:
   * Journey 123 (scheduled for noon)
   * Journey 456 (scheduled for noon)
   * Journey 789 (scheduled for 1 pm)

   In this example, the Daily Frequency cap will not guarantee <= 2/day. The rule will only be guaranteed when Journeys are at least 2 hours apart:
   * Journey 123 (scheduled for noon)
   * Journey 456 (scheduled for 2 pm)
   * Journey 789 (scheduled for 4 pm)-->

例えば、メールチャネルのルールセットに対して 2 日以下の日別ルールを設定し、次のキャンペーンを作成した場合です。
* キャンペーン A （正午予定）
* キャンペーン A （午後 3 時予定）
* キャンペーン B （午後 1 時予定）

この設定は、次の 2 つの理由で機能しません。
* キャンペーンは 2 時間離れていないので、1 日のフリークエンシーキャップは保証されません。
* 毎日の上限数を利用するために、同じキャンペーンを 1 日に複数回スケジュールすることはベストプラクティスではありません。

以下の例は、毎日のフリークエンシーキャップで順守される必要があります。
* キャンペーン A （正午予定）
* キャンペーン B （午後 2 時予定）

<!--* To use the Daily Cap with a Journey, customers can use either an Event Triggered Journey or an Audience Qualified Journey. If customers wish to use the Daily Cap with a Read Audience Journey, they should use a Campaign instead and associate a Local Ruleset with the campaign, following the example given above.-->

## ルールおよびルールセットのアクティブ化 {#activate-rule}

作成時、ルールには以下が含まれます **[!UICONTROL ドラフト]** ステータスおよびは、まだどのメッセージにも影響を与えていません。 有効にするには、 **[!UICONTROL その他のアクション]** ボタンがルールの隣に表示され、を選択します。 **[!UICONTROL Activate]**.

![](assets/rule-set-activate-rule.png)

また、キャンペーン/ジャーニーでルールセットにアクセスしてメッセージに適用できるようにするには、ルールセットをアクティブ化する必要があります。

![](assets/rule-set-activate-set.png)

ルールセットをアクティブ化すると、次回の実行時に適用されるメッセージに影響します。 方法を学ぶ [メッセージへのルールセットの適用](#apply-rule-set).

>[!NOTE]
>
>ルールまたはルールセットが完全にアクティブ化されるまでに、最大 10 分かかる場合があります。 ルールを有効にするために、メッセージを変更したり、ジャーニーを再公開したりする必要はありません。

<!--Currently, once a rule set is activated, no more rules can be added to that rule set.-->

## ルールとルールセットの非アクティブ化 {#deactivate-rule}

ルールまたはルールセットを非アクティブ化するには、 **[!UICONTROL その他のアクション]** ボタンをクリックし、目的の項目の横にあるを選択します。 **[!UICONTROL 非アクティブ化]**.

![](assets/rule-set-inactive-rule.png)

ワークフローのステータスは、次のように変更されます **[!UICONTROL Inactive]** また、このルールは今後のメッセージ実行には適用されません。 現在実行中のメッセージは影響を受けません。

>[!NOTE]
>
>ルールまたはルールセットのアクティベートを解除しても、個々のプロファイルのカウントに影響したり、リセットしたりすることはありません。

## メッセージに頻度ルールを適用する {#apply-frequency-rule}

メッセージに頻度ルールを適用するには、次の手順に従います。

1. の作成時 [campaign](../campaigns/create-campaign.md)で、ルールセットに定義したチャネルの 1 つを選択し、メッセージのコンテンツを編集します。

1. コンテンツ編集画面で、 **[!UICONTROL ビジネス ルールの追加]** ボタン。

1. 「」を選択します [作成したルールセット](#create-rule-set).

   ![](assets/rule-set-campaign-add-rule-button.png)

   >[!NOTE]
   >
   >のみ [有効化済み](#activate-rule) ルールセットがリストに表示されます。

   <!--Messages where the category selected is **[!UICONTROL Transactional]** will not be evaluated against business rules.-->

1. [グローバルレポート](../reports/global-report.md)および[ライブレポート](../reports/live-report.md)では、配信から除外されたプロファイルの数を確認でき、配信から除外されたユーザーの理由として考えられる頻度ルールが一覧表示されます。

>[!NOTE]
>
>複数のルールを同じチャネルに適用できますが、下限に達すると、プロファイルは次の配信から除外されます。

<!--
## Example: combine several rules {#frequency-rule-example}

You can combine several message frequency rules, such as described in the example below.

1. [Create a rule](#create-new-rule) called *Overall Marketing Capping*:

   * Select all channels.
   * Set capping to 12 monthly.

   ![](assets/message-rules-ex-overall-cap.png)

1. To further restrict the number of marketing-based push notifications that a user is sent, create a second rule called *Push Marketing Cap*:

   * Select Push channel.
   * Set capping to 4 monthly.

   ![](assets/message-rules-ex-push-cap.png)

1. Save and [activate](#activate-rule) the rule.

1. [Create a message](../building-journeys/journeys-message.md) for every channel you want to communicate through and select the **[!UICONTROL Marketing]** category for each message. [Learn how to apply a frequency rule](#apply-frequency-rule)

   ![](assets/journey-message-category.png)

In this scenario, an individual profile:
* can receive up to 12 marketing messages per month;
* but will be excluded from marketing push notifications after they have received 4 push notifications.-->

頻度ルールをテストする場合は、新規作成したを使用することをお勧めします [テストプロファイル](../audience/creating-test-profiles.md)プロファイルのフリークエンシーキャップに達すると、次の期間までカウンターをリセットする方法はないからです。 ルールを非アクティブ化すると、上限を設定されたプロファイルがメッセージを受け取ることはできますが、カウンターの増分は削除されません。

