---
title: コンテンツのプレビュー
description: コンテンツをプレビューする方法を説明します。
feature: Preview, Proofs
role: User
level: Beginner
exl-id: 6477270c-0309-411a-8254-c7ffc4419492
source-git-commit: 03cb3298c905766bc059e82c58969a2111379345
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 75%

---

# テストプロファイルを使用したコンテンツのプレビュー {#preview}

<!--## Preview your content {#preview-content}-->

[ テストプロファイル ](test-profiles.md) を定義すると、コンテンツをプレビューできます。

>[!NOTE]
>
>[!DNL Journey optimizer] た、CSV/JSON ファイルからアップロードされた、または手動で追加されたサンプル入力データを使用して、コンテンツの様々なバリアントをプレビューし、配達確認を送信することで、テストすることもできます。 [ サンプル入力データを使用してコンテンツをテストする方法を説明します ](../test-approve/simulate-sample-input.md)

テストプロファイルを使用してコンテンツをプレビューするには、次の手順に従います。

1. メッセージのコンテンツを編集画面または E メールデザイナーで、「**[!UICONTROL コンテンツをシミュレート]**」ボタンをクリックします。

1. テストプロファイルを選択します。列内で利用可能な値を確認できます。右向きや左向きの矢印を使用して、データを参照します。

   ![](../email/assets/preview-select-profile.png)

   >[!NOTE]
   >
   >テストプロファイルをさらに追加するには、「**[!UICONTROL テストプロファイルを管理]**」を選択します。[詳細情報](test-profiles.md)

1. 列を追加または削除するには、リストの上にある「**[!UICONTROL データを選択]**」アイコンをクリックします。

   リストの最後に、現在のメッセージに固有のパーソナライゼーションフィールドを表示できます。この例では、プロファイルの市区町村、姓、名を使用しています。これらのフィールドを選択し、テストプロファイルにこれらの値が入力されていることを確認します。

   ![](../email/assets/preview-select-data.png)

1. メッセージプレビューでは、パーソナライズされた要素が、選択したテストプロファイルデータに置き換えられます。例えば、次のメッセージの場合、メールのコンテンツと件名の両方がパーソナライズされています。

   ![](../email/assets/preview-test-profile.png)

1. メッセージの各バリエーションに対してメールをプレビューするには、他のテストプロファイルを選択します。

>[!NOTE]
>
>設定の詳細にエラーがある場合は、「**[!UICONTROL 設定の詳細を表示]**」ボタンをクリックします。[詳細情報](../email/surface-personalization.md#check-configuration)

コードベースのエクスペリエンスを作成する場合、ブラウザーまたはモバイルデバイスでパーソナライズされたコンテンツをプレビューして、実際のシミュレーションを行うことができます。[詳細情報](../code-based/create-code-based.md#preview-on-device)

