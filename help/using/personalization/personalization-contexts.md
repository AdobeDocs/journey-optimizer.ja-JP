---
title: パーソナライゼーションのコンテキスト
description: 'コンテンツをパーソナライズし、メッセージを表示する方法について説明します。 '
feature: Personalization
topic: Personalization
role: Data Engineer
level: Intermediate
exl-id: fe39570b-cbd2-4b24-af10-e12990a9a885
source-git-commit: 1993dc5648bcd294ec2f8dfbbb783b81addf873f
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 90%

---

# パーソナライゼーションのコンテキスト{#personalization-areas}

[!DNL Journey Optimizer] が配信するメッセージの内容や表示は、様々な方法でパーソナライズできます。

エディターアイコンが付いているすべてのフィールドで、パーソナライゼーションエディター（式エディターとも呼ばれます）を開き、パーソナライゼーションを定義できます。

![](assets/perso_icon.png)

## メールのパーソナライズ {#personalize-emails}

メールを作成する際に、メッセージの「**[!UICONTROL 件名]**」フィールドにパーソナライゼーションを追加できます。

![](assets/perso_subject.png)

E メールデザイナーでは、コンテンツをパーソナライズできます。

* **メッセージ**&#x200B;内：テキストブロック内をクリックし、コンテキストツールバーの&#x200B;**パーソナライズ**&#x200B;アイコンをクリックして、「**パーソナライゼーションを挿入**」フィールドを選択します。E メールデザイナーインターフェイスについて詳しくは、この[節](../messages/design-emails.md)を参照してください。

   ![](assets/perso_insert.png)

* **リンク**&#x200B;の場合：テキストブロック内のテキストまたは画像を選択し、コンテキストツールバーから「**リンクを挿入**」アイコンをクリックします。このウィンドウで、**パーソナライゼーション追加**&#x200B;アイコンをクリックすると、パーソナライゼーションブロックを追加できます。

   ![](assets/perso_link.png)

どちらの場合も、パーソナライゼーションエディターにアクセスします。

![](assets/perso_ee.png)

## プッシュ通知のパーソナライズ {#personalize-push}

以下の&#x200B;**プッシュ通知**&#x200B;のフィールドをパーソナライズすることもできます。

* **タイトル**
* **本文**
* **カスタムサウンド**
* **バッジ**
* **カスタムデータ**

![](assets/perso_push.png)

プッシュ通知の設定については、[この節](../messages/push-gs.md)を参照してください。

## オファーのパーソナライズ {#personalize-offers}

テキストタイプのコンテンツをオファーの表示域に追加する場合は、パーソナライゼーションエディターを利用することもできます。

意思決定管理を使用したコンテンツ管理について詳しくは、[この節](../offers/offer-library/creating-personalized-offers.md#custom-text)を参照してください。

## パーソナライズした URL の作成{#personalize-urls}

パーソナライズされた URL は、プロファイル属性に応じて、受信者を web サイトの特定のページに誘導するか、パーソナライズされたマイクロサイトに誘導します。 Adobe Journey Optimizerでは、メッセージコンテンツの URL にパーソナライゼーションを追加できます。 URL のパーソナライゼーションはテキストや画像に適用でき、その際にプロファイルデータやコンテキストデータを使用できます。

にパーソナライズ URL を挿入する方法を説明します。 [この節](personalization-syntax.md#perso-urls).

