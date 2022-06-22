---
title: Adobe Stock
description: Adobe Stock の基本を学ぶ
feature: Overview
topic: Content Management
role: User
level: Beginner
exl-id: 0715f65f-04bd-4dc2-a152-98111f4c42e6
source-git-commit: f2426b8696983b22dd2c80296e2c9dfc2426c439
workflow-type: tm+mt
source-wordcount: '478'
ht-degree: 84%

---

# [!DNL Adobe Stock] 画像の管理 {#stock}

## [!DNL Adobe Stock] の基本を学ぶ {#get-started-stock}

[!DNL Adobe Stock] では、数百万もの高品質で厳選された、ロイヤリティフリーの写真、ビデオ、イラスト、ベクターグラフィックを利用できます。クレジットパックを購入してアセットのライセンスを取得するか、必要なアセットに対して通常ライセンスまたは強化ライセンスを 1 つだけ購入するかどうかを選択できます。Adobe Stock はまた、アセットの無料コレクションを提供しています。

[!DNL Adobe Stock] について詳しくは、[Adobe Stock 入門](https://helpx.adobe.com/jp/stock/get-started.html)を参照してください。

[!DNL Adobe Journey Optimizer] を使用すると、[!DNL Adobe Stock] から画像を直接メールにアップロードし、Assets フォルダーに追加することができます。「**[!UICONTROL 類似画像を検索]**」オプションを使用すると、配信で使用されるアセットのコンテンツ、色、構成に一致する画像を検索することができます。
メールデザインについて詳しくは、[こちら](design-emails.md)を参照してください。

## [!DNL Adobe Stock] 画像の挿入および読み込み {#add-stock-image}

>[!NOTE]
>
> この **[!UICONTROL Adobe Stockの写真を検索]** オプションは、AEM Assets Essentials 製品プロファイルへのアクセス権を持つユーザーのみが使用できます。 詳しくは、 [Assets の基本ドキュメント](https://experienceleague.adobe.com/docs/experience-manager-assets-essentials/help/get-started-admins/deploy-administer.html#add-users-to-essentials).

メールを編集およびパーソナライズした後、[!DNL Adobe Stock] から画像をテンプレートに追加できます。

1. 画像の&#x200B;**[!UICONTROL コンテンツコンポーネント]**&#x200B;をメールにドラッグ＆ドロップします。

   ![](assets/stock_1.png)

1. **[!UICONTROL コンポーネント設定]**&#x200B;メニューから、**[!UICONTROL Adobe Stock 写真の検索]**&#x200B;を選択します。

   ![](assets/stock_2.png)

1. ライブラリを参照するか、フィールドに検索語句を入力します。選んだ画像を選択し、「**[!UICONTROL 保存]**」をクリックします。

   ![](assets/stock_3.png)

1. 画像のライセンスを取得してダウンロードするには、画像の&#x200B;**[!UICONTROL コンテンツコンポーネント]**&#x200B;を選択し、**[!UICONTROL ライセンス Adobe Stock 画像]**&#x200B;をクリックします。[!DNL Adobe Stock] web サイトにリダイレクトされます。

   >[!NOTE]
   > 画像がライセンス済みの場合は、![](assets/stock_10.png) アイコンによって表示されます。その場合は、手順 7 に進みます。

   ![](assets/stock_4.png)

1. [!DNL Adobe Stock] web サイトで、画像をダウンロードして透かしを削除するには、アセットを購入する必要があります。

   価格は、Adobe Stock のプランまたはサブスクリプションによって異なります。複数のAdobe Stockアカウントがある場合は、最後に使用した Stock ID にリダイレクトされます。 この場合、アセットのライセンスを取得する前に、正しいアカウントにサインインしていることを確認してください。
詳しくは、この[ページ](https://stock.adobe.com/jp/plans)を参照してください。

   >[!WARNING]
   > 未ライセンスの画像を含むメールが送信された場合、画像は透かしのある未ライセンスのフォームを保持します。

   ![](assets/stock_5.png)

1. 購入が完了したら、[!DNL Adobe Journey Optimizer] でメールに戻り、「**[!UICONTROL ストック画像を読み込み]**」を選択して、ライセンス済みの画像をアセットに読み込むことができます。

   ![](assets/stock_6.png)

1. アセットを保存するフォルダーを選択します。[!DNL Assets Essentials] について詳しくは、[この節](assets-essentials.md#get-started-assets-essentials)を参照してください。

   ![](assets/stock_7.png)

1. 画像を [!DNL Adobe Stock] から選択した後、「**[!UICONTROL 類似したストック写真の検索]**」オプションを使用して、画像のコンテンツ、カラーおよび構成に一致するアセットを検索できます。

   このオプションは、Assets フォルダー内のライセンス済み／未ライセンスのストック画像と画像に対して使用できます。

   ![](assets/stock_8.png)

1. 画像を&#x200B;**[!UICONTROL コンポーネント設定]**&#x200B;メニューでさらにカスタマイズします。コンポーネント設定について詳しくは、[こちら](content-components.md)を参照してください。

   ![](assets/stock_11.png)

メッセージを作成してパーソナライズしたら、公開することで実行が可能になります。[詳細情報](../messages/publish-manage-message.md)
