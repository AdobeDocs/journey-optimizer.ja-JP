---
solution: Journey Optimizer
product: journey optimizer
title: ディメンションを変更アクティビティの使用
description: ディメンションの変更アクティビティの使用方法を説明します
hide: true
hidefromtoc: true
exl-id: 83e66f10-93dd-4759-840c-2c83abc42a28
source-git-commit: 3d380d2d02eb7043aebcffd00bb2092e7341b0d5
workflow-type: tm+mt
source-wordcount: '340'
ht-degree: 67%

---

# ディメンションを変更 {#change-dimension}

>[!CONTEXTUALHELP]
>id="ajo_orchestration_dimension_complement"
>title="補集合を生成"
>abstract="重複として除外された残りの母集団を使用して、追加のアウトバウンドトランジションを生成できます。 これを行うには、「**補集合を生成**」オプションの切替スイッチをオンにします。"

>[!CONTEXTUALHELP]
>id="ajo_orchestration_change_dimension"
>title="ディメンションを変更アクティビティ"
>abstract="このアクティビティを使用すると、オーディエンスの作成時にターゲティングディメンションを変更できます。 データテンプレートと入力ディメンションに応じて軸を移動します。 例えば、「契約」ディメンションから「クライアント」ディメンションに切り替えることができます。"

**ディメンションを変更**&#x200B;アクティビティは、**ターゲティング**&#x200B;アクティビティです。This activity allows you to change the targeting dimension as you are building your orchestrated campaign. データテンプレートと入力ディメンションに応じて軸を移動します。

For example, you can switch an orchestrated campaign&#39;s targeting dimension from &quot;Recipients&quot; to &quot;Subscribers application&quot; in order to send push notifications to the targeted recipients.

>[!IMPORTANT]
>
>「**[!UICONTROL ディメンションを変更]**」アクティビティと「**[!UICONTROL データソースを変更]**」アクティビティを 1 つの行に追加しないでください。両方のアクティビティを連続して使用する必要がある場合は、これらの間に「**[!UICONTROL エンリッチメント]**」アクティビティを含める必要があります。これにより適切な実行が保証され、潜在的な競合やエラーが回避されます。

## ディメンションを変更アクティビティの設定 {#configure}

**ディメンションを変更**&#x200B;アクティビティを設定するには、次の手順に従います。

1. Add a **Change dimension** activity to your orchestrated campaign.

   ![](../assets/workflow-change-dimension.png)

1. **新しいターゲットディメンション**&#x200B;を定義します。ディメンションの変更時に、すべてのレコードが保持されます。その他のオプションはまだ利用できません。

1. Execute the orchestrated campaign to view the result. Compare the data in the tables before and after the change dimension activity, and compare the structure of the orchestrated campaign tables.

## 例 {#example}

この例では、購入を行ったすべてのプロファイルに SMS 配信を送信します。これを行うには、まず、カスタムの「購入」ターゲティングディメンションにリンクされた&#x200B;**[!UICONTROL オーディエンスを作成]**&#x200B;アクティビティを使用して、発生したすべての購入をターゲットにします。

We then use a **[!UICONTROL Change dimension]** activity to switch the orchestrated campaign targeting dimension to &quot;Recipients&quot;. これにより、クエリに一致する受信者をターゲットにすることができます。

![](../assets/workflow-change-dimension-example.png)
