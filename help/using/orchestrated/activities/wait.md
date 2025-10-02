---
solution: Journey Optimizer
product: journey optimizer
title: 調整されたキャンペーンでの待機アクティビティの使用
description: 調整されたキャンペーンでの待機アクティビティの使用方法について説明します
exl-id: 11ef095b-77ec-4e2e-ab4d-49a248354f08
version: Campaign Orchestration
source-git-commit: 07ec28f7d64296bdc2020a77f50c49fa92074a83
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 100%

---


# 待機 {#wait}

>[!CONTEXTUALHELP]
>id="ajo_orchestration_wait"
>title="待機アクティビティ"
>abstract="**待機**&#x200B;アクティビティは、アクティビティ間のトランジションを遅延させるために使用します。"

**[!UICONTROL 待機]**&#x200B;アクティビティは、調整されたキャンペーン内の 2 つのアクティビティ間に遅延を導入するのに使用される&#x200B;**[!UICONTROL フロー制御]**&#x200B;コンポーネントです。これにより、フォローアップアクティビティの時間を短縮し、ユーザーエンゲージメントとの関連性を高めることができます。

例えば、メール配信後に数日待機して、開封数とクリック数を追跡してから、フォローアップメッセージを送信できます。

## 設定{#wait-configuration}

**[!UICONTROL 待機]**&#x200B;アクティビティを設定するには、次の手順に従います。

1. **[!UICONTROL 待機]**&#x200B;アクティビティを調整されたキャンペーンに追加します。

1. ニーズに最適な待機タイプを選択します。

   * **[!UICONTROL 期間]**：次のアクティビティに進む前に、秒、分、時間、日で遅延を指定します。

   * **[!UICONTROL 固定時間]**：次のアクティビティが開始される特定の日時を設定します。

   ![](../assets/wait_activity.png)

## 例{#wait-example}

次に、**[!UICONTROL 待機]**&#x200B;アクティビティの一般的なユースケースを示します。誕生日を祝うプロファイルには、プロモーションコードが記載されたメールが送信されます。29 日後、誕生日のプロモーションコードの有効期限が近づいていることを示すリマインダーとして、SMS が同じグループに送信されます。

![](../assets/wait-example.png)
