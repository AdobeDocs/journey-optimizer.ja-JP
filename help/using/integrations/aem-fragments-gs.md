---
solution: Journey Optimizer
product: journey optimizer
title: AEM コンテンツフラグメント
description: AEM コンテンツフラグメントへのアクセスと管理の方法について説明します。
topic: Content Management
role: User
level: Beginner
source-git-commit: b06229e7a2fc64fbe28154c798b152cca8203a86
workflow-type: tm+mt
source-wordcount: '866'
ht-degree: 12%

---

# Adobe Experience Manager コンテンツフラグメントの基本を学ぶ {#aem-fragments}

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


### コンテンツフラグメントのライフサイクル

![](assets/do-not-localize/AEM_CF.png)

コンテンツフラグメントは、存在するAdobe Experience Manager層に応じて、異なるライフサイクルステージに従います。 [&#x200B; 詳しくは、Adobe Experience Manager ドキュメントを参照してください &#x200B;](https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/sites/authoring/author-publish)

コンテンツは **オーサー層** で作成および管理されます。この層では、フラグメントのステータスとして、新規、ドラフト、公開済み、変更済み、未公開のいずれかを使用できます。 これらのステータスは **オーサー層** にのみ適用され、コンテンツの作成とレビューをサポートします。

コンテンツフラグメントが公開されると、**パブリッシュ層** にコピーが作成され、認証されていないパブリックなエンドポイントを介して公開されます。 Journey Optimizerは、この **パブリッシュ層** のみと統合されます。

その結果、Journey Optimizerでは、公開済みコンテンツフラグメントまたは変更済みコンテンツフラグメントのみを表示し、常に最新の公開済みバージョンを使用します。 公開後に行われた変更は、コンテンツフラグメントが再公開されるまでJourney Optimizerに反映されません。


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
