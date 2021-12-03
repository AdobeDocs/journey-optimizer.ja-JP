---
title: ランディングページの使用例
description: Journey Optimizerのランディングページの最も一般的な使用例を確認する
feature: Landing Pages
topic: Content Management
role: User
level: Intermediate
hidefromtoc: true
hide: true
source-git-commit: 4d564ff89a8cb6c6d76161f2e6cedf39d33e70a0
workflow-type: tm+mt
source-wordcount: '652'
ht-degree: 27%

---

# ランディングページの使用例

以下に、 [!DNL Journey Optimizer] ランディングページを使用して、一部またはすべてのコミュニケーションの受信から顧客がオプトイン/オプトアウトできるようにすることを検討してください。

<!--The main use cases are:
* Subscription to a service
* Opt-in
* Opt-out-->

## サービスの購読 {#subscription-to-a-service}

受信者にサービスを購読登録させる主な手順を以下に示します。

![](../assets/lp_subscription-uc.png)

例えば、来月イベントを整理し、イベント登録キャンペーンを開始して、関心のある顧客をそのイベントで更新し続けたいとします。

1. イベント登録の購読リストを作成します。 詳細情報： [購読リスト](subscription-list.md)

1. [ランディングページの作成](create-lp.md)：受信者がイベントに登録できるようにします。

1. 購読リストへのリンクを含む、登録ランディングページを設定およびデザインします。 ビルドの詳細 [プライマリランディングページ](create-lp.md#configure-primary-page)

1. 受信者が登録フォームを送信した後に表示する「ありがとうございます」ページを作成します。 詳細情報： [ランディングサブページ](create-lp.md#configure-subpages)

1. メールメッセージを作成します。詳細情報： [メッセージの作成](../create-message.md)

1. [リンクを挿入](../message-tracking.md#insert-links) メッセージに含めます。 選択 **[!UICONTROL ランディングページ]** を **[!UICONTROL リンクタイプ]** を選択し、 [ランディングページ](create-lp.md#configure-primary-page) 登録用に作成した

   ![](../assets/lp_subscription-uc-link.png)

1. コンテンツを保存し、[メッセージを公開](../publish-manage-message.md)します。

1. 次を通じてメッセージを送信： [ジャーニー](../building-journeys/journey.md) イベントの登録をお知らせし、登録ランディングページへのトラフィックを促すために、

   受信者が E メールを受け取ったら、ランディングページへのリンクをクリックすると、「ありがとうございます」ページに移動し、購読リストに追加されます。

1. イベントに登録した受信者に確認 E メールを送信できます。 それには、 **[!UICONTROL セグメントの選定]** イベントを追加し、作成した購読リストをセグメントとして選択します。

<!--The event registration's subscription list tracks the profiles who registered and you can send them targeted event updates.-->

## オプトアウト {#opt-out}

受信者がコミュニケーションを購読解除できるようにするには、オプトアウトランディングページへのリンクを E メールに含めます。

受信者の同意の管理と、これが重要な理由について詳しくは、 [この節](../consent.md).

### オプトアウト管理 {#opt-out-management}

ブランドからの連絡を購読解除する機能を受信者に提供することは、法的要件です。適用される法律について詳しくは、[Experience Platform のドキュメント](https://experienceleague.adobe.com/docs/experience-platform/privacy/regulations/overview.html?lang=ja#regulations){target=&quot;_blank&quot;}を参照してください。

したがって、受信者に送信されるすべての メールに、**登録解除リンク**&#x200B;を必ず含める必要があります。

* 受信者がこのリンクをクリックすると、オプトアウトを確認するボタンを含んだランディングページが表示されます。
* オプトアウトボタンをクリックすると、プロファイルデータがこの情報で更新されます。

### オプトアウトの設定 {#configure-opt-out}

メッセージの受信者がランディングページを通じてコミュニケーションを購読解除できるようにするには、次の手順に従います。

1. のビルド [ランディングページ](create-lp.md). ランディングページ固有のを使用 **[!UICONTROL フォーム]** コンポーネント、定義 **[!UICONTROL オプトアウト]** チェックボックスをオンにして更新を選択 **[!UICONTROL チャネル（E メール）]**:ランディングページのオプトアウトボックスをチェックするプロファイルは、すべてのコミュニケーションからオプトアウトされます。 [詳細情報](design-lp.md)

   <!--You can also build your own landing page and host it on the third-party system of your choice. To keep?-->

1. [!DNL Journey Optimizer] で[メッセージを作成](../create-message.md)します。

1. コンテンツ内のテキストを選択し、 [リンクを挿入](../message-tracking.md#insert-links) コンテキストツールバーを使用する。 ボタンにリンクを使用することもできます。

   ![](../assets/lp_opt-out-insert-link.png)

1. 選択 **[!UICONTROL ランディングページ]** から **[!UICONTROL リンクタイプ]** 」ドロップダウンリストから選択できます。

1. を選択します。 [ランディングページ](create-lp.md#configure-primary-page) オプトアウト用に作成した

   ![](../assets/lp_opt-out-landing-page.png)

1. 「**[!UICONTROL 保存]**」をクリックします。

1. コンテンツを保存し、[メッセージを公開](../publish-manage-message.md)します。

1. 次を通じてメッセージを送信： [ジャーニー](../building-journeys/journey.md).

1. メッセージを受け取った受信者が登録解除リンクをクリックすると、ランディングページが表示されます。

   <!--![](../assets/lp_opt-out-lp-example.png)-->

1. 受信者がランディングページのオプトアウトリンクをクリックすると、プロファイルデータが更新され、再度購読しない限り、ブランドからの通信が受信されなくなります。

   <!--The opted-out recipient is then redirected to a confirmation message screen indicating that opting out was successful.-->

   <!--![](../assets/lp_opt-out-confirmation-example.png)-->

対応するプロファイルの選択が更新されたことを確認するには、Experience Platform に移動し、ID 名前空間と対応する ID 値を選択してプロファイルにアクセスします。詳しくは、[Experience Platform のドキュメント](https://experienceleague.adobe.com/docs/experience-platform/profile/ui/user-guide.html?lang=ja#getting-started){target=&quot;_blank&quot;}を参照してください。

![](../assets/lp_opt-out-profile-choice.png)

「**[!UICONTROL 属性]**」タブで、**[!UICONTROL choice]** の値が **[!UICONTROL no]** に変更されたことを確認できます。

<!--

### Other ways to opt out

You can also enable your recipients to unsubscribe whithout using landing pages.

* **One-click opt-out**

    You can add a one-click opt-out link into your email content. This will enable your recipients to quickly unsubscribe from your communications, without being redirected to a landing page where they need to confirm opting out. [Learn more](../message-tracking.md#one-click-opt-out-link)

* **Unsubscribe link in header**

    If the recipients' email client supports displaying an unsubscribe link in the email header, emails sent with [!DNL Journey Optimizer] automatically include this link. [Learn more](../consent.md#unsubscribe-email)
-->