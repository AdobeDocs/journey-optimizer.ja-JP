---
solution: Journey Optimizer
product: journey optimizer
title: メールコンテンツのインポート
description: メールコンテンツのインポート方法を学ぶ
feature: Email Design
topic: Content Management
role: User
level: Intermediate
keywords: メール, 読み込み, コンテンツ, html, zip, css
exl-id: 52011299-0c65-49c3-9edd-ba7bed5d7205
TQID: https://experienceleague.adobe.com/R0Csd9gbvY-iyW81G-clHoXozEBYWBfjb0y9PWq4zZA
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2:
  - id: dc22c819-3f29-4e91-8b7d-5c6719831141
  - id: fe338112-e2ce-4876-8989-fc4d497613f1
subfeature_v2:
  - id: ee5bb250-0884-4d71-86eb-d8489e8bcadd
  - id: fb9a80eb-bebc-492f-a0e9-584595621ebb
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
source-git-commit: f9b8e1590f14cdcd00432295c653769f753b9b40
workflow-type: tm+mt
source-wordcount: 260
ht-degree: 100%

---

# メールコンテンツのインポート {#existing-content}

[!DNL Journey Optimizer] では、既存の HTML コンテンツをインポートしてメールをデザインできます。 このコンテンツには次のようなものがあります。

* スタイルシートが組み込まれた **HTML ファイル**
* HTML ファイル、スタイルシート（.css）および画像を含んだ **.zip フォルダー**

  >[!NOTE]
  >
  >.zip ファイル構造に制限はありません。 ただし、.zip フォルダーのツリー構造に合わせて、相対参照を指定する必要があります。


>[!TIP]
>
>HTML ファイルの代わりに画像デザイン（JPEG または PNG）がある場合は、[画像から HTML へのコンバーター](../content-management/image-to-html.md)を使用して、AI によって編集可能な HTML メールテンプレートに自動的に変換できます。

HTML コンテンツを含んだファイルをインポートするには、次の手順に従います。

1. E メールデザイナーのホームページで、「**[!UICONTROL HTML をインポート]**」を選択します。

   ![](assets/import-html_2.png)

1. HTML コンテンツを含んだ HTML または .zip ファイルをドラッグ＆ドロップし、「**[!UICONTROL 読み込み]**」をクリックします。

   ![](assets/html-imported_2.png)

1. HTML コンテンツをアップロードすると、コンテンツは&#x200B;**[!UICONTROL 互換性モード]**&#x200B;になります。

   このモードでは、テキストのパーソナライズ、リンクの追加またはコンテンツへのアセットの組み込みのみ可能です。

1. E メールデザイナーのコンテンツコンポーネントを活用できるようにするには、「**[!UICONTROL HTML コンバーター]**」タブにアクセスし、「**[!UICONTROL 変換]**」をクリックします。

   ![](assets/html-imported.png)

   >[!NOTE]
   >
   > `<table>` タグを HTML ファイルの最初のレイヤーとして使用すると、上部レイヤータグの背景や幅の設定などのスタイルが失われる可能性があります。

1. これで、E メールデザイナーの機能を使用して、読み込んだファイルを必要に応じてパーソナライズできるようになりました。 [詳細情報](content-from-scratch.md)

## チュートリアルビデオ {#video}

既存の HTML コンテンツの読み込み、デザインの調整、ミラーページと購読解除リンクの追加およびコンテンツのコーディング方法について説明します。

>[!VIDEO](https://video.tv.adobe.com/v/334102?quality=12)
