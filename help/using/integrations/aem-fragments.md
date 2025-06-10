---
solution: Journey Optimizer
product: journey optimizer
title: AEM コンテンツフラグメント
description: AEM コンテンツフラグメントへのアクセスと管理の方法について説明します。
topic: Content Management
role: User
level: Beginner
exl-id: 57d7c25f-7e39-46ad-85c1-65e2c18e2686
source-git-commit: 7098a643c8026ed00f83a66fd45f957c2403a569
workflow-type: tm+mt
source-wordcount: '623'
ht-degree: 92%

---

# Adobe Experience Manager コンテンツフラグメント {#aem-fragments}

Adobe Experience Manager as a Cloud Service を Adobe Journey Optimizer と統合することで、AEM コンテンツフラグメントを Journey Optimizer のコンテンツにシームレスに組み込めるようになりました。この合理化された接続により、AEM コンテンツへのアクセスと活用のプロセスが簡略化され、パーソナライズされた動的なキャンペーンやジャーニーの作成が可能になります。

AEM コンテンツフラグメントについて詳しくは、Experience Manager ドキュメントの[コンテンツフラグメントの操作](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/sites/administering/content-fragments/content-fragments-with-journey-optimizer){target="_blank"}を参照してください。

>[!AVAILABILITY]
>
>ヘルスケアのお客様の場合、統合は Journey Optimizer Healthcare Shield および Adobe Experience Manager Enhanced Security アドオン製品のライセンスを取得した場合にのみ有効になります。

## 制限事項 {#limitations}

* 誤ったエラーのリスクを減らすために、コンテンツフラグメントを公開するアクセス権を持つユーザー数を制限することをお勧めします。

* 多言語コンテンツの場合、手動フローのみがサポートされます。

* 現在、バリエーションはサポートされていません。

* 公開済みキャンペーンおよびジャーニーのプルーフに、最新のExperience Manager コンテンツフラグメント公開からのデータが反映される。

## Experience Manager でのタグの作成と割り当て

Journey Optimizer でコンテンツフラグメントを使用する前に、Journey Optimizer 専用のタグを作成する必要があります。

1. **Experience Manager** 環境にアクセスします。

1. **ツール**&#x200B;メニューで、「**タグ付け**」を選択します。

   ![](assets/do-not-localize/aem_tag_1.png)

1. 「**タグを作成**」をクリックします。

1. ID が次の構文 `ajo-enabled:{AJO-OrgId}/{AJO-SandboxName}` に従っていることを確認します。

1. 「**作成**」をクリックします。

1. [Experience Manager ドキュメント](https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/sites/administering/content-fragments/content-fragment-models){target="_blank"}の説明に従ってコンテンツフラグメントモデルを定義し、新しく作成した Journey Optimizer タグを割り当てます。

これで、Journey Optimizer で後で使用するためにコンテンツフラグメントの作成と設定を開始できます。詳しくは、[Experience Manager ドキュメント](https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/sites/administering/content-fragments/managing){target="_blank"}を参照してください。

## Experience Manager コンテンツフラグメントの追加 {#aem-add}

AEM コンテンツフラグメントを作成およびパーソナライズした後、それを Journey Optimizer キャンペーンまたはジャーニーに読み込めるようになりました。

1. [キャンペーン](../campaigns/create-campaign.md)または[ジャーニー](../building-journeys/journey-gs.md)を作成します。

1. AEM コンテンツフラグメントにアクセスするには、任意のテキストフィールド内の![パーソナライゼーションアイコン](assets/do-not-localize/Smock_PersonalizationField_18_N.svg)をクリックするか、HTML コンテンツコンポーネントを通じてソースコードを開きます。

   ![](assets/aem_campaign_2.png)

1. 左側のペインの **[!UICONTROL AEM コンテンツフラグメント]**&#x200B;メニューで、「**[!UICONTROL AEM CF セレクターを開く]**」をクリックします。

   ![](assets/aem_campaign_3.png)

1. 使用可能なリストから&#x200B;**[!UICONTROL コンテンツフラグメント]**&#x200B;を選択して、Journey Optimizer コンテンツに読み込みます。

1. 「**[!UICONTROL フィルターを表示]**」をクリックして、コンテンツフラグメントリストを微調整します。

   デフォルトでは、コンテンツフラグメントフィルターは承認済みコンテンツのみを表示するようにプリセットされています。

   ![](assets/aem_campaign_4.png)

1. **[!UICONTROL コンテンツフラグメント]**&#x200B;を選択したら、「**[!UICONTROL 選択]**」をクリックして開きます。

   ![](assets/aem_campaign_5.png)

1. 「**[!UICONTROL フラグメントを表示]**」をクリックして、フラグメント情報を表示します。**[!UICONTROL フラグメント情報]**&#x200B;メニューを開くと、エディターは読み取り専用モードになります。

   Adobe Experience Manager でフラグメントを表示するには、右側のメニューから「**[!UICONTROL プレビュー]**」を選択します。

   ![](assets/aem_campaign_7.png)

1. ![その他のアクションアイコン](assets/do-not-localize/Smock_MoreSmallList_18_N.svg)をクリックして、フラグメントの詳細メニューにアクセスします。

   * **[!UICONTROL フラグメントをスワップ]**
   * **[!UICONTROL 参照を探索]**
   * **[!UICONTROL AEM で開く]**

   ![](assets/aem_campaign_8.png)

1. **[!UICONTROL フラグメント]**&#x200B;から目的のフィールドを選択して、コンテンツに追加します。
   <!--
    Note that if you choose to copy the value, any future updates to the Content Fragment will not be reflected in your campaign or journey. However, using dynamic placeholders ensures real-time updates.-->

   ![](assets/aem_campaign_6.png)

1. リアルタイムのパーソナライゼーションを有効にするには、**[!UICONTROL コンテンツフラグメント]**&#x200B;内で使用されるすべてのプレースホルダーを、フラグメントヘルパータグ内のパラメーターとしてユーザーが明示的に宣言する必要があります。次の方法を使用して、これらのプレースホルダーをプロファイル属性、コンテキスト属性、静的文字列または定義済み変数にマッピングできます。

   1. **プロファイルまたはコンテキスト属性のマッピング**：プレースホルダーをプロファイルまたはコンテキスト属性に割り当てます（例：name = profile.person.name.firstName）。

   1. **静的文字列マッピング**：二重引用符で囲んで固定文字列値を割り当てます（例：name = &quot;John&quot;）。

   1. **変数マッピング**：同じ HTML 内で以前に宣言された変数を参照します（例：name = &#39;variableName&#39;）。
この場合、次の構文を使用して、フラグメント ID を追加する前に、**_variableName_** が宣言されていることを確認します。

      ```html
      {% let variableName = attribute name %} 
      ```

   次の例では、**_名前_**&#x200B;プレースホルダーはフラグメント内の **_profile.person.name.firstName_** 属性にマッピングされています。

   ![](assets/aem_campaign_9.png){zoomable="yes"}


1. 「**[!UICONTROL 保存]**」をクリックします。メッセージのコンテンツをテストして確認するには、[この節](../content-management/preview.md)を参照してください。

テストを実行してコンテンツを検証したら、[キャンペーンを送信](../campaigns/review-activate-campaign.md)したり、オーディエンスに[ジャーニーを公開](../building-journeys/publishing-the-journey.md)したりできます。

Adobe Experience Managerを使用すると、コンテンツフラグメントが使用されているJourney Optimizer キャンペーンまたはジャーニーを特定できます。 詳しくは、[Adobe Experience Manager ドキュメント ](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/sites/administering/content-fragments/extension-content-fragment-ajo-external-references) を参照してください。
