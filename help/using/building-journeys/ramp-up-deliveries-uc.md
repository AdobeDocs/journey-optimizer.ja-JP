---
solution: Journey Optimizer
product: journey optimizer
title: 配信の増強
description: 配信を増強する方法を説明します
feature: Journeys, Use Cases, IP Warmup Plans
topic: Content Management
role: User, Developer
level: Intermediate, Experienced
hide: true
keywords: 配信品質, ジャーニー, 使用例, メール, 評価
exl-id: 83d1b68d-011a-4109-b5f0-6ca1ade2944d
version: Journey Orchestration
TQID: https://experienceleague.adobe.com/en0jMw69ddHSQrIH05-9FfGuDwNKb36f5Lp3fLp2oAk
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2:
  - id: b3538224-471e-4c63-a444-9b19d89ae29c
  - id: d998adac-2f81-400b-a669-d07bb196e4eb
subfeature_v2:
  - id: d8353d85-5da7-453d-bd68-40ad33fa0ab7
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
source-git-commit: 0ee10a0689d38c22b1180b197796b08a10c286cf
workflow-type: tm+mt
source-wordcount: 300
ht-degree: 92%

---

# ユースケース：配信を増やす{#use-case-ramp-up-your-deliveries}

最近、別のメールサービスプロバイダー、IP アドレス、メールドメインまたはサブドメインに移動した場合は、送信者としての評判を確立する必要があります。 そうしないと、配信がブロックされたり、受信者のメールボックスのスパムフォルダーに送られる可能性があります。 IP ウォーミングを使用してメールの評判を高める方法について詳しくは、[配信品質のベストプラクティスガイド](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/generic-resources/increase-reputation-with-ip-warming.html?lang=ja){target="_blank"}を参照してください。

IP をウォームアップするために、配信数を徐々に増やすことができます。 詳しくは、[Journey Optimizer での配信品質の最適化](../reports/deliverability.md)を参照してください。

この使用例の目的は、ジャーニーを作成してメール配信を増やすことです。 このジャーニーを設定するには、次の手順に従います。

1. ジャーニーを作成します。 [詳細情報](journey-gs.md)。

1. ジャーニーに&#x200B;**[!UICONTROL Optimize]** アクティビティを追加します。 [詳細情報](optimize.md)。

1. **[!UICONTROL 条件]**&#x200B;アクティビティの設定で、配信の最大受信者数を設定します。

   1. **[!UICONTROL 最適化]** アクティビティ設定で、**[!UICONTROL 条件]** メソッドを選択し、**[!UICONTROL タイプ]** フィールドを&#x200B;**[!UICONTROL プロファイル キャップ]**&#x200B;に設定します。 [詳細情報](conditions.md#profile_cap)。

   1. 「**[!UICONTROL 制限]**」フィールドをこの配信の最大受信者数に設定します。

   ![配信ボリュームを制御するプロファイルキャップ条件の設定](assets/profile-cap-condition.png)

   この制限は、購読者の合計数まで徐々に増やすことができます。

1. **[!UICONTROL メール]**&#x200B;アクションアクティビティを&#x200B;**[!UICONTROL 条件]**&#x200B;アクティビティの後の呼びパスに追加します。

   ![増強した配信ジャーニーでのメールメッセージ設定](assets/ramp-up-deliveries-message.png)

   ジャーニーが実行されると、指定したプロファイルの最大数まで、メッセージが入力プロファイルに送信されます。 この制限に達すると、入力したプロファイルは代替パスを使用します。

1. 選択したアクティビティでジャーニーを完了します。

IP がウォームアップされたら、この条件を削除できます。
