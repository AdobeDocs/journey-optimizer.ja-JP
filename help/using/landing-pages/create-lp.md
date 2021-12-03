---
title: ランディングページの作成
description: Journey Optimizerでランディングページを設定して公開する方法を説明します
feature: Landing Pages
topic: Content Management
role: User
level: Beginner
hidefromtoc: true
hide: true
source-git-commit: 4d564ff89a8cb6c6d76161f2e6cedf39d33e70a0
workflow-type: tm+mt
source-wordcount: '884'
ht-degree: 14%

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

1. 「**[!UICONTROL 作成]**」をクリックします。

1. プライマリページとそのプロパティが表示されます。 ページ設定の設定方法を説明します [ここ](#configure-primary-page).

   ![](../assets/lp_primary-page.png)

1. 「+」アイコンをクリックしてサブページを追加します。 設定方法を説明します [ここ](#configure-subpages).

   ![](../assets/lp_add-subpage.png)

設定および設計が完了したら、 [プライマリページ](#configure-primary-page) そして [サブページ](#configure-subpages) 存在する場合は、次の操作を実行できます。 [テスト](#test) および [公開](#publish) ランディングページを作成します。

## プライマリページの設定 {#configure-primary-page}

プライマリページとは、ユーザーが E メールや Web サイトなどのランディングページへのリンクをクリックすると、そのページが直ちに表示されるページです。

プライマリページの設定を定義するには、次の手順に従います。

1. ページ名を変更できます ( **[!UICONTROL プライマリページ]** デフォルトでは。

1. コンテンツデザイナーを使用してページのコンテンツを編集します。 ランディングページのコンテンツをデザインする方法を説明します [ここ](design-lp.md).

   ![](../assets/lp_open-designer.png)

1. ランディングページの URL を定義します。

   >[!CAUTION]
   >
   >ランディングページの URL は一意である必要があります。

   ![](../assets/lp_access-url.png)

   URL の最初の部分は事前に入力されており、ユーザーインターフェイスで編集することはできません。 設定するには、担当のAdobeアカウント担当者または [Adobeカスタマーケアサポートチーム](https://helpx.adobe.com/jp/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html){target=&quot;_blank&quot;}。

1. ページの有効期限を定義できます。 その場合、ページの有効期限が切れたらアクションを選択する必要があります。

   * **[!UICONTROL リダイレクト URL]**:ページの有効期限が切れたときにユーザーがリダイレクトされるページの URL を入力します。
   * **[!UICONTROL カスタムページ]**: [サブページの設定](#configure-subpages) を選択し、表示されるドロップダウンリストから選択します。
   * **[!UICONTROL ブラウザーエラー]**:ページの代わりに表示するエラーテキストを入力します。

   ![](../assets/lp_expiry-date.png)

   <!--1. In the **[!UICONTROL Additional data]** section, define a **[!UICONTROL Key]** and the corresponding **[!UICONTROL Parameter value]**. // you can define how the data entered in the landing page is managed once it has been submitted by a user??-->

1. プライマリページの 1 つ以上の購読リストを選択した場合は、リストが **[!UICONTROL 購読リスト]** 」セクションに入力します。

   ![](../assets/lp_subscription-list.png)

1. ランディングページから、ユーザーがフォームを送信したときに確認メッセージを送信するジャーニーを直接作成できます。

   ![](../assets/lp_create-journey.png)

   クリック **[!UICONTROL ジャーニーを作成]** 開始 [このジャーニーの設定](../building-journeys/journey-gs.md#jo-build). 次のページにリダイレクトされます： **[!UICONTROL ジャーニー管理]** > **[!UICONTROL ジャーニー]** リスト。

## サブページの設定 {#configure-subpages}

サブページは必要な数だけ追加できます。 例えば、ユーザーがフォームを送信した後に表示される「ありがとうございます」ページを作成できます。 また、ランディングページでエラーが発生したときに呼び出されるエラーページを定義することもできます。

サブページ設定を定義するには、次の手順に従います。

1. ページ名を変更できます ( **[!UICONTROL サブページ 1]** デフォルトでは。

1. コンテンツデザイナーを使用してページのコンテンツを編集します。 ランディングページのコンテンツをデザインする方法を説明します [ここ](design-lp.md).

1. ランディングページの URL を定義します。

   URL の最初の部分は事前に入力されており、ユーザーインターフェイスで編集することはできません。 設定するには、担当のAdobeアカウント担当者または [Adobeカスタマーケアサポートチーム](https://helpx.adobe.com/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html){target=&quot;_blank&quot;}。

   >[!CAUTION]
   >
   >ランディングページの URL は一意である必要があります。

![](../assets/lp_subpage-settings.png)

## ランディングページのテスト {#test}

ランディングページの設定とコンテンツを定義したら、テストプロファイルを使用してプレビューできます。 以下を [パーソナライズされたコンテンツ](../personalization/personalize.md)を使用すると、テストプロファイルデータを活用して、このコンテンツがランディングページにどのように表示されるかを確認できます。

>[!CAUTION]
>
>メッセージのプレビューや配達確認の送信をおこなうには、テストプロファイルを使用可能にしておく必要があります。テストプロファイルの作成方法については、[このページ](../building-journeys/creating-test-profiles.md)を参照してください。

1. ランディングページのインターフェイスまたはコンテンツデザイナーで、 **[!UICONTROL プレビューとテスト]** ボタンをクリックして、テストプロファイルの選択にアクセスします。

   ![](../assets/lp_preview-button.png)

1. 1 つ以上のテストプロファイルを選択します。

   ![](../assets/lp_test-profiles.png)

   テストプロファイルを選択する手順は、メッセージをテストする場合と同じです。 詳しくは、[この節](../preview.md#select-test-profiles)を参照してください。

1. 次をクリック： **[!UICONTROL プレビュー]** タブをクリックして、ランディングページをテストします。

   <!--![](../assets/lp_preview.png)-->

1. パーソナライズされた要素は、選択したテストプロファイルデータに置き換えられます。 他のテストプロファイルを選択して、ランディングページの各バリアントのレンダリングをプレビューします。

## アラートの確認 {#alerts}

ランディングページを作成している間、は、公開する前に重要なアクションを実行する必要がある場合に警告を表示します。

次に示すように、画面の右上にアラートが表示されます。

![](../assets/lp_alerts.png)

>[!NOTE]
>
>このボタンが表示されない場合、アラートは検出されていません。

次の 2 種類のアラートが発生する可能性があります。

* **警告**&#x200B;は、推奨奨事項とベストプラクティスを表します。<!--For example, a message will display if -->

* **エラー**&#x200B;は、解決されない限り、メッセージを公開することができません。例えば、プライマリページの URL が見つからないことを警告するメッセージが表示されます。

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

ランディングページの準備が整ったら、公開して、メッセージや Web サイトで使用できるようにします。

![](../assets/lp_publish.png)

>[!CAUTION]
>
>公開する前に、アラートを確認して解決します。[詳細情報](#alerts)

ランディングページが公開されると、ランディングページは **[!UICONTROL 公開済み]** ステータス。

これで、ライブ状態になり、そのリンクを [メッセージ](../create-message.md) そして、 [ジャーニー](../building-journeys/journey.md).
