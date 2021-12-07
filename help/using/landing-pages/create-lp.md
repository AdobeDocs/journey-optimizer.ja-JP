---
title: ランディングページの作成
description: Journey Optimizerでランディングページを設定して公開する方法を説明します
feature: Landing Pages
topic: Content Management
role: User
level: Beginner
hidefromtoc: true
hide: true
exl-id: 18f9bdff-f5c6-4601-919d-4f3124e484b5
source-git-commit: 88b037e079a46e10f7ee4715e78e5edc5a34a6ce
workflow-type: tm+mt
source-wordcount: '966'
ht-degree: 13%

---

# ランディングページの作成と公開 {#create-lp}

>[!CAUTION]
>
>現在、ランディングページは一部のユーザーに対してのみ、早期にアクセスできます。 この機能を利用する場合は、担当のAdobeアカウント担当者にお問い合わせください。

## ランディングページへのアクセス

ランディングページのリストにアクセスするには、「 **[!UICONTROL ジャーニー管理]** > **[!UICONTROL ランディングページ]** を選択します。

![](../assets/lp_access-list.png)

この **[!UICONTROL ランディングページ]** リストには、作成されたすべての項目が表示されます。 ステータスや変更日に基づいてフィルタリングできます。

![](../assets/lp_access-list-filter.png)

## ランディングページの作成

ランディングページを作成する手順は次のとおりです。

1. ランディングページのリストで、 **[!UICONTROL ランディングページを作成]**.

   ![](../assets/lp_create-lp.png)

1. タイトルを追加します。 必要に応じて、説明を追加できます。

   ![](../assets/lp_create-lp-details.png)

1. プリセットを選択します。

   ![](../assets/lp_create-lp-presets.png)

   >[!NOTE]
   >
   >ランディングページプリセットを定義するには、Adobeのアカウント担当者または [Adobeカスタマーケアサポートチーム](https://helpx.adobe.com/jp/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html){target=&quot;_blank&quot;}。

1. 「**[!UICONTROL 作成]**」をクリックします。

1. プライマリページとそのプロパティが表示されます。 プライマリページの設定方法を説明します [ここ](#configure-primary-page).

   ![](../assets/lp_primary-page.png)

1. 「+」アイコンをクリックしてサブページを追加します。 サブページの設定方法を説明します [ここ](#configure-subpages).

   ![](../assets/lp_add-subpage.png)

設定および設計が完了したら、 [プライマリページ](#configure-primary-page)、および [サブページ](#configure-subpages) 存在する場合は、次の操作を実行できます。 [テスト](#test) および [公開](#publish) ランディングページを作成します。

## プライマリページの設定 {#configure-primary-page}

プライマリページとは、E メールや Web サイトなど、ランディングページへのリンクをクリックした後、ユーザーに対して直ちに表示されるページです。

プライマリページの設定を定義するには、次の手順に従います。

1. ページ名を変更できます ( **[!UICONTROL プライマリページ]** デフォルトでは。

1. コンテンツデザイナーを使用してページのコンテンツを編集します。 ランディングページのコンテンツを定義する方法を説明します [ここ](design-lp.md).

   ![](../assets/lp_open-designer.png)

1. ランディングページの URL を定義します。 URL の最初の部分では、ドメインデリゲーションを実行する必要があります。 事前入力済みで、ユーザーインターフェイスで編集することはできません。 設定するには、担当のAdobeアカウント担当者または [Adobeカスタマーケアサポートチーム](https://helpx.adobe.com/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html){target=&quot;_blank&quot;}。

   >[!CAUTION]
   >
   >ランディングページの URL は一意である必要があります。

   ![](../assets/lp_access-url.png)

1. ページの有効期限を定義できます。 その場合、ページの有効期限が切れたらアクションを選択する必要があります。

   * **[!UICONTROL リダイレクト URL]**:ページの有効期限が切れたときにユーザーがリダイレクトされるページの URL を入力します。
   * **[!UICONTROL カスタムページ]**: [サブページの設定](#configure-subpages) を選択し、表示されるドロップダウンリストから選択します。
   * **[!UICONTROL ブラウザーエラー]**:ページの代わりに表示するエラーテキストを入力します。

   ![](../assets/lp_expiry-date.png)

   <!--1. In the **[!UICONTROL Additional data]** section, define a **[!UICONTROL Key]** and the corresponding **[!UICONTROL Parameter value]**. // you can define how the data entered in the landing page is managed once it has been submitted by a user??-->

1. 1 つ以上の購読リストを選択した場合、 [プライマリページのデザイン](design-lp.md)を使用する場合、 **[!UICONTROL 購読リスト]** 」セクションに入力します。

   ![](../assets/lp_subscription-list.png)

1. ランディングページから、次の操作を直接実行できます。 [ジャーニーの作成](../building-journeys/journey-gs.md#jo-build) これにより、ユーザーがフォームを送信する際に確認メッセージが送信されます。 この最後に、このようなジャーニーを構築する方法を学ぶ [使用例](lp-use-cases.md#subscription-to-a-service).

   ![](../assets/lp_create-journey.png)

   クリック **[!UICONTROL ジャーニーを作成]** リダイレクト先 **[!UICONTROL ジャーニー管理]** > **[!UICONTROL ジャーニー]** リスト。

## サブページの設定 {#configure-subpages}

最大 2 つのサブページを追加できます。 例えば、ユーザーがフォームを送信すると表示される「ありがとうございます」ページを作成し、ランディングページに問題が発生した場合に呼び出されるエラーページを定義できます。

サブページ設定を定義するには、次の手順に従います。

1. ページ名を変更できます ( **[!UICONTROL サブページ 1]** デフォルトでは。

1. コンテンツデザイナーを使用してページのコンテンツを編集します。 ランディングページのコンテンツを定義する方法を説明します [ここ](design-lp.md).

1. ランディングページの URL を定義します。 URL の最初の部分では、ドメインデリゲーションを実行する必要があります。 事前入力済みで、ユーザーインターフェイスで編集することはできません。 設定するには、担当のAdobeアカウント担当者または [Adobeカスタマーケアサポートチーム](https://helpx.adobe.com/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html){target=&quot;_blank&quot;}。

   >[!CAUTION]
   >
   >ランディングページの URL は一意である必要があります。

![](../assets/lp_subpage-settings.png)

## ランディングページのテスト {#test}

ランディングページの設定とコンテンツを定義したら、テストプロファイルを使用してプレビューできます。 以下を [パーソナライズされたコンテンツ](../personalization/personalize.md)を使用すると、テストプロファイルデータを活用して、このコンテンツがランディングページにどのように表示されるかを確認できます。

>[!CAUTION]
>
>メッセージのプレビューや配達確認の送信をおこなうには、テストプロファイルを使用可能にしておく必要があります。[テストプロファイルを作成](../building-journeys/creating-test-profiles.md)する方法を学びます。

1. ランディングページのインターフェイスで、 **[!UICONTROL プレビューとテスト]** ボタンをクリックして、テストプロファイルの選択にアクセスします。

   ![](../assets/lp_preview-button.png)

   >[!NOTE]
   >
   >この **[!UICONTROL プレビュー]** ボタンには、コンテンツデザイナーからもアクセスできます。

1. 次の **[!UICONTROL プレビューとテスト]** 画面で、1 つ以上のテストプロファイルを選択します。

   ![](../assets/lp_test-profiles.png)

   テストプロファイルを選択する手順は、メッセージをテストする場合と同じです。 詳しくは、[この節](../preview.md#select-test-profiles)を参照してください。

1. を選択します。 **[!UICONTROL プレビュー]** タブをクリックし、 **[!UICONTROL プレビューを開く]** をクリックしてランディングページをテストします。

   ![](../assets/lp_open-preview.png)

1. ランディングページのプレビューが新しいタブで開きます。 パーソナライズされた要素は、選択したテストプロファイルデータに置き換えられます。

   ![](../assets/lp_preview.png)

1. 他のテストプロファイルを選択して、ランディングページの各バリアントのレンダリングをプレビューします。

## アラートの確認 {#alerts}

ランディングページを作成している間、は、公開する前に重要なアクションを実行する必要がある場合に警告を表示します。

次に示すように、画面の右上にアラートが表示されます。

![](../assets/lp_alerts.png)

>[!NOTE]
>
>このボタンが表示されない場合、アラートは検出されていません。

次の 2 種類のアラートが発生する可能性があります。

* **警告**&#x200B;は、推奨奨事項とベストプラクティスを表します。<!--For example, a message will display if -->

* **エラー**&#x200B;は、解決されない限り、メッセージを公開することができません。例えば、プライマリページの URL が見つからない場合に警告が表示されます。

<!--All possible warnings and errors are detailed [below](#alerts-and-warnings).-->

>[!CAUTION]
>
> 公開する前に、すべての&#x200B;**エラー**&#x200B;アラートを解決する必要があります。

<!--The settings and elements checked by the system are listed below. You will also find information on how to adapt your configuration to resolve the corresponding issues.

**Warnings**:

* 

**Errors**:

* 

>[!CAUTION]
>
> To be able to publish your message, you need to resolve all **error** alerts.
-->

## ランディングページの公開 {#publish}

ランディングページの準備が整ったら、公開して、メッセージで使用できるようにします。

![](../assets/lp_publish.png)

>[!CAUTION]
>
>公開する前に、アラートを確認して解決します。[詳細情報](#alerts)

ランディングページが公開されると、ランディングページは **[!UICONTROL 公開済み]** ステータス。

これでライブになり、 [!DNL Journey Optimizer] [メッセージ](../create-message.md) それは [ジャーニー](../building-journeys/journey.md).

>[!NOTE]
>
>特定のレポートを使用して、ランディングページの影響を監視できます。 [詳細情報](lp-report.md)

