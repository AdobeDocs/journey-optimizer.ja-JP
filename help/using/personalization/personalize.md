---
title: Journey Optimizer でのコンテンツのパーソナライズ
description: パーソナライゼーションの概要
feature: パーソナライズ機能
topic: パーソナライズ機能
role: Data Engineer
level: Beginner
source-git-commit: 9656fc4b9f0935949abfd83db194c00da0f35cf4
workflow-type: tm+mt
source-wordcount: '624'
ht-degree: 75%

---

# パーソナライゼーションの基本を学ぶ {#add-personalization}

[!DNL Adobe Journey Optimizer]のパーソナライゼーション機能を利用して、特定の受信者に関するデータと情報を活用し、メッセージを個々の受信者に合わせて調整します。 この情報には、名前、興味、居住地および購入履歴などが含まれます。

[!DNL Journey Optimizer] は、Handlebarsに **** 基づくinlinesimpleパーソナライゼーション構文を使用して、中括弧{}}で囲まれたコンテンツを含む式を作&#x200B;**成できます。**&#x200B;同じコンテンツまたはフィールドに、制限なく複数の式を追加できます。詳しくは、[パーソナライゼーション構文](personalization-syntax.md)を参照してください。

パーソナライゼーションは、**XDM 個人版プロファイル**&#x200B;スキーマ（Adobe Experience Platform で定義）で管理されるプロファイルデータに基づいています。詳しくは、[Adobe Experience Platform データモデル（XDM）ドキュメント](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=ja)を参照してください。

>[!CAUTION]
>**XDM Individual Profile**&#x200B;スキーマは、[!DNL Journey Optimizer]内のコンテンツをパーソナライズするために使用できる唯一のスキーマです。

**例：**

* `Hello {{profile.person.name.firstName}} {{profile.person.name.lastName}}`

* `Hello {{profile.person.name.fullName}}`

Journey Optimizerは、メッセージ（Eメールおよびプッシュ）を処理する際に、式をPlatformデータベースに含まれるExperience Cloudで置き換えます。 `Hello {{profile.person.name.firstName}} {{profile.person.name.lastName}}`は「Hello John Doe」になります。


## パーソナライゼーションコンテキスト{#personalization-areas}

[!DNL Journey Optimizer]から配信されるメッセージのコンテンツと表示は、複数の方法でパーソナライズできます。

エディターアイコンを含むすべてのフィールドで、パーソナライゼーションエディター（式エディターとも呼ばれます）を開き、パーソナライゼーションを定義できます。

![](assets/perso_icon.png)

### メールのパーソナライズ

メールを作成する際、メッセージの「**件名**」フィールドにパーソナライゼーションを追加できます。

![](assets/perso_subject.png)

E メールデザイナーでは、コンテンツをパーソナライズできます。

* **メッセージ**&#x200B;内：テキストブロック内をクリックし、コンテキストツールバーの&#x200B;**パーソナライズ**&#x200B;アイコンをクリックして、「**パーソナライゼーションを挿入**」フィールドを選択します。E メールデザイナーインターフェイスについて詳しくは、この[節](../design-emails.md)を参照してください。

   ![](assets/perso_insert.png)

* **リンク**&#x200B;の場合：テキストブロック内のテキストまたは画像を選択し、コンテキストツールバーから「**リンクを挿入**」アイコンをクリックします。このウィンドウで、**パーソナライゼーション追加**&#x200B;アイコンをクリックすると、パーソナライゼーションブロックを追加できます。

   ![](assets/perso_link.png)

どちらの場合も、パーソナライゼーションエディターにアクセスします。

![](assets/perso_ee.png)


### プッシュ通知のパーソナライズ

以下の&#x200B;**プッシュ通知**&#x200B;のフィールドをパーソナライズすることもできます。

* **タイトル**
* **本文**
* **カスタムサウンド**
* **バッジ**
* **カスタムデータ**

![](assets/perso_push.png)

プッシュ通知の設定については、[この節](../push-gs.md)を参照してください。

## 式エディターの使用

式エディターは、[!DNL Journey Optimizer]のパーソナライゼーションの中心となるものです。

メール、プッシュ、オファーなど、パーソナライゼーションを定義する必要があるすべてのコンテキストで利用できます。

式エディターインターフェイスでは、すべてのデータを選択、整理、カスタマイズ、および検証して、コンテンツ用にカスタマイズされたパーソナライゼーションを作成します。

![](assets/perso_ee1.png)

画面の左側には、パーソナライゼーションのソースを選択できるドメインセレクターが表示されます。利用可能なソースは次のとおりです。

* **プロファイル** : [Adobe Experience Platform データモデル（XDM）ドキュメント](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html)に記載されているプロファイルスキーマに関連付けられたすべての参照をリストします。
* **セグメントのメンバーシップ**：Adobe Experience Platform Segmentation Service で作成されたすべてのセグメントをリストします。セグメント化の詳細については、[こちら](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=ja)を参照してください。
* **オファー** ：特定の配置に関連付けられているすべてのオファーをリストします。配置を選択し、コンテンツにオファーを挿入します。オファーの管理方法に関する詳細なドキュメントについては、[この節](../deliver-personalized-offers.md)を参照してください。
* **コンテキスト**：ジャーニー で&#x200B;**メッセージ**&#x200B;アクティビティを使用する場合、このメニューからコンテキストジャーニーフィールドを使用できます。詳しくは、[この節](personalization-use-case.md)を参照してください。
* **ヘルパー関数**：データの操作を実行できるすべてのヘルパー関数を示します。データの操作には、計算、データのフォーマットやコンバージョン、条件、パーソナライズ機能のコンテキストでの操作などがあります。詳しくは、[この節](functions/functions.md)を参照してください。

選択すると、エディターに参照が追加されます。

>[!NOTE]
>
>「+」アイコンの横の情報アイコンをクリックすると、ツールチップが開き、各変数の詳細が表示されます。

次の例では、式エディターを使用して、本日が誕生日のプロファイルを選択し、この日に対応する特定のオファーを挿入してカスタマイズを完了できます。

![](assets/perso_ee2.png)

