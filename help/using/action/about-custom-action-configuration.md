---
solution: Journey Orchestration
title: カスタムアクション設定について
description: カスタムアクションの設定方法を学ぶ
feature: Actions
topic: Administration
role: Admin
level: Intermediate
source-git-commit: c62048e0fb7e5de2e7cdf8bc6ae17d62ef04d35c
workflow-type: tm+mt
source-wordcount: '817'
ht-degree: 67%

---

# アクションの設定 {#configure-an-action}

サードパーティ製システムを使用してメッセージを送信する場合、またはジャーニーがサードパーティ製システムに API 呼び出しを送信する場合は、ここでジャーニーへの接続を設定します。技術ユーザーが定義したカスタムアクションは、ジャーニーの左側のパレットの&#x200B;**[!UICONTROL アクション]**&#x200B;カテゴリーで利用できます（[このページ](../building-journeys/about-journey-activities.md#action-activities)を参照）。カスタムアクションを使用して接続できるシステムには、Epsilon、Facebook、Adobe.io、Firebase などが挙げられます。
制限に関しては[このページ](../building-journeys/limitations.md)に記載されています。

カスタムアクションを設定する際に必要となる、主な手順は次のとおりです。

1. 管理メニューセクションで、「**[!UICONTROL 設定]**」を選択します。 「**[!UICONTROL アクション]**」セクションで、「**[!UICONTROL 管理]**」をクリックします。 「**[!UICONTROL アクションを作成]**」をクリックして、新規のアクションを作成します。画面右側にアクション設定ウィンドウが開きます。

   ![](../assets/custom2.png)

1. アクションの名前を入力します。

   >[!NOTE]
   >
   >スペースや特殊文字は使用しないでください。30 文字以内にしてください。

1. アクションに説明を追加します。この手順はオプションです。
1. このイベントを使用しているジャーニーの数は、「**[!UICONTROL 使用されている場所]**」フィールドに表示されます。「**[!UICONTROL ジャーニーを表示]**」ボタンをクリックすると、このイベントを使用するジャーニーのリストを表示できます。
1. さまざまな **[!UICONTROL URL 設定]**&#x200B;パラメーターを定義します。[このページ](../action/about-custom-action-configuration.md#url-configuration)を参照してください。
1. 「**[!UICONTROL 認証]**」セクションを設定します。この設定はデータソースの場合と同じです。[この節](../datasource/external-data-sources.md#section_wjp_nl5_nhb)を参照してください。
1. **[!UICONTROL アクションパラメーター]**&#x200B;を定義します。[このページ](../action/about-custom-action-configuration.md#define-the-message-parameters)を参照してください。
1. 「**[!UICONTROL 保存]**」をクリックします。

   カスタムアクションが設定され、ジャーニーで使用できる状態になります。[このページ](../building-journeys/about-journey-activities.md#action-activities)を参照してください。

   >[!NOTE]
   >
   >ジャーニーでカスタムアクションを使用する場合、ほとんどのパラメーターは読み取り専用です。変更できるのは、**[!UICONTROL 名前]**、**[!UICONTROL 説明]**、**[!UICONTROL URL]** フィールド、および&#x200B;**[!UICONTROL 認証]**&#x200B;セクションのみです。

## URL 設定 {#url-configuration}

カスタムアクションを設定する場合、次の **[!UICONTROL URL 設定]**&#x200B;パラメーターを定義する必要があります。

![](../assets/journeyurlconfiguration.png)

1. 「**[!UICONTROL URL]**」フィールドに、外部サービスのURLを指定します。

   * URLが静的な場合は、このフィールドにURLを入力します。

   * URLに動的パスが含まれる場合は、URLの静的な部分（スキーム、ホスト、ポート、オプションでパスの静的な部分）のみを入力します。

      例：`https://xxx.yyy.com:8080/somethingstatic/`

      カスタムアクションをジャーニーに追加する際に、URLの動的パスを指定します。 [詳細情報](../building-journeys/using-custom-actions.md)。
   >[!NOTE]
   >
   >セキュリティ上の理由から、URLにはHTTPSスキームを使用することを強くお勧めします。 また、一般公開されていないアドビのアドレスの使用および IP アドレスの使用は許可されていません。

1. 呼び出し&#x200B;**[!UICONTROL メソッド]**&#x200B;を選択します。**[!UICONTROL POST]** または **[!UICONTROL PUT]** を指定できます。
1. **[!UICONTROL Headers]**&#x200B;セクションで、外部サービスに送信する要求メッセージのHTTPヘッダーを定義します。
   1. ヘッダーフィールドを追加するには、「**[!UICONTROL ヘッダーフィールドを追加]**」をクリックします。
   1. ヘッダーフィールドのキーを入力します。
   1. キーと値のペアに動的な値を設定するには、**[!UICONTROL Variable]**&#x200B;を選択します。 それ以外の場合は、「**[!UICONTROL 定数]**」を選択します。

      例えば、タイムスタンプの場合、動的値を設定できます。

   1. 「**[!UICONTROL 定数]**」を選択した場合は、定数値を入力します。

      **[!UICONTROL 変数]**&#x200B;を選択した場合、カスタムアクションをジャーニーに追加する際にこの変数を指定します。 [詳細情報](../building-journeys/using-custom-actions.md)。

      ![](../assets/journeyurlconfiguration2.png)

   1. ヘッダーフィールドを削除するには、ヘッダーフィールドをポイントし、**[!UICONTROL 削除]**&#x200B;アイコンをクリックします。
   **[!UICONTROL Content-Type]**&#x200B;および&#x200B;**[!UICONTROL Charset]**&#x200B;ヘッダーフィールドは、デフォルトで設定されます。 これらのフィールドは変更または削除できません。

   カスタムアクションをジャーニーに追加した後も、ジャーニーがドラフトステータスの場合は、ヘッダーフィールドを追加できます。 設定の変更によるジャーニーの影響を受けない場合は、カスタムアクションを複製し、新しいカスタムアクションにヘッダーフィールドを追加します。

   >[!NOTE]
   >
   >ヘッダーは、フィールド解析ルールに従って検証されます。 [詳細情報](https://tools.ietf.org/html/rfc7230#section-3.2.4)。

## アクションパラメーターの定義 {#define-the-message-parameters}

![](../assets/messageparameterssection.png)

「**[!UICONTROL アクションパラメーター]**」セクションに、外部サービスに送信する JSON ペイロードの例を貼り付けます。

![](../assets/customactionpayloadmessage.png)

>[!NOTE]
>
>ペイロード内のフィールド名に「.」を含めることはできません。文字。文字「$」で始めることはできません。

パラメーターのタイプ（例：文字列、整数など）を定義できます。

また、パラメーターが定数か変数かを指定することもできます。

* 「定数」は、パラメーターの値が、技術担当者によって「アクション設定」ウィンドウで定義されることを意味します。この値は、ジャーニーをまたいで常に同じになります。ジャーニーでカスタムアクションを使用する場合、この値は変わらず、マーケターには表示されません。例えば、サードパーティのシステムが予期する ID を指定できます。この場合、「定数／変数」トグルの右側にあるフィールドの値が渡されます。
* 変数は、パラメーターの値が変化することを意味します。ジャーニーでこのカスタムアクションを使用するマーケターは、必要な値を渡したり、このパラメーターの値を受け取る場所（例：イベント、Adobe Experience Platform など）を指定したりできます。この場合、「定数／変数」トグルの右側にあるフィールドは、ジャーニーでマーケターがこのパラメーターに名前を付ける際に表示されるラベルです。

![](../assets/customactionpayloadmessage2.png)
