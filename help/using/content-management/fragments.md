---
solution: Journey Optimizer
product: journey optimizer
title: フラグメントの基本を学ぶ
description: コンテンツフラグメントを操作して、Journey Optimizer のキャンペーンとジャーニーでコンテンツを再利用する方法を学ぶ
feature: Fragments
topic: Content Management
role: User
level: Beginner, Intermediate
exl-id: 7131a953-baca-4e7c-a8df-97c0bd6ac567
TQID: https://experienceleague.adobe.com/2XVXr3MjYnD-7o0C2ARXQ8j3sJOFfJfvjfCEZdkV50I
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2:
  - id: a653cc2e-bc85-4353-a306-399e5b247978
  - id: d998adac-2f81-400b-a669-d07bb196e4eb
  - id: dc22c819-3f29-4e91-8b7d-5c6719831141
  - id: fe338112-e2ce-4876-8989-fc4d497613f1
subfeature_v2:
  - id: c6e980f5-2d4f-494f-beef-186b9ecf1513
  - id: d595a60b-bcf5-4a63-a189-66a0be755cc7
  - id: ee5bb250-0884-4d71-86eb-d8489e8bcadd
  - id: fb9a80eb-bebc-492f-a0e9-584595621ebb
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2:
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: f9b8e1590f14cdcd00432295c653769f753b9b40
workflow-type: tm+mt
source-wordcount: 346
ht-degree: 97%

---

# フラグメントの基本を学ぶ {#fragments}

>[!CONTEXTUALHELP]
>id="ajo_create_fragment"
>title="独自のフラグメントを定義"
>abstract="スタンドアロンのフラグメントを作成および管理して、複数のジャーニーやキャンペーンでコンテンツを再利用できるようにします。"
>additional-url="https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/content-management/fragments/create-fragments" text="フラグメントを作成"

フラグメントは、[!DNL Journey Optimizer] キャンペーンおよびジャーニー全体で 1 つ以上のメールで参照できる再利用可能なコンポーネントです。 この機能を使用すると、マーケティングユーザーが改善されたデザインプロセスでメールコンテンツを迅速に組み立てるために使用できる複数のカスタムコンテンツブロックを事前に作成できます。

![](../rn/assets/do-not-localize/fragments.gif)

➡️ [フラグメントの管理、作成、使用方法については、これらのビデオをご覧ください](#video-fragments)

フラグメントを最大限に活用するには：

* **独自のフラグメントを作成**：ビジュアルフラグメントまたは式フラグメントを、ゼロから作成するか、コンテンツをフラグメントとして保存して作成します。 [フラグメントの作成方法を学ぶ](create-fragments.md) また、Journey Optimizer の **Content REST API** を活用すると、コンテンツフラグメントを管理できます。 詳しくは、[Journey Optimizer API ドキュメント](https://developer.adobe.com/journey-optimizer-apis/references/content){target="_blank"}を参照してください。
* **フラグメントの再利用**：作成したフラグメントを、必要な回数だけコンテンツで使用します。 [ビジュアルフラグメントの追加](../email/use-visual-fragments.md)および[式フラグメントの活用](../personalization/use-expression-fragments.md)を参照してください

## 開始する前に {#fragment-prerequisites}

フラグメントを作成、編集、アーカイブおよび公開するには、**[!DNL Content Library Manager]** 製品プロファイルに含まれている **[!DNL Manage library items]** および&#x200B;**[フラグメントを公開]**&#x200B;する権限が必要です。 [詳細情報](../administration/ootb-product-profiles.md#content-library-manager)

このバージョンでは、次の制限が適用されます。

* **ビジュアルフラグメント**&#x200B;は、メールチャネルでのみ使用できます。
* **式フラグメント**&#x200B;は、アプリ内チャネルでは使用できません。

フラグメントに適用されるその他のガードレールについて詳しくは、[この節](../start/guardrails.md#fragments-guardrails)を参照してください。

## ビジュアルフラグメントと式フラグメント {#visual-expression}

次の 2 つのタイプの除外を使用できます。

* **ビジュアルフラグメント**&#x200B;は、[E メールデザイナー](../email/get-started-email-design.md)または[コンテンツテンプレート](../email/use-email-templates.md)を使用して、複数のメール配信で再利用できる、事前定義されたビジュアルブロックです。
* **式フラグメント**&#x200B;は、[パーソナライゼーションエディター](../personalization/personalization-build-expressions.md)の専用のエントリから使用できる、事前定義された式です。

作成されたすべてのフラグメントには、左メニューの&#x200B;**[!UICONTROL コンテンツ管理]**／**[!UICONTROL フラグメント]**&#x200B;からアクセスできます。 [フラグメントの管理方法を学ぶ](../content-management/manage-fragments.md)

![](assets/fragment-list.png)

## チュートリアルビデオ {#video-fragments}

[!DNL Journey Optimizer] で&#x200B;**ビジュアルフラグメント**&#x200B;を管理、作成および使用する方法について説明します。

>[!VIDEO](https://video.tv.adobe.com/v/3419932/?quality=12)

[!DNL Journey Optimizer] で&#x200B;**式フラグメント**&#x200B;を管理、作成および使用する方法について説明します。

>[!VIDEO](https://video.tv.adobe.com/v/3424587/?quality=12)
