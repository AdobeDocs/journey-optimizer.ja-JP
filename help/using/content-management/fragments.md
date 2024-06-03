---
solution: Journey Optimizer
product: journey optimizer
title: フラグメントの基本を学ぶ
description: コンテンツフラグメントを操作して、Journey Optimizerのキャンペーンやジャーニーでコンテンツを再利用する方法を説明します
feature: Fragments
topic: Content Management
role: User
level: Beginner, Intermediate
exl-id: 7131a953-baca-4e7c-a8df-97c0bd6ac567
source-git-commit: e7ff784d51da48c1970841e416c655c02cfafb7c
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 46%

---

# フラグメントの基本を学ぶ {#fragments}

>[!CONTEXTUALHELP]
>id="ajo_create_fragment"
>title="独自のフラグメントを定義"
>abstract="スタンドアロンのフラグメントを作成および管理して、複数のジャーニーやキャンペーンでコンテンツを再利用できるようにします。"
>additional-url="https://experienceleague.adobe.com/en/docs/journey-optimizer/using/content-management/fragments/create-fragments" text="フラグメントを作成"

>[!CONTEXTUALHELP]
>id="ajo_fragments_update_campaigns"
>title="フラグメント更新キャンペーン"
>abstract="フラグメント更新キャンペーン"

>[!CONTEXTUALHELP]
>id="ajo_fragments_update_journeys"
>title="フラグメント更新ジャーニー"
>abstract="フラグメント更新ジャーニー"

フラグメントは、全体で 1 つ以上のメールで参照できる再利用可能なコンポーネントです [!DNL Journey Optimizer] キャンペーンとジャーニー。 この機能を使用すると、マーケティングユーザーが改善されたデザインプロセスでメールコンテンツを迅速に組み立てるために使用できる複数のカスタムコンテンツブロックを事前に構築できます。

![](../rn/assets/do-not-localize/fragments.gif)

➡️ [フラグメントの管理、作成、使用方法については、これらのビデオをご覧ください](#video-fragments)

フラグメントを最大限に活用するには：

* **独自のフラグメントを作成**：最初から、またはコンテンツをフラグメントとして保存することで、ビジュアルフラグメントまたは式フラグメントを作成します。 [フラグメントの作成方法を学ぶ](#create-fragments). また、Journey Optimizer の **Content REST API** を活用すると、コンテンツフラグメントを管理できます。詳しくは、[Journey Optimizer API ドキュメント](https://developer.adobe.com/journey-optimizer-apis/references/content/){target="_blank"}を参照してください。
* **フラグメントを再利用します。** コンテンツで必要な回数だけ使用します。 [ビジュアルフラグメントの追加](../email/use-visual-fragments.md)および[式フラグメントの活用](../personalization/use-expression-fragments.md)を参照してください

## 開始する前に {#fragment-prerequisites}

>[!NOTE]
>
>フラグメントを作成、編集、アーカイブするには、**[!DNL Content Library Manager]** 製品プロファイルに **[!DNL Manage library items]** 権限が付与されている必要があります。[詳細情報](../administration/ootb-product-profiles.md#content-library-manager)

このバージョンでは、次の制限が適用されます。

* **ビジュアルフラグメント** は、メール チャネルでのみ使用できます。
* **式フラグメント** は、アプリ内チャネルでは使用できません。

## ビジュアルおよび式フラグメント {#visual-expression}

次の 2 種類のフラグメントを使用できます。

* **ビジュアルフラグメント** は、を使用して複数のメール配信で再利用できる、事前定義されたビジュアルブロックです [電子メールデザイナー](../email/get-started-email-design.md)、または [コンテンツテンプレート](../email/use-email-templates.md).
* **式フラグメント** は、の専用のエントリから使用できる、事前定義された式です [パーソナライゼーションエディター](../personalization/personalization-build-expressions.md).


すべてのフラグメントは、 **[!UICONTROL コンテンツ管理]** > **[!UICONTROL フラグメント]**  左メニュー。

![](assets/fragment-list.png)

## チュートリアルビデオ {#video-fragments}

ビジュアルフラグメントを管理、作成および使用する方法については、[!DNL Journey Optimizer] を参照してください。

>[!VIDEO](https://video.tv.adobe.com/v/3419932/?quality=12)

フラグメントを管理、作成および使用する方法については、[!DNL Journey Optimizer] を参照してください。

>[!VIDEO](https://video.tv.adobe.com/v/3424587/?quality=12)
