---
title: 式エディターについて
description: 式エディターの操作方法を説明します。
feature: Personalization
topic: Personalization
role: Data Engineer
level: Intermediate
exl-id: 1ac2a376-a3a8-41ae-9b04-37886697f0fc
source-git-commit: f1ac47a0cb405eaadc5428e7e5479eaf776d7abe
workflow-type: tm+mt
source-wordcount: '345'
ht-degree: 96%

---

# 式エディターについて {#build-personalization-expressions}

>[!CONTEXTUALHELP]
>id="ajo_perso_editor"
>title="式エディターについて"
>abstract="式エディターインターフェイスを使用すると、すべてのデータを選択、整理、カスタマイズ、および検証して、コンテンツ用にカスタマイズされたパーソナライゼーションを作成できます。"

式エディターは、[!DNL Journey Optimizer] のパーソナライゼーションの中核です。メール、プッシュ、オファーなど、パーソナライゼーションを定義する必要があるすべてのコンテキストで利用できます。

式エディターインターフェイスでは、すべてのデータを選択、整理、カスタマイズ、および検証して、コンテンツ用にカスタマイズされたパーソナライゼーションを作成します。

![](assets/perso_ee1.png)

画面の左側には、パーソナライゼーションのソースを選択できるドメインセレクターが表示されます。

![](assets/perso_ee3.png)

利用可能なソースは次のとおりです。

* **[!UICONTROL プロファイル属性]**：[Adobe Experience Platform データモデル（XDM）ドキュメント](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=ja){target=&quot;_blank&quot;}に記載のプロファイルスキーマに関連付けられているすべての参照を一覧表示します。
* **[!UICONTROL セグメントのメンバーシップ]** :に、Adobe Experience Platform Segmentation サービスで作成されたすべてのセグメントを示します。 セグメント化について詳しくは、[こちら](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html?lang=ja){target=&quot;_blank&quot;}を参照してください。
* **[!UICONTROL オファー決定]**：特定のプレースメントに関連付けられているすべてのオファーを一覧表示します。配置を選択し、コンテンツにオファーを挿入します。オファーの管理方法に関する詳細なドキュメントについては、[この節](../design/deliver-personalized-offers.md)を参照してください。
* **[!UICONTROL コンテキスト属性]**：ジャーニーで&#x200B;**メッセージ**&#x200B;を使用している場合は、ジャーニーのコンテキストフィールドをこのメニューから使用できます。詳しくは、[この節](personalization-use-case.md)を参照してください。
* **[!UICONTROL ヘルパー関数]**：データの操作を実行できるすべてのヘルパー関数を示します。データの操作には、計算、データのフォーマットやコンバージョン、条件、パーソナライゼーションのコンテキストでの操作などがあります。詳しくは、[この節](functions/functions.md)を参照してください。

「+」ボタンをクリックすると、エディターに属性を追加できます。

>[!NOTE]
>
>「+」アイコンの横にある楕円メニューを使用すると、各変数の詳細を取得したり、使用頻度の高い属性を[お気に入り](personalization-favorites.md)に追加したりできます。

![](assets/attribute-details.png)

次の例では、式エディターを使用して、本日が誕生日のプロファイルを選択し、この日に対応する特定のオファーを挿入してカスタマイズを完了します。

![](assets/perso_ee2.png)

パーソナライズ機能の式を準備できたら、式エディターで検証する必要があります。詳しくは、[この節](personalization-validation.md)を参照してください。
