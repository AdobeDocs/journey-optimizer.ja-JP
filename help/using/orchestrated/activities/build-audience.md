---
solution: Journey Optimizer
product: journey optimizer
title: オーディエンスを作成アクティビティを使用する
description: オーケストレーションされたキャンペーンでオーディエンスを作成アクティビティを使用する方法を説明します
exl-id: 3959b5fa-0c47-42a5-828f-4d7ca9b7e72d
version: Campaign Orchestration
TQID: https://experienceleague.adobe.com/9hEr5kAHco1iq8arv-FddaG3vm54CS-cPFUA63soeAg
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2:
  - id: b3538224-471e-4c63-a444-9b19d89ae29c
  - id: d556b755-390a-43f0-be32-a08cf6236126
  - id: fe338112-e2ce-4876-8989-fc4d497613f1
source-git-commit: f9b8e1590f14cdcd00432295c653769f753b9b40
workflow-type: tm+mt
source-wordcount: 338
ht-degree: 0%

---

# オーディエンスを構築 {#build-audience}

>[!CONTEXTUALHELP]
>id="ajo_orchestration_build_audience"
>title="オーディエンス活動の構築"
>abstract="「**オーディエンスを作成**」アクティビティを使用すると、オーケストレーションされたキャンペーンに参加するオーディエンスを定義できます。 オーケストレーションされたキャンペーンのコンテキストでメッセージを送信する場合、メッセージオーディエンスはチャネルアクティビティではなく、**オーディエンスを構築** アクティビティで定義されます。"

マーケターは、直観的なインターフェイスで複雑なオーディエンスセグメントを作成できるため、さまざまな基準や行動にもとづいて利用者をターゲティングし、より効果的にキャンペーンを展開できます。

これを行うには、**[!UICONTROL オーディエンスを作成]** ターゲティングアクティビティを使用します。 このアクティビティは、オーケストレーションされたキャンペーンに入るオーディエンスを定義します。 オーケストレーションされたキャンペーンの一部としてメッセージを送信する場合、オーディエンスは、オーケストレーションされたキャンペーン内ではなく、**[!UICONTROL オーディエンスを作成]** アクティビティで定義されます。

## オーディエンスを作成アクティビティの設定 {#build-audience-configuration}

>[!CONTEXTUALHELP]
>id="ajo_orchestration_build_audience_audienceselector"
>title="Audience"
>abstract="新しい配信を設計する際にオーディエンスを使用するのと同じように、オーディエンスを選択します。"

次の手順に従って、**[!UICONTROL オーディエンスを作成]** アクティビティを設定します。

1. **[!UICONTROL オーディエンスを作成]** アクティビティを追加します。

   ![](../assets/build-audience.png)

1. **[!UICONTROL ラベル]**&#x200B;を定義します。

1. 以下のタブで詳しく説明されている手順に従って、オーディエンスを設定します。

1. **[!UICONTROL ターゲティングディメンション]**&#x200B;を選択します。 ターゲティングディメンションを使用すると、操作のターゲットとなる母集団（受信者、契約受益者、オペレーター、サブスクライバーなど）を定義できます。デフォルトでは、ターゲットは受信者から選択されます。

1. **[!UICONTROL 続行]**&#x200B;をクリックします。

1. ルールビルダーを使用してクエリを定義します。 [&#x200B; ルールビルダーについて詳しくは、この節を参照してください](../orchestrated-rule-builder.md)

1. オーディエンスが空の場合にアウトバウンドトランジションを生成するかどうかを指定します。

## 例{#build-audience-examples}

ここでは、2つの&#x200B;**[!UICONTROL オーディエンスを構築]** アクティビティを持つオーケストレーションされたキャンペーンの例を示します。 最初のターゲットは、カートに商品が入ったプロファイルで、その後にメール配信が続きます。 2つ目は、ウィッシュリストを使用してプロファイルをターゲットにし、その後にSMS配信を行います。

![](../assets/build-audience-2.png)

次の例では、**[!UICONTROL オーディエンスを作成]** アクティビティがルールビルダーを使用して、サブスクリプションプランでプロファイルをフィルタリングしています。 `plan`属性に条件を設定して、`plan = "basic"`のプロファイルのみを含め、オーディエンスを次のアクティビティに渡す前に基本階層のサブスクライバーに絞り込みます。

![](../assets/build-audience-plan.png){width="50%" align="left"}
