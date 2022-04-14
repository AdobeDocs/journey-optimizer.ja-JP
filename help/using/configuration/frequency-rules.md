---
title: 頻度ルール
description: 頻度ルールの定義方法を学ぶ
feature: Overview
topic: Content Management
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 49248fb6-5a91-45b2-9de8-2f078d59c0fc
source-git-commit: f1ac47a0cb405eaadc5428e7e5479eaf776d7abe
workflow-type: tm+mt
source-wordcount: '790'
ht-degree: 64%

---

# メッセージ頻度ルール {#frequency-rules}

[!DNL Journey Optimizer] では、過剰に配信を受けているプロファイルをメッセージやアクションから自動的に除外するクロスチャネルルールを設定することで、ユーザーがメッセージを受け取ったり、ジャーニーにエントリする頻度を制御できます。

例えば、ブランドが顧客に送信するメッセージを 1 か月に 3 件以内に抑える場合などです。

これを行うには、頻度ルールを使用して、月別のカレンダー期間に、1 つ以上のチャネルに基づいて送信されるメッセージの件数に上限を設定することができます。

>[!NOTE]
>
>メッセージ頻度ルールは、ユーザーがブランドからの通信の受信を登録解除できる、オプトアウト管理とは異なります。[詳細情報](../messages/consent.md#opt-out-management)

## アクセスルール {#access-rules}

ルールは、**[!UICONTROL 管理]**／**[!UICONTROL ルール]**&#x200B;メニューから利用できます。すべてのルールが、変更日順に表示されます。

>[!NOTE]
>
>メッセージ頻度ルールにアクセス、作成、編集または削除するには、 [頻度ルールの管理](../administration/high-low-permissions.md#manage-frequency-rules) 権限。

![](assets/message-rules-access.png)

フィルターアイコンを使用して、カテゴリ、ステータスまたはチャネル（あるいはその両方）に基づいてフィルターを適用します。また、メッセージラベルで検索することもできます。

![](assets/message-rules-filter.png)

## ルールの作成 {#create-new-rule}

新しいルールを作成するには、次の手順に従います。

1. **[!UICONTROL メッセージ頻度ルール]**&#x200B;リストにアクセスし、「**[!UICONTROL ルールを作成]**」をクリックします。

   ![](assets/message-rules-create.png)

1. ルール名を定義します。

   ![](assets/message-rules-details.png)

1. メッセージルールカテゴリを選択します。

   >[!NOTE]
   >
   >現在、 **[!UICONTROL マーケティング]** カテゴリが使用可能です。

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

1. 「**[!UICONTROL ドラフトとして保存]**」をクリックして、ルールの作成を確定します。メッセージが、（**[!UICONTROL ドラフト]**&#x200B;ステータスで）ルールリストに追加されます。

   ![](assets/message-rules-created.png)

## ルールをアクティブ化 {#activate-rule}

メッセージ頻度ルールを作成すると、 **[!UICONTROL ドラフト]** ステータスであり、まだどのメッセージにも影響を与えていません。 有効にするには、ルールの横の省略記号をクリックし、「 」を選択します。 **[!UICONTROL 有効化]**.

![](assets/message-rules-activate.png)

ルールをアクティブ化すると、次回の実行時に適用されるメッセージに影響します。[メッセージに頻度ルールを適用する](#apply-frequency-rule)方法を説明します。

>[!NOTE]
>
>ルールを有効にするために、メッセージやジャーニーを変更または再公開する必要はありません。

メッセージ頻度ルールを非アクティブ化するには、ルールの横の「...」をクリックし、「**[!UICONTROL 非アクティブ化]**」を選択します。

![](assets/message-rules-deactivate.png)

ルールのステータスは、「**[!UICONTROL 非アクティブ]**」に変わり、今後のメッセージの実行にはルールが適用されません。現在実行中のメッセージは影響を受けません。

>[!NOTE]
>
>ルールのアクティベートを解除しても、個々のプロファイルのカウントに影響したり、リセットしたりすることはありません。

## メッセージに頻度ルールを適用する {#apply-frequency-rule}

メッセージに頻度ルールを適用するには、次の手順に従います。

1. メッセージを作成. [詳細情報](../messages/get-started-content.md#create-new-message)

1. 定義したカテゴリを [作成したルール](#create-new-rule).

   ![](assets/message-rules-msg-properties.png)

   >[!NOTE]
   >
   >現在、 **[!UICONTROL マーケティング]** カテゴリは、メッセージ頻度ルールで使用できます。

1. メッセージ用に選択したチャネルを選択します。

   ![](assets/message-rules-msg-channels.png)

1. 次の項目をクリックします。 **[!UICONTROL 頻度ルール]** リンクをクリックして、選択したカテゴリおよびチャネルに適用される頻度ルールを表示します。

   ![](assets/message-rules-msg-link.png)

   新しいタブが開き、一致するメッセージ頻度ルールが表示されます。

1. [デザイン](../design/design-emails.md) および [公開](../messages/publish-manage-message.md) メッセージ。

選択したカテゴリとチャネルに一致するすべての頻度ルールが、このメッセージに自動的に適用されます。

<!--Clicking the link out button next to the category selector will jump you over to the rules inventory screen to see which rules will be applied to the message.-->

配信から除外されたプロファイルの数を[ライブ表示とグローバル表示](../reports/message-monitoring.md)および[メールライブレポート](../reports/email-live-report.md)で表示でき、配信から除外されたユーザーの理由として考えられる頻度ルールが示されます。

>[!NOTE]
>
>複数のルールを同じチャネルに適用できますが、下限に達すると、プロファイルは次の配信から除外されます。

## 例：複数のルールを組み合わせる {#frequency-rule-example}

次の例に示すように、複数のメッセージ頻度ルールを組み合わせることができます。

1. [ルールの作成](#create-new-rule) 呼び出し *マーケティングキャッピング全体*:

   * すべてのチャネル（メール、プッシュ）を選択します。
   * キャッピングを 12 に設定します。

   ![](assets/message-rules-ex-overall-cap.png)

1. ユーザーが送信されるマーケティングベースのプッシュ通知の数をさらに制限するには、2 つ目のルールとして *プッシュマーケティングキャップ*:

   * 「プッシュ」チャネルを選択します。
   * キャッピングを 4 に設定します。

   ![](assets/message-rules-ex-push-cap.png)

1. 保存して [有効化](#activate-rule) ルール。

1. メッセージを作成. [詳細情報](../messages/get-started-content.md#create-new-message)

1. を選択します。 **[!UICONTROL マーケティング]** カテゴリ。

   ![](assets/message-rules-ex-category-maktg.png)

1. を選択します。 **[!UICONTROL 電子メール]** および **[!UICONTROL プッシュ通知]** チャネル。

   ![](assets/message-rules-ex-channels.png)

1. 次の項目をクリックします。 **[!UICONTROL 頻度ルール]** リンクをクリックして、選択したカテゴリおよびチャネルに適用される頻度ルールを表示します。

1. [デザイン](../design/design-emails.md) および [公開](../messages/publish-manage-message.md) メッセージ。

このシナリオでは、個々のプロファイルは次のようになります。
* は、1 か月に最大 12 件のマーケティングメッセージを受信できます。
* ただし、4 件のプッシュ通知を受信した後は、マーケティングプッシュ通知から除外されます。
