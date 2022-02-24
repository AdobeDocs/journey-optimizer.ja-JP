---
title: パーソナライゼーションのコンテキスト
description: 'コンテンツをパーソナライズし、メッセージを表示する方法について説明します。 '
feature: Personalization
topic: Personalization
role: Data Engineer
level: Intermediate
exl-id: fe39570b-cbd2-4b24-af10-e12990a9a885
source-git-commit: 1ffa268304ab6343847cdc57b54a3933eb61c902
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 85%

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

## パーソナライズされた URL{#personalize-urls}

メッセージコンテンツ内に、パーソナライゼーションを使用したリンクを作成できます。 例えば、新規顧客向けに Web サイトの特定のページへのリンクを追加します。

パーソナライゼーション機能を使用してパーソナライズされた URL を挿入する方法を説明します。 [この節](personalization-syntax.md#perso-urls).

