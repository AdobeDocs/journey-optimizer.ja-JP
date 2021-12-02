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
workflow-type: tm+mt
source-wordcount: '454'
ht-degree: 1%

---


# 送信者としてのレピュテーションの確立

最近別の電子メールサービスプロバイダー、IP アドレス、電子メールドメインまたはサブドメインに移動した場合は、送信者としてのレピュテーションを確立する必要があります。 そうしないと、配信がブロックされたり、受信者のメールボックスのスパムフォルダーに移動したりする可能性があります。

IP をウォームアップするには、配信数を徐々に増やすことができます。 参照 [使用例](../building-journeys/ramp-up-deliveries-uc.md).

## プロファイルキャップ条件のタイプ {#profile_cap}

その他の条件タイプについて詳しくは、 [セクション](../building-journeys/condition-activity.md).

この条件タイプを使用して、ジャーニーパスの最大プロファイル数を設定します。 この制限に達すると、入力するプロファイルは別のパスを取ります。

この条件タイプを使用して、配信の量を増やすことができます。 参照 [使用例](../building-journeys/ramp-up-deliveries-uc.md).

デフォルトのキャップは 1000 です。 1 ～ 20,000 の整数値を設定できます。

カウンターは、選択したジャーニーバージョンにのみ適用されます。 カウンターは 1 ヶ月後に 0 にリセットされます。 リセット後、入力プロファイルは、カウンタ制限に達するまで呼びパスを再び使用します。

ジャーニーキャンバス上で呼びパスの上に代替パスを移動した場合でも、呼びパスは常に代替パスよりも優先されます。

![](../assets/profile-cap-condition.png)

## 使用例：配信を強化

最近別の電子メールサービスプロバイダー、IP アドレス、電子メールドメインまたはサブドメインに移動した場合は、送信者としてのレピュテーションを確立する必要があります。 そうしないと、配信がブロックされたり、受信者のメールボックスのスパムフォルダーに移動したりする可能性があります。 IP ウォーミングを使用して E メールの評判を高める方法については、 [配信品質のベストプラクティスガイド](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/generic-resources/increase-reputation-with-ip-warming.html){target=&quot;_blank&quot;}。

IP をウォームアップするには、配信数を徐々に増やすことができます。 詳細を表示 [Journey Optimizerでの配信品質の最適化](../deliverability.md).

この使用例の目的は、E メール配信を強化するジャーニーを作成することです。 このジャーニーを設定するには、次の手順に従います。

1. ジャーニーの作成. [詳細を読む](../building-journeys/journey-gs.md)。

1. を追加します。 **[!UICONTROL 条件]** アクティビティをジャーニーに追加します。 [詳細を読む](../building-journeys/condition-activity.md)。

1. 内 **[!UICONTROL 条件]** アクティビティの設定で、配信の最大受信者数を設定します。

   1. 内 **[!UICONTROL 条件]** アクティビティの設定を行うには、 **[!UICONTROL タイプ]** ～に向かって **[!UICONTROL プロファイルキャップ]**. [詳細を読む](profile-cap.md#profile_cap)。

   1. を **[!UICONTROL 制限]** フィールドに、この配信の最大受信者数を入力します。

   ![](../assets/profile-cap-condition.png)

   この制限は、購読者の合計数まで徐々に増やすことができます。

1. を追加します。 **[!UICONTROL メッセージ]** 次の呼び出し経路に対する活動 **[!UICONTROL 条件]** アクティビティ。

   ![](../assets/ramp-up-deliveries-message.png)

   ジャーニーの実行時に、入力したプロファイルに対し、指定した最大数のプロファイルに対して、メッセージが送信されます。 この制限に達すると、入力するプロファイルは代替パスを取ります。

1. 選択したアクティビティでジャーニーを完了します。

IP がウォームアップされたら、この条件を削除できます。

