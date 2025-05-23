---
solution: Journey Optimizer
product: journey optimizer
title: コンテンツテンプレートの作成
description: テンプレートを作成して、Journey Optimizer のキャンペーンとジャーニーでコンテンツを再利用する方法を学ぶ
feature: Templates
topic: Content Management
role: User
level: Beginner
exl-id: a205539b-b7ea-4832-92b0-49637c4dac47
source-git-commit: e35d18002fa32df8c1cfd9e0a609ce167df4641a
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# コンテンツテンプレートの作成 {#create-content-templates}

>[!CONTEXTUALHELP]
>id="ajo_create_template"
>title="独自のコンテンツテンプレートを定義"
>abstract="スタンドアロンのカスタムテンプレートをゼロから作成して、複数のジャーニーやキャンペーンでコンテンツを再利用できるようにします。"

コンテンツテンプレートを作成する方法は 2 つあります。

* 左側のパネルの&#x200B;**[!UICONTROL コンテンツテンプレート]**&#x200B;メニューを使用して、コンテンツテンプレートをゼロから作成します。[方法についてはこちらを参照](#create-template-from-scratch)

* キャンペーンまたはジャーニー内でコンテンツをデザインする際に、テンプレートとして保存する。[方法についてはこちらを参照](#save-as-template)

保存すると、コンテンツテンプレートをキャンペーンやジャーニーで使用できるようになります。 ゼロから作成した場合でも、以前のコンテンツから作成した場合でも、[!DNL Journey Optimizer] 内でコンテンツを作成する際にこのテンプレートを使用できるようになりました。[方法についてはこちらを参照](#use-content-templates)

>[!NOTE]
>
>* コンテンツテンプレートに加えられた変更は、ライブかドラフトかに関わらず、キャンペーンやジャーニーには反映されません。
>
>* 同様に、キャンペーンやジャーニーでテンプレートを使用する場合、キャンペーンやジャーニーのコンテンツにを編集しても、以前に使用したコンテンツテンプレートには影響しません。

## テンプレートをゼロから作成 {#create-template-from-scratch}

>[!NOTE]
>
>2025年3月以降、HTML タイプのコンテンツテンプレートは非推奨（廃止予定）になりました。[!DNL Journey Optimizer] で以前に作成した既存の HTML コンテンツテンプレートは引き続き使用できます。

コンテンツテンプレートをゼロから作成するには、次の手順に従います。

1. **[!UICONTROL コンテンツ管理]**／**[!UICONTROL コンテンツテンプレート]**&#x200B;の左側のメニューからコンテンツテンプレートリストにアクセスします。

1. 「**[!UICONTROL テンプレートの作成]**」を選択します。

1. テンプレートの詳細を入力し、目的のチャネルを選択します。

   ![](assets/content-template-channels.png)

   >[!NOTE]
   >
   >現在、web を除くすべてのチャネルを使用できます。

1. 「**[!UICONTROL タグ]**」フィールドから Adobe Experience Platform タグを選択または作成してテンプレートを分類し、検索の向上を図ります。[詳細情報](../start/search-filter-categorize.md#tags)

1. テンプレートにカスタムまたはコアのデータ使用ラベルを割り当てるには、「**[!UICONTROL アクセスを管理]**」を選択します。[詳しくは、オブジェクトレベルのアクセス制御（OLAC）を参照してください](../administration/object-based-access.md)。

1. 「**[!UICONTROL 作成]**」をクリックし、選択したチャネルに従って、ジャーニーやキャンペーン内のコンテンツと同じ方法で、必要に応じてコンテンツをデザインします。

   ![](assets/content-template-edition.png)

   様々なチャネル用のコンテンツを作成する方法については、次の節を参照してください。
   * [メールコンテンツの定義](../email/get-started-email-design.md)
   * [プッシュコンテンツの定義](../push/design-push.md)
   * [SMS コンテンツの定義](../sms/create-sms.md#sms-content)
   * [ダイレクトメールコンテンツの定義](../direct-mail/create-direct-mail.md)
   * [アプリ内コンテンツの定義](../in-app/design-in-app.md)

1. コンテンツをテストできます。[方法についてはこちらを参照](#test-template)

1. テンプレートの準備が整ったら、「**[!UICONTROL 保存]**」をクリックします。

1. テンプレート名の横にある矢印をクリックして&#x200B;**[!UICONTROL 詳細]**&#x200B;画面に戻ります。

   ![](assets/content-template-back.png)

このテンプレートを、[!DNL Journey Optimizer] 内でコンテンツを作成する際に使用できるようになりました。[方法についてはこちらを参照](#use-content-templates)

>[!NOTE]
>
>メールコンテンツテンプレートを作成する際に、ブランドやデザインに合った特定のスタイルをすばやく適用するには、コンテンツにテーマを適用します。 [詳細情報](../email/apply-email-themes.md)

## コンテンツをコンテンツテンプレートとして保存 {#save-as-template}

>[!CONTEXTUALHELP]
>id="ajo_messages_depecrated_inventory"
>title="メッセージの移行方法を説明します。"
>abstract="2022年7月25日（PT）より、メッセージメニューが表示されなくなり、ジャーニーから直接メッセージが作成されます。 従来のメッセージをジャーニーで再利用する場合は、それらをテンプレートとして保存する必要があります。"

キャンペーンやジャーニーでコンテンツをデザインする際、保存しておくと、後で再利用できます。それには、次の手順に従います。

1. メッセージの&#x200B;**[!UICONTROL コンテンツを編集]**&#x200B;画面で、「**[!UICONTROL コンテンツテンプレート]**」ボタンをクリックします。

1. ドロップダウンメニューから「**[!UICONTROL コンテンツテンプレートとして保存]**」を選択します。

   ![](assets/content-template-button-save.png)

   [メールデザイナー](../email/get-started-email-design.md)を使用している場合は、画面右上の&#x200B;**[!UICONTROL その他]**&#x200B;ドロップダウンリストからこのオプションを選択することもできます。

   ![](assets/content-template-more-button-save.png)

1. このテンプレートの名前と説明を追加します。

   ![](assets/content-template-name.png)

   >[!NOTE]
   >
   >現在のチャネルは自動的に入力されており、編集できません。

1. 「**タグ**」フィールドから Adobe Experience Platform タグを選択または作成して、テンプレートを分類します。[詳細情報](../start/search-filter-categorize.md#tags)

1. テンプレートにカスタムまたはコアのデータ使用ラベルを割り当てるには、「**[!UICONTROL アクセスを管理]**」を選択します。[詳細情報](../administration/object-based-access.md)。

1. 「**[!UICONTROL 保存]**」をクリックします。

1. テンプレートは&#x200B;**[!UICONTROL コンテンツテンプレート]**&#x200B;リストに保存され、[!DNL Journey Optimizer] 専用メニューからアクセスできます。このテンプレートは、そのリストの他の項目と同様に、アクセス、編集、削除できるスタンドアロンのコンテンツテンプレートになります。[詳細情報](#access-manage-templates)

[!DNL Journey Optimizer] 内でコンテンツを作成する際に、このテンプレートを使用できるようになりました。[方法についてはこちらを参照](#use-content-templates)

>[!NOTE]
>
>その新しいテンプレートに対する変更は、送信元のコンテンツには生成されません。同様に、そのコンテンツ内で元のコンテンツを編集しても、新しいテンプレートは変更されません。
