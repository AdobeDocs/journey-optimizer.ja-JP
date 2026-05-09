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
source-git-commit: 384f4e4b4c3acd9f1f1d73d4b140845870b31289
workflow-type: tm+mt
source-wordcount: '299'
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
>* Campaign v7/v8 アクションは、同じジャーニー内のネイティブチャネルアクションと一緒に使用できます。 これは、Campaign Standardのアクションには適用されません。 [ キャンペーンアクティビティガードレール ](../start/guardrails.md#ac-g)を参照してください。
>* Campaign v7/v8 アクションは、「オーディエンスを読み取り」または「オーディエンスの選定」アクティビティでは使用できません。 ガードレール ページの「オーディエンスとオーディエンスの選定に関するガードレールを読む」を参照してください。

![[!DNL Adobe Campaign] v7/v8 アクションの設定と統合設定](assets/accintegration2.png)
