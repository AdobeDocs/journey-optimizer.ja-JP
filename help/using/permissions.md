---
title: 権限の管理
description: 権限の管理方法を学ぶ
source-git-commit: 55b9e5d8ed259ec6ed7746e835691d7d6261a8a4
workflow-type: ht
source-wordcount: '1073'
ht-degree: 100%

---

# 権限の管理 {#manage-permissions}

![](assets/do-not-localize/badge.png)

## Journey Optimizer へのアクセス{#access-CJM}

[!DNL Journey Optimizer] では、ユーザーに各種の権限を割り当てて、ユーザーがアクセスできるインターフェイスの部分を定義できます。

ユーザーは、Admin Console にアクセスできる管理者によって管理されます。[Adobe Admin Console の詳細情報](https://helpx.adobe.com/jp/enterprise/managing/user-guide.html)。

[!DNL Journey Optimizer] にアクセスするには、次の条件を満たす必要があります。

* [!DNL Journey Optimizer] 権限に関連付けられた [!DNL Journey Optimizer] **[!UICONTROL 製品プロファイル]**&#x200B;の一部。

* [!DNL Adobe Experience Platform] **[!UICONTROL 製品プロファイル]**&#x200B;の一部。必須の権限はありません。[!DNL Journey Optimizer] インターフェイスからプラットフォームセグメントを作成および編集できるようにするには、**[!UICONTROL プロファイル管理]**&#x200B;権限が必要です。[アクセス制御の詳細情報](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=ja#video-overview)。

Admin Console では、あらかじめ用意されている以下のデフォルト製品プロファイルのいずれかを、ユーザーに割り当てることができます。

* **[!UICONTROL 制限付きアクセスユーザー]**：ジャーニーおよびレポートに対する読み取り専用アクセス権を持つユーザー。この製品プロファイルには、次の権限が含まれます。
   * ジャーニーの読み取り
   * レポートの読み取り

* **[!UICONTROL 管理者]**：ジャーニー、イベント、レポートを管理できる、管理メニューへのアクセス権を持つユーザー。この製品プロファイルには、次の権限が含まれます。
   * ジャーニーの管理
   * ジャーニーの公開
   * イベント、データソース、アクションの管理
   * レポートの管理

* **[!UICONTROL 標準ユーザー]**：ジャーニー管理などの基本的なアクセス権を持つユーザー。この製品プロファイルには、次の権限が含まれます。
   * ジャーニーの管理
   * ジャーニーの公開
   * レポートの管理
   * イベント、データソース、アクションの読み取り

デフォルトのプロファイルでは十分にユーザー管理できない場合は、独自のプロファイルを作成することもできます。
ユーザーは常に製品プロファイルにリンクされ、用意されている以下のような特定の権限を割り当てる必要があります。

* **[!UICONTROL ジャーニーの読み取り]**
* **[!UICONTROL レポートの読み取り]**
* **[!UICONTROL イベント、データソース、アクションの管理]**
* **[!UICONTROL イベント、データソース、アクションの読み取り]**
* **[!UICONTROL ジャーニーの管理]**
* **[!UICONTROL ジャーニーの公開]**
* **[!UICONTROL レポートの管理]**

>[!NOTE]
>
> 権限の管理に次のメッセージは含まれません：すべてのユーザーは、メッセージを作成または変更できます。

### 製品プロファイルの作成 {#create-product-profile}

[!DNL Journey Optimizer] では、独自の製品プロファイルを作成し、ユーザーに一連の権限とサンドボックスを割り当てることができます。製品プロファイルを使用すると、インターフェイス内の特定の機能やオブジェクトへのアクセスを許可または拒否できます。

サンドボックスの作成および管理方法について詳しくは、[Adobe Experience Platform ドキュメント](https://experienceleague.adobe.com/docs/experience-platform/sandbox/ui/user-guide.html?lang=ja)を参照してください。

製品プロファイルを作成し、権限とサンドボックスのセットを割り当てるには、次の手順に従います。

1. Admin Console で「**[!UICONTROL Journey Orchestration]**」を選択します。「**[!UICONTROL 製品プロファイル]**」タブで、「**[!UICONTROL 新規プロファイル]**」をクリックします。

   ![](assets/do-not-localize/user_management_5.png)

1. 新しい製品プロファイルの&#x200B;**[!UICONTROL プロファイル名]**&#x200B;と&#x200B;**[!UICONTROL 説明]**&#x200B;を追加します。プロファイルの&#x200B;**[!UICONTROL 表示名]**&#x200B;をプロファイル名と異なる名前に設定するには、「**[!UICONTROL プロファイル名と同じ]**」をオフにし、**[!UICONTROL 表示名]**&#x200B;を入力します。

1. 「**[!UICONTROL ユーザー通知]**」カテゴリで、ユーザーがこの製品プロファイルに追加されたとき、または削除されたときにメールで通知するかどうかを選択します。

1. 終了したら、「**[!UICONTROL 完了]**」をクリックします。これで、新しい製品プロファイルが作成されました。

   ![](assets/do-not-localize/user_management_1.png)

1. 新しい製品プロファイルを選択して、権限の管理を開始します。「**[!UICONTROL ユーザー]**」タブで、製品プロファイルにユーザーを追加します。[製品プロファイルの割り当て方法を学ぶ](permissions.md#assigning-product-profile)。

1. 上記と同じ手順を実行して、製品プロファイルに&#x200B;**[!UICONTROL 管理者]**&#x200B;を追加します。

1. 「**[!UICONTROL 権限]**」タブから、「**[!UICONTROL サンドボックス]**」または「**[!UICONTROL オーサリング]**」の 2 つのカテゴリのいずれかを選択して&#x200B;**[!UICONTROL 権限を編集]**&#x200B;ページを開き、製品プロファイルに対する権限を追加または削除します。

   ![](assets/do-not-localize/user_management_7.png)

1. 「**[!UICONTROL サンドボックス]**」権限カテゴリで、製品プロファイルに割り当てるサンドボックスを選択します。「**[!UICONTROL 利用可能な権限項目]**」で、プラス（+）アイコンをクリックして、サンドボックスをプロファイルに割り当てます。[サンドボックスの詳細情報](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=ja)。

   ![](assets/do-not-localize/user_management_8.png)

1. 必要に応じて、「**[!UICONTROL 含まれる権限項目]**」で、横の X アイコンをクリックして製品プロファイルに対する権限を削除します。

   ![](assets/do-not-localize/user_management_9.png)

1. 「**[!UICONTROL オーサリング]**」権限カテゴリから、上記と同じ手順を実行して、製品プロファイルに権限を追加します。

   ![](assets/do-not-localize/user_management_10.png)

1. 終了したら、「**[!UICONTROL 保存]**」をクリックします。

これで、製品プロファイルの作成と設定が完了しました。このプロファイルにリンクされたユーザーは、[!DNL Journey Optimizer] に接続できます。

### 製品プロファイルの割り当て {#assigning-product-profile}

製品プロファイルは、組織内で同じ権限を共有する一連のユーザーに割り当てられます。
デフォルトで権限が割り当てられているすべての製品プロファイルのリストについては、この節を参照してください。

ジャーニーにアクセスするユーザーに製品プロファイルを割り当てるには、以下の手順に従います。

1. Admin Console で「**[!UICONTROL Journey Orchestration]**」を選択します。

   ![](assets/do-not-localize/user_management.png)

1. 新しいユーザーをリンクする製品プロファイルを選択します。

   ![](assets/do-not-localize/user_management_2.png)

1. 「**[!UICONTROL ユーザーを追加]**」をクリックします。

   また、新しいユーザーをユーザーグループに追加して、共有された一連の権限を微調整することもできます。[ユーザーグループの詳細情報](https://helpx.adobe.com/jp/enterprise/using/user-groups.html)。

   ![](assets/do-not-localize/user_management_3.png)

1. 新しいユーザーのメールアドレスを入力し、「**[!UICONTROL 保存]**」をクリックします。

   ![](assets/do-not-localize/user_management_4.png)

その後、 インスタンスにリダイレクトするメールがユーザーに送信されます。

## サンドボックスの使用 {#sandboxes}

[!DNL Journey Optimizer] では、インスタンスをサンドボックスと呼ばれる個別の仮想環境に分割できます。
サンドボックスは、Admin Console の製品プロファイルから割り当てられます。[サンドボックスの割り当て方法を学ぶ](permissions.md#create-product-profile)。

[!DNL Journey Optimizer] は、特定の組織用に作成された Adobe Experience Platform サンドボックスを反映します。
Adobe Experience Platform サンドボックスは、Adobe Experience Platform インスタンスから作成またはリセットできます。[詳しくは、Sandboxユーザーガイドを参照してください](https://experienceleague.adobe.com/docs/experience-platform/sandbox/ui/user-guide.html?lang=ja)。

画面の左上に、サンドボックス切り替えコントロールがあります。サンドボックスを切り替えるには、切り替えボタンで現在アクティブなサンドボックスをクリックし、ドロップダウンリストから別のサンドボックスを選択します。

## コンテンツへのアクセス {#content-access}

コンテンツのアクセシビリティを設定するには、コンテンツの共有フォルダーを各サンドボックスに割り当てる必要があります。管理者向けの [!DNL Admin Console] に表示される「**[!UICONTROL ストレージ]**」タブで、共有フォルダーを作成し、設定できます。システム管理者として [!DNL Admin Console] にアクセスできる場合は、共有フォルダーを作成し、異なるアクセスレベルの委任を共有フォルダーに追加できます。

![](assets/do-not-localize/content_access.png)

コンテンツを正しいサンドボックスと同期させるには、サンドボックスと同じ構文に従う必要があります。例えば、サンドボックスの名前が「開発」の場合、共有フォルダーも同じ名前にする必要があります。

[共有フォルダーの管理方法を学ぶ](https://helpx.adobe.com/jp/enterprise/admin-guide.html/enterprise/using/adobe-asset-link.ug.html)。

## Assets Essentials の権限{#assets-permissions}

Adobe Experience Manager Assets Essentials は、メッセージの入力に使用できる、アセットの一元的なリポジトリを提供します。
各アセットは、フォルダーまたはサブフォルダーに保存されます。フォルダーを共有し、どのアクセスレベルを割り当てるかを選択できます。

1. 「**[!UICONTROL アセット]**」タブから、フォルダー内を移動し、共有する必要のあるフォルダーを見つけます。

1. フォルダーまたはアセットを選択し、「**[!UICONTROL 共有]**」をクリックします。

   ![](assets/share_media_1.png)

1. フォルダーへのアクセスを共有する相手のメールアドレスを入力します。

1. 異なるアクセスレベルを選択します。

   * **[!UICONTROL 表示可能]**
   * **[!UICONTROL 編集可能]**
   * **[!UICONTROL 所有権を持つ（共有、編集、削除が可能）]**

   ![](assets/share_media_2.png)

1. 必要に応じて、招待状にメッセージを追加します。

1. 「**[!UICONTROL 招待]**」をクリックします。

   ![](assets/share_media_3.png)
