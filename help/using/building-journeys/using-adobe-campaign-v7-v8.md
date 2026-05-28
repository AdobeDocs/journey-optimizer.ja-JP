---
solution: Journey Optimizer
product: journey optimizer
title: Adobe Campaign v7／v8 のアクション
description: Adobe Campaign v7／v8 のアクションについて説明します
feature: Journeys, Actions, Custom Actions
topic: Administration
role: User
level: Intermediate
keywords: ジャーニー, 統合, キャンペーン, v7, v8
exl-id: 3da712e7-0e08-4585-8ca4-b6ff79df0b68
version: Journey Orchestration
TQID: https://experienceleague.adobe.com/Saqu6Kkm1Rdym10IuwLF88Fj-hT2crAwENajyKBeY5w
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2:
  - id: b3538224-471e-4c63-a444-9b19d89ae29c
  - id: d998adac-2f81-400b-a669-d07bb196e4eb
subfeature_v2:
  - id: c2beecbb-b93e-4ae3-baa9-72adcdc06781
  - id: cfba2953-2ce9-4b00-a00c-71cd338ae63f
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 0ee10a0689d38c22b1180b197796b08a10c286cf
workflow-type: tm+mt
source-wordcount: 299
ht-degree: 63%

---

# [!DNL Adobe Campaign] v7/v8 のアクション {#using_campaign_v7-v8}

>[!CONTEXTUALHELP]
>id="ajo_journey_action_custom_acc"
>title="カスタムアクション"
>abstract="統合は、[!DNL Adobe Campaign] v7 または v8 のユーザーが使用できます。 [!DNL Adobe Campaign] のトランザクションメッセージ機能を使用して、メール、プッシュ通知、SMS などを送信できるようになります。"

統合は、[!DNL Adobe Campaign] v7 または v8 のユーザーが使用できます。 [!DNL Adobe Campaign] のトランザクションメッセージ機能を使用して、メール、プッシュ通知、SMS などを送信できるようになります。

Journey Optimizer と Campaign インスタンスとの接続は、プロビジョニング時にアドビによって設定されます。 アドビにご連絡ください。

**使用する場合**: メッセージがCampaign トランザクションテンプレート、Campaign固有のデータモデル、または既存のCampaign配信ワークフローに依存している場合は、Campaign v7/v8 アクションを使用します。

**前提条件**

* お使いの[!DNL Adobe Campaign] v7/v8 インスタンスはプロビジョニングされ、AdobeによってJourney Optimizerに接続されています。
* Campaign トランザクションメッセージと必要な権限にアクセスできます。

これを機能させるには、専用のアクションを設定する必要があります。 詳しくは、この[節](../action/acc-action.md)を参照してください。

エンドツーエンドのユースケースについては、この[節](../building-journeys/ajo-ac.md)を参照してください。

1. イベントから始めて、ジャーニーを設計します。 詳しくは、この[節](../building-journeys/journey.md)を参照してください。
1. パレットの「**アクション**」セクションで、Campaign アクションを選択してジャーニーに追加します。
1. **アクションパラメーター**&#x200B;には、メッセージペイロードで想定されるすべてのフィールドが表示されます。 これらの各フィールドを、イベントまたはデータソースのいずれかから使用するフィールドにマッピングする必要があります。 これはカスタムアクションと似ています。 詳しくは、この[節](../building-journeys/using-custom-actions.md)を参照してください。

>[!NOTE]
>
>* Campaign v7/v8 アクションは、同じジャーニー内のネイティブチャネルアクションと一緒に使用できます。 これは、Campaign Standardのアクションには適用されません。 [&#x200B; キャンペーンアクティビティガードレール &#x200B;](../start/guardrails.md#ac-g)を参照してください。
>* Campaign v7/v8 アクションは、「オーディエンスを読み取り」または「オーディエンスの選定」アクティビティでは使用できません。 ガードレール ページの「オーディエンスとオーディエンスの選定に関するガードレールを読む」を参照してください。

![[!DNL Adobe Campaign] v7/v8 アクションの設定と統合設定](assets/accintegration2.png)
