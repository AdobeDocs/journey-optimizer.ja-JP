---
solution: Journey Optimizer
product: journey optimizer
title: ディメンションを変更アクティビティの使用
description: ディメンションの変更アクティビティの使用方法を説明します
exl-id: 83e66f10-93dd-4759-840c-2c83abc42a28
version: Campaign Orchestration
source-git-commit: 07ec28f7d64296bdc2020a77f50c49fa92074a83
workflow-type: tm+mt
source-wordcount: '260'
ht-degree: 100%

---


# ディメンションを変更 {#change-dimension}

>[!CONTEXTUALHELP]
>id="ajo_orchestration_dimension_complement"
>title="補集合の生成"
>abstract="重複として除外された残りの母集団を使用して、追加のアウトバウンドトランジションを生成できます。 これを行うには、「**補集合を生成**」オプションの切替スイッチをオンにします。"

>[!CONTEXTUALHELP]
>id="ajo_orchestration_change_dimension"
>title="ディメンションを変更アクティビティ"
>abstract="このアクティビティを使用すると、オーディエンスの作成時にターゲティングディメンションを変更できます。 データテンプレートと入力ディメンションに応じて軸を移動します。 例えば、「契約」ディメンションから「クライアント」ディメンションに切り替えることができます。"

マーケターは、調整されたキャンペーン内で 1 つのデータエンティティから関連するデータエンティティに移行することで、オーディエンスのターゲティングを強化できます。これにより、ユーザープロファイルを超えて、購入、予約、その他のインタラクションなどの特定の行動に焦点を当てることができます。

これを実現するには、**[!UICONTROL ディメンションを変更]**&#x200B;アクティビティを使用します。調整されたキャンペーン中にターゲティングディメンションを調整できます。

<!--
>[!IMPORTANT]
>
>Please note that the **[!UICONTROL Change Dimension]** and **[!UICONTROL Change Data source]** activities should not be added in one row. If you need to use both activities consecutively, make sure you include an **[!UICONTROL Enrichement]** activity in between them. This ensures proper execution and prevents potential conflicts or errors.-->

## ディメンションを変更アクティビティの設定 {#configure}

**[!UICONTROL ディメンションを変更]**&#x200B;アクティビティを設定するには、次の手順に従います。

1. **[!UICONTROL ディメンションを変更]**&#x200B;アクティビティを調整されたキャンペーンに追加します。

   ![](../assets/orchestrated-change-dimension.png)

1. **[!UICONTROL 新しいターゲットディメンション]**&#x200B;を定義します。ディメンションの変更時に、すべてのレコードが保持されます。


## 例 {#example}

このユースケースは、過去 1 か月以内にウィッシュリストを作成したプロファイルへの SMS の送信に焦点を当てています。

**[!UICONTROL オーディエンスを作成]**&#x200B;アクティビティから開始し、**[!UICONTROL ウィッシュリスト]**&#x200B;ターゲティングディメンションを使用して関連するすべてのウィッシュリストを特定します。

次に、**[!UICONTROL ディメンションを変更]**&#x200B;アクティビティを追加して、ターゲティングディメンションを&#x200B;**[!UICONTROL ウィッシュリスト]**&#x200B;から&#x200B;**[!UICONTROL 受信者]に切り替えます**&#x200B;この手順により、調整されたキャンペーンがウィッシュリストにリンクされた正しいプロファイルをターゲットにすることが確保され、SMS を目的のプロファイルに送信できます。

![](../assets/orchestrated-change-dimension-example.png)
