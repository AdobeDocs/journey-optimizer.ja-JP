---
title: Journey Optimizer でのコンテンツのパーソナライズ
description: パーソナライゼーションの概要
feature: パーソナライズ機能
topic: パーソナライズ機能
role: Data Engineer
level: Beginner
source-git-commit: b07970ff11f1ba7c4e6db30dc2eca1252a579ca4
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# パーソナライゼーションの概要{#add-personalization}

[!DNL Adobe Journey Optimizer] のパーソナライゼーション機能を学び、ユーザーに関するデータと情報を活用して、特定の受信者に合わせたメッセージを作成します。この情報には、名、興味、居住地および購入履歴などが含まれます。

➡️ [メッセージをパーソナライズする方法については、次のビデオを参照してください](#video-perso)

[!DNL Journey Optimizer] ではハンドルバーに基づいた、**インライン**&#x200B;のシンプルなパーソナライゼーション構文を使用します。この構文を使用すると、コンテンツを二重の中括弧 **{{}}** で囲んだ式を作成することができます。同じコンテンツまたはフィールドに、制限なく複数の式を追加できます。詳しくは、[パーソナライゼーション構文](personalization-syntax.md)を参照してください。

パーソナライゼーションは、**XDM 個人版プロファイル**&#x200B;スキーマ（Adobe Experience Platform で定義）で管理されるプロファイルデータに基づいています。詳しくは、[Adobe Experience Platformデータモデル(XDM)のドキュメント](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=ja){target=&quot;_blank&quot;}を参照してください。

>[!CAUTION]
>**XDM 個人版プロファイル**&#x200B;スキーマは、[!DNL Journey Optimizer] でコンテンツをパーソナライズするために使用できる唯一のスキーマです。

**例：**

* `Hello {{profile.person.name.firstName}} {{profile.person.name.lastName}}`

* `Hello {{profile.person.name.fullName}}`

メッセージ（メールおよびプッシュ）を処理する際に、Journey Optimizer は式を、 Experience Cloud Platform データベースに含まれるデータに置き換えます。`Hello {{profile.person.name.firstName}} {{profile.person.name.lastName}}` は “Hello John Doe” となります。


## パーソナライゼーションのコンテキスト{#personalization-areas}

[!DNL Journey Optimizer] が配信するメッセージの内容や表示は、様々な方法でパーソナライズできます。

エディターアイコンが付いているすべてのフィールドで、パーソナライゼーションエディター（式エディターとも呼ばれます）を開き、パーソナライゼーションを定義できます。

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

式エディターは、[!DNL Journey Optimizer] のパーソナライゼーションの中核です。

メール、プッシュ、オファーなど、パーソナライゼーションを定義する必要があるすべてのコンテキストで利用できます。

式エディターインターフェイスでは、すべてのデータを選択、整理、カスタマイズ、および検証して、コンテンツ用にカスタマイズされたパーソナライゼーションを作成します。

![](assets/perso_ee1.png)

画面の左側には、パーソナライゼーションのソースを選択できるドメインセレクターが表示されます。利用可能なソースは次のとおりです。

* **プロファイル** : [Adobe Experience Platform Data Model(XDM)のドキュメント](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html){target=&quot;_blank&quot;}で説明されているプロファイルスキーマに関連するすべての参照を示します。
* **セグメントのメンバーシップ**：Adobe Experience Platform Segmentation Service で作成されたすべてのセグメントをリストします。セグメント化の詳細については、[こちら](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=ja)を参照してください。{target=&quot;_blank&quot;}。
* **オファー** ：特定の配置に関連付けられているすべてのオファーをリストします。配置を選択し、コンテンツにオファーを挿入します。オファーの管理方法に関する詳細なドキュメントについては、[この節](../deliver-personalized-offers.md)を参照してください。
* **コンテキスト**：ジャーニー で&#x200B;**メッセージ**&#x200B;アクティビティを使用する場合、このメニューからコンテキストジャーニーフィールドを使用できます。詳しくは、[この節](personalization-use-case.md)を参照してください。
* **ヘルパー関数**：データの操作を実行できるすべてのヘルパー関数を示します。データの操作には、計算、データのフォーマットやコンバージョン、条件、パーソナライズ機能のコンテキストでの操作などがあります。詳しくは、[この節](functions/functions.md)を参照してください。。

選択すると、エディターに参照が追加されます。

>[!NOTE]
>
>「+」アイコンの横の情報アイコンをクリックすると、ツールチップが開き、各変数の詳細が表示されます。

次の例では、式エディターを使用して、本日が誕生日のプロファイルを選択し、この日に対応する特定のオファーを挿入してカスタマイズを完了できます。

![](assets/perso_ee2.png)

## ハウツービデオ{#video-perso}

ジャーニーのコンテキストイベント情報を使用してメッセージをパーソナライズする方法を説明します。

>[!VIDEO](https://video.tv.adobe.com/v/334165?quality=12)

ジャーニーのコンテキストイベント情報を使用してメッセージをパーソナライズする方法を説明します。

>[!VIDEO](https://video.tv.adobe.com/v/334078?quality=12)
