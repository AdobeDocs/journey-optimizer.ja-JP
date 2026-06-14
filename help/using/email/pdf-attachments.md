---
solution: Journey Optimizer
product: journey optimizer
title: メールへの PDF ファイルの添付
description: 静的 PDF ファイルをメールに添付する方法について説明します
feature: Email Design
topic: Content Management
role: User
level: Beginner
keywords: メール, メッセージ, 添付ファイル, PDF, エディター
exl-id: 71e218d0-5b3b-4db5-8b7b-d08df8f088c4
TQID: https://experienceleague.adobe.com/9IgYERskcUrIAhTb3xlNgWTRyY-04O58ZB8I0lYFh4g
product_v2: id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2: id: dc22c819-3f29-4e91-8b7d-5c6719831141id: fe338112-e2ce-4876-8989-fc4d497613f1
subfeature_v2: id: ee5bb250-0884-4d71-86eb-d8489e8bcaddid: fb9a80eb-bebc-492f-a0e9-584595621ebb
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
source-git-commit: bc98cb2b61c7c5c8dac78b494fe293a4106a88c4
workflow-type: tm+mt
source-wordcount: 375
ht-degree: 93%

---

# メールへの PDF ファイルの添付 {#pdf-attachments}

>[!BEGINSHADEBOX]

**このページ：**&#x200B;適用されるファイルサイズと送信ボリュームの制限など、静的なPDF ファイルをメールに添付する方法について説明します。

>[!ENDSHADEBOX]

>[!CONTEXTUALHELP]
>id="ajo_pdf_attachments"
>title="PDF 添付ファイルの追加"
>abstract="メールに添付する PDF ファイルを参照して選択します。</br>プロファイルごとに、年間最大 6 件の PDF 添付ファイル付きメッセージを送信できます。 各添付ファイルの最大許容ファイルサイズは 5MB です。</br>追加のサイズまたはボリュームは、添付ファイルパックアドオンを購入できます。 詳しくは、アドビ担当者にお問い合わせください。"

[!DNL Journey Optimizer] を使用して送信するメールメッセージに静的 PDF ファイルを添付できます。

>[!IMPORTANT]
>
>* プロファイルごとに、年間最大 6 件の PDF 添付ファイル付きメッセージを送信できます。
>
>* 各添付ファイルの最大許容ファイルサイズは 5 MB です。
>
>追加のサイズまたはボリュームについては、PDF 添付ファイルアドオンを購入できます。 詳しくは、アドビ担当者にお問い合わせください。

PDF ファイルをメールメッセージに添付するには、次の手順に従います。

1. ジャーニーまたはキャンペーンでメールを作成します。 [詳細情報](create-email.md)

1. ジャーニーまたはキャンペーンの「**[!UICONTROL コンテンツ]**」タブで、「**[!UICONTROL 添付ファイル]**」セクションから「**[!UICONTROL アセットを追加]**」を選択します。

   ![](assets/email-select-pdf.png)

1. Assets Essentials リポジトリが表示されます。

   >[!NOTE]
   >
   >メッセージをデザインする際は、Journey Optimizer インターフェイス内から Assets Essentials リポジトリに直接アクセスします。 組み込みの [!DNL Assets Essentials] ユーザーインターフェイスについて詳しくは、[Experience Manager Assets Essentials ドキュメント](https://experienceleague.adobe.com/docs/experience-manager-assets-essentials/help/introduction.html?lang=ja){target="_blank"}を参照してください。

1. 「**[!UICONTROL MIME タイプ]**」セクションの **[!UICONTROL PDF]** フィルターを使用して、正しいファイル形式への選択を制限します。

   ![](assets/email-assets-pdf.png)

   >[!NOTE]
   >
   >添付ファイルは、PDF 形式のみ許可されます。

1. 任意のファイルを選択します。

   * 一度に選択できるファイルは 1 つだけです。
   * 各添付ファイルの最大許容ファイルサイズは 5 MB です。

1. 完了したら、選択したファイルの名前とサイズが「**[!UICONTROL 添付ファイル]**」セクションに表示されます。

   ファイル名の横にある「その他のアクション」アイコンを使用して、選択したファイルを削除できます。

   ![](assets/email-remove-attachment.png)

>[!NOTE]
>
>メッセージを[コンテンツテンプレート](../content-management/create-content-templates.md)として保存した場合、PDF 添付ファイルはテンプレートに保持されません。 保存したコンテンツテンプレートから新しいメールを作成する場合は、ファイルを再添付する必要があります。
