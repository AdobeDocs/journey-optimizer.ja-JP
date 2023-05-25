---
solution: Journey Optimizer
product: journey optimizer
title: オプトアウトの管理
description: オプトアウトとプライバシーを管理する方法について説明します。
feature: Journeys
topic: Content Management
role: User
level: Intermediate
exl-id: c5bae757-a109-45f8-bf8d-182044a73cca
source-git-commit: 8b459f71852d031dc650b77725bdc693325cdb1d
workflow-type: tm+mt
source-wordcount: '478'
ht-degree: 45%

---

# オプトアウトの管理 {#consent}

受信者に対して、ブランドからの通信の受信を購読解除する機能を提供することは、法的要件であり、この選択を確実におこなうためにも必要です。 適用される法律について詳しくは、[Experience Platform ドキュメント](https://experienceleague.adobe.com/docs/experience-platform/privacy/regulations/overview.html?lang=ja#regulations){target="_blank"}を参照してください。

**なぜそれが重要なのでしょうか？**

* これらの規制に準拠できないと、ブランドに法規制上のリスクが生じます。
* この機能を使用すると、未承諾の通信を受信者に送信して、メッセージがスパムと見なされたり、ブランドの評判が損なわれたりする危険性を避けることができます。

## ジャーニーとキャンペーンでの購読解除の管理 {#opt-out-ajo}

ジャーニーやキャンペーンからメッセージを送信する場合は、顧客が今後の通信を登録解除できるようにする必要があります。登録解除すると、プロファイルは、今後のマーケティングメッセージのオーディエンスから自動的に削除されます。

**[!DNL Journey Optimizer]** には、メールと SMS メッセージでオプトアウトを管理する方法が用意されていますが、プッシュ通知では、受信者が自分のデバイスを介して登録解除できるので、顧客側でのアクションは不要です。例えば、アプリのダウンロード時や使用時に、通知の停止を選択できます。同様に、モバイルオペレーティングシステムから通知設定を変更することもできます。

Journey Optimizer のメールと SMS メッセージでオプトアウトを管理する方法について、以下の節で説明します。

<table style="table-layout:fixed"><tr style="border: 0;">
<td>
<a href="../email/email-opt-out.md">
<img alt="リード" src="../assets/do-not-localize/privacy-email-optout.jpeg" width="50%">
</a>
<div><a href="../email/email-opt-out.md"><strong>メールオプトアウトの管理</strong>
</div>
<p>
</td>
<td>
<a href="../sms/sms-opt-out.md">
<img alt="低頻度" src="../assets/do-not-localize/privacy-sms-opt-out.jpeg" width="50%">
</a>
<div>
<a href="../sms/sms-opt-out.md"><strong>SMS オプトアウトの管理</strong></a>
</div>
<p></td>
</tr></table>

>[!NOTE]
>
>[!DNL Journey Optimizer] では、同意は Experience Platform [同意スキーマ](https://experienceleague.adobe.com/docs/experience-platform/xdm/field-groups/profile/consents.html?lang=ja){target="_blank"}. By default, the value for the consent field is empty and treated as consent to receive your communications. You can modify this default value while onboarding to one of the possible values listed [here](https://experienceleague.adobe.com/docs/experience-platform/xdm/data-types/consents.html?lang=ja#choice-values){target="_blank"}で処理されます。

## パーソナライゼーションの同意の実装 {#opt-out-personalization}

顧客は、パーソナライズされたコンテンツの表示をオプトアウトすることもできます。 プロファイルがパーソナライゼーションからオプトアウトしたら、そのデータがパーソナライゼーションに使用されないようにする必要があります。パーソナライズされたコンテンツをフォールバックバリアントで置き換える必要があります。

### 決定管理

オファーを活用する場合、パーソナライゼーション環境設定は [決定範囲](../offers/offer-activities/create-offer-activities.md#add-decision-scopes) から使用 [判定](../offers/api-reference/offer-delivery-api/decisioning-api.md) API リクエストまたは [エッジ判定](../offers/api-reference/offer-delivery-api/edge-decisioning-api.md) API リクエスト。 その場合は、パーソナライゼーションの同意を手動で実施する必要があります。 これを行うには、以下の手順に従います。

>[!NOTE]
>
>で使用される決定範囲 [!DNL Journey Optimizer] オーサリングされたチャネルは、所属するジャーニーまたはキャンペーンからこの要件を満たします。



1. の作成 [Adobe Experience Platformセグメント](../segment/about-segments.md) 次のようなプロファイル属性を使用する。 *&quot;パーソナライゼーションに対する同意= True&quot;* パーソナライゼーションに同意したユーザーをターゲットにする

1. を作成する際に [決定](../offers/offer-activities/create-offer-activities.md)、決定範囲を追加し、パーソナライズされたオファーを含む各評価条件コレクションに対して、このセグメントに基づいて実施要件の制約を定義します。

1. の作成 [フォールバックオファー](../offers/offer-library/creating-fallback-offers.md) パーソナライズされたコンテンツを含まない

1. [割り当て](../offers/offer-activities/create-offer-activities.md#add-fallback) 決定に対する、パーソナライズされていないフォールバックオファー。

1. [決定のレビューと保存.](../offers/offer-activities/create-offer-activities.md#review)

ユーザーが以下の条件を満たしている場合：

* パーソナライゼーションに同意した場合、決定範囲は、そのプロファイルに最適なオファーを決定します。

* パーソナライゼーションに同意しない場合、対応するプロファイルは評価条件に含まれるオファーの対象にならないので、パーソナライズされていないフォールバックオファーを受け取ります。

>[!NOTE]
>
>プロファイルデータをで使用することに対する同意 [データモデリング](../offers/ranking/ai-models.md) 次ではまだサポートされていません： [!DNL Journey Optimizer].

