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
source-git-commit: b5d14f7b40933f110ff666db858e976e5de711db
workflow-type: tm+mt
source-wordcount: 761
ht-degree: 24%

---

# [!DNL Adobe Campaign] v7/v8 のアクション {#using_campaign_v7-v8}

>[!BEGINSHADEBOX]

**このページ：** Adobe Campaign v7とv8の統合を使用して、Campaignのトランザクションメッセージを通じて、ジャーニーから電子メール、プッシュ通知、SMSを送信する方法を説明します。

>[!ENDSHADEBOX]

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

+++ AI ナレッジリファレンス

このセクションには、このトピックに関連する解釈、検索、質問への回答をサポートすることを目的とした構造化された知識が含まれています。

理解を深めるには、この情報をこのページのドキュメントと組み合わせる必要があります。 どちらのソースも単独で使用することを意図していません。このページでは、機能について説明しますが、この節では、用語、意図、適用可能性、および制約の曖昧さを解消するのに役立つ追加のコンテキストを提供します。

* **TL;DR:**&#x200B;このページでは、Adobe Campaign v7/v8をJourney Optimizer ジャーニーのアクションとして使用して、Campaign トランザクションメッセージを介して電子メール、プッシュ通知、およびSMSを送信する方法について説明します。

**インテント：**

* トランザクションメッセージを送信するCampaign v7/v8 アクションをジャーニーに追加する
* ジャーニーイベントまたはデータソースフィールドをCampaign メッセージペイロードパラメーターにマッピングする
* Campaign v7/v8 アクションを、Journey Optimizerのネイティブチャネルアクションと同じジャーニー内で組み合わせる
* Campaign v7/v8統合に必要な専用アクションを設定します

**用語集：**

* **Campaign トランザクションメッセージ**: Adobe Campaign v7/v8は、Journey Optimizer *（製品固有）と統合された専用アクションを介してトリガーメッセージ（電子メール、SMS、プッシュ）を送信する機能です*
* **アクションパラメーター**: ジャーニーアクティビティペインのフィールドで、ジャーニーデータを想定されるCampaign メッセージペイロード *（製品固有）*&#x200B;にマッピングします

**ガードレール：**

* Journey OptimizerとCampaign インスタンスの間の接続は、プロビジョニング時にAdobeによって設定されます。Adobeに連絡して有効にしてください。
* Campaign v7/v8 アクションをジャーニーパレットで使用するには、専用アクションを設定する必要があります。
* Campaign v7/v8 アクションは、「オーディエンスを読み取り」または「オーディエンスの選定」アクティビティでは使用できません。
* Campaign トランザクションメッセージへのアクセスと、Campaignで必要な権限は前提条件です。

**用語：**

* 正式名称：Adobe Campaign v7/v8 – 略語：ACC – 変種：Campaign v7、Campaign v8、Campaign Classic
* 混同しないでください。「Campaign v7/v8 アクション」（ネイティブアクションと一緒に使用できます）≠「Campaign Standard アクション」（同じジャーニー内のネイティブアクションと組み合わせることはできません）

**FAQ:**

* **Q: Journey OptimizerとCampaign v7/v8の間の接続を設定するのは誰ですか？** — Adobeは、プロビジョニング時に接続を設定します。設定するには、Adobeに連絡する必要があります。
* **Q: Campaign v7/v8 アクションを、同じジャーニー内のネイティブ Journey Optimizer チャネルアクションと組み合わせることはできますか？**  – はい、Campaign v7/v8 アクションは、ネイティブチャネルアクションと一緒に使用できます。これは、Campaign Standard アクションの場合は異なります。
* **Q: Campaign v7/v8 アクションは、オーディエンスの読み取りまたはオーディエンスの選定アクティビティと共に使用できますか？**  – いいえ、Campaign v7/v8 アクションは、オーディエンスの読み取りまたはオーディエンスの選定アクティビティでは使用できません。
* **Q: ジャーニーデータをCampaign メッセージペイロードにマッピングするにはどうすればよいですか？** — アクションパラメーターペインで、カスタムアクションと同じように、期待される各ペイロードフィールドをジャーニーイベントまたはデータソースの対応するフィールドにマッピングします。

+++
