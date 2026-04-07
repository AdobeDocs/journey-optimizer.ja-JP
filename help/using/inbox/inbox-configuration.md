---
title: 受信トレイ設定
description: インボックスチャネル設定
feature: Channel Configuration, Content Cards
topic: Content Management
role: Admin
level: Experienced
source-git-commit: d84cc0f4d9226876e55e37409a685550fe0c9050
workflow-type: tm+mt
source-wordcount: '295'
ht-degree: 41%

---

# 受信トレイの設定 {#inbox-configuration}

受信トレイを通じてコンテンツカードエクスペリエンスを配信する前に、**チャネル設定**&#x200B;で&#x200B;**[!UICONTROL 受信トレイ]** チャネル設定を定義する必要があります。 この設定は、サーフェスを同意、オプションのアクセスラベル、およびエクスペリエンスがweb上またはiOSまたはAndroid アプリに表示される場所に関連付けます。 設定を作成するには、次の手順に従います。

1. **[!UICONTROL チャネル]**／**[!UICONTROL 一般設定]**／**[!UICONTROL チャネル設定]**&#x200B;メニューにアクセスし、「**[!UICONTROL チャネル設定を作成]**」をクリックします。

   ![](assets/inbox-configuration-1.png)

1. 設定の名前と説明（オプション）を入力します。

   >[!NOTE]
   >
   > 名前は、文字（A ～ Z）で始める必要があります。使用できるのは英数字のみです。アンダースコア（`_`）、ドット（`.`）、ハイフン（`-`）も使用できます。

1. 設定にカスタムまたはコアのデータ使用ラベルを割り当てるには、「**[!UICONTROL アクセスを管理]**」を選択します。[詳しくは、オブジェクトレベルのアクセス制御（OLAC）を参照してください](../administration/object-based-access.md)。

1. **[!UICONTROL 受信トレイ]** チャネルを選択します。

   ![](assets/inbox-configuration-2.png)

1. この設定を使用してメッセージに同意ポリシーを関連付けるには、**[!UICONTROL マーケティングアクション]**&#x200B;を選択します。顧客の意向に従うために、そのマーケティングアクションに関連付けられているすべての同意ポリシーが活用されます。[詳細情報](../action/consent.md#surface-marketing-actions)

1. インボックスエクスペリエンスを適用するプラットフォームを選択します。

   ![](assets/inbox-configuration-3.png)

1. Web の場合：

   * **[!UICONTROL ページ URL]**&#x200B;で、受信トレイが表示されるページのURLを入力または選択します。 この機能は、エクスペリエンスが1 ページに制限されている場合に使用します。

   * **[!UICONTROL ページ上の場所]**&#x200B;で、ページ内の配置（サイトが受信トレイ サーフェスに使用する地域や識別子など）を定義します。 [詳細情報](../web/web-configuration.md)

     ![](assets/inbox-configuration-4.png)

1. iOS および Android の場合：

   * **[!UICONTROL アプリ ID]**&#x200B;で、アプリのIDを入力または選択して、正しいiOSまたはAndroid ビルドに設定を適用します。

   * **[!UICONTROL アプリ内の場所またはパス]**&#x200B;で、ユーザーが受信トレイを開く画面、ルート、またはコンテナを指定します。

1. 変更を送信します。

インボックスエクスペリエンスの作成時に設定を選択できるようになりました。

➡️ [このページで説明する手順に従います](inbox-create.md)
