---
title: アプリ内通知の作成
description: このような場合は、旅オプティマイザーでアプリ内メッセージを作成する方法について学習します。
feature: Overview
topic: Content Management
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: b3b79fe2-7db3-490d-9c3d-87267aa55eea
source-git-commit: 8d56e3060e78422b028ced17f415497789908ff9
workflow-type: tm+mt
source-wordcount: '543'
ht-degree: 0%

---

# アプリ内メッセージの作成 {#create-in-app}

## キャンペーンとアプリ内メッセージの作成{#create-in-app-in-a-campaign}

アプリ内メッセージを作成するには、次の手順を実行します。

1. メニューに **[!UICONTROL Campaigns]** アクセスし、をクリック **[!UICONTROL Create campaign]** します。

1. **[!UICONTROL Properties]**&#x200B;セクションで、キャンペーンをいつ実行するかを指定します。

1. **[!UICONTROL Actions]**&#x200B;セクションで、App In app メッセージに対して既に設定されていると **[!UICONTROL App surface]** を選択 **[!UICONTROL In-app message]** します。次に、をクリック **[!UICONTROL Create]** します。

   [アプリ内設定 ](inapp-configuration.md) について詳しくは、こちらを参照してください。

   ![](assets/in_app_create_1.png)

1. **[!UICONTROL Properties]**&#x200B;セクションで、キャンペーンの **[!UICONTROL Title]** およびを **[!UICONTROL Description]** 編集します。

1. カスタムまたはコアデータ使用状況のラベルをランディングページに割り当てるには、を選択 **[!UICONTROL Manage access]** します。 [詳しく ](../administration/object-based-access.md) は、こちらを参照してください。

1. **[!UICONTROL Select audience]**&#x200B;このボタンをクリックして、使用可能な Adobe エクスペリエンスプラットフォームセグメントのリストから対象ユーザーを定義します。[詳しく ](../segment/about-segments.md) は、こちらを参照してください。

   ![](assets/in_app_create_2.png)

1. **[!UICONTROL Identity namespace]**「」フィールドで、選択した区分の個人を識別するために使用する名前空間を選択します。[詳しく ](../event/about-creating.md#select-the-namespace) は、こちらを参照してください。

1. アプリ内メッセージがアクティブな場合のトリガーの頻度を選択します。

   * **[!UICONTROL Show every time]**: ドロップダウンで **[!UICONTROL Mobile app trigger]** 選択したイベントが発生した場合は、常にメッセージを表示します。
   * **[!UICONTROL Show once]**: ドロップダウンで **[!UICONTROL Mobile app trigger]** イベントを最初に選択した場合にのみ、このメッセージを表示します。
   * **[!UICONTROL Show until click through]**&#x200B;このメッセージは、 **[!UICONTROL Mobile app trigger]** SDK によって「クリックされた」アクションによって対話イベントが送信されるまで、ドロップダウンで選択されたイベントが発生した場合に表示されます。

1. **[!UICONTROL Mobile app trigger]**&#x200B;ドロップダウンで、次のようなイベントが発生した場合にメッセージを表示するように選択します。

   1. 左のドロップダウンリストから、メッセージをトリガーするために必要なイベントを選択します。
   1. 右側のドロップダウンリストから、選択したイベントに対して要求された検証を選択します。
   1. 複数のイベントまたは条件をトリガーする場合は、 **[!UICONTROL Add]** このボタンをクリックします。 その後、上記の手順を繰り返します。
   1. イベントをリンクする方法を選択します。例えば、メッセージが表示されるようにするには両方のトリガーを true に設定し、いずれか **のトリガーが true の場合** は、メッセージを表示するかどうかを選択します **[!UICONTROL And]** **。** **[!UICONTROL Or]**

   ![](assets/in_app_create_3.png)

1. メッセージをトリガーするイベントを選択します **[!UICONTROL Mobile app trigger]** 。
ドロップダウンリストになります。

   トリガーを選択することにより、アプリ内メッセージを表示させるユーザーアクションを選択します。

   ![](assets/in_app_create_3.png)

1. キャンペーンは、特定の日付または定期的な頻度で実行するように設計されています。 この節 ](../campaigns/create-campaign.md#schedule) で [ は、 **[!UICONTROL Schedule]** キャンペーンの設定方法について説明します。

   ![](assets/in-app-schedule.png)

1. これで、 **[!UICONTROL Edit content]** ボタンを使用したコンテンツのデザインを開始できるようになりました。

   ![](assets/in_app_create_4.png)

## アプリ内メッセージの送信{#in-app-send}

### デバイスでのプレビュー {#preview-device}

特定のデバイスでアプリ内通知をプレビューできます。

1. をクリック **[!UICONTROL Preview on device]** します。

   ![](assets/in_app_create_6.png)

1. **[!UICONTROL Connect to device]**&#x200B;ウィンドウでをクリック **[!UICONTROL Start]** します。

1. **[!UICONTROL Base URL]**&#x200B;アプリケーションのを入力し、をクリック **[!UICONTROL Next]** します。

   ![](assets/in_app_create_7.png)

1. デバイスで QR コードをスキャンして、表示された PIN コードを入力します。

アプリ内メッセージはデバイス上で直接トリガーされるようになったので、実際のデバイスでメッセージをプレビューして確認することができます。

### アプリ内通知を確認し、アクティブ化します{#in-app-review}

アプリ内メッセージとそのコンテンツが定義され、カスタマイズされた後で、メッセージを確認し、アクティブ化することができます。

これを行うには、次の手順に従います。

1. **[!UICONTROL Review to activate]**&#x200B;ボタンを使用して、メッセージの概要を表示します。

   この概要を使用して、必要に応じてキャンペーンを変更し、パラメーターが間違っていたり、失われていないかどうかをチェックすることができます。

   ![](assets/in_app_create_5.png)

1. キャンペーンが正しく設定されていることを確認してから、をクリック **[!UICONTROL Activate]** します。

これで、キャンペーンが有効になります。 キャンペーンに設定されたアプリ内通知は、ただちに送信されるか、指定した日付に送信されます。

送信すると、アプリ内メッセージがキャンペーンレポート内のどのような影響を受けるかを測定できます。 レポートについて詳しくは、ここ ](inapp-report.md) を [ 参照してください。

**関連トピック:**

* [アプリ内メッセージのデザイン](design-in-app.md)
* [アプリ内レポート](inapp-report.md)
* [アプリ内設定](inapp-configuration.md)
