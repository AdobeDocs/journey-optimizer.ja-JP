---
title: プロファイルキャップ
description: プロファイルキャップ
feature: Journeys
topic: Content Management
role: User
level: Intermediate
exl-id: 496c7666-a133-4aeb-be8e-c37b3b9bf5f9
hide: true
hidefromtoc: true
source-git-commit: b5ce2ea81d4091b4fa9c09e83573f9043c5e55a8
workflow-type: ht
source-wordcount: '454'
ht-degree: 100%

---


# 送信者としての評判を確立する

最近、別のメールサービスプロバイダー、IP アドレス、メールドメインまたはサブドメインに移動した場合は、送信者としての評判を確立する必要があります。そうしないと、配信がブロックされたり、受信者のメールボックスのスパムフォルダーに送られる可能性があります。

IP をウォームアップするために、配信数を徐々に増やすことができます。この[ユースケース](../building-journeys/ramp-up-deliveries-uc.md)を参照してください。

## プロファイルキャップの条件タイプ {#profile_cap}

その他の条件タイプについて詳しくは、[この節](../building-journeys/condition-activity.md)を参照してください。

この条件タイプを使用して、ジャーニーパスの最大プロファイル数を設定します。この制限に達すると、入力プロファイルは代替パスを使用します。

この条件タイプを使用すると、配信の量を増やすことができます。この[ユースケース](../building-journeys/ramp-up-deliveries-uc.md)を参照してください。

デフォルトのキャップは 1000 です。1～20,000 の整数値を設定できます。

カウンターは、選択したジャーニーバージョンにのみ適用されます。カウンターは 1 か月後に 0 にリセットされます。リセット後、入力プロファイルは、カウンターの上限に到達するまでもう一度呼びパスをたどります。

ジャーニーキャンバス上で呼びパスの上に代替パスを移動した場合でも、呼びパスは常に代替パスよりも優先されます。

![](../assets/profile-cap-condition.png)

## ユースケース：配信を増やす

最近、別のメールサービスプロバイダー、IP アドレス、メールドメインまたはサブドメインに移動した場合は、送信者としての評判を確立する必要があります。そうしないと、配信がブロックされたり、受信者のメールボックスのスパムフォルダーに送られる可能性があります。IP ウォーミングを使用してメールの評判を高める方法については、[配信品質のベストプラクティスガイド](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/generic-resources/increase-reputation-with-ip-warming.html?lang=ja){target=&quot;_blank&quot;}を参照してください。

IP をウォームアップするために、配信数を徐々に増やすことができます。詳しくは、[Journey Optimizer での配信品質の最適化](../deliverability.md)を参照してください。

この使用例の目的は、ジャーニーを作成してメール配信を増やすことです。このジャーニーを設定するには、次の手順に従います。

1. ジャーニーを作成します。[詳細情報](../building-journeys/journey-gs.md)

1. **[!UICONTROL 条件]**&#x200B;アクティビティをジャーニーに追加します。[詳細情報](../building-journeys/condition-activity.md)

1. **[!UICONTROL 条件]**&#x200B;アクティビティの設定で、配信の最大受信者数を設定します。

   1. **[!UICONTROL 条件]**&#x200B;アクティビティの設定で、「**[!UICONTROL タイプ]**」フィールドを「**[!UICONTROL プロファイルキャップ]**」に設定します。[詳細情報](profile-cap.md#profile_cap)

   1. 「**[!UICONTROL 制限]**」フィールドをこの配信の最大受信者数に設定します。

   ![](../assets/profile-cap-condition.png)

   この制限は、購読者の合計数まで徐々に増やすことができます。

1. **[!UICONTROL メッセージ]**&#x200B;アクティビティを&#x200B;**[!UICONTROL 条件]**&#x200B;アクティビティの後の呼びパスに追加します。

   ![](../assets/ramp-up-deliveries-message.png)

   ジャーニーが実行されると、指定したプロファイルの最大数まで、メッセージが入力プロファイルに送信されます。この制限に達すると、入力したプロファイルは代替パスを使用します。

1. 選択したアクティビティでジャーニーを完了します。

IP がウォームアップされたら、この条件を削除できます。

