---
solution: Journey Optimizer
product: journey optimizer
title: Adobe Experience Manager コンテンツフラグメントに関する考慮事項とトラブルシューティング
description: Journey OptimizerのAEM コンテンツフラグメントに関する考慮事項と一般的な問題。
topic: Content Management
role: User
level: Beginner
source-git-commit: 4f7e36a6cc19e4138e867950e34c5a5e6452b364
workflow-type: tm+mt
source-wordcount: '733'
ht-degree: 0%

---

# 考慮事項とトラブルシューティング {#aem-fragments-limitations}

## 重要な考慮事項 {#considerations}

[!DNL Adobe Experience Manager]で[!DNL Journey Optimizer]のコンテンツフラグメントを使用する場合は、次の点に注意してください。

* **コンテンツフラグメントタイプ**
   * シンプルなコンテンツフラグメント、ネストされたコンテンツフラグメント、および&#x200B;**コンテンツフラグメントのバリエーション**&#x200B;がサポートされています。 [!DNL Journey Optimizer]にフラグメントを挿入するときに、バリエーションを選択します。 バリエーションを選択しない場合、**Main** バリエーション（[!DNL Adobe Experience Manager]のフラグメントのプライマリコンテンツ）が使用されます。

* **多言語コンテンツ**
   * 各バリエーションは、[!DNL Adobe Experience Manager]で作成、タグ付け、公開する必要があります。 [!DNL Journey Optimizer]で、各メッセージ言語またはロケールに一致するフラグメントのバリエーションを選択します。
   * バリエーション間に自動の言語解決やフォールバックはありません。

* **リポジトリアクセス**
   * [!DNL Journey Optimizer]は、[!DNL Adobe Experience Manager] **公開**&#x200B;階層のみ（サイト、コンテンツフラグメント）と統合されます。 コンテンツフラグメントは、未認証の公開エンドポイントを通じて利用できます。
   * オーサーリポジトリはリポジトリセレクターに表示されますが、**パブリッシュ**&#x200B;に公開されたフラグメントのみが[!DNL Journey Optimizer]で使用できます。

* **コンテンツフラグメントの状態**
   * フラグメントでは、**[!UICONTROL 公開済み]**&#x200B;または&#x200B;**[!UICONTROL 変更済み]**&#x200B;のステータスを表示できます。[!DNL Journey Optimizer]では、常に&#x200B;**最新の公開済みバージョン**&#x200B;が使用されます。
   * 公開後に行われた変更は、フラグメントが[!DNL Journey Optimizer]で再公開されるまで[!DNL Adobe Experience Manager]に反映されません。 2つの製品間に自動バージョン調整はありません。

* **パーソナライゼーション**
   * サポートされているプロファイル属性、コンテキスト属性、静的文字列、事前定義済み変数。
   * サポートされていない：派生属性または計算属性。

* **更新とバージョン管理**
   * 更新するには、[!DNL Adobe Experience Manager]から手動で再公開する必要があります。 自動バージョン紐付けはありません。
   * コンテンツフラグメントが[!DNL Adobe Experience Manager]で公開または再公開されると、[!DNL Journey Optimizer]はそのフラグメントを更新し、**アクティブなキャンペーンまたはジャーニーで参照されているそのフラグメントのすべてのバリエーション**&#x200B;を更新します。
   * [!DNL Adobe Experience Manager] [公開アクション &#x200B;](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/assets/manage/manage-publication)を遅延させることができます。 完了すると、[!DNL Journey Optimizer]はイベントを受け取り、コンテンツを更新します。
   * 更新が正常に完了すると、通常、単一ジャーニーの場合は約&#x200B;**5分以内**&#x200B;に、バッチのユースケースの場合は&#x200B;**次のバッチ**&#x200B;に変更を利用できます。

* **キャッシュとプルーフ**
   * フラグメントがキャンペーンまたはジャーニーに最初に追加されると、[!DNL Journey Optimizer]はそれをキャッシュします。 **[!UICONTROL AEM CF セレクターを開く]**&#x200B;を通じてすでに他の場所で使用されているフラグメントを選択した場合は、[!DNL Journey Optimizer] キャッシュから読み込まれます。
   * 変更されたフラグメントを[!DNL Adobe Experience Manager]で再公開すると、[!DNL Journey Optimizer]はイベントをリッスンし、キャッシュを更新します。
   * プルーフは常に&#x200B;**直近に公開された** バージョンを反映します。プルーフ用に履歴バージョンをロックすることはできません。

## トラブルシューティング {#troubleshooting}

Journey OptimizerでAdobe Experience Manager コンテンツフラグメントを使用する際に問題が発生した場合は、次の一般的な問題と解決策を参照してください。

| 問題 | 原因 | 解決策 |
|-|-|-|
| **タグが見つかりません**&#x200B;または&#x200B;**コンテンツフラグメントがセレクター**&#x200B;に表示されません | Adobe Experience Manager タグの構文が必要な書式`ajo-enabled:{OrgId}/{SandboxName}`と一致しません | タグ IDが正しい&#x200B;**組織ID**&#x200B;と&#x200B;**サンドボックス名**&#x200B;を使用していることを検証します。 スペースや誤った区切り記号がないことを確認します。 タグを修正した後、コンテンツフラグメントを再公開します。 |
| **コンテンツフラグメントがリストに表示されない** | コンテンツフラグメントがドラフト状態であるか、公開されていません | 承認済みおよび公開されたコンテンツフラグメントのみがJourney Optimizer セレクターに表示されます。 Adobe Experience Managerでコンテンツフラグメントを公開し、公開済みステータスであることを確認します。 |
| **変数の未定義エラー** | Personalization プレースホルダーがフラグメントヘルパータグで宣言されていません | 必要なすべてのパラメーターをフラグメントヘルパータグに追加します。 コンテンツフラグメントで使用される各プレースホルダーは、そのマッピングで明示的に宣言する必要があります。 |
| **プルーフに予期しないコンテンツが表示される** | プルーフは、Adobe Experience Managerから公開された最新バージョンを使用します | プルーフには、常にAdobe Experience Managerでのコンテンツフラグメントの最新の公開が反映されます。 Adobe Experience Managerで最近変更した場合は、フラグメントを再公開してプルーフを更新します。 |
| **アクセス拒否（CPES）エラー** | 特定の属性へのアクセスが許可されていないユーザーの役割 | システム管理者に連絡して、パーソナライゼーションで使用されるプロファイルまたはコンテキスト属性に対する適切な権限が役割に付与されていることを確認します。 |
| **フラグメントに空白または不足しているコンテンツが表示される** | 必須のパーソナライゼーションパラメーターまたはフォールバック値がありません | 必要なすべてのパラメーターが指定されていることを確認し、オプションの属性にフォールバック値を追加することを検討します。 |
| **画像がレンダリングされないか、壊れているように見えます** | コンテンツフラグメント内の画像URLが相対パスであるか、チャネルから到達できない | 画像フィールドには&#x200B;**絶対** URL （`https://...`）を使用します。 Adobe Experience Managerからの相対パスはサポートされていません。 ブラウザーまたはメッセージのプレビューでURLを確認します。 |
| **Experience League AEM リンクは404**&#x200B;を返します | 古いブックマーク、プレビュービルド、または未公開のAEM ヘルプページ | ライブExperience Manager ドキュメントから[Adobe Journey Optimizer](https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/sites/administering/content-fragments/content-fragments-with-journey-optimizer){target="_blank"} トピックのコンテンツフラグメントを開き、ページ上の目次から移動するか、セクション名（**Dispatcher Configuration**&#x200B;など）を検索します。 |

問題が解決しない場合は、コンテンツフラグメント ID、キャンペーン IDまたはジャーニーIDの詳細、および表示されるエラーメッセージについて、Adobe担当者にお問い合わせください。
