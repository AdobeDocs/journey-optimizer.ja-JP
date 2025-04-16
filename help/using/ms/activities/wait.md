---
solution: Journey Optimizer
product: journey optimizer
title: 調整されたキャンペーンでの待機アクティビティの使用
description: 調整されたキャンペーンで待機アクティビティを使用する方法を学ぶ
hide: true
hidefromtoc: true
exl-id: 11ef095b-77ec-4e2e-ab4d-49a248354f08
source-git-commit: 3d380d2d02eb7043aebcffd00bb2092e7341b0d5
workflow-type: tm+mt
source-wordcount: '168'
ht-degree: 85%

---

# 待機 {#wait}

>[!CONTEXTUALHELP]
>id="ajo_orchestration_wait"
>title="待機アクティビティ"
>abstract="**待機**&#x200B;アクティビティは、アクティビティ間のトランジションを遅延させるために使用します。"

**待機**&#x200B;アクティビティは、**フロー制御**&#x200B;アクティビティです。これは、実行する 2 つのアクティビティ間に一定の時間間隔を設定するために使用します。例えば、メール配信アクティビティを実行したあと数日間待機し、この期間中に発生した開封数とクリック数を分析してから、フォローアップ操作（リマインダーメール、オーディエンスの作成など）を実行します。

## 設定{#wait-configuration}

**待機**&#x200B;アクティビティを設定するには、次の手順に従います。

1. **待機** アクティビティを、調整したキャンペーンに追加します。

1. インバウンドトランジションとアウトバウンドトランジションの間の待機&#x200B;**期間**&#x200B;を指定します。

1. 「**期間**」フィールドで、秒、分、時間、日などの時間単位を選択します。

## 例{#wait-example}

以下に、**待機**&#x200B;アクティビティの一般的なユースケースを示します。イベントへの招待メールを送信します。送信後 24 時間が経過すると、同じ母集団に SMS 配信が送信されます。

![](../assets/workflow-wait-example.png)
