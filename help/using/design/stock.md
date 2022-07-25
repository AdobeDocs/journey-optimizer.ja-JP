---
title: Adobe Stock画像の操作
description: Adobe Stock の基本を学ぶ
feature: Overview
topic: Content Management
role: User
level: Beginner
exl-id: 0715f65f-04bd-4dc2-a152-98111f4c42e6
source-git-commit: 0e978d0eab570a28c187f3e7779c450437f16cfb
workflow-type: tm+mt
source-wordcount: '586'
ht-degree: 17%

---

# の操作 [!DNL Adobe Stock] 画像 {#stock}

## [!DNL Adobe Stock] の基本を学ぶ {#get-started-stock}

この [!DNL Adobe Stock] および [!DNL Adobe Journey Optimizer] Email Designer 統合プラグインを使用すると、メッセージのオーサリングで使用するために、画像のナビゲーション、ライセンス取得、保存を簡単におこなえます。

[Adobe Stock](https://helpx.adobe.com/jp/stock/get-started.html){target=&quot;_blank&quot;} は、何百万もの高品質で厳選された、ロイヤリティーフリーの写真、ビデオ、イラスト、ベクトルグラフィックを利用できます。 クレジットパックを購入してアセットのライセンスを取得するか、必要なアセットに対して通常ライセンスまたは強化ライセンスを 1 つだけ購入するかどうかを選択できます。Adobe Stock はまた、アセットの無料コレクションを提供しています。

を使用 [!DNL Adobe Journey Optimizer]を使用すると、 [!DNL Adobe Stock] をクリックし、 **[!UICONTROL Adobe Stockの写真を検索]** オプション。 また、 **[!UICONTROL 類似した写真を検索]** 「 」オプションを使用すると、配信で使用されるアセットのコンテンツ、色、構成に一致する画像を検索できます。

## 権限{#stock-permissions}

この **[!UICONTROL Adobe Stockの写真を検索]** および **[!UICONTROL 類似画像を検索]** オプションは、AEM Assets Essentials 製品プロファイルへのアクセス権を持つユーザーが使用できます。

詳しくは、 [Assets の基本ドキュメント](https://experienceleague.adobe.com/docs/experience-manager-assets-essentials/help/get-started-admins/deploy-administer.html#add-users-to-essentials){target=&quot;_blank&quot;}。

## 画像の挿入元 [!DNL Adobe Stock] {#add-stock-image}

画像を追加するには [!DNL Adobe Stock] をコンテンツに追加するには、次の手順に従います。

1. 次の **[!UICONTROL コンテンツコンポーネント]** E メールデザイナーのセクションで、 **画像**.

1. 次をクリック： **[!UICONTROL Adobe Stockの写真を検索]** ボタンをクリックします。

   ![](assets/stock-find-photos.png)

1. ライブラリを参照するか、検索フィールドに用語を入力します。

   ![](assets/stock-select-from-lib.png)

1. 選んだ画像を選択し、「**[!UICONTROL 保存]**」をクリックします。

   選択した画像がライセンスされていない場合、 [免許を取る](#license-stock-image).


## 類似の写真を検索 {#similar-stock-image}

E メールコンテンツ内の既存の画像を、次の写真で置き換えることができます： [!DNL Adobe Stock]. このオプションは、すべての画像で使用できます。ライセンス済み/ライセンス未取得の Stock 画像と画像を Assets フォルダーから取得します。

類似した写真を参照するには、次の手順に従います。

1. 置き換える画像を選択します。
1. 次をクリック： **[!UICONTROL 類似の写真を検索]** ボタン [!DNL Adobe Stock] 画像のコンテンツ、色、構成に一致する

   ![](assets/stock-similar.png)

1. 選んだ画像を選択し、「**[!UICONTROL 保存]**」をクリックします。

   ![](assets/stock-similar-results.png)

   選択した画像がライセンスされていない場合、 [免許を取る](#license-stock-image).

1. 必要に応じて、 **[!UICONTROL コンポーネント設定]** メニュー [コンポーネント設定の詳細](content-components.md).

## ライセンスの取得元 [!DNL Adobe Stock] {#license-stock-image}

画像が既にライセンスされている場合は、 ![](assets/stock_10.png) アイコン ライセンスがない場合は、ライセンスが必要です。

画像のライセンスを取得してダウンロードするには、次の手順に従います。

1. 選択し、 **[!UICONTROL Adobe Stock画像のライセンス]** アイコン

   ![](assets/stock-license-icon.png)

   その後、 [!DNL Adobe Stock] web サイトからライセンスを除く。

   ![](assets/stock-license-photo.png)

1. 次の [!DNL Adobe Stock] web サイトで画像をダウンロードして透かしを削除するには、アセットを購入する必要があります。

   この購入は、Adobe Stockのプランまたはサブスクリプションによって異なります。 複数のAdobe Stockアカウントがある場合は、最後に使用した Stock ID にリダイレクトされます。 この場合、アセットのライセンスを取得する前に、正しいアカウントにサインインしていることを確認してください。

   でのAdobe Stockの計画と価格について詳しくは、 [Adobe Stockドキュメント](https://stock.adobe.com/jp/plans){target=&quot;_blank&quot;}。

   >[!WARNING]
   > ライセンスが不要な画像を含む E メールが送信された場合、画像は、ライセンスが不要なフォームに透かしが付いたままになります。

1. 購入が完了したら、[!DNL Adobe Journey Optimizer] でメールに戻り、「**[!UICONTROL ストック画像を読み込み]**」を選択して、ライセンス済みの画像をアセットに読み込むことができます。

   ![](assets/stock_6.png)

1. アセットを保存するフォルダーを選択します。 [!DNL Assets Essentials] について詳しくは、[この節](assets-essentials.md#get-started-assets-essentials)を参照してください。

## 関連トピック{#stock-related-topics}

* [Journey Optimizerでの E メールデザイン](design-emails.md)
* [電子メールデザインのコンポーネント設定](content-components.md)
* [Adobe Stockはじめに](https://helpx.adobe.com/stock/get-started.html){target=&quot;_blank&quot;}。

