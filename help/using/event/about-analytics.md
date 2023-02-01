---
solution: Journey Optimizer
product: journey optimizer
title: Adobe Analytics の統合
description: Adobe Analytics データの活用方法について説明します
feature: Events
topic: Administration
role: Admin
level: Intermediate
keywords: 分析, 統合, web sdk, Platform
exl-id: 9d842722-e5eb-4743-849d-b7ba9448062f
source-git-commit: c0afa3e2bc6dbcb0f2f2357eebc04285de8c5773
workflow-type: ht
source-wordcount: '618'
ht-degree: 100%

---

# Adobe Analytics の統合 {#analytics-data}

## Adobe Analytics または Web SDK データの活用 {#leverage-analytics-data}

ジャーニーをトリガーし顧客向けのエクスペリエンスを自動化するために、既にキャプチャして Adobe Experience Platform にストリーミングしている web のあらゆる行動イベントデータを（Adobe Analytics または Web SDK を介して）活用できます。

>[!NOTE]
>
>この節は、ルールベースのイベントと、Adobe Analytics または Web SDK データを使用する必要があるお客様が対象です。

Adobe Analytics と連携させるには、利用するレポートスイートを Adobe Experience Platform で有効化する必要があります。これを行うには、以下の手順に従います。

1. Adobe Experience Platform に接続し、**[!UICONTROL ソース]**&#x200B;を参照します。

1. 「Adobe Analytics」セクションで、「**[!UICONTROL データを追加]**」を選択します。

   ![](assets/ajo-aa_1.png)

1. 使用可能な Adobe Analytics レポートスイートのリストから、有効にする&#x200B;**[!UICONTROL レポートスイート]**&#x200B;を選択します。次に、「**[!UICONTROL 次へ]**」をクリックします。

   ![](assets/ajo-aa_2.png)

1. デフォルトスキーマまたはカスタムスキーマを使用するかどうかを選択します。

1. **[!UICONTROL データフローの詳細]**&#x200B;画面から、「**[!UICONTROL データフロー名]**」を選択します。

1. 設定が完了したら、「**[!UICONTROL 終了]**」をクリックします。

   ![](assets/ajo-aa_3.png)

これにより、そのレポートスイートの Analytics ソースコネクタが有効になります。データが入ってくるたびに、データはエクスペリエンスイベントに変換され、Adobe Experience Platform に送信されます。

![](assets/ajo-aa_4.png)

Adobe Analytics ソースコネクタについて詳しくは、[Adobe Experience Platform ドキュメント](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=ja){target="_blank"} and [tutorial](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=ja){target="_blank"}を参照してください。

## Adobe Analytics または Web SDK データを使用したイベントでのジャーニーの作成 {#event-analytics}

[Adobe Analytics ソース](#leverage-analytics-data)または [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=ja) を使用して Adobe Analytics との統合を実装したら、後でジャーニーで使用できるイベントを作成できます。

この例では、製品を買い物かごに追加したユーザーをターゲットにします。

* 注文が完了すると、2 日後にフィードバックを求めるフォローアップメールが届きます。
* 注文が完了していない場合は、注文を完了するように通知するメールが届きます。

1. Adobe Journey Optimizer から、**[!UICONTROL 設定]**&#x200B;メニューにアクセスします。

1. 次に、**[!UICONTROL イベント]**&#x200B;カードから「**[!UICONTROL 管理]**」を選択します。

   ![](assets/ajo-aa_5.png)

1. 「**[!UICONTROL イベントを作成]**」をクリックします。画面の右側にイベント設定ペインが開きます。

1. 次の&#x200B;**[!UICONTROL イベント]**&#x200B;パラメーターを入力します。

   * **[!UICONTROL 名前]**：**[!UICONTROL イベント]**&#x200B;の名前をパーソナライズします。
   * **[!UICONTROL タイプ]**：**[!UICONTROL 単一]**&#x200B;タイプを選択します。[詳細情報](../event/about-events.md)
   * **[!UICONTROL イベント ID タイプ]**：**[!UICONTROL ルールベース]**&#x200B;のイベント ID タイプを選択します。[詳細情報](../event/about-events.md#event-id-type)
   * **[!UICONTROL スキーマ]**：上記の節で作成した Analytics または Web SDK のスキーマを選択します。
   * **[!UICONTROL フィールド]**：「ペイロード」フィールドを選択します。[詳細情報](../event/about-creating.md#define-the-payload-fields)
   * **[!UICONTROL イベント ID 条件]**：簡単な式エディターを使用して、ジャーニーをトリガーするイベントを識別するためにシステムが使用する条件を定義します。

      ここでは、顧客が買い物かごにアイテムを追加すると、イベントがトリガーされます。
   * **[!UICONTROL プロファイル識別子]**：ペイロードフィールドからフィールドを選択するか、イベントに関連付けられた個人を識別する式を定義します。

   ![](assets/ajo-aa_6.png)

1. 設定したら、「**[!UICONTROL 保存]**」を選択します。これで、イベントをジャーニーで使用できるようになります。

1. これで、**[!UICONTROL ジャーニー]**&#x200B;から、ジャーニーの作成を開始できます。詳しくは、[この節](../building-journeys/journey-gs.md)を参照してください。

1. 以前に設定した Analytics イベントをジャーニーに追加します。

   ![](assets/ajo-aa_8.png)

1. 注文が完了した場合にトリガーされるイベントを追加します。

1. **[!UICONTROL イベントメニュー]**&#x200B;から、「**[!UICONTROL イベントのタイムアウトを定義]**」および「**[!UICONTROL タイムアウトパスを設定]**」オプションを選択します。

   ![](assets/ajo-aa_9.png)

1. タイムアウトパスから、**[!UICONTROL メール]**&#x200B;アクションを追加します。このパスは、注文を完了していない顧客にメールを送信して、買い物かごがまだ使用可能であることを通知するために使用されます。

1. **[!UICONTROL 待機]**&#x200B;アクティビティをメインパスの後に追加し、必要な期間に設定します。

   ![](assets/ajo-aa_10.png)

1. 次に、**[!UICONTROL メールアクション]**&#x200B;を追加します。このメールでは、顧客は注文に関するフィードバックを提供するよう求められます。

これで、有効性をテストした後にジャーニーを公開できます。[詳細情報](../building-journeys/publishing-the-journey.md)

![](assets/ajo-aa_7.png)
