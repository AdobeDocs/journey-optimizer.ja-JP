---
solution: Journey Optimizer
product: journey optimizer
title: AEM コンテンツフラグメント
description: AEM コンテンツフラグメントへのアクセスと管理の方法について説明します。
topic: Content Management
role: User
level: Beginner
exl-id: 57d7c25f-7e39-46ad-85c1-65e2c18e2686
source-git-commit: 92690f1b3f73c75d9b81746b49836a24ebf7c457
workflow-type: tm+mt
source-wordcount: '1510'
ht-degree: 37%

---

# Adobe Experience Manager コンテンツフラグメント {#aem-fragments}

Adobe Experience Manager as a Cloud Service を Adobe Journey Optimizer と統合することで、AEM コンテンツフラグメントを Journey Optimizer のコンテンツにシームレスに組み込めるようになりました。この合理化された接続により、AEM コンテンツへのアクセスと活用のプロセスが簡略化され、パーソナライズされた動的なキャンペーンやジャーニーの作成が可能になります。

AEM コンテンツフラグメントについて詳しくは、Experience Manager ドキュメントの[コンテンツフラグメントの操作](https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/sites/administering/content-fragments/content-fragments-with-journey-optimizer){target="_blank"}を参照してください。

## 開始する前に {#start}

>[!AVAILABILITY]
>
>ヘルスケアのお客様の場合、統合は Journey Optimizer Healthcare Shield および Adobe Experience Manager Enhanced Security アドオン製品のライセンスを取得した場合にのみ有効になります。

### 制限事項 {#limitations}

Journey OptimizerでAdobe Experience Manager コンテンツフラグメントを使用する場合は、次の制限事項に注意してください。

* **コンテンツフラグメントタイプ**：シンプルなコンテンツフラグメントとネストされたコンテンツフラグメントがサポートされます。 コンテンツフラグメントのバリエーションは、現在サポートされていません。

* **多言語コンテンツ**：手動フローのみがサポートされます。 各言語バリアントは、Adobe Experience Managerで個別にオーサリングし、タグ付けおよび公開し、Journey Optimizerで手動で選択する必要があります。 自動言語の解決やフォールバックのメカニズムはありません。

* **リポジトリアクセス**:Journey Optimizerは、Adobe Experience Manager パブリッシュ層とのみ統合されます。この層では、認証されていないパブリックエンドポイントを介してコンテンツフラグメントを利用できます。 オーサーリポジトリがリポジトリセレクターに表示される場合がありますが、Journey Optimizerで使用できるのはパブリッシュ層に公開されたコンテンツフラグメントのみです。

* **コンテンツフラグメントのステータス**:Journey Optimizerには、「公開済み **&#x200B;**&#x200B;および **変更済み** ステータスのコンテンツフラグメントが表示されます。 いずれの場合も、最新の公開済みバージョンのみが使用されます。 公開後にフラグメントが変更された場合、その変更は、コンテンツフラグメントがJourney Optimizerで再公開されるまで、Adobe Experience Managerには反映されません。 Adobe Experience ManagerとJourney Optimizerの間には、バージョンの自動調整は行われません。

* **Personalization**: プロファイル属性、コンテキスト属性、静的文字列、および事前宣言済み変数のみがサポートされています。 派生属性または計算属性はサポートされていません。

* **アップデートとバージョン管理**：コンテンツフラグメントを更新するには、Adobe Experience Managerから手動で再公開する必要があります。 Adobe Experience ManagerとJourney Optimizerの間には、バージョンの自動調整は行われません。 コンテンツフラグメントがAdobe Experience Managerに公開されると、Journey OptimizerはJourney Optimizer側でイベントと更新を受け取ります。 成功した場合、更新は、単一ジャーニーの場合は 5 分後、バッチのユースケースの場合は次のバッチで利用できます。

* **キャッシュとプルーフ**：コンテンツフラグメントは、Adobe Experience Manager パブリッシュ層からリアルタイムで取得されます。 プリレンダリングやスナップショットのキャッシュはありません。 キャンペーンおよびジャーニーのプルーフでは、常にコンテンツフラグメントの最近公開されたバージョンが反映されます。履歴バージョンをプルーフ用にロックすることはできません。

* **ユーザーアクセス**：誤ったエラーのリスクを減らすために、コンテンツフラグメントを公開するためのアクセス権を持つユーザーの数を制限することをお勧めします。

### コンテンツ同期フロー {#content-sync-flow}

Adobe Experience ManagerとJourney Optimizerの統合は、次のデータフローに従います。

1. **[作成と作成 &#x200B;](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/sites/administering/content-fragments/managing#creating-a-content-fragment)**：コンテンツが作成され、コンテンツフラグメントとしてAdobe Experience Managerに設定されます。

1. **[タグ付け &#x200B;](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/sites/administering/content-fragments/managing#manage-tags)**：コンテンツフラグメントは、Journey Optimizer固有のタグ（`ajo-enabled:{OrgId}/{SandboxName}`）でタグ付けされている必要があります。

1. **[公開 &#x200B;](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/sites/administering/content-fragments/managing#publishing-and-previewing-a-fragment)**：コンテンツフラグメントはAdobe Experience Managerで公開され、Journey Optimizerで使用できるようになります。

1. **[アクセス](#aem-add)**:Journey Optimizerは、Adobe Experience Manager パブリッシュインスタンスから利用可能なコンテンツフラグメントをリアルタイムで取得し、表示します。

1. **[統合](#aem-add)**：コンテンツフラグメントが選択され、キャンペーンやジャーニーに統合されます。

コンテンツフラグメントがAdobe Experience Managerに公開されると、Journey Optimizer側でコンテンツを更新するためのイベントが送信されます。 更新に成功すると、コンテンツフラグメントは、単一ジャーニーの場合は約 5 分以内に、バッチ使用例の場合は次の処理バッチで使用できるようになります。 更新がJourney Optimizerで使用可能になると、適用可能なすべてのキャンペーンとジャーニーで最新の公開済みコンテンツが使用されます。

### コンテンツフラグメントのライフサイクル

![](assets/do-not-localize/AEM_CF.png)

コンテンツフラグメントは、存在するAdobe Experience Manager層に応じて、異なるライフサイクルステージに従います。 [&#x200B; 詳しくは、Adobe Experience Manager ドキュメントを参照してください &#x200B;](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/sites/authoring/author-publish)

コンテンツは **オーサー層** で作成および管理されます。この層では、フラグメントのステータスとして、新規、ドラフト、公開済み、変更済み、未公開のいずれかを使用できます。 これらのステータスは **オーサー層** にのみ適用され、コンテンツの作成とレビューをサポートします。

コンテンツフラグメントが公開されると、**パブリッシュ層** にコピーが作成され、認証されていないパブリックなエンドポイントを介して公開されます。 Journey Optimizerは、この **パブリッシュ層** のみと統合されます。

その結果、Journey Optimizerでは、公開済みコンテンツフラグメントまたは変更済みコンテンツフラグメントのみを表示し、常に最新の公開済みバージョンを使用します。 公開後に行われた変更は、コンテンツフラグメントが再公開されるまでJourney Optimizerに反映されません。

## Experience Manager でのタグの作成と割り当て

Journey Optimizer でコンテンツフラグメントを使用する前に、Journey Optimizer 専用のタグを作成する必要があります。

1. **Experience Manager** 環境にアクセスします。

1. **ツール**&#x200B;メニューで、「**タグ付け**」を選択します。

   ![](assets/do-not-localize/aem_tag_1.png)

1. 「**タグを作成**」をクリックします。

1. ID が次の構文 `ajo-enabled:{AJO-OrgId}/{AJO-SandboxName}` に従っていることを確認します。

1. 「**作成**」をクリックします。

1. [Experience Manager ドキュメント](https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/sites/administering/content-fragments/content-fragment-models){target="_blank"}の説明に従ってコンテンツフラグメントモデルを定義し、新しく作成した Journey Optimizer タグを割り当てます。

このリアルタイム接続により、コンテンツが常に最新の状態に保たれるだけでなく、公開済みのフラグメントに変更があった場合、アクティブなキャンペーンとジャーニーに直ちに影響を与えることも意味します。

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

1. 「**[!UICONTROL 保存]**」をクリックします。[&#x200B; この節 &#x200B;](../content-management/preview.md) で説明されているように、メッセージコンテンツをテストおよび確認できるようになりました。
テストを実行してコンテンツを検証したら、[キャンペーンを送信](../campaigns/review-activate-campaign.md)したり、オーディエンスに[ジャーニーを公開](../building-journeys/publish-journey.md)したりできます。

Adobe Experience Manager を使用すると、コンテンツフラグメントが使用されている Journey Optimizer キャンペーンまたはジャーニーを識別できます。詳しくは、[Adobe Experience Manager ドキュメント](https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/sites/administering/content-fragments/extension-content-fragment-ajo-external-references)を参照してください。

## トラブルシューティング {#troubleshooting}

Journey OptimizerでAdobe Experience Manager コンテンツフラグメントを使用する際に問題が発生した場合は、次の一般的な問題と解決策を参照してください。

| 問題 | 原因 | 解決策 |
|-|-|-|
| **タグが見つかりません** または **コンテンツフラグメントがセレクターに表示されません** | Adobe Experience Manager タグ構文が必要なフォーマット `ajo-enabled:{OrgId}/{SandboxName}` と一致しません | タグ ID で正しい **組織 ID** と **サンドボックス名** が使用されていることを確認します。 スペースや誤った区切り文字がないことを確認します。 タグを修正した後、コンテンツフラグメントを再公開します。 |
| **コンテンツフラグメントがリストに表示されない** | コンテンツフラグメントがドラフト状態であるか、承認されていません | 承認および公開されたコンテンツフラグメントのみがJourney Optimizer セレクターに表示されます。 コンテンツフラグメントをAdobe Experience Managerで公開し、「承認済み」ステータスになっていることを確認します。 |
| **変数の未定義エラー** | フラグメントヘルパータグにPersonalizationのプレースホルダーが宣言されていない | 必要なすべてのパラメーターをフラグメントヘルパータグに追加します。 コンテンツフラグメントで使用される各プレースホルダーは、マッピングを使用して明示的に宣言する必要があります。 |
| **プルーフに予期しないコンテンツが表示される** | プルーフでAdobe Experience Managerの最新の公開済みバージョンが使用されている | 配達確認は、常にAdobe Experience Managerでのコンテンツフラグメントの最新の公開を反映します。 Adobe Experience Managerで最近の変更を行った場合は、フラグメントを再公開し、プルーフを更新します。 |
| **アクセス拒否（CPES）エラー** | ユーザーの役割には、特定の属性へのアクセスが許可されていません | システム管理者に問い合わせて、役割がパーソナライゼーションで使用されるプロファイルまたはコンテキスト属性に適した権限を持っていることを確認します。 |
| **フラグメントに空白のコンテンツが表示される、またはコンテンツが見つからない** | 必須のパーソナライゼーションパラメーターまたはフォールバック値がありません | 必要なパラメーターがすべて指定されていることを確認し、オプション属性のフォールバック値を追加することを検討してください。 |

問題が解決しない場合は、コンテンツフラグメント ID、キャンペーン ID またはジャーニー ID の詳細および表示されるエラーメッセージをAdobe担当者にお問い合わせください。
