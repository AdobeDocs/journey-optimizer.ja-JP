---
title: コンテンツのプレビュー
description: コンテンツをプレビューする方法を説明します。
feature: Preview, Proofs
role: User
level: Beginner
exl-id: 6477270c-0309-411a-8254-c7ffc4419492
feature_v2: []
subfeature_v2: id: f8d2e9f0-69c9-40cd-890f-71336c8dfff7
source-git-commit: a4e4f5ca5c3eb9dbfb5691cb5de420009ed7e5a5
workflow-type: tm+mt
source-wordcount: 231
ht-degree: 86%

---

# テストプロファイルを使用したコンテンツのプレビュー {#preview}

[テストプロファイル](test-profiles.md)を選択すると、このデータを使用してコンテンツをプレビューできます。 どちらのシミュレーションメソッドも使用できます。

1. メッセージのコンテンツを編集画面またはメールDesignerで、「**[!UICONTROL コンテンツをシミュレート]**」をクリックし、ドロップダウンから「**[!UICONTROL コンテンツをシミュレート（AEP プロファイル）]**」を選択します。

1. テストプロファイルを選択します。 列内で利用可能な値を確認できます。 右向きや左向きの矢印を使用して、データを参照します。

   ![](../email/assets/preview-select-profile.png)

   >[!NOTE]
   >
   >テストプロファイルをさらに追加するには、「**[!UICONTROL テストプロファイルを管理]**」を選択します。 [詳細情報](test-profiles.md)

1. 列を追加または削除するには、リストの上にある「**[!UICONTROL データを選択]**」アイコンをクリックします。

   リストの最後に、現在のメッセージに固有のパーソナライゼーションフィールドを表示できます。 この例では、プロファイルの市区町村、姓、名を使用しています。 これらのフィールドを選択し、テストプロファイルにこれらの値が入力されていることを確認します。

   ![](../email/assets/preview-select-data.png)

1. メッセージプレビューでは、パーソナライズされた要素が、選択したテストプロファイルデータに置き換えられます。 例えば、次のメッセージの場合、メールのコンテンツと件名の両方がパーソナライズされています。

   ![](../email/assets/preview-test-profile.png)

1. メッセージの各バリエーションに対してメールをプレビューするには、他のテストプロファイルを選択します。

   >[!NOTE]
   >
   >設定の詳細にエラーがある場合は、「**[!UICONTROL 設定の詳細を表示]**」ボタンをクリックします。 [詳細情報](../email/surface-personalization.md#check-configuration)

コードベースのエクスペリエンスを作成する場合、ブラウザーまたはモバイルデバイスでパーソナライズされたコンテンツをプレビューして、実際のシミュレーションを行うことができます。 [詳細情報](../code-based/test-code-based.md#preview-on-device)
