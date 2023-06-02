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
source-wordcount: '0'
ht-degree: 0%

---

# オプトアウトの管理 {#consent}

ブランドからの連絡を登録解除する機能を受信者に提供することは、法的要件であり、この選択を確実に行うためにも必要です。適用される法律について詳しくは、[Experience Platform ドキュメント](https://experienceleague.adobe.com/docs/experience-platform/privacy/regulations/overview.html?lang=ja#regulations){target="_blank"}を参照してください。

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

顧客は、パーソナライズされたコンテンツの表示をオプトアウトすることもできます。あるプロファイルがパーソナライゼーションからオプトアウトされたら、そのデータがパーソナライゼーションに使用されていないことを確認し、パーソナライズされたコンテンツをフォールバックバリアントに置き換える必要があります。

### 意思決定管理の場合

オファーを活用する場合、パーソナライゼーション環境設定は、[Decisioning](../offers/api-reference/offer-delivery-api/decisioning-api.md) API リクエストまたは [Edge Decisioning](../offers/api-reference/offer-delivery-api/edge-decisioning-api.md) API リクエストから使用される[決定範囲](../offers/offer-activities/create-offer-activities.md#add-decision-scopes)に自動的に実装されません。この場合、パーソナライゼーションの同意を手動で実施する必要があります。これを行うには、以下の手順に従います。

>[!NOTE]
>
>[!DNL Journey Optimizer] で作成したチャネルで使用される決定範囲は、属するジャーニーまたはキャンペーンからのこの要件を満たします。



1. *「パーソナライゼーションに対する同意 = True」*&#x200B;などのプロファイル属性を使用して [Adobe Experience Platform セグメント](../segment/about-segments.md)を作成し、パーソナライゼーションに同意したユーザーをターゲットにします。

1. [決定](../offers/offer-activities/create-offer-activities.md)を作成する際は、パーソナライズされたオファーを含む評価条件コレクションごとに、決定範囲を追加し、このセグメントに基づいて実施要件の制約を定義します。

1. パーソナライズされたコンテンツを含まない[フォールバックオファー](../offers/offer-library/creating-fallback-offers.md)を作成します。

1. パーソナライズされていないフォールバックオファーを決定に[割り当てます](../offers/offer-activities/create-offer-activities.md#add-fallback)。

1. [決定のレビューと保存](../offers/offer-activities/create-offer-activities.md#review)を行います。

ユーザーが以下の条件を満たしている場合：

* パーソナライゼーションに同意した場合、決定範囲によってそのプロファイルに最適なオファーが決定されます。

* パーソナライゼーションに同意していない場合、対応するプロファイルは評価条件に含まれるオファーの対象外となるので、パーソナライズされていないフォールバックオファーを受信します。

>[!NOTE]
>
>[データモデリング](../offers/ranking/ai-models.md)でプロファイルデータを使用するための同意は、[!DNL Journey Optimizer] ではまだサポートされていません。

