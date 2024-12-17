---
solution: Journey Optimizer
product: journey optimizer
title: AEM コンテンツフラグメント
description: AEM コンテンツフラグメントにアクセスして管理する方法を学ぶ
topic: Content Management
role: User
level: Beginner
hide: true
hidefromtoc: true
source-git-commit: 50b36446ff0e9f4aec9f28056c3c30cc2df3f530
workflow-type: tm+mt
source-wordcount: '405'
ht-degree: 6%

---

# Adobe Experience Manager コンテンツフラグメント {#aem-fragments}

Adobe Experience ManagerをAdobe Journey Optimizerと統合することで、AEM コンテンツフラグメントをJourney Optimizerのメールコンテンツにシームレスに組み込めるようになりました。 この合理化された接続により、AEM コンテンツへのアクセスと活用のプロセスが簡略化され、パーソナライズされた動的なキャンペーンとジャーニーを作成できます。

AEM コンテンツフラグメントについて詳しくは、[Experience Managerドキュメント ](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/sites/authoring/fragments/content-fragments) を参照してください。

## 制限事項 {#limitations}

* メールチャネルでのみ使用できます。

* 各サンドボックスは 1 つのインスタンスに制限されているので、現在、接続先のAEM インスタンスを切り替えることができません。

* メールでの誤ったエラーのリスクを減らすために、コンテンツフラグメントを公開するアクセス権を持つユーザーの数を制限することをお勧めします。

* 多言語コンテンツの場合、手動フローのみがサポートされます。

* 現在、バリアントはサポートされていません。

* Journey Optimizer専用のタグを作成する必要があります。

+++ Journey Optimizer タグの作成方法を学ぶ

   1. **Experience Manager** にアクセスします。

   1. **ツール** メニューから「**一般** タブに移動し、「**タグ付け**」を選択します。

   1. **新しいタグを作成** をクリックします。

   1. ID が次の構文に従っていることを確認します。`ajo-enabled:{AJO-OrgId}/{AJO-SandboxName}`。

   1. 「**作成**」をクリックします。

  これで、このJourney Optimizer タグをコンテンツフラグメントに割り当てることができます。
+++

## AEM コンテンツフラグメントの追加 {#aem-add}

[AEM コンテンツフラグメント ](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/sites/authoring/fragments/content-fragments) を作成およびパーソナライズした後、それをジャーニーオプティマイザーキャンペーンまたはジャーニーに読み込めるようになりました。

1. メールのアクションを使用して [ キャンペーン ](../email/create-email.md) または [ジャーニー](../email/create-email.md) を作成したら、E メールデザイナーにアクセスしてメールのコンテンツを設定します。 [詳細情報](../email/get-started-email-design.md)

1. テキストブロック内または件名行をクリックし、コンテキストツールバーから **[!UICONTROL Personalizationを追加]** を選択します。

   ![](assets/aem_campaign_2.png)

1. 左側のペインの **[!UICONTROL AEM コンテンツフラグメント]** メニューで、「**[!UICONTROL AEM CF セレクターを開く]** をクリックします。

   ![](assets/aem_campaign_3.png)

1. 使用可能なリストから **[!UICONTROL コンテンツフラグメント]** を選択して、Journey Optimizer コンテンツに読み込みます。

   >[!IMPORTANT]
   >
   >公開済みの **[!UICONTROL コンテンツフラグメント]** のみを使用できます。

1. 「**[!UICONTROL フィルターを表示]**」をクリックして、コンテンツフラグメントリストを微調整します。

   コンテンツフラグメントセレクターには事前設定済みのフィルターが含まれています。

   * **[!UICONTROL ステータス]**：公開済み、変更済み
   * **[!UICONTROL タグ]**:Journey Optimizer環境（組織 ID とサンドボックス）に基づいて自動的に定義されます

   ![](assets/aem_campaign_4.png)

1. **[!UICONTROL コンテンツフラグメント]** を選択したら、**[!UICONTROL 選択]** をクリックして開きます。

   ![](assets/aem_campaign_5.png)

1. **[!UICONTROL コンテンツフラグメント]** から目的のフィールドを選択して、コンテンツに追加します。

   ![](assets/aem_campaign_6.png)

1. 「**[!UICONTROL 保存]**」をクリックして、プレビューでメッセージを確認します。メッセージのコンテンツをテストして確認するには、[この節](preview.md)を参照してください。

テストを実行してコンテンツを検証したら、{Campaign](../campaigns/review-activate-campaign.md) または [2}ジャーニー](../building-journeys/publishing-the-journey.md) を記載したメールをオーディエンスに送信できます。[

