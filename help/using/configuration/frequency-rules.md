---
title: 頻度ルール
description: 頻度ルールの定義方法を学ぶ
feature: Overview
topic: Content Management
role: User
level: Beginner
exl-id: 49248fb6-5a91-45b2-9de8-2f078d59c0fc
source-git-commit: 8766f64c4ea7985c6c9d6e4ba022ef6b1fc0dbed
workflow-type: tm+mt
source-wordcount: '856'
ht-degree: 85%

---

# メッセージ頻度ルール {#frequency-rules}

[!DNL Journey Optimizer] では、過剰に配信を受けているプロファイルをメッセージやアクションから自動的に除外するクロスチャネルルールを設定することで、ユーザーがメッセージを受け取ったり、ジャーニーにエントリする頻度を制御できます。

例えば、ブランドが顧客に送信するメッセージを 1 か月に 3 件以内に抑える場合などです。

これを行うには、頻度ルールを使用して、月別のカレンダー期間に、1 つ以上のチャネルに基づいて送信されるメッセージの件数に上限を設定することができます。

>[!NOTE]
>
>メッセージ頻度ルールは、ユーザーがブランドからの通信の受信を登録解除できる、オプトアウト管理とは異なります。[詳細情報](../messages/consent.md#opt-out-management)

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

新しいルールを作成するには、次の手順に従います。

1. **[!UICONTROL メッセージ頻度ルール]**&#x200B;リストにアクセスし、「**[!UICONTROL ルールを作成]**」をクリックします。

   ![](assets/message-rules-create.png)

1. ルール名を定義します。

   ![](assets/message-rules-details.png)

1. メッセージルールカテゴリを選択します。

   >[!NOTE]
   >
   >現在、**[!UICONTROL マーケティング]**&#x200B;カテゴリのみが使用可能です。

1. ルールにキャッピングを設定します。キャッピングは、毎月個々のユーザープロファイルに送信できるメッセージの最大数を意味します。

   ![](assets/message-rules-capping.png)

   >[!NOTE]
   >
   >フリークエンシーキャップは、月別のカレンダー期間に基づいています。毎月初めにリセットされます。

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
>ルールが完全にアクティブ化されるまでに、最大 10 分かかる場合があります。ルールを有効にするために、メッセージを変更したり、ジャーニーを再公開する必要はありません。

メッセージ頻度ルールを非アクティブ化するには、ルールの横の「...」をクリックし、「**[!UICONTROL 非アクティブ化]**」を選択します。

![](assets/message-rules-deactivate.png)

ルールのステータスは、「**[!UICONTROL 非アクティブ]**」に変わり、今後のメッセージの実行にはルールが適用されません。現在実行中のメッセージは影響を受けません。

>[!NOTE]
>
>ルールのアクティベートを解除しても、個々のプロファイルのカウントに影響したり、リセットしたりすることはありません。

## メッセージに頻度ルールを適用する {#apply-frequency-rule}

メッセージに頻度ルールを適用するには、次の手順に従います。

1. [メッセージの作成](../messages/get-started-content.md#create-new-message) ルールに定義したチャネルの 1 つを選択します。

1. 定義したカテゴリを[作成したルール](#create-new-rule)に選択します。

   ![](assets/inline-message-category.png)

   >[!NOTE]
   >
   >現在、**[!UICONTROL マーケティング]**&#x200B;カテゴリのみが、メッセージ頻度ルールで使用できます。

   <!--
   1. You can click the **[!UICONTROL Frequency rule]** link to view the frequency rules that will apply for the selected category and channel(s). A new tab will open to display the matching message frequency rules.-->

1. 選択したカテゴリとチャネルに一致するすべての頻度ルールが、このメッセージに自動的に適用されます。

   >[!NOTE]
   >
   >**[!UICONTROL トランザクション]**&#x200B;カテゴリを選択したメッセージ<!--that do not have any selected category or messages -->は、頻度ルールに照らして評価されません。

   <!--Clicking the link out button next to the category selector will jump you over to the rules inventory screen to see which rules will be applied to the message.-->

1. 配信から除外されたプロファイルの数を [グローバルレポート](../reports/global-report.md)、および [ライブレポート](../reports/live-report.md)：頻度ルールが、配信から除外されたユーザーに考えられる理由として表示されます。

>[!NOTE]
>
>複数のルールを同じチャネルに適用できますが、下限に達すると、プロファイルは次の配信から除外されます。

## 例：複数のルールを組み合わせる {#frequency-rule-example}

次の例に示すように、複数のメッセージ頻度ルールを組み合わせることができます。

1. 「*全マーケティングキャッピング*」という名前の[ルールを作成](#create-new-rule)します。

   * 「電子メール」および「プッシュ」チャネルを選択します。
   * キャッピングを 12 に設定します。

   ![](assets/message-rules-ex-overall-cap.png)

1. ユーザーに送信されるマーケティングベースのプッシュ通知の数をさらに制限するには、2 つ目のルールとして「*プッシュマーケティングの上限*」という名前のルールを作成します。

   * 「プッシュ」チャネルを選択します。
   * キャッピングを 4 に設定します。

   ![](assets/message-rules-ex-push-cap.png)

1. ルールを保存して[アクティブ化](#activate-rule)します。

1. E メールを作成し、 **[!UICONTROL マーケティング]** カテゴリに表示されます。 [詳細情報](../messages/get-started-content.md#create-new-message)

1. プッシュ通知を作成し、 **[!UICONTROL マーケティング]** カテゴリに表示されます。 [詳細情報](../messages/get-started-content.md#create-new-message)

このシナリオでは、個々のプロファイルは次のようになります。
* 1 か月に最大 12 件のマーケティングメッセージを受信できます。
* ただし、4 件のプッシュ通知を受信した後は、マーケティングプッシュ通知から除外されます。

>[!NOTE]
>
>頻度ルールをテストする場合は、新しく作成した [テストプロファイル](../segment/creating-test-profiles.md)を使用する場合、プロファイルの頻度キャップに達すると、翌月までカウンターをリセットする方法がなくなります。 ルールを非アクティブ化すると、上限を設定されたプロファイルがメッセージを受け取ることはできますが、カウンターの増分は削除されません。

## ハウツービデオ {#video}

頻度ルールを作成、アクティブ化、テスト、およびレポートする方法について説明します。

>[!VIDEO](https://video.tv.adobe.com/v/344451?quality=12)
