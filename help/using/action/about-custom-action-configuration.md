---
solution: Journey Optimizer
product: journey optimizer
title: カスタムアクションの設定
description: カスタムアクションの設定方法を学ぶ
feature: Journeys, Actions, Custom Actions
topic: Administration
role: Data Engineer, Data Architect, Admin
level: Experienced
keywords: アクション, サードパーティ, カスタム, ジャーニー, API
exl-id: 4df2fc7c-85cb-410a-a31f-1bc1ece237bb
source-git-commit: 067c990f7f82594418d59c3b1587a62a04799c09
workflow-type: tm+mt
source-wordcount: '1561'
ht-degree: 93%

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

カスタムアクションは、[リクエスト](../action/about-custom-action-configuration.md#define-the-message-parameters)または[応答ペイロード](../action/action-response.md)を使用する際にのみ JSON 形式をサポートします。

## ベストプラクティス{#custom-action-enhancements-best-practices}

ターゲットにするエンドポイントをカスタムアクションを使用して選択する場合は、次の点を確認します。

* このエンドポイントは、[Throttling API](../configuration/throttling.md) または [Capping API](../configuration/capping.md) の設定を使用してジャーニーのスループットを制限することでサポートできます。スロットル設定は、200 TPS を下回ることはできません。ターゲットにするエンドポイントは、200 TPS 以上をサポートする必要があります。
* このエンドポイントの応答時間は、できるだけ短くする必要があります。求めるスループットによっては、応答時間が長いと、実際のスループットに影響を与える可能性があります。

すべてのカスタムアクションには、1 分間に 300,000 件の呼び出しというキャッピングが定義されています。また、デフォルトのキャッピングは、ホストごとおよびサンドボックスごとに実行されます。例えば、サンドボックスで、同じホストに 2 つのエンドポイントがある場合（例：`https://www.adobe.com/endpoint1` と `https://www.adobe.com/endpoint2`）、キャッピングは adobe.com ホストの下にあるすべてのエンドポイントに適用されます。「endpoint1」と「endpoint2」は同じキャッピング設定を共有し、一方のエンドポイントが制限に達すると、もう一方のエンドポイントに影響が生じます。

この制限は、カスタムアクションの対象となる外部エンドポイントを保護するために、顧客の使用状況に基づいて設定されています。適切な読み取り率（カスタムアクションを使用する場合は 5,000 件のプロファイル）を定義して、オーディエンスベースのジャーニーでこの点を考慮する必要があります。必要に応じて、キャッピング／スロットリング API で上限またはスロットル制限を大きく定義することで、この設定を上書きできます。[このページ](../configuration/external-systems.md)を参照してください。

次に示すような様々な理由により、カスタムアクションを使用してパブリックエンドポイントをターゲット設定しないでください。

* 適切な制限やスロットルがない場合、パブリックエンドポイントに対して過剰な呼び出しが送信される恐れがあり、その量に対応できない可能性があります。
* プロファイルデータは、カスタムアクションを通じて送信できるため、パブリックエンドポイントをターゲットに設定すると、誤って個人情報を外部と共有してしまう可能性があります。
* パブリックエンドポイントから返されるデータを制御できません。エンドポイントの API を変更した場合や誤った情報の送信を開始した場合は、送信された通信でそれらの情報が使用可能になり、悪影響が出る可能性があります。

## 同意とデータガバナンス {#privacy}

Journey Optimizer では、カスタムアクションにデータガバナンスポリシーと同意ポリシーを適用して、特定のフィールドがサードパーティシステムにエクスポートされないようにしたり、メール、プッシュまたは SMS 通信の受信に同意しない顧客を除外したりできます。詳しくは、次のページを参照してください。

* [データガバナンス](../action/action-privacy.md)。
* [同意](../action/action-privacy.md).


## 設定の手順 {#configuration-steps}

カスタムアクションを設定する際に必要な主な手順は次のとおりです。

1. 管理メニューセクションで、「**[!UICONTROL 設定]**」を選択します。「**[!UICONTROL アクション]**」セクションで、「**[!UICONTROL 管理]**」をクリックします。「**[!UICONTROL アクションを作成]**」をクリックして、新規のアクションを作成します。画面右側にアクション設定ペインが開きます。

   ![](assets/custom2.png)

1. アクションの名前を入力します。

   >[!NOTE]
   >
   >英数字とアンダースコアのみが使用できます。最大長は 30 文字です。

1. アクションに説明を追加します。この手順はオプションです。
1. このアクションを使用しているジャーニーの数は、「**[!UICONTROL 使用されている場所]**」フィールドに表示されます。「**[!UICONTROL ジャーニーを表示]**」ボタンをクリックすると、このアクションを使用するジャーニーのリストを表示できます。
1. 様々な **[!UICONTROL URL 設定]**&#x200B;パラメーターを定義します。[このページ](../action/about-custom-action-configuration.md#url-configuration)を参照してください。
1. 「**[!UICONTROL 認証]**」セクションを設定します。この設定はデータソースの場合と同じです。[この節](../datasource/external-data-sources.md#custom-authentication-mode)を参照してください。
1. **[!UICONTROL アクションパラメーター]**&#x200B;を定義します。[このページ](../action/about-custom-action-configuration.md#define-the-message-parameters)を参照してください。
1. 「**[!UICONTROL 保存]**」をクリックします。

   カスタムアクションが設定され、ジャーニーで使用できる状態になります。[このページ](../building-journeys/about-journey-activities.md#action-activities)を参照してください。

   >[!NOTE]
   >
   >ジャーニーでカスタムアクションを使用する場合、ほとんどのパラメーターは読み取り専用です。変更できるのは、**[!UICONTROL 名前]**、**[!UICONTROL 説明]**、**[!UICONTROL URL]** フィールド、および&#x200B;**[!UICONTROL 認証]**&#x200B;セクションのみです。

## エンドポイントの設定 {#url-configuration}

カスタムアクションを設定する際に、次の&#x200B;**[!UICONTROL エンドポイント設定]**&#x200B;パラメーターを定義する必要があります。

![](assets/action-response1bis.png){width="70%" align="left"}

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

1. 呼び出し&#x200B;**[!UICONTROL メソッド]**&#x200B;を選択します。**[!UICONTROL POST]**、**[!UICONTROL GET]** または **[!UICONTROL PUT]** を選択できます。

   >[!NOTE]
   >
   > **DELETE** メソッドはサポートされていません。既存のリソースを更新する必要がある場合は、**PUT** メソッドを選択します。

1. ヘッダーとクエリパラメーターを定義：

   * 「**[!UICONTROL ヘッダー]**」セクションで「**[!UICONTROL ヘッダーフィールドを追加]**」をクリックし、外部サービスに送信されるリクエストメッセージの HTTP ヘッダーを定義します。**[!UICONTROL Content-Type]** および **[!UICONTROL Charset]** ヘッダーフィールドは、デフォルトで設定されます。これらのフィールドは削除できません。**[!UICONTROL Content-Type]** ヘッダーのみを変更できます。この値は JSON 形式に従う必要があります。デフォルト値は次のとおりです。

   ![](assets/content-type-header.png)

   * 「**[!UICONTROL クエリパラメーター]**」セクションで「**[!UICONTROL クエリパラメーターフィールドを追加]**」をクリックして、URL に追加するパラメーターを定義します。

   ![](assets/journeyurlconfiguration2bis.png)

1. フィールドのラベルまたは名前を入力します。

1. タイプを選択：**[!UICONTROL 定数]**&#x200B;または&#x200B;**[!UICONTROL 変数]**。**[!UICONTROL 定数]**&#x200B;を選択した場合は、**[!UICONTROL 値]**&#x200B;フィールドに定数の値を入力します。「**[!UICONTROL 変数]**」を選択した場合は、カスタムアクションをジャーニーに追加する際に、この変数を指定します。[詳細情報](../building-journeys/using-custom-actions.md)。

   ![](assets/journeyurlconfiguration2.png)

   >[!NOTE]
   >
   >カスタムアクションをジャーニーに追加した後でも、ジャーニーがドラフトステータスの場合は、ヘッダーフィールドまたはクエリパラメータフィールドを追加できます。設定変更によってジャーニーに影響を与えたくない場合は、カスタムアクションを複製し、フィールドを新しいカスタムアクションに追加します。
   >
   >ヘッダーは、フィールド解析ルールに従って検証されます。詳しくは、[このドキュメント](https://tools.ietf.org/html/rfc7230#section-3.2.4){_blank} を参照してください。

## mTLS プロトコルのサポート {#mtls-protocol-support}

相互トランスポート層セキュリティ（mTLS）を使用して、Adobe Journey Optimizer カスタムアクションへの送信接続のセキュリティを強化できるようになりました。 mTLS は、相互認証のためのエンドツーエンドのセキュリティ方法であり、情報を共有する両方の関係者が、データが共有される前に主張している人物であることを保証します。 mTLS には、TLS と比較して追加の手順が含まれています。この手順では、サーバーもクライアントの証明書を要求し、最後に確認します。

カスタムアクションでは、相互 TLS （mTLS）認証がサポートされています。 カスタムアクションやジャーニーでは、mTLS を有効化するために追加の設定は必要ありません。mTLS が有効なエンドポイントが検出されると、この設定は自動的に行われます。 [詳細情報](https://experienceleague.adobe.com/en/docs/experience-platform/landing/governance-privacy-security/encryption#mtls-protocol-support)。

## ペイロードパラメーターの定義 {#define-the-message-parameters}

1. 「**[!UICONTROL リクエスト]**」セクションに、外部サービスに送信する JSON ペイロードの例をペーストします。このフィールドはオプションで、POST および PUT 呼び出しメソッドでのみ使用できます。

1. 「**[!UICONTROL 応答]**」セクションに、呼び出しで返されたペイロードの例をペーストします。このフィールドはオプションで、すべての呼び出しメソッドで使用できます。カスタムアクションで API 呼び出し応答を活用する方法について詳しくは、[このページ](../action/action-response.md)を参照してください。

>[!NOTE]
>
>現在、応答機能はベータ版で利用できます。

![](assets/action-response2bis.png){width="70%" align="left"}

>[!NOTE]
>
>ペイロード例に null 値を含めることはできません。ペイロード内のフィールド名に「.」を含めることはできません。文字。文字「$」で始めることはできません。

パラメーターのタイプ（例：文字列、整数など）を定義できます。

また、パラメーターが定数か変数かを指定することもできます。

* **定数**&#x200B;は、パラメーターの値が、技術担当者によって「アクション設定」ペインで定義されることを意味します。この値は、ジャーニーをまたいで常に同じになります。ジャーニーでカスタムアクションを使用する場合、この値は変わらず、マーケターには表示されません。例えば、サードパーティのシステムが予期する ID を指定できます。この場合、「定数／変数」トグルの右側にあるフィールドの値が渡されます。
* **変数**&#x200B;は、パラメーターの値が変化することを意味します。ジャーニーでこのカスタムアクションを使用するマーケターは、必要な値を渡したり、このパラメーターの値をどこから取得するか（例：イベント、Adobe Experience Platform など）を指定したりすることが自由にできます。この場合、定数／変数トグルの右側にあるフィールドは、マーケターがこのパラメーターに名前を付ける際にジャーニーで表示されるラベルです。

![](assets/customactionpayloadmessage2.png)
