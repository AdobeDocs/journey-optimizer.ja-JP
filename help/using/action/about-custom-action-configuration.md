---
solution: Journey Optimizer
product: journey optimizer
title: カスタムアクションの設定
description: カスタムアクションの設定方法を学ぶ
feature: Actions
topic: Administration
role: Admin
level: Experienced
keywords: アクション, サードパーティ, カスタム, ジャーニー, API
exl-id: 4df2fc7c-85cb-410a-a31f-1bc1ece237bb
source-git-commit: 803c9f9f05669fad0a9fdeeceef58652b6dccf70
workflow-type: tm+mt
source-wordcount: '1045'
ht-degree: 87%

---

# カスタムアクションの設定 {#configure-an-action}

>[!CONTEXTUALHELP]
>id="ajo_journey_action_custom_configuration"
>title="カスタムアクション"
>abstract="サードパーティ製システムを使用してメッセージを送信する場合、またはジャーニーがサードパーティ製システムに API 呼び出しを送信する場合は、カスタムアクションを使用してジャーニーへの接続を設定します。例えば、カスタムアクションを使用して Epsilon、Slack、[Adobe Developer](https://developer.adobe.com/)、Firebase などのシステムに接続できます。"

サードパーティ製システムを使用してメッセージを送信する場合、またはジャーニーがサードパーティ製システムに API 呼び出しを送信する場合は、カスタムアクションを使用してジャーニーへの接続を設定します。例えば、カスタムアクションを使用して Epsilon、Slack、[Adobe Developer](https://developer.adobe.com/){target="_blank"}、Firebase などのシステムに接続できます。

カスタムアクションは、技術ユーザーが定義し、マーケターが使用できる追加のアクションです。設定が完了すると、**[!UICONTROL アクション]**&#x200B;カテゴリの、ジャーニーの左側のパレットに表示されます。詳しくは、[このページ](../building-journeys/about-journey-activities.md#action-activities)を参照してください。

## 制限事項{#custom-actions-limitations}

カスタムアクションには、[このページ](../start/guardrails.md)に一覧表示されるいくつかの制限事項が伴います。

カスタムアクションパラメーターでは、単純なコレクションとオブジェクトのコレクションを渡すことができます。コレクションの制限事項について詳しくは、[このページ](../building-journeys/collections.md#limitations)を参照してください。

また、カスタムアクションパラメーターには想定される形式（例：文字列、10 進数など）があります。これらの想定される形式に従うように注意する必要があります。詳しくは、この[ユースケース](../building-journeys/collections.md)を参照してください。

## 同意とデータガバナンス {#privacy}

Journey Optimizer では、カスタムアクションにデータガバナンスポリシーと同意ポリシーを適用して、特定のフィールドがサードパーティシステムにエクスポートされないようにしたり、メール、プッシュまたは SMS 通信の受信に同意しない顧客を除外したりできます。詳しくは、次のページを参照してください。

* [データガバナンス](../action/action.md)。
* [同意](../action/action.md).


## 設定の手順 {#configuration-steps}

カスタムアクションを設定する際に必要な主な手順は次のとおりです。

1. 管理メニューセクションで、「**[!UICONTROL 設定]**」を選択します。「**[!UICONTROL アクション]**」セクションで、「**[!UICONTROL 管理]**」をクリックします。「**[!UICONTROL アクションを作成]**」をクリックして、新規のアクションを作成します。画面右側にアクション設定ペインが開きます。

   ![](assets/custom2.png)

1. アクションの名前を入力します。

   >[!NOTE]
   >
   >スペースや特殊文字は使用しないでください。30 文字以内にしてください。

1. アクションに説明を追加します。この手順はオプションです。
1. このイベントを使用しているジャーニーの数は、「**[!UICONTROL 使用されている場所]**」フィールドに表示されます。「**[!UICONTROL ジャーニーを表示]**」ボタンをクリックすると、このイベントを使用するジャーニーのリストを表示できます。
1. 様々な **[!UICONTROL URL 設定]**&#x200B;パラメーターを定義します。[このページ](../action/about-custom-action-configuration.md#url-configuration)を参照してください。
1. 「**[!UICONTROL 認証]**」セクションを設定します。この設定はデータソースの場合と同じです。[この節](../datasource/external-data-sources.md#custom-authentication-mode)を参照してください。
1. **[!UICONTROL アクションパラメーター]**&#x200B;を定義します。[このページ](../action/about-custom-action-configuration.md#define-the-message-parameters)を参照してください。
1. 「**[!UICONTROL 保存]**」をクリックします。

   カスタムアクションが設定され、ジャーニーで使用できる状態になります。[このページ](../building-journeys/about-journey-activities.md#action-activities)を参照してください。

   >[!NOTE]
   >
   >ジャーニーでカスタムアクションを使用する場合、ほとんどのパラメーターは読み取り専用です。変更できるのは、**[!UICONTROL 名前]**、**[!UICONTROL 説明]**、**[!UICONTROL URL]** フィールド、および&#x200B;**[!UICONTROL 認証]**&#x200B;セクションのみです。

## URL 設定 {#url-configuration}

カスタムアクションを設定する場合、次の **[!UICONTROL URL 設定]**&#x200B;パラメーターを定義する必要があります。

![](assets/journeyurlconfiguration.png)

1. 「**[!UICONTROL URL]**」フィールドに、外部サービスの URL を指定します。

   * URL が静的な場合は、このフィールドに URL を入力します。

   * URL に動的パスが含まれる場合は、URL の静的な部分（スキーム、ホスト、ポート、オプションでパスの静的な部分）のみを入力します。

      例：`https://xxx.yyy.com/somethingstatic/`

      URL の動的パスは、カスタムアクションをジャーニーに追加する際に指定します。[詳細情報](../building-journeys/using-custom-actions.md)。
   >[!NOTE]
   >
   >セキュリティ上の理由から、URL には HTTPS スキームを使用することを強くお勧めします。また、アドビの非公開アドレスや IP アドレスの使用は許可されていません。
   >
   >カスタムアクションを定義する場合は、デフォルトのポートのみ使用できます。http の場合は 80、https の場合は 443 です。

1. 呼び出し&#x200B;**[!UICONTROL メソッド]**&#x200B;を選択します。**[!UICONTROL POST]** または **[!UICONTROL PUT]** を指定できます。

   >[!NOTE]
   >
   > **DELETE** メソッドはサポートされていません。既存のリソースを更新する必要がある場合は、**PUT** メソッドを選択します。

1. ヘッダーとクエリのパラメーターを定義します。

   * 内 **[!UICONTROL ヘッダー]** セクションで、 **[!UICONTROL ヘッダーフィールドを追加]** 外部サービスに送信する要求メッセージの HTTP ヘッダーを定義する。 **[!UICONTROL Content-Type]** および **[!UICONTROL Charset]** ヘッダーフィールドは、デフォルトで設定されます。これらのフィールドは変更または削除できません。

   * 内 **[!UICONTROL クエリパラメーター]** セクションで、 **[!UICONTROL クエリパラメーターフィールドを追加する]** をクリックして、URL に追加するパラメーターを定義します。

   ![](assets/journeyurlconfiguration2bis.png)

1. フィールドのラベルまたは名前を入力します。

1. タイプを選択します。 **[!UICONTROL 定数]** または **[!UICONTROL 変数]**. 次を選択した場合、 **[!UICONTROL 定数]**&#x200B;をクリックし、 **[!UICONTROL 値]** フィールドに入力します。 「**[!UICONTROL 変数]**」を選択した場合は、カスタムアクションをジャーニーに追加する際に、この変数を指定します。[詳細情報](../building-journeys/using-custom-actions.md)。

   ![](assets/journeyurlconfiguration2.png)

   >[!NOTE]
   >
   >カスタムアクションをジャーニーに追加した後でも、ジャーニーがドラフトステータスの場合は、ヘッダーまたはクエリパラメーターのフィールドを追加できます。 設定の変更によるジャーニーの影響を受けない場合は、カスタムアクションを複製し、新しいカスタムアクションにフィールドを追加します。
   >
   >ヘッダーは、フィールド解析ルールに従って検証されます。詳しくは、[このドキュメント](https://tools.ietf.org/html/rfc7230#section-3.2.4){_blank} を参照してください。

## アクションパラメーターの定義 {#define-the-message-parameters}

「**[!UICONTROL アクションパラメーター]**」セクションに、外部サービスに送信する JSON ペイロードの例を貼り付けます。

![](assets/messageparameterssection.png)

>[!NOTE]
>
>ペイロード例に null 値を含めることはできません。ペイロード内のフィールド名に「.」を含めることはできません。文字。文字「$」で始めることはできません。

パラメーターのタイプ（例：文字列、整数など）を定義できます。

また、パラメーターが定数か変数かを指定することもできます。

* **「定数」は、パラメーターの値が、技術担当者によって「アクション設定」ペインで定義されることを意味します。**&#x200B;この値は、ジャーニーをまたいで常に同じになります。ジャーニーでカスタムアクションを使用する場合、この値は変わらず、マーケターには表示されません。例えば、サードパーティのシステムが予期する ID を指定できます。この場合、「定数／変数」トグルの右側にあるフィールドの値が渡されます。
* **変数は、パラメーターの値が変化することを意味します。**&#x200B;ジャーニーでこのカスタムアクションを使用するマーケターは、必要な値を渡したり、このパラメーターの値をどこから取得するか（例：イベント、Adobe Experience Platform など）を指定したりすることが自由にできます。この場合、定数／変数トグルの右側にあるフィールドは、マーケターがこのパラメーターに名前を付ける際にジャーニーで表示されるラベルです。

![](assets/customactionpayloadmessage2.png)
