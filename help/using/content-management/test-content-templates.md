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
source-git-commit: b9208544b08b474db386cce3d4fab0a4429a5f54
workflow-type: ht
source-wordcount: '193'
ht-degree: 100%

---

# メールコンテンツテンプレートのテスト {#test-template}

ゼロから作成した場合でも、既存のコンテンツから作成した場合でも、一部のメールテンプレートのレンダリングをテストできます。これを行うには、以下の手順に従います。

1. **[!UICONTROL コンテンツ管理]**／**[!UICONTROL コンテンツテンプレート]**&#x200B;メニューからコンテンツテンプレートリストにアクセスし、任意のメールテンプレートを選択します。

1. **[!UICONTROL テンプレートプロパティ]**&#x200B;から「**[!UICONTROL コンテンツを編集]**」をクリックします。

1. 「**[!UICONTROL コンテンツをシミュレート]**」をクリックし、テストプロファイルを選択して、レンダリングを確認します。[詳細情報](../content-management/preview-test.md)

   ![](assets/content-template-stimulate.png)

1. ジャーニーやキャンペーンで使用する前に、コンテンツをテストするための配達確認を送信し、一部の内部ユーザーから承認を得ることができます。

   * これを行うには、「**[!UICONTROL 配達確認を送信]**」ボタンをクリックし、[この節](../content-management/proofs.md)で説明されている手順に従います。

   * 配達確認を送信する前に、コンテンツのテストに使用する[メール設定](../configuration/channel-surfaces.md)を選択する必要があります。

     ![](assets/content-template-stimulate-proof-surface.png)

>[!CAUTION]
>
>現在、メールコンテンツテンプレートをテストする際の追跡はサポートされていません。つまり、テンプレートから送信される配達確認で、イベント、UTM パラメーター、ランディングページリンクの追跡が有効になりません。追跡をテストするには、メールで[コンテンツテンプレートを使用](../email/use-email-templates.md)し、[配達確認を送信](../content-management/preview-test.md#send-proofs)します。
