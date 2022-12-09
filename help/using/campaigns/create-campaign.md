---
solution: Journey Optimizer
product: journey optimizer
title: キャンペーンの作成
description: にキャンペーンを作成する方法を説明しています。 [!DNL Journey Optimizer]
feature: Overview
topic: Content Management
role: User
level: Intermediate
exl-id: 617d623c-e038-4b5b-a367-5254116b7815
source-git-commit: 020c4fb18cbd0c10a6eb92865f7f0457e5db8bc0
workflow-type: tm+mt
source-wordcount: '533'
ht-degree: 0%

---

# キャンペーンの作成 {#create-campaign}

>[!NOTE]
>
>新規キャンペーンを作成する前に、surface channel (メッセージプリセット) があり、Adobe エクスペリエンスプラットフォームセグメントを使用できるようになっているかどうかを確認してください。 詳細については、以下の項目を参照してください。
>
>* [チャンネルサーフェスの作成](../configuration/channel-surfaces.md)
>* [セグメントでの作業の開始](../segment/about-segments.md)


## 最初のキャンペーンの作成 {#create}

1. メニューに **[!UICONTROL Campaigns]** アクセスし、をクリック **[!UICONTROL Create campaign]** します。

   >[!NOTE]
   >
   >また、既存のライブキャンペーンを複製して新しいものを作成することもできます。 [詳細情報](modify-stop-campaign.md#duplicate)

   ![](assets/create-campaign.png)

1. **[!UICONTROL Properties]**&#x200B;セクションで、キャンペーンを実行する方法を次のように指定します。

   * **[!UICONTROL Scheduled]**
   * **[!UICONTROL API-triggered]**

   キャンペーンタイプおよび関連付けられた involvements について詳しくは、この [ 項 ](#campaigntype) を参照してください。

1. **[!UICONTROL Actions]**&#x200B;セクションで、メッセージの送信に使用するチャンネルとチャンネルを選択し、をクリック **[!UICONTROL Create]** します。

   サーフェスは、システム管理者 ](../start/path/administrator.md) によっ [ て定義された設定です。このファイルには、ヘッダパラメーター、サブドメイン、モバイルアプリケーションなど、メッセージを送信するためのすべての技術的なパラメーターが含まれています。 [詳しく ](../configuration/channel-surfaces.md) は、こちらを参照してください。

   ![](assets/create-campaign-action.png)

   >[!NOTE]
   >
   >ドロップダウンリストには、マーケティングキャンペーンタイプと互換性のあるチャンネルサーフェスのみが一覧表示されます。

1. キャンペーンのタイトルと説明を指定します。

   <!--To test the content of your message, toggle the **[!UICONTROL Content experiment]** option on. This allows you to test multiple variables of a delivery on populations samples, in order to define which treatment has the biggest impact on the targeted population.[Learn more about content experiment](../campaigns/content-experiment.md).-->

1. カスタムまたはコアデータ使用状況のラベルをキャンペーンに割り当てるには、ボタンをクリック **[!UICONTROL Manage access]** します。 [オブジェクトレベルのアクセス制御について詳しくは、(OLA)](../administration/object-based-access.md)

## メッセージの作成 {#content}

**[!UICONTROL Actions]**&#x200B;セクションで、キャンペーンと一緒に送信するメッセージを作成します。

1. **[!UICONTROL Edit content]**&#x200B;ボタンをクリックし、メッセージの内容を作成してデザインします。

   以下のページで、メッセージコンテンツを作成するための詳細な手順について説明します。

   <table style="table-layout:fixed">
    <tr style="border: 0;">
    <td>
    <a href="../email/create-email.md">
    <img alt="招き" src="../assets/do-not-localize/email.jpg">
    </a>
    <div><a href="../email/create-email.md"><strong>電子メールの作成</strong>
    </div>
    <p>
    </td>
    <td>
    <a href="../push/create-push.md">
      <img alt="ときどき" src="../assets/do-not-localize/push.jpg">
    </a>
    <div>
    <a href="../push/create-push.md"><strong>プッシュ通知の作成</strong></a>
    </div>
    <p>
    </td>
    <td>
    <a href="../sms/create-sms.md">
      <img alt="検証" src="../assets/do-not-localize/sms.jpg">
    </a>
    <div>
    <a href="../sms/create-sms.md"><strong>SMS メッセージの作成</strong></a>
    </div>
    <p>
    </td>
    </tr>
    </table>

1. コンテンツを定義したら、ボタンを使用 **[!UICONTROL Simulate content]** して、コンテンツをテストプロファイルでプレビューおよびテストします。 [詳しく ](../email/preview.md) は、こちらを参照してください。

1. 矢印をクリックして、キャンペーン作成画面に戻ります。

   ![](assets/create-campaign-design.png)

1. **[!UICONTROL Actions tracking]**&#x200B;セクションで、受信者の配信状況を記録するかどうかを指定します。クリックを追跡したり、開いたりすることができます。

   キャンペーンの実行後、追跡結果はキャンペーンレポートからアクセス可能になります。 [キャンペーンレポートに関する詳細情報](../reports/campaign-global-report.md)

## 対象ユーザーの定義 {#audience}

1. 対象ユーザーを定義します。 これを行うには、このボタンをクリックし **[!UICONTROL Select audience]** て、使用可能な Adobe エクスペリエンスプラットフォームセグメントのリストを表示します。 [セグメントに関する詳細情報](../segment/about-segments.md)

   >[!NOTE]
   >
   >API によってトリガーされたキャンペーンの場合は、ユーザーを API 呼び出しを使用して設定する必要があります。 [詳細情報](api-triggered-campaigns.md)

   **[!UICONTROL Identity namespace]**「」フィールドで、選択した区分の個人を識別するために使用する名前空間を選択します。[名前空間について詳しくは、](../event/about-creating.md#select-the-namespace)

   ![](assets/create-campaign-namespace.png)

   >[!NOTE]
   >
   >セグメントに属していて、選択した id が含まれていない複数の人物は、キャンペーンの対象ではありません。

   <!--If you are are creating an API-triggered campaign, the **[!UICONTROL cURL request]** section allows you to retrieve the **[!UICONTROL Campaign ID]** to use in the API call. [Learn more](api-triggered-campaigns.md)-->

## キャンペーンのスケジュール {#schedule}

1. 特定の日付または定期的な頻度でキャンペーンを実行するには、「」セクションを設定 **[!UICONTROL Schedule]** します。 [キャンペーンのスケジューリング方法について説明します。](#schedule)

1. カスタムまたはコアデータ使用状況のラベルをキャンペーンに割り当てるには、ボタンをクリック **[!UICONTROL Manage access]** します。 [オブジェクトレベルのアクセス制御について詳しくは、(OLA)](../administration/object-based-access.md)

キャンペーンの準備が整ったら、それを確認して公開することができます。 [詳細情報](#review-activate)

## キャンペーンタイプ {#campaigntype}

>[!CONTEXTUALHELP]
>id="ajo_campaigns_campaign_type"
>title="キャンペーンタイプ"
>abstract="TBC"

>[!CONTEXTUALHELP]
>id="ajo_campaigns_campaign_category"
>title="キャンペーンカテゴリー"
>abstract="TBC"

使用可能なキャンペーンには、次の2種類があります。

* **[!UICONTROL Scheduled]**: キャンペーンをすぐに実行することも、指定した日付に実行することもできます。 定期的なキャンペーンは、マーケティング **タイプメッセージを送信** することを目的としています。

* **[!UICONTROL API-triggered]**: API 呼び出しを使用してキャンペーンを実行します。 API によってトリガーされるキャンペーンは、ユーザーが実行するアクションによって送信されたメッセージ、つまり、パスワードのリセット、カード abandonment など、トランザクション **メッセージを送信** することを目的としています。[Api を使用したキャンペーンの開始方法について説明します。](api-triggered-campaigns.md)
