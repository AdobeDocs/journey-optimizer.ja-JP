---
solution: Journey Optimizer
product: journey optimizer
title: パーソナル化コンテキスト
description: コンテンツを個人用に設定し、メッセージを表示する方法について詳しくは、こちらを参照してください。
feature: Personalization
topic: Personalization
role: Data Engineer
level: Intermediate
exl-id: fe39570b-cbd2-4b24-af10-e12990a9a885
source-git-commit: 020c4fb18cbd0c10a6eb92865f7f0457e5db8bc0
workflow-type: tm+mt
source-wordcount: '281'
ht-degree: 0%

---

# パーソナル化コンテキスト{#personalization-areas}

で [!DNL Journey Optimizer] 配信されたメッセージのコンテンツと表示は、様々な方法で個人用にすることができます。

エディターアイコンが表示されたすべてのフィールドに、パーソナル化エディター (エクスプレッションエディターとも呼ばれます) を開き、パーソナル化を定義することができます。

![](assets/perso_icon.png)

## 電子メールの個人用設定 {#personalize-emails}

電子メールの作成時に、メッセージのフィールドに **[!UICONTROL Subject line]** 個人用設定を追加することができます。

![](assets/perso_subject.png)

電子メールデザイナーでは、以下のようにコンテンツをカスタマイズすることができます。

* 次のようなメッセージ **が表示され** た場合は、テキストブロックの内側をクリックし、状況に応じたツールバー **で「個人用** 設定 **」アイコンをクリック** します。電子メールデザイナーインターフェイスについて詳しくは、この [ 節 ](../email/get-started-email-design.md) を参照してください。

   ![](assets/perso_insert.png)

* **リンク** について: テキストブロック内のテキストまたはイメージを選択し、状況に応じたツールバーの「リンク **の挿入」アイコンをクリック** します。ウィンドウで、個人用設定 **の** 追加アイコンをクリックして、個人用設定ブロックを追加することができます。

   ![](assets/perso_link.png)

どちらの場合も、パーソナル化エディターにアクセスします。

![](assets/perso_ee.png)

## プッシュ通知の個人用設定 {#personalize-push}

以下のフィールドで、 **プッシュ通知** をカスタマイズすることもできます。

* **書籍**
* **Body**
* **カスタムサウンド**
* **バッジ**
* **カスタムデータ**

![](assets/perso_push.png)

この節 ](../push/push-gs.md) では、プッシュ通知の [ 設定について詳しく説明しています。

## キャンペーンのカスタマイズ {#personalize-offers}

テキストタイプのコンテンツをデルオファーに追加する際に、個人用設定エディターにアクセスすることもできます。

このセクション ](../offers/offer-library/creating-personalized-offers.md#custom-text) では、 [ 意志決定管理を使用したコンテンツの管理について詳しく説明しています。

## パーソナライズされた Url の作成{#personalize-urls}

パーソナライズされた Url では、プロファイル属性に応じて、web サイトの特定のページ、またはパーソナライズされたマイクロサイトが宛先になります。 Adobe 旅のオプティマイザーでは、メッセージコンテンツ内の Url にパーソナライズ機能を追加することができます。 URL パーソナル化は、テキストとイメージに適用できます。また、プロファイルデータまたは文脈データを使用することもできます。

この節 ](personalization-syntax.md#perso-urls) で [ は、パーソナライズされた URL を挿入する方法について説明します。

