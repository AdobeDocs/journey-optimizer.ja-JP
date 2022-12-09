---
solution: Journey Optimizer
product: journey optimizer
title: カスタムアクションの設定
description: カスタムアクションの設定方法について説明しています。
feature: Actions
topic: Administration
role: Admin
level: Intermediate
exl-id: 4df2fc7c-85cb-410a-a31f-1bc1ece237bb
source-git-commit: d17e64e03d093a8a459caef2fb0197a5710dfb7d
workflow-type: tm+mt
source-wordcount: '1003'
ht-degree: 0%

---

# カスタムアクションの設定 {#configure-an-action}

>[!CONTEXTUALHELP]
>id="ajo_journey_action_custom_configuration"
>title="カスタムアクション"
>abstract="サードパーティシステムを使用してメッセージを送信する場合や、サードパーティシステムに journeys を送信する場合は、カスタムアクションを使用して、その接続を設定します。 例えば、カスタムアクション (イプシロン、余裕期間、 [ Adobe Developer ](https://developer.adobe.com) 、焼討基地など) を使用して次のシステムに接続できます。"

サードパーティシステムを使用してメッセージを送信する場合や、サードパーティシステムに journeys を送信する場合は、カスタムアクションを使用して、その接続を設定します。 例えば、カスタムアクションを使用して次のシステムに接続できます。: イプシロン、余裕期間、 [ Adobe Developer ](https://developer.adobe.com) {target = &quot;_blank&quot;}、焼討ベースなど

カスタムアクションは、テクニカルユーザーによって定義された追加のアクションで、マーケティング担当者に公開されています。 設定すると、旅の左側のパレットにカテゴリーで **[!UICONTROL Action]** 表示されます。 詳しくは、このページ ](../building-journeys/about-journey-activities.md#action-activities) を [ 参照してください。

## 限界{#custom-actions-limitations}

カスタムアクションについては、このページ ](../start/guardrails.md) に [ 一覧表示されているいくつかの制限があります。

カスタムアクションパラメーターでは、簡単なコレクションだけでなく、オブジェクトのコレクションも渡すことができます。 コレクションの制限について詳しくは、このページ ](../building-journeys/collections.md#limitations) を [ 参照してください。

さらに、カスタムアクションのパラメーターには、必要な形式 (「string」、「decimal」など) が指定されていることに注意してください。 このような予想されるフォーマットを使用するには注意が必要です。 この [ ような使用例 ](../building-journeys/collections.md) について詳しくは、こちらを参照してください。

## 同意およびデータガバナンス {#privacy}

このような場合、カスタムアクションにはデータガバナンスと同意ポリシーを適用して、特定のフィールドをサードパーティシステムに書き出さないようにすることや、電子メールの受信を consented にしていないユーザーを除外することができます。 詳しくは、次のページを参照してください。

* [データガバナンス ](../action/action.md)
* [同意 ](../action/action.md) を得ることができます。


## 設定手順 {#configuration-steps}

カスタムアクションを設定するには、次の手順を実行する必要があります。

1. 「管理メニュー」セクションで、を選択 **[!UICONTROL Configurations]** します。 **[!UICONTROL Actions]**&#x200B;セクションのをクリック **[!UICONTROL Manage]** します。新しいアクションを作成するには、をクリック **[!UICONTROL Create Action]** します。 画面の右側に、操作設定ウィンドウが表示されます。

   ![](assets/custom2.png)

1. アクションの名前を入力します。

   >[!NOTE]
   >
   >スペースまたは特殊文字は使用しないでください。 30文字を超えないようにしてください。

1. アクションに説明を追加します。 この手順はオプションです。
1. このアクションを使用している journeys の数がフィールドに **[!UICONTROL Used in]** 表示されます。 このアクションを使用して journeys のリストを表示するには、 **[!UICONTROL View journeys]** ボタンをクリックします。
1. 様々な **[!UICONTROL URL Configuration]** パラメーターを定義します。 このページ ](../action/about-custom-action-configuration.md#url-configuration) を参照してください [ 。
1. セクションを **[!UICONTROL Authentication]** 設定します。 この設定はデータソースと同じです。  この項 ](../datasource/external-data-sources.md#custom-authentication-mode) を参照してください [ 。
1. を **[!UICONTROL Action parameters]** 定義します。 このページ ](../action/about-custom-action-configuration.md#define-the-message-parameters) を参照してください [ 。
1. をクリック **[!UICONTROL Save]** します。

   これで、カスタムアクションが設定され、journeys に使用できるようになりました。 このページ ](../building-journeys/about-journey-activities.md#action-activities) を参照してください [ 。

   >[!NOTE]
   >
   >カスタムアクションが旅に使用された場合、ほとんどのパラメーターは読み取り専用になります。 、、フィールド **[!UICONTROL Authentication]** 、セクションの変更 **[!UICONTROL URL]** **[!UICONTROL Name]** **[!UICONTROL Description]** のみができます。

## URL の設定 {#url-configuration}

カスタムアクションを設定する場合は、次 **[!UICONTROL URL Configuration]** のパラメーターを定義する必要があります。

![](assets/journeyurlconfiguration.png)

1. **[!UICONTROL URL]**「」フィールドで、次のように外部サービスの URL を指定します。

   * URL が静的な場合は、このフィールドに URL を入力します。

   * URL に動的パスが含まれている場合は、URL の静的な部分 (スキーム、ホスト、ポート、および必要に応じてパスの静的な部分) のみを入力します。

      一 `https://xxx.yyy.com/somethingstatic/`

      カスタムアクションを旅に追加する場合は、URL の動的パスを指定します。 [詳しく ](../building-journeys/using-custom-actions.md) は、こちらを参照してください。
   >[!NOTE]
   >
   >セキュリティ上の理由から、URL には HTTPS スキームを使用することを強くお勧めします。 公共の、または IP アドレスを使用していない Adobe アドレスを使用することはできません。
   >
   >カスタムアクションの定義時には、デフォルトのポート 443 80 のみが許可されます。

1. 「呼び出し **[!UICONTROL Method]** 」を選択します。または **[!UICONTROL PUT]** 、のいずれか **[!UICONTROL POST]** を指定できます。

   >[!NOTE]
   >
   > **DELETE** メソッドはサポートされていません。既存のリソースを更新する必要がある場合は、PUT **メソッドを選択** します。

1. **[!UICONTROL Headers]**&#x200B;セクションで、次のように、外部サービスに送信される要求メッセージの HTTP ヘッダーを定義します。
   1. ヘッダーフィールドを追加するには、をクリック **[!UICONTROL Add a header field]** します。
   1. ヘッダフィールドのキーを入力します。
   1. キーと値のペアに動的な値を設定するには、「」を選択 **[!UICONTROL Variable]** します。 それ以外の場合は、を選択 **[!UICONTROL Constant]** します。

      例えば、タイムスタンプに動的な値を設定することができます。

   1. 「」を選択 **[!UICONTROL Constant]** した場合は、定数値を入力します。

      この設定を選択 **[!UICONTROL Variable]** した場合は、カスタムアクションを旅に追加するときに、この変数を指定します。 [詳しく ](../building-journeys/using-custom-actions.md) は、こちらを参照してください。

      ![](assets/journeyurlconfiguration2.png)

   1. ヘッダフィールドを削除するには、ヘッダフィールドをポイントしてアイコンをクリック **[!UICONTROL Delete]** します。
   **[!UICONTROL Content-Type]**「」および **[!UICONTROL Charset]** 「ヘッダ」フィールドはデフォルトで設定されています。これらのフィールドを変更または削除することはできません。

   カスタムアクションを追加した後も、その旅がドラフト状態である場合は、ヘッダーフィールドを追加することができます。 設定を変更しても、旅には反映されないようにするには、カスタムアクションを複製し、新しいカスタムアクションにヘッダフィールドを追加します。

   >[!NOTE]
   >
   >ヘッダーは、フィールド解析ルールに従って検証されます。 詳細については、このドキュメント ](https://tools.ietf.org/html/rfc7230#section-3.2.4) の _blank} を [ 参照してください。

## アクションパラメーターの定義 {#define-the-message-parameters}

![](assets/messageparameterssection.png)

**[!UICONTROL Action parameters]**&#x200B;セクションで、外部サービスに送信する JSON ペイロードの例をペーストします。

![](assets/customactionpayloadmessage.png)

>[!NOTE]
>
>Payload の例に null 値を含めることはできません。 ペイロードのフィールド名に &quot;.&quot; を含めることはできません。 文字. 「$」文字を使用して開始することはできません。

パラメーターの型を定義することができます (例: string、integer、など)。

また、パラメーターが定数または変数のどちらであるかを指定することもできます。

* 定数は、このパラメーターの値が「アクションの構成」ペインで技術的なペルソナによって定義されていることを意味します。 Journeys では、常に同じ値が表示されます。 このような場合は、カスタムアクションを使用しても、marketer は変更されません。 例えば、サードパーティ製システムが予期していた ID を使用できます。 このような場合は、定数の表示/非表示の右側にあるフィールドが引き渡される値になります。
* Variable は、パラメーターの値が変化することを意味します。 このカスタムアクションを使用して行うマーケティング担当は、必要な値を渡したり、このパラメーターの値を取得する場所を指定することができます (例えば、イベント、Adobe 経験プラットフォームなど)。 この場合、切り替え定数/変数の右側に表示されるフィールドは、このパラメーターの名前を示すために、各マーケティング担当が旅に出てきたラベルになります。

![](assets/customactionpayloadmessage2.png)
