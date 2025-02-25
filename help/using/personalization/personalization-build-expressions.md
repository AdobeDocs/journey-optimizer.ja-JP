---
solution: Journey Optimizer
product: journey optimizer
title: パーソナライゼーションエディターについて
description: パーソナライゼーションエディターの操作方法を説明します。
feature: Personalization
topic: Personalization
role: Data Engineer
level: Intermediate
keywords: 式, エディター, 説明, 開始
exl-id: 1ac2a376-a3a8-41ae-9b04-37886697f0fc
source-git-commit: fe22eef1e1d74101ba7c046fca28a5a95007dd81
workflow-type: tm+mt
source-wordcount: '484'
ht-degree: 94%

---

# パーソナライゼーションエディターの基本を学ぶ {#build-personalization-expressions}

>[!CONTEXTUALHELP]
>id="ajo_perso_editor"
>title="パーソナライゼーションエディターについて"
>abstract="パーソナライゼーションエディターを使用すると、すべてのデータを選択、整理、カスタマイズ、検証して、コンテンツ用にカスタマイズされたパーソナライゼーションを作成できます。"

>[!CONTEXTUALHELP]
>id="ajo_perso_editor_autocomplete"
>title="オートコンプリート"
>abstract="このオプションをオンにすると、式を入力している間、コードが自動的に入力され、提案が行われます。 このオプションは、HTML形式でのみ使用できます。"

パーソナライゼーションエディターは、[!DNL Journey Optimizer] のパーソナライズ機能の中核です。メール、プッシュ、オファーなど、パーソナライゼーションを定義する必要があるすべてのコンテキストで利用できます。

パーソナライゼーションエディターインターフェイスでは、すべてのデータを選択、整理、カスタマイズ、検証して、コンテンツ用にカスタマイズされたパーソナライゼーションを作成します。

![](assets/perso_ee1.png)

## 使用可能なパーソナライゼーションソース {#sources}

画面の左側には、パーソナライゼーションのソースを選択できるドメインセレクターが表示されます。利用可能なソースは次のとおりです。

* **[!UICONTROL プロファイル属性]**：[Adobe Experience Platform データモデル（XDM）ドキュメント](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=ja){target="_blank"}に記載のプロファイルスキーマに関連付けられているすべての参照をリストします。
* **[!UICONTROL オーディエンス]**：Adobe Experience Platform セグメント化サービスで作成されたすべてのオーディエンスをリストします。セグメント化について詳しくは、[こちら](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html?lang=ja){target="_blank"}を参照してください。
* **[!UICONTROL オファー決定]**：特定のプレースメントに関連付けられているすべてのオファーを一覧表示します。配置を選択し、コンテンツにオファーを挿入します。オファーの管理方法に関する詳細なドキュメントについては、[この節](../offers/get-started/starting-offer-decisioning.md)を参照してください。
* **[!UICONTROL コンテキスト属性]**：チャネルアクションアクティビティ（メール、プッシュ、SMS）をジャーニーまたはキャンペーンで使用する場合、イベントやプロパティに関連するコンテキスト属性をパーソナライズに使用できます。コンテキスト属性を活用したパーソナライゼーションの例については、[この節](personalization-use-case.md)を参照してください。
* **[!UICONTROL ヘルパー関数]**：データに対する操作（計算、データの書式設定や変換、条件、パーソナライゼーションのコンテキストでの操作など）の実行に使用できるすべてのヘルパー関数をリストします。詳しくは、[この節](functions/functions.md)を参照してください。

## パーソナライゼーション属性の追加 {#add}

「+」ボタンをクリックして、パーソナライゼーション式に属性を追加します。

「+」アイコンの横にある省略記号メニューを使用すると、各変数の詳細を取得したり、使用頻度の高い属性をお気に入りに追加したりできます。[詳しくは、お気に入りに属性を追加する方法を参照してください](personalization-favorites.md)

>[!NOTE]
>
>コンポジションワークフローを使用して生成されたエンリッチメント属性でオーディエンスをターゲットにしている場合は、これらのエンリッチメント属性を活用してメッセージをパーソナライズできます。[詳しくは、オーディエンスのエンリッチメント属性の使用方法を参照してください](../audience/about-audiences.md#enrichment)

さらに、文字列タイプのプロファイル属性が空の場合に表示されるデフォルトの代替テキストを定義できます。これを行うには、属性の横にある省略記号ボタンをクリックし、「**[!UICONTROL 代替テキストで挿入]**」を選択します。プロファイルの属性の値が空の場合にデフォルトで表示するテキストを書き込み、「**[!UICONTROL 追加]**」をクリックします。

![](assets/attribute-details.png)

次の例では、パーソナライゼーションエディターを使用して、本日が誕生日のプロファイルを選択し、この日に対応する特定のオファーを挿入してカスタマイズを完了します。

![](assets/perso_ee2.png)

パーソナライゼーション式を準備できたら、パーソナライゼーションエディターで検証する必要があります。詳しくは、[この節](personalization-validation.md)を参照してください。
