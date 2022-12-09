---
solution: Journey Optimizer
product: journey optimizer
title: 購読リストの作成
description: このような場合は、旅オプティマイザーで購読リストを設定する方法について説明します。
feature: Landing Pages
topic: Content Management
role: User
level: Beginner
exl-id: 5e5419a0-5121-4aa7-a975-b1f08e2918c9
source-git-commit: 63c52f04da9fd1a5fafc36ffb5079380229f885e
workflow-type: tm+mt
source-wordcount: '403'
ht-degree: 0%

---

# 購読リスト {#create-subscription-list}

## 購読リストについて {#subscription-list-definition}

>[!CONTEXTUALHELP]
>id="ajo_subscription_list"
>title="購読リストの設定"
>abstract="購読リストを作成して、特定のテーマやイベントに関する通信を受信することをオプトインするプロファイルを収集します。 "
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/landing-pages/subscription-list.html#define-subscription-list" text="購読リストの作成"

購読サービスとは、特定の題名、イベント、利息などについてのコミュニケーションを受信することをオプトインにしている顧客に提供されるマーケティング商品とサービスを意味します。 、継続的に実行されます。 で [!DNL Journey Optimizer] は、これらのオプトインユーザーは、購読リストにまとめられています。

購読サービスは、次のようなものです。

* ニュースレター (例: 「series 実行中」)
* イベント (例: 「サミット2021」)
* ウェビナー: 「暗号化について詳しくは、次のように説明します。
* 特定の製品/スポーツ/サービスなどに関心がある場合、例えば「次の12か月に住宅を購入することに関心がある」のようになります。
* 通知を受け取る方法の環境設定。例えば、「電子メールに新しい楽曲通知を受け取る」を指定します。

プロファイルは、ランディングページ ](create-lp.md) を [ 使用して購読リストに追加できます。この節 ](lp-use-cases.md#subscription-to-a-service) では、この例に [ ついて説明します。

## 購読リストの作成 {#define-subscription-list}

購読リストを作成するには、次の手順に従います。

1. 購読リストにアクセスするには、「> **[!UICONTROL Subscription list]** 」を選択 **[!UICONTROL Customer]** します。

   ![](assets/lp_subscription-lists.png)

1. **[!UICONTROL Create subscription list]**&#x200B;ボタンを選択します。

   ![](assets/lp_create-subscription-list.png)

1. タイトルと説明を追加します。 これらのフィールドは必須です。

   ![](assets/lp_subscription-list-name.png)

   >[!CAUTION]
   >
   >現在、 **[!UICONTROL Title]** 他の購読リストの名前をフィールドに使用することはできません。

1. 開始日と終了日を定義することができます。

   ![](assets/lp_subscription-list-dates.png)

1. をクリック **[!UICONTROL Save]** します。

リストには、作成したすべての購読リストが表示されます。 フィルターは、作成日時とその状態に基づいてフィルタリングできます。

![](assets/lp_subscription-filters.png)

次のような状態になります。

* **[!UICONTROL Not started]**: 現在の日付以降の開始日を定義しています。 サブスクライブされたプロファイルは、この購読リストに関する通信を受信しません。
* **[!UICONTROL Live]**: 当日は、購読リストの開始日と終了日の間に設定されているか、定義されていません。これは、購読リストが常にライブの状態であることを意味します。
* **[!UICONTROL Expired]**: 終了日が経過したので、購読リストが有効になっていません。 サブスクライブされたプロファイルには、この購読リストに関する通信はこれ以上通知されません。

購読リストは、作成されると、ランディングページで使用できるようになります。 ランディングページフォームを使用するプロファイルがリストに追加されます。 [詳細情報](design-lp.md)

Journeys ](../building-journeys/journey-gs.md#jo-build) を作成し、パーソナル化を追加する場合 [ は、購読リストをセグメントとして使用することもできます。

>[!NOTE]
>
>特定のレポートを使用して、購読リストの影響を監視することができます。 [詳細情報](../reports/subscription-report-live.md)
