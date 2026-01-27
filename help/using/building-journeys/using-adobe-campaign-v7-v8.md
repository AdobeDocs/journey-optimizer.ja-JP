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
source-git-commit: a068d3a4005d8f2247755f56ffb70665dc4c957f
workflow-type: tm+mt
source-wordcount: '310'
ht-degree: 66%

---

# Adobe Campaign v7／v8 のアクション {#using_campaign_v7-v8}

>[!CONTEXTUALHELP]
>id="ajo_journey_action_custom_acc"
>title="カスタムアクション"
>abstract="統合は、Adobe Campaign v7 または v8 のユーザーが使用できます。Adobe Campaign のトランザクションメッセージ機能を使用して、メール、プッシュ通知、SMS などを送信できるようになります。"

統合は、Adobe Campaign v7 または v8 のユーザーが使用できます。Adobe Campaign のトランザクションメッセージ機能を使用して、メール、プッシュ通知、SMS などを送信できるようになります。

Journey Optimizer と Campaign インスタンスとの接続は、プロビジョニング時にアドビによって設定されます。アドビにご連絡ください。

**用途**：メッセージで Campaign トランザクションテンプレート、Campaign 固有のデータモデル、既存の Campaign 配信ワークフローのいずれかを使用する場合は、Campaign v7/v8 アクションを使用します。

**前提条件**

* Adobe Campaign v7/v8 インスタンスは、Adobeによってプロビジョニングされ、Journey Optimizerに接続されます。
* Campaign トランザクションメッセージへのアクセスと必要な権限があります。

これを機能させるには、専用のアクションを設定する必要があります。この[節](../action/acc-action.md)を参照してください。

エンドツーエンドのユースケースについては、この[節](../building-journeys/ajo-ac.md)を参照してください。

1. イベントから始めて、ジャーニーを設計します。この[節](../building-journeys/journey.md)を参照してください。
1. パレットの「**アクション**」セクションで、Campaign アクションを選択してジャーニーに追加します。
1. **アクションパラメーター**&#x200B;には、メッセージペイロードで想定されるすべてのフィールドが表示されます。これらの各フィールドを、イベントまたはデータソースのいずれかから使用するフィールドにマッピングする必要があります。これはカスタムアクションと似ています。この[節](../building-journeys/using-custom-actions.md)を参照してください。

>[!NOTE]
>
>* Campaign v7/v8 アクションは、同じジャーニーで、ネイティブチャネルアクションと同時に使用できます。 これは、Campaign Standardのアクションには適用されません。 [&#x200B; キャンペーンアクティビティガードレール &#x200B;](../start/guardrails.md#ac-g) を参照してください。
>* Campaign v7/v8 アクションは、オーディエンスを読み取りアクティビティやオーディエンスの選定アクティビティでは使用できません。 ガードレールのページのオーディエンスの読み取りとオーディエンスの選定ガードレールを参照してください。

![Adobe Campaign v7／v8 アクション設定と統合設定](assets/accintegration2.png)
