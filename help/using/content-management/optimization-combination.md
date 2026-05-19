---
solution: Journey Optimizer
product: journey optimizer
title: ターゲティングと実験を組み合わせ
description: 単一のジャーニーやキャンペーン内でターゲティングと実験を組み合わせて、高度な最適化戦略を構築する方法を説明します。
role: User
level: Intermediate
keywords: 最適化，ターゲティング，実験，組み合わせ，高度な
exl-id: dafcb4d3-e33c-40c5-a5c6-972822a23cc0
TQID: https://experienceleague.adobe.com/klXmy7KQLcIHm-T6BMS1RaMKrwzdCfzvK3KK6fUs7KU
product_v2: id: cb954087-f4fc-4456-afb9-e939cabcdc79
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2: id: bcc5edb5-84c3-4940-9f84-ed88b6c16274id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
source-git-commit: f9b8e1590f14cdcd00432295c653769f753b9b40
workflow-type: tm+mt
source-wordcount: 306
ht-degree: 92%

---

# ターゲティングと実験を組み合わせ {#combination}

Journey Optimizer では、単一のジャーニーまたはキャンペーン内でターゲティングと実験を組み合わせて、より高度な戦略を作成することもできます。

実際、ターゲティングを使用して複数のバリエーションを作成し、各バリアントに対して、実験を使用して各コンテンツをさらに最適化できます。 これにより、実験が各ターゲティングルールに固有となり、複数のバリアントにまたがらないようにします。

例えば、米国のお客様に対しては「50％オフのプロモーション」と「50 ドルのギフトカード」を比較してテストし、ヨーロッパのお客様に対しては「50 ユーロを超える注文で送料無料」と「次回購入時に 20％オフ」などの異なるテストを実行できます。

ジャーニーまたはキャンペーンでターゲティングと実験の両方を組み合わせるには、次の手順に従います。

1. 複数のターゲティングルールを定義するジャーニーまたはキャンペーンを作成します。 [詳細情報](optimization-targeting.md)

   ![](../campaigns/assets/msg-optimization-create-targeting.png){width=85%}

1. 最初のターゲティングルールの実験を作成します。

1. 必要に応じて、コンテンツ実験を設計および設定します。 [詳細情報](../content-management/content-experiment.md)

   ![](../campaigns/assets/msg-optimization-targeting-with-experiment.png){width=85%}

   実験を定義すると、最初のターゲティングルールにのみ適用されます。

1. 「**[!UICONTROL アクション]**」タブに戻り、「**[!UICONTROL コンテンツを編集]**」を選択します。

1. 最初のターゲティングルールで定義したグループに対して、実験の各バリアントに特定のコンテンツを定義できます。

   ジャーニーまたはキャンペーンに複数のインバウンドアクションを追加した場合、各アクションに同じターゲティングと実験の組み合わせが適用されます。 ただし、各アクションのバリアントごとに特定のコンテンツを定義する必要があります。

   ![](../campaigns/assets/msg-optimization-targeting-experiment-design.png){width=85%}

1. 他のターゲティングルールについても同様に進め、各バリアントに対応するコンテンツを設計します。

1. 変更を保存し、ジャーニーまたはキャンペーンを[アクティブ化](../campaigns/review-activate-campaign.md)します。

ジャーニー／キャンペーンがライブになると、各ターゲットグループのユーザーには、所属するグループに定義した様々なコンテンツのバリエーションがランダムに割り当てられます。

<!--
## Reporting on Message optimization

E.g. explaining how a marketer can look at the report to determine which treatment (e.g. which message content) is performing the best for the targeting audience
-->
