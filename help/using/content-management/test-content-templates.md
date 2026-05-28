---
solution: Journey Optimizer
product: journey optimizer
title: コンテンツテンプレートのテスト
description: 一部のメールコンテンツテンプレートのレンダリングをテストする方法について説明します。
feature: Templates
topic: Content Management
role: User
level: Beginner
exl-id: 01726ab6-f581-4d19-aedd-2541bc0f27c6
TQID: https://experienceleague.adobe.com/CC56E9rV4TImjLBbm-fsq2a4JKLnEA4wJB2DVLgOAfM
product_v2: id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2: id: dc22c819-3f29-4e91-8b7d-5c6719831141id: fe338112-e2ce-4876-8989-fc4d497613f1
subfeature_v2: id: a5683ded-e5d5-4ec6-b9fd-e1b56a94ab96id: d595a60b-bcf5-4a63-a189-66a0be755cc7id: f8d2e9f0-69c9-40cd-890f-71336c8dfff7id: fb9a80eb-bebc-492f-a0e9-584595621ebb
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
source-git-commit: 0ee10a0689d38c22b1180b197796b08a10c286cf
workflow-type: tm+mt
source-wordcount: 252
ht-degree: 100%

---

# メールコンテンツテンプレートのテスト {#test-template}

ゼロから作成した場合でも、既存のコンテンツから作成した場合でも、一部のメールテンプレートのレンダリングをテストできます。 これを行うには、以下の手順に従います。

1. **[!UICONTROL コンテンツ管理]**／**[!UICONTROL コンテンツテンプレート]**&#x200B;メニューからコンテンツテンプレートリストにアクセスし、任意のメールテンプレートを選択します。

1. **[!UICONTROL テンプレートプロパティ]**&#x200B;から「**[!UICONTROL コンテンツを編集]**」をクリックします。

1. 「**[!UICONTROL コンテンツをシミュレート]**」をクリックし、テストプロファイルを選択して、レンダリングを確認します。 [詳細情報](../content-management/preview-test.md)

   ![](assets/content-template-stimulate.png)

   >[!NOTE]
   >
   >また、[!DNL Journey optimizer] を使用すると、CSV／JSON ファイルからアップロードした、または手動で追加したサンプル入力データを使用してコンテンツテンプレートをプレビューし、本配信前確認を送信することで、コンテンツテンプレートの様々なバリアントをテストできます。 [コンテンツバリエーションのシミュレート方法を学ぶ](../test-approve/simulate-sample-input.md)

1. ジャーニーやキャンペーンで使用する前に、コンテンツをテストするための配達確認を送信し、一部の内部ユーザーから承認を得ることができます。

   * これを行うには、「**[!UICONTROL 配達確認を送信]**」ボタンをクリックし、[この節](../content-management/proofs.md)で説明されている手順に従います。

   * 配達確認を送信する前に、コンテンツのテストに使用する[メール設定](../configuration/channel-surfaces.md)を選択する必要があります。

     ![](assets/content-template-stimulate-proof-surface.png)

>[!CAUTION]
>
>現在、メールコンテンツテンプレートをテストする際のトラッキングはサポートされていません。つまり、テンプレートから送信される配達確認では、トラッキングイベント、UTM パラメーター、ランディングページリンクの追跡が有効になりません。 トラッキングをテストするには、メールで[コンテンツテンプレート](../email/use-email-templates.md)を使用し、テストプロファイルや、CSV／JSON ファイルからアップロードまたは手動で追加したサンプル入力データを使用して、配達確認を送信します。 [詳しくは、コンテンツをプレビューおよびテストする方法を参照してください](../content-management/preview-test.md)
