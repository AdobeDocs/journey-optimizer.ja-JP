---
solution: Journey Optimizer
product: journey optimizer
title: SMS メッセージの作成
description: 旅オプティマイザーで SMS メッセージを作成する方法について説明します。
feature: Overview
topic: Content Management
role: User
level: Beginner
exl-id: 1f88626a-b491-4b36-8e3f-57f2b7567dd0
source-git-commit: 34ab78408981d2b53736b31c94412da06cb860c4
workflow-type: tm+mt
source-wordcount: '393'
ht-degree: 0%

---

# SMS メッセージの作成 {#create-sms}

>[!CONTEXTUALHELP]
>id="ajo_message_sms"
>title="SMS 作成"
>abstract="テキストメッセージを追加し、式エディターを使用してテキストをカスタマイズします。"

>[!NOTE]
>
>すべての SMS マーケティングメッセージには、業界規格と規制に従い、受信者が購読を容易に解除できるようにするための方法が含まれている必要があります。 これを行うために、SMS 受信者はオプトインキーワードとオプトアウトキーワードを使用して応答することができます。 [脱退を管理する方法について説明します。](../privacy/opt-out.md#sms-opt-out-management-sms-opt-out-management)

## 旅またはキャンペーンでの SMS メッセージの作成 {#create-sms-journey-campaign}

SMS メッセージのパーソナライズを開始するには、次の手順を実行します。

>[!BEGINTABS]

>[!TAB 旅への SMS メッセージの追加]

1. 「パレット」の「アクション」セクションから、SMS アクティビティをドラッグ &amp; ドロップします。

   ![](assets/sms_create_1.png)

1. メッセージに基本的な情報 (ラベル、説明、カテゴリー) を入力してから、使用するメッセージサーフェスを選択します。

   ![](assets/sms_create_2.png)

   旅の設定方法について詳しくは、このページを [ 参照してください。](../building-journeys/journey-gs.md)

これで、ボタンを **[!UICONTROL Edit content]** クリックして、SMS メッセージのコンテンツのデザインを開始できるようになりました。 [SMS コンテンツのデザイン](#sms-content)

>[!TAB キャンペーンへの SMS メッセージの追加]

1. 新しくスケジュール設定されたまたは API トリガキャンペーンを作成するには、「操作として」を選択 **[!UICONTROL SMS]** し、「使用する」を選択 **[!UICONTROL App surface]** します。 [SMS 設定 ](sms-configuration.md) について説明します。

   ![](assets/sms_create_3.png)

1. をクリック **[!UICONTROL Create]** します。

1. **[!UICONTROL Properties]**&#x200B;セクションで、キャンペーンの **[!UICONTROL Title]** およびを **[!UICONTROL Description]** 編集します。

   ![](assets/sms_create_4.png)

1. **[!UICONTROL Actions tracking]**&#x200B;セクションで、SMS メッセージ内のリンクのクリックを追跡するかどうかを指定します。

1. **[!UICONTROL Select audience]**&#x200B;このボタンをクリックして、使用可能な Adobe エクスペリエンスプラットフォームセグメントのリストから対象ユーザーを定義します。[詳しく ](../segment/about-segments.md) は、こちらを参照してください。

1. **[!UICONTROL Identity namespace]**「」フィールドで、選択した区分の個人を識別するために使用する名前空間を選択します。[詳しく ](../event/about-creating.md#select-the-namespace) は、こちらを参照してください。

   ![](assets/sms_create_5.png)

1. キャンペーンは、特定の日付または定期的な頻度で実行するように設計されています。 この節 ](../campaigns/create-campaign.md#schedule) で [ は、 **[!UICONTROL Schedule]** キャンペーンの設定方法について説明します。

1. **[!UICONTROL Action triggers]**&#x200B;メニューから、SMS メッセージの次のいずれかを選択 **[!UICONTROL Frequency]** します。

   * ある時
   * あたり
   * ごと
   * 月

これで、ボタンを **[!UICONTROL Edit content]** クリックして、SMS メッセージのコンテンツのデザインを開始できるようになりました。 [SMS コンテンツのデザイン](#sms-content)

>[!ENDTABS]

## SMS コンテンツの定義{#sms-content}

1. 「情報の送受信」画面で、ボタンをクリック **[!UICONTROL Edit content]** して SMS コンテンツを設定します。

1. **[!UICONTROL Message]**&#x200B;フィールドをクリックして、式エディターを開きます。

   ![](assets/sms-content.png)

1. エクスプレッションエディターを使用して、コンテンツを定義し、動的コンテンツを追加します。 プロファイル名または市区町村のように、任意の属性を使用することができます。 エクスプレッションエディターで、パーソナル化 ](../personalization/personalize.md) と [ 動的コンテンツ ](../personalization/get-started-dynamic-content.md) について [ 詳しく説明します。

1. プレビューで、メッセージをクリック **[!UICONTROL Save]** して確認します。 [詳細情報](send-sms.md)

   ![](assets/sms-content-preview.png)

**関連トピック**

* [SMS チャネルの設定](sms-configuration.md)
* [SMS レポート](../reports/journey-global-report.md#sms-global)
* [メッセージの追加](../building-journeys/journeys-message.md)
