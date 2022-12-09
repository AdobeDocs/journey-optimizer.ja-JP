---
solution: Journey Optimizer
product: journey optimizer
title: エクスプレッションエディターについて
description: 式エディターを使用した作業について説明します。
feature: Personalization
topic: Personalization
role: Data Engineer
level: Intermediate
exl-id: 1ac2a376-a3a8-41ae-9b04-37886697f0fc
source-git-commit: 020c4fb18cbd0c10a6eb92865f7f0457e5db8bc0
workflow-type: tm+mt
source-wordcount: '330'
ht-degree: 0%

---

# エクスプレッションエディターについて {#build-personalization-expressions}

>[!CONTEXTUALHELP]
>id="ajo_perso_editor"
>title="エクスプレッションエディターについて"
>abstract="式エディターを使用すると、すべてのデータを選択、配置、カスタマイズ、検証して、コンテンツのカスタマイズされたパーソナル化を作成できます。"

式エディターは、の [!DNL Journey Optimizer] 個人用設定の centerpiece です。 この機能は、電子メール、プッシュ、オファーのような個人用設定を定義する必要があるすべてのコンテキストで使用できます。

式エディターのインターフェイスでは、すべてのデータを選択、配置、カスタマイズ、検証することで、コンテンツのカスタマイズされたパーソナル化を作成できます。

![](assets/perso_ee1.png)

画面の左側にはドメインセレクターが表示されます。これにより、パーソナル化のソースを選択することができます。

![](assets/perso_ee3.png)

使用できるソースは以下のとおりです。

* **[!UICONTROL Profile attributes]**: Adobe エクスペリエンス Platform データモデル (XDM) マニュアル ](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) で [ 説明されているプロファイルスキーマに関連するすべての参照が一覧表示されます (target = &quot;_blank&quot;})。
* **[!UICONTROL Segment memberships]** : Adobe エクスペリエンスプラットフォームセグメンテーションサービスで作成されたすべてのセグメントの一覧を表示します。 セグメンテーション [ について詳しくは ](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html) 、{target = &quot;_blank&quot;} を参照してください。
* **[!UICONTROL Offer decisions]** : 特定の配置に関連付けられたすべてのオファーを一覧表示します。 「配置」を選択して、コンテンツに「オファー」を挿入します。 キャンペーンの管理方法について詳しくは、ここ ](../email/add-offers-email.md) を [ 参照してください。
* **[!UICONTROL Contextual attributes]** : チャネルアクションアクティビティ (電子メール、プッシュ、SMS) が旅に使用されると、状況に応じた各フィールドが表示されます。 詳しくは、ここを [ ](personalization-use-case.md) 参照してください。
* **[!UICONTROL Helper functions]** : 計算、データフォーマット、変換、条件など、データに対する操作を実行するために使用できるすべてのヘルパー関数が一覧表示されます。これは、パーソナル化のコンテキストでそれらを操作するときに使用されます。 詳しくは、ここを [ ](functions/functions.md) 参照してください。

「+」ボタンをクリックすると、エディターに属性が追加されます。

>[!NOTE]
>
>「+」アイコンの横にある楕円メニューを使用すると、各変数に関する詳細情報を取得し、最も頻繁に [ 使用される「お気に入り ](personalization-favorites.md) 」属性を追加することができます。

![](assets/attribute-details.png)

次の例では、式エディターを使用して、今日の誕生日が含まれているプロファイルを選択します。これにより、その日に対応する特定の特典が挿入されます。

![](assets/perso_ee2.png)

パーソナル化条件式の準備が完了したら、式エディターを使用して、その式が検証されるようにする必要があります。 詳しくは、ここを [ ](personalization-validation.md) 参照してください。
