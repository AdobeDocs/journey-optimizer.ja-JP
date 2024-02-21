---
solution: Journey Optimizer
product: journey optimizer
title: 頻度ルール
description: 頻度ルールの定義方法を学ぶ
feature: Rules
topic: Content Management
role: User
level: Intermediate
keywords: メッセージ, 頻度, ルール, プレッシャー
exl-id: 49248fb6-5a91-45b2-9de8-2f078d59c0fc
source-git-commit: 09142fa8d8c48d9ba56ef03e6a97b0be3da45916
workflow-type: tm+mt
source-wordcount: '1118'
ht-degree: 94%

---

# メッセージ頻度ルール {#frequency-rules}

[!DNL Journey Optimizer] では、過剰に配信を受けているプロファイルをメッセージやアクションから自動的に除外するクロスチャネルルールを設定することで、ユーザーがメッセージを受け取ったり、ジャーニーにエントリする頻度を制御できます。

例えば、ブランドの場合、顧客に月に 3 件を超えるマーケティングメッセージを送信しないというルールを設定できます。これを行うには、頻度ルールを使用して、月別のカレンダー期間に、1 つ以上のチャネルに基づいて送信されるメッセージの件数に上限を設定することができます。

>[!NOTE]
>
>メッセージ頻度ルールは、ユーザーがブランドからの通信の受信を登録解除できる、オプトアウト管理とは異なります。[詳細情報](../privacy/opt-out.md#opt-out-management)

➡️ [この機能をビデオで確認](#video)

## アクセスルール {#access-rules}

ルールは、**[!UICONTROL 管理]**／**[!UICONTROL ルール]**&#x200B;メニューから利用できます。すべてのルールが、変更日順に表示されます。

フィルターアイコンを使用して、カテゴリ、ステータスまたはチャネル（あるいはその両方）に基づいてフィルターを適用します。また、メッセージラベルで検索することもできます。

![](assets/message-rules-filter.png)

### 権限{#permissions-frequency-rules}

メッセージ頻度ルールにアクセス、作成、編集または削除するには、**[!UICONTROL 頻度ルールの管理]**&#x200B;権限を備えている必要があります。

**[!UICONTROL 頻度ルールの表示]**&#x200B;権限を持つユーザーはルールを表示できますが、変更や削除はできません。

![](assets/message-rules-access.png)

権限について詳しくは、[この節](../administration/high-low-permissions.md)を参照してください。

## ルールの作成 {#create-new-rule}

>[!CONTEXTUALHELP]
>id="ajo_rules_category"
>title="メッセージルールカテゴリの選択"
>abstract="アクティブ化してメッセージに適用すると、選択したカテゴリに一致するすべての頻度ルールがこのメッセージに自動的に適用されます。現在、マーケティングカテゴリのみが使用可能です。"

>[!CONTEXTUALHELP]
>id="ajo_rules_capping"
>title="ルールのキャッピングの設定"
>abstract="毎月顧客プロファイルに送信されるメッセージの最大数を指定します。頻度キャップは、毎月のカレンダー期間に基づいており、毎月の初めにリセットされます。"

>[!CONTEXTUALHELP]
>id="ajo_rules_channel"
>title="ルールを適用するチャネルの定義"
>abstract="少なくとも 1 つのチャネルを選択します。キャッピングは、チャネル間で合計カウントとして適用されます。"

新しいルールを作成するには、次の手順に従います。

1. **[!UICONTROL メッセージ頻度ルール]**&#x200B;リストにアクセスし、「**[!UICONTROL ルールを作成]**」をクリックします。

   ![](assets/message-rules-create.png)

1. ルール名を定義します。

   <!--![](assets/message-rules-details.png)-->
   ![](assets/message-rules-details-temp.png)

1. メッセージルールカテゴリを選択します。

   >[!NOTE]
   >
   >現在、**[!UICONTROL マーケティング]**&#x200B;カテゴリのみが使用可能です。

1. 次から： **[!UICONTROL 期間]** 」ドロップダウンリストから、キャッピングを適用する期間を選択します。

   <!--![](assets/message-rules-capping-duration.png)-->
   ![](assets/message-rules-capping-duration-temp.png)

   フリークエンシーキャップは、選択したカレンダーの期間に基づきます。対応する時間枠の開始時にリセットされます。

   各期間のカウンターの有効期限は次のとおりです。

   <!--* **[!UICONTROL Daily]**: The frequency cap is valid for the day until 23:59:59 UTC and resets to 0 at the start of the next day.-->

   * **[!UICONTROL 毎週]**：フリークエンシーキャップは、暦週が日曜日に始まるため、その週の土曜日 23:59:59 UTC まで有効です。有効期限は、ルールの作成に関係なく設定されます。例えば、木曜日にルールが作成された場合、このルールは土曜日の 23:59:59 まで有効です。

   * **[!UICONTROL 毎月]**：フリークエンシーキャップは、その月の最終日の 23:59:59 UTC まで有効です。例えば、1 月の月次有効期限は 1/31 23:59:59 UTC です。

   &lt;!  — 注意： [バッチセグメント化](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html?lang=ja#batch){target="_blank"}, the daily counters may not accurately reflect the current values as the daily counter snapshot is taken at midnight UTC the night before. Consequently, relying on daily counters in this scenario becomes impractical, as the snapshot does not reflect the most up-to-date counter values on the profile. To ensure accuracy for daily frequency capping rules, the use of [streaming segmentation](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/streaming-segmentation.html?lang=ja){target="_blank"} をお勧めします。 <!--Learn more on audience evaluation methods in [this section](using/audience/about-audiences.md#evaluation-method-in-journey-optimizer).-->

1. ルールの上限を設定します。つまり、1 ヶ月または 1 週間に個々のユーザープロファイルに送信できるメッセージの最大数を示します <!--or day-->  — 上で選択した内容に従います。

   <!--![](assets/message-rules-capping.png)-->

1. このルールに使用するチャネルを「**[!UICONTROL メール]**」または「**[!UICONTROL プッシュ通知]**」から選択します。

   ![](assets/message-rules-channels.png)

   >[!NOTE]
   >
   >ルールを作成するためには、少なくとも 1 つのチャネルを選択する必要があります。

1. 選択したすべてのチャネルに対して合計数としてキャッピングを適用する場合は、複数のチャネルを選択します。

   例えば、キャッピングを 15 に設定し、メールチャネルとプッシュチャネルの両方を選択します。プロファイルが既に 10 件のマーケティングメールと 5 件のマーケティングプッシュ通知を受信している場合、このプロファイルは、次に配信されるマーケティングメールまたはプッシュ通知の対象から除外されます。

1. 「**[!UICONTROL ドラフトとして保存]**」をクリックして、ルールの作成を確定します。メッセージが&#x200B;**[!UICONTROL ドラフト]**&#x200B;ステータスで、ルールリストに追加されます。

   ![](assets/message-rules-created.png)

## ルールのアクティブ化 {#activate-rule}

作成時、メッセージ頻度ルールは&#x200B;**[!UICONTROL ドラフト]**&#x200B;ステータスであり、まだどのメッセージにも影響を与えていません。有効にするには、ルールの横の楕円をクリックし、「**[!UICONTROL アクティブ化]**」を選択します。

![](assets/message-rules-activate.png)

ルールをアクティブ化すると、次回の実行時に適用されるメッセージに影響します。[メッセージに頻度ルールを適用する](#apply-frequency-rule)方法を説明します。

>[!NOTE]
>
>ルールが完全にアクティブ化されるまでに、最大 10 分かかる場合があります。ルールを有効にするために、メッセージを変更したり、ジャーニーを再公開したりする必要はありません。

メッセージ頻度ルールを非アクティブ化するには、ルールの横の「...」をクリックし、「**[!UICONTROL 非アクティブ化]**」を選択します。

![](assets/message-rules-deactivate.png)

ルールのステータスは、「**[!UICONTROL 非アクティブ]**」に変わり、今後のメッセージの実行にはルールが適用されません。現在実行中のメッセージは影響を受けません。

>[!NOTE]
>
>ルールのアクティベートを解除しても、個々のプロファイルのカウントに影響したり、リセットしたりすることはありません。

## メッセージに頻度ルールを適用する {#apply-frequency-rule}

メッセージに頻度ルールを適用するには、次の手順に従います。

1. [ジャーニー](../building-journeys/journey-gs.md)を作成する際は、ルールに定義したチャネルの 1 つを選択してメッセージを追加します。

1. 定義したカテゴリを[作成したルール](#create-new-rule)に選択します。

   ![](assets/journey-message-category.png)

   >[!NOTE]
   >
   >現在、**[!UICONTROL マーケティング]**&#x200B;カテゴリのみが、メッセージ頻度ルールで使用できます。

1. **[!UICONTROL 頻度ルール]**&#x200B;リンクをクリックすると、頻度ルール画面が新しいタブで表示されます。[詳細情報](#access-rules)

   選択したカテゴリとチャネルに一致するすべての頻度ルールが、このメッセージに自動的に適用されます。

   >[!NOTE]
   >
   >**[!UICONTROL トランザクション]**&#x200B;カテゴリを選択したメッセージは、頻度ルールに照らして評価されません。

1. [グローバルレポート](../reports/global-report.md)および[ライブレポート](../reports/live-report.md)では、配信から除外されたプロファイルの数を確認でき、配信から除外されたユーザーの理由として考えられる頻度ルールが一覧表示されます。

>[!NOTE]
>
>複数のルールを同じチャネルに適用できますが、下限に達すると、プロファイルは次の配信から除外されます。

## 例：複数のルールを組み合わせる {#frequency-rule-example}

次の例に示すように、複数のメッセージ頻度ルールを組み合わせることができます。

1. 「*全マーケティングキャッピング*」という名前の[ルールを作成](#create-new-rule)します。

   * 「メール」および「プッシュ」チャネルを選択します。
   * 制限を 12 か月に設定します。

   ![](assets/message-rules-ex-overall-cap.png)

1. ユーザーに送信されるマーケティングベースのプッシュ通知の数をさらに制限するには、2 つ目のルールとして「*プッシュマーケティングの上限*」という名前のルールを作成します。

   * 「プッシュ」チャネルを選択します。
   * 上限を 4 ヶ月に設定します。

   ![](assets/message-rules-ex-push-cap.png)

1. ルールを保存して[アクティブ化](#activate-rule)します。

1. メールを作成し、そのメッセージの&#x200B;**[!UICONTROL マーケティング]**&#x200B;カテゴリを選択します。[詳細情報](../email/create-email.md)

1. プッシュ通知を作成し、そのメッセージの&#x200B;**[!UICONTROL マーケティング]**&#x200B;カテゴリを選択します。[詳細情報](../push/create-push.md)

このシナリオでは、個々のプロファイルは次のようになります。
* 1 か月に最大 12 件のマーケティングメッセージを受信できます。
* ただし、4 件のプッシュ通知を受信した後は、マーケティングプッシュ通知から除外されます。

>[!NOTE]
>
>プロファイルのフリークエンシーキャップに達すると、翌月までカウンターをリセットする方法はないので、頻度ルールをテストする場合は、新しく作成した[テストプロファイル](../audience/creating-test-profiles.md)を使用することをお勧めします。ルールを非アクティブ化すると、上限を設定されたプロファイルがメッセージを受け取ることはできますが、カウンターの増分は削除されません。

## チュートリアルビデオ {#video}

頻度ルールを作成、アクティブ化、テスト、およびレポートする方法について説明します。

>[!VIDEO](https://video.tv.adobe.com/v/344451?quality=12)
