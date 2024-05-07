---
solution: Journey Optimizer
product: journey optimizer
title: ビジネスルール
description: ビジネスルールを作成および適用する方法を説明します
feature: Rules
topic: Content Management
role: User
level: Intermediate
keywords: メッセージ, 頻度, ルール, プレッシャー
hide: true
hidefromtoc: true
badge: label="Beta"
exl-id: 07f5f0b4-417e-408e-8d9e-86615c8a3fbf
source-git-commit: f8d257b04d8682bb16fcccd3fd0ef9d5389a058d
workflow-type: ht
source-wordcount: '1426'
ht-degree: 100%

---

# ビジネスルール {#business-rules}

>[!AVAILABILITY]
>
>ビジネスルールは現在、一部のユーザーのみを対象としたベータ版として提供されています。

[!DNL Journey Optimizer] では、過剰に配信を受けているプロファイルをメッセージやアクションから自動的に除外するクロスチャネルルールを設定することで、ユーザーがメッセージを受け取る頻度を制御できます。

例えば、あるブランドについて、顧客に月に 4 件を超えるマーケティングメッセージを送信しないというルールを設定できます。これを行うには、頻度ルールを使用して、月別のカレンダー期間中に 1 つ以上のチャネルに基づいて送信されるメッセージの件数を制限することができます。

精度を向上させるために、様々なルールセットを作成します。[!DNL Journey Optimizer] を使用すると、様々なタイプのマーケティングコミュニケーションにフリークエンシーキャップを適用できます。例えば、顧客に送信する&#x200B;**プロモーション情報**&#x200B;の数を制限するルールセットを作成する一方で、顧客に送信する&#x200B;**ニュースレター**&#x200B;の数を制限する別のルールセットを作成できます。

>[!NOTE]
>
>ビジネスルールは、ユーザーがブランドからの配信の受信を登録解除できるオプトアウト管理とは異なります。[詳細情報](../privacy/opt-out.md#opt-out-management)

## アクセスルールセット {#access-rule-sets}

ルールセットは、**[!UICONTROL 管理]**／**[!UICONTROL ビジネスルール（ベータ版）]**&#x200B;メニューから使用できます。すべてのルールが作成日順に表示されます。

![](assets/rule-sets-list.png)

ルールセット名をクリックし、そのコンテンツを表示および編集します。そのルールセットに含まれるすべてのルールが一覧表示されます。

右上のコンテキストメニューでは、次のことが可能です。

* ルールセットの名前と説明を編集する
* ルールセットをアクティベートする – [詳細情報](#activate-rule)
* ルールセットを削除する

![](assets/rule-set-example.png)

ルールセットに含まれるルールごとに、「**[!UICONTROL その他のアクション]**」ボタンを使用して次のことを行えます。

* ルールを編集する
* ルールをアクティベートする[詳細情報](#activate-rule)
* ルールを定義する

![](assets/rule-set-example-rules.png)

<!--### Permissions{#permissions-frequency-rules}

To access, create, edit or delete message frequency rules, you must have the **[!UICONTROL Manage frequency rules]** permission. 

Users with the **[!UICONTROL View frequency rules]** permission are able to view rules, but not to modify or delete them.

![](assets/message-rules-access.png)

Learn more about permissions in [this section](../administration/high-low-permissions.md).-->

## ルールセットを作成する {#create-rule-set}

ルールセットを作成するには、次の手順に従います。

1. **[!UICONTROL ルールセット]**&#x200B;のリストにアクセスし、「**[!UICONTROL ルールセットを作成]**」をクリックします。

   ![](assets/rule-sets-create-button.png)

1. ルールセット名を定義し、必要に応じて説明を追加して、「**[!UICONTROL 保存]**」をクリックします。

   ![](assets/rule-sets-create.png)

   >[!NOTE]
   >
   >ルールセット名は一意にする必要があります。

1. これで、このルールセットに追加する[ルールを定義](#create-new-rule)して[アクティベート](#activate-rule)できるようになりました。

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

1. 作成したルールセットで、「**[!UICONTROL ルールを追加]**」をクリックします。

   ![](assets/rule-sets-create-rule-button.png)

1. ルール名を定義します。

   >[!NOTE]
   >
   >ルールセット名は一意にする必要があります。

1. メッセージルールカテゴリを選択します。

   >[!NOTE]
   >
   >現在、**[!UICONTROL マーケティング]**&#x200B;カテゴリのみが使用可能です。

1. **[!UICONTROL 期間]**&#x200B;ドロップダウンリストから、キャッピングを適用する時間枠を選択します。[詳細情報](#frequency-cap)

1. ルールのキャッピングを設定します。これは、上記の選択に応じて、毎月、毎週または毎日、個々のユーザープロファイルに送信できるメッセージの最大数を意味します。

1. このルールに使用するチャネルを「**[!UICONTROL メール]**」、「**[!UICONTROL SMS]**」、「**[!UICONTROL プッシュ通知]**」または「**[!UICONTROL ダイレクトメール]**」から選択します。

   ![](assets/rule-set-channels.png)

   >[!NOTE]
   >
   >ルールを作成するためには、少なくとも 1 つのチャネルを選択する必要があります。

1. 選択したすべてのチャネルに対して合計数としてキャッピングを適用する場合は、複数のチャネルを選択します。

   例えば、キャップを 5 に設定し、メールチャネルと SMS チャネルの両方を選択します。プロファイルが既に 3 件のマーケティングメールと 5 件のマーケティング SMS を受信している場合、このプロファイルは、次に配信されるマーケティングメールまたは SMS の対象から除外されます。

1. 「**[!UICONTROL 保存]**」をクリックして、ルールの作成を確定します。メッセージが、**[!UICONTROL ドラフト]**&#x200B;ステータスでルールリストに追加されます。

   ![](assets/rule-set-rule-created.png)

1. 上記の手順を繰り返して、必要な数のルールをルールセットに追加します。

次に、メッセージに適用する前に、各ルールをアクティブ化する必要があります。[詳細情報](#activate-rule)

>[!NOTE]
>
>また、メッセージで選択できるように、ルールセットもアクティブ化します。

### フリークエンシーキャップ {#frequency-cap}

>[!CONTEXTUALHELP]
>id="ajo_rule_sets_duration"
>title="メッセージルールカテゴリの選択"
>abstract="アクティブ化してメッセージに適用すると、選択したカテゴリに一致するすべての頻度ルールがこのメッセージに自動的に適用されます。現在、マーケティングカテゴリのみが使用可能です。"

**[!UICONTROL 期間]**&#x200B;ドロップダウンリストから、キャップを毎月、毎週、毎日のどちらの頻度で適用するかを選択します。

フリークエンシーキャップは、選択したカレンダーの期間に基づきます。対応する時間枠の開始時にリセットされます。

![](assets/rule-set-capping-duration.png)

各期間のカウンターの有効期限は次のとおりです。

* **[!UICONTROL 毎月]**：フリークエンシーキャップは、その月の最終日の 23:59:59 UTC まで有効です。例えば、1 月の月次有効期限は 1/31 23:59:59 UTC です。

* **[!UICONTROL 毎週]**：フリークエンシーキャップは、暦週が日曜日に始まるため、その週の土曜日 23:59:59 UTC まで有効です。有効期限は、ルールの作成に関係なく設定されます。例えば、木曜日にルールが作成された場合、このルールは土曜日の 23:59:59 まで有効です。

* **[!UICONTROL 毎日]**：日別のフリークエンシーキャップは、その日の 23:59:59 UTC まで有効で、翌日の開始とともに 0 にリセットされます。

### 日別のフリークエンシーキャップ {#daily-frequency-cap}

>[!CAUTION]
>
>日別のフリークエンシーキャップの精度を確保するには、[ストリーミングセグメント化](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/streaming-segmentation.html?lang=ja){target="_blank"}の使用が必須です。オーディエンスの評価方法について詳しくは、[この節](../audience/about-audiences.md#evaluation-method-in-journey-optimizer)を参照してください。

セグメントサイズが 1 時間あたり 6,000 万メッセージの制限までの場合<!--not clear-->、キャンペーンの間隔を 2 時間以上にする必要があります。


<!-- Journey example:

* If customer sets a Daily rule under the Global Ruleset for email <= 2/day:
   * Journey 123 (scheduled for noon)
   * Journey 456 (scheduled for noon)
   * Journey 789 (scheduled for 1 pm)

   In this example, the Daily Frequency cap will not guarantee <= 2/day. The rule will only be guaranteed when Journeys are at least 2 hours apart:
   * Journey 123 (scheduled for noon)
   * Journey 456 (scheduled for 2 pm)
   * Journey 789 (scheduled for 4 pm)-->

例えば、メールチャネルのルールセットの下に 2 日以下の日別ルールを設定し、次のキャンペーンを作成するとします。
* キャンペーン A（正午に予定）
* キャンペーン A（午後 3:00 に予定）
* キャンペーン B（午後 1:00 に予定）

この設定は、次の 2 つの理由により機能しません。
* キャンペーンは 2 時間間隔ではないので、日別のフリークエンシーキャップは保証されません。
* 日別のキャップを利用するために、同じキャンペーンを 1 日に複数回スケジュールすることはベストプラクティスではありません。

以下の例では、日別のフリークエンシーキャップを適用する必要があります。
* キャンペーン A（正午に予定）
* キャンペーン B（午後 2 :00 に予定）

<!--* To use the Daily Cap with a Journey, customers can use either an Event Triggered Journey or an Audience Qualified Journey. If customers wish to use the Daily Cap with a Read Audience Journey, they should use a Campaign instead and associate a Local Ruleset with the campaign, following the example given above.-->

## ルールおよびルールセットのアクティブ化 {#activate-rule}

作成時、ルールは&#x200B;**[!UICONTROL ドラフト]**&#x200B;ステータスになり、まだメッセージには影響を与えません。ルールを有効にするには、ルールの横にある「**[!UICONTROL その他のアクション]**」ボタンをクリックし、「**[!UICONTROL アクティブ化]**」を選択します。

![](assets/rule-set-activate-rule.png)

また、キャンペーン／ジャーニーでルールセットにアクセスし、メッセージに適用できるようにするには、ルールセットもアクティブ化する必要があります。

![](assets/rule-set-activate-set.png)

ルールセットをアクティブ化すると、次回の実行時に適用されるメッセージに影響します。メッセージにルールセットを適用する方法については、[こちら](#apply-rule-set)を参照してください。

>[!NOTE]
>
>ルールまたはルールセットが完全にアクティブ化されるまでに、最大 10 分かかる場合があります。ルールを有効にするために、メッセージを変更したり、ジャーニーを再公開したりする必要はありません。

<!--Currently, once a rule set is activated, no more rules can be added to that rule set.-->

## ルールとルールセットの非アクティブ化 {#deactivate-rule}

ルールまたはルールセットを非アクティブ化するには、目的の項目の横にある「**[!UICONTROL その他のアクション]**」ボタンをクリックし、「**[!UICONTROL 非アクティブ化]**」を選択します。

![](assets/rule-set-inactive-rule.png)

ステータスは&#x200B;**[!UICONTROL 非アクティブ]**&#x200B;に変わり、今後のメッセージの実行にはルールが適用されません。現在実行中のメッセージは影響を受けません。

>[!NOTE]
>
>ルールまたはルールセットを非アクティブ化しても、個々のプロファイルのカウントは影響を受けず、リセットされません。

## メッセージに頻度ルールを適用する {#apply-frequency-rule}

メッセージに頻度ルールを適用するには、次の手順に従います。

1. [キャンペーン](../campaigns/create-campaign.md)の作成時、ルールセットに定義したチャネルの 1 つを選択し、メッセージのコンテンツを編集します。

1. コンテンツ編集画面で、「**[!UICONTROL ビジネスルールを追加]**」ボタンをクリックします。

1. [作成したルールセット](#create-rule-set)を選択します。

   ![](assets/rule-set-campaign-add-rule-button.png)

   >[!NOTE]
   >
   >[アクティブ化](#activate-rule)したルールセットのみがリストに表示されます。

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

プロファイルのフリークエンシーキャップに達すると、次の期間までカウンターをリセットする方法はないので、頻度ルールをテストする場合は、新しく作成した[テストプロファイル](../audience/creating-test-profiles.md)を使用することをお勧めします。ルールを非アクティブ化すると、上限を設定されたプロファイルがメッセージを受け取ることはできますが、カウンターの増分は削除されません。
