---
solution: Journey Orchestration
title: カスタムアクション設定について
description: カスタムアクションの設定方法を学びます。
translation-type: tm+mt
source-git-commit: 55b9e5d8ed259ec6ed7746e835691d7d6261a8a4
workflow-type: tm+mt
source-wordcount: '603'
ht-degree: 8%

---

# アクションの設定 {#configure-an-action}

![](../assets/do-not-localize/badge.png)

サードパーティ製システムを使用してメッセージを送信する場合、またはジャーニーがサードパーティ製システムにAPI呼び出しを送信する場合は、ここでジャーニーへの接続を設定します。 技術ユーザーが定義したカスタムアクションは、ジャーニーの左側のパレットの&#x200B;**[!UICONTROL アクション]**&#x200B;カテゴリーで利用できます（[このページ](../building-journeys/about-journey-activities.md#action-activities)を参照）。 次に、カスタムアクションを使用して接続できるシステムの例を示します。イプシロン、Facebook、Adobe.io、Firebaseなど
[このページ](../building-journeys/limitations.md)には制限が記載されています。

カスタムアクションを設定する際に必要な主な手順は次のとおりです。

1. **[!UICONTROL アクション]**&#x200B;リストで、**[!UICONTROL 追加]**&#x200B;をクリックして、新しいアクションを作成します。 アクション設定ペインが画面の右側に開きます。

   ![](../assets/custom2.png)

1. アクションの名前を入力します。

   >[!NOTE]
   >
   >スペースや特殊文字は使用しないでください。30 文字以内にしてください。

1. ア追加クションの説明。 この手順はオプションです。
1. このアクションを使用するジャーニーの数は、「**[!UICONTROL 使用場所]**」フィールドに表示されます。 「**[!UICONTROL 表示ジャーニー]**」ボタンをクリックすると、このアクションを使用するジャーニーのリストを表示できます。
1. 様々な&#x200B;**[!UICONTROL URL設定]**&#x200B;パラメーターを定義します。 [このページ](../action/about-custom-action-configuration.md#url-configuration)を参照してください。
1. **[!UICONTROL 認証]**&#x200B;セクションを設定します。 この設定は、データソースの場合と同じです。  詳しくは、[この節](../datasource/external-data-sources.md#section_wjp_nl5_nhb)を参照してください。
1. **[!UICONTROL メッセージパラメーター]**&#x200B;を定義します。 [このページ](../action/about-custom-action-configuration.md#define-the-message-parameters)を参照してください。
1. 「**[!UICONTROL 保存]**」をクリックします。

   これで、カスタムアクションが設定され、ジャーニーで使用できる状態になりました。 [このページ](../building-journeys/about-journey-activities.md#action-activities)を参照してください。

   >[!NOTE]
   >
   >ジャーニーでカスタムアクションを使用する場合、ほとんどのパラメーターは読み取り専用です。 **[!UICONTROL 名前]**、**[!UICONTROL 説明]**、**[!UICONTROL URL]**&#x200B;フィールド、および&#x200B;**[!UICONTROL 認証]**&#x200B;セクションのみを変更できます。

## URL 設定 {#url-configuration}

カスタムアクションを設定する場合、次の&#x200B;**[!UICONTROL URL Configuration]**&#x200B;パラメーターを定義する必要があります。

![](../assets/journeyurlconfiguration.png)

1. 追加外部サービスの&#x200B;**[!UICONTROL URL]**。

   >[!NOTE]
   >
   >セキュリティ上の理由から、HTTPS の使用を強くお勧めします。パブリックでないAdobeアドレスの使用とIPアドレスの使用は許可されません。

1. 呼び出し&#x200B;**[!UICONTROL メソッド]**&#x200B;を選択します。**[!UICONTROL POST]**&#x200B;または&#x200B;**[!UICONTROL PUT]**&#x200B;を指定できます。
1. 「**[!UICONTROL ヘッダー]**」セクションで、**[!UICONTROL ヘッダーフィールド追加]**&#x200B;をクリックして、新しいキーと値のペアを定義します。 これらは、外部サービスに対して行われた要求のHTTPヘッダーに対応します。 キーと値のペアを削除するには、**[!UICONTROL ヘッダー]**&#x200B;フィールドにカーソルを置き、**[!UICONTROL 削除]**&#x200B;アイコンをクリックします。

   **[!UICONTROL Content-]** Typeと **** Charsetはデフォルトで設定され、削除または上書きはできません。

   >[!NOTE]
   >
   >以下の[解析ルール](https://tools.ietf.org/html/rfc7230#section-3.2.4)に従って、ヘッダーの検証が行われます。

## メッセージのパラメーターを定義{#define-the-message-parameters}

![](../assets/messageparameterssection.png)

**[!UICONTROL Message parameters]**&#x200B;セクションに、外部サービスに送信するJSONペイロードの例を貼り付けます。

![](../assets/customactionpayloadmessage.png)

パラメーターのタイプを定義できます(例：文字列、整数など)。

また、パラメーターが定数か変数かを指定することもできます。

* 「定数」は、パラメーターの値が、アクション設定ウィンドウで技術的な人物によって定義されることを意味します。 この値は、ジャーニー間で常に同じになります。 ジャーニーでカスタムアクションを使用する場合、この値は変わらず、マーケティング担当者には表示されません。 例えば、サードパーティのシステムが予期するIDを指定できます。 この場合、トグル定数/変数の右側にあるフィールドが渡される値です。
* 変数は、パラメーターの値が変化することを意味します。 ジャーニーでこのカスタムアクションを使用するマーケターは、自由に、必要な値を渡したり、このイベントーの値を取得する場所を指定したりできます(例：パラメーター、Adobe Experience Platformなど)。 この場合、トグル定数/変数の右側にあるフィールドが、ジャーニーーに表示されるラベルで、このパラメーターに名前を付けます。

![](../assets/customactionpayloadmessage2.png)
