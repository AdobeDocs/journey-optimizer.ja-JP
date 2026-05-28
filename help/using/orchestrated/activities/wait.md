---
solution: Journey Optimizer
product: journey optimizer
title: 調整されたキャンペーンでの待機アクティビティの使用
description: 調整されたキャンペーンでの待機アクティビティの使用方法について説明します
exl-id: 11ef095b-77ec-4e2e-ab4d-49a248354f08
version: Campaign Orchestration
TQID: https://experienceleague.adobe.com/-AI0PuvH2o43jG3d6cpP9-IwD6LxL37nzFv19R-wkcQ
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2:
  - id: b3538224-471e-4c63-a444-9b19d89ae29c
  - id: b423a773-0a58-4a77-b65d-3dd4ae6ef841
subfeature_v2:
  - id: b5e335a9-0e5f-4dda-8845-c4ac5dca2be4
source-git-commit: 0ee10a0689d38c22b1180b197796b08a10c286cf
workflow-type: tm+mt
source-wordcount: 233
ht-degree: 75%

---

# 待機 {#wait}

>[!CONTEXTUALHELP]
>id="ajo_orchestration_wait"
>title="待機アクティビティ"
>abstract="**待機**&#x200B;アクティビティは、アクティビティ間のトランジションを遅延させるために使用します。"

**[!UICONTROL 待機]**&#x200B;アクティビティは、調整されたキャンペーン内の 2 つのアクティビティ間に遅延を導入するのに使用される&#x200B;**[!UICONTROL フロー制御]**&#x200B;コンポーネントです。 これにより、フォローアップアクティビティの時間を短縮し、ユーザーエンゲージメントとの関連性を高めることができます。

例えば、メール配信後に数日待機して、開封数とクリック数を追跡してから、フォローアップメッセージを送信できます。

## 設定{#wait-configuration}

>[!IMPORTANT]
>
>一時テーブルのデータは&#x200B;**5日**&#x200B;以降は保持されません。 **[!UICONTROL 期間]**&#x200B;または&#x200B;**[!UICONTROL 固定時間]**&#x200B;待機を使用する場合は、中間データが引き続き利用できるように、次のアクティビティがその制限内で完了するまで経過時間を確保してください。

**[!UICONTROL 待機]**&#x200B;アクティビティを設定するには、次の手順に従います。

1. **[!UICONTROL 待機]**&#x200B;アクティビティを調整されたキャンペーンに追加します。

1. ニーズに最適な待機タイプを選択します。

   * **[!UICONTROL 期間]**：次のアクティビティに進む前に、秒、分、時間、日で遅延を指定します。

   * **[!UICONTROL 固定時間]**：次のアクティビティが開始される特定の日時を設定します。

   ![](../assets/wait_activity.png)

## 例{#wait-example}

次に、**[!UICONTROL 待機]**&#x200B;アクティビティの一般的なユースケースを示します。  誕生日を祝うプロファイルには、プロモーションコードが記載されたメールが送信されます。 2日後、誕生日プロモーションコードの有効期限が近づいたことを知らせるリマインダーとして、SMSが同じグループに送信されます。

![](../assets/wait-example.png)
