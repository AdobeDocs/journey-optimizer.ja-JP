---
title: テストプロファイルを選択
description: コンテンツをプレビューおよびテストするためのテストプロファイルの選択方法を説明します。
feature: Preview, Proofs
role: User
level: Beginner
exl-id: c51e4089-7f51-437d-a5ed-de10bab46cf8
source-git-commit: bc433a215021b9c5c6a8948468468808e7121712
workflow-type: tm+mt
source-wordcount: '276'
ht-degree: 80%

---

# テストプロファイルを選択 {#select-test-profiles}

>[!CONTEXTUALHELP]
>id="ajo_preview_test_profiles"
>title="テストプロファイルを使用したコンテンツの確認"
>abstract="テストプロファイルを使用して、コンテンツをプレビューおよびテストします。パーソナライズされたフィールドを追加した場合は、テストプロファイルデータを使用して、その表示方法を確認できます。"

テストプロファイルは、定義されたターゲティング条件に一致しない、追加の受信者です。 [詳しくは、テストプロファイルの作成方法を参照してください](../audience/creating-test-profiles.md)

テストプロファイルを使用してコンテンツをテストする前に、まず選択する必要があります。 それには、次の手順に従います。

1. メッセージのコンテンツを編集画面またはメールDesignerで、「**[!UICONTROL コンテンツをシミュレート]**」ボタンをクリックし、「**[!UICONTROL コンテンツをシミュレート]**」を選択します。

1. 「**[!UICONTROL テストプロファイルを管理]**」ボタンをクリックし、「**[!UICONTROL ID 名前空間]**」選択アイコンをクリックして、テストプロファイルの識別に使用する名前空間を選択します。[詳しくは、Adobe Experience Platform の ID 名前空間を参照してください](../audience/get-started-identity.md)。

   以下の例では、**メール**&#x200B;名前空間を使用します。

   ![](../email/assets/previewselect-namespace.png)

1. 検索フィールドで名前空間を探して選択し、「**[!UICONTROL 選択]**」をクリックします。

   ![](../email/assets/preview-email-namespace.png)

1. 「**[!UICONTROL ID 値]**」フィールドに値（ここではメールアドレス）を入力して、テストプロファイルを識別し、「**[!UICONTROL プロファイルを追加]**」をクリックします。

   <!--![](assets/preview-identity-value.png)-->

1. メッセージにパーソナライゼーションを追加した場合は、別のプロファイルを追加して、プロファイルデータに応じて異なるバリエーションのメッセージをテストできるようにします。追加したプロファイルは、選択フィールドの下に表示されます。

   ![](../email/assets/preview-profile-list.png)

   メッセージのパーソナライゼーションの要素に基づいて、各テストプロファイルのデータがリストの関連する列に表示されます。

>[!NOTE]
>
>テストプロファイルに加えて、[!DNL Journey optimizer] を使用すると、CSV／JSON ファイルからアップロードした、または手動で追加したサンプル入力データを使用してコンテンツをプレビューし、配達確認を送信することで、コンテンツの様々なバリアントをテストできます。[ コンテンツのバリエーションをシミュレートする方法を学ぶ ](../test-approve/simulate-sample-input.md)
