---
solution: Journey Optimizer
product: journey optimizer
title: ロイヤルティプログラムの設定
description: Adobe Journey Optimizerでロイヤルティプログラムの報酬プロバイダー、イベント定義、組織設定を設定する方法について説明します。
feature: Journeys
topic: Content Management
role: Admin
level: Intermediate
hide: true
badge: label="Private Beta" type="Informative"
mini-toc-levels: 1
exl-id: f8a3b2c1-4d5e-6f7a-8b9c-0d1e2f3a4b5c
source-git-commit: e66628ab1d9df497226ab625947aa18a2a3b6f48
workflow-type: tm+mt
source-wordcount: '1221'
ht-degree: 2%

---

# ロイヤルティプログラムの設定 {#loyalty-admin}

>[!BEGINSHADEBOX]

**ロイヤルティの課題に関するドキュメント：**

* [ロイヤルティに関する課題を解決](get-started.md)
* [課題とタスクへのアクセスと管理](access-loyalty-challenges.md)
* [課題の創出](create-challenges.md)
* [タスクの作成](create-tasks.md)
* [ロイヤルティチャレンジのパフォーマンスを監視する](loyalty-reporting.md)
* **ロイヤルティプログラムの設定** ◀︎ **現在地**
* [ロイヤルティチャレンジ API リファレンス](https://developer.adobe.com/journey-optimizer-apis/references/loyalty-challenges){target="_blank"}

>[!ENDSHADEBOX]

>[!AVAILABILITY]
>
>この機能は現在&#x200B;**プライベートベータ版**&#x200B;です。 リリースサイクルと可用性フェーズについて詳しくは、[Journey Optimizer リリースサイクル](../rn/releases.md)を参照してください。

**[!UICONTROL ロイヤルティ管理者]** セクションでは、管理者がJourney Optimizerをロイヤルティプログラムのバックエンドに接続する方法を設定します。 マーケターは&#x200B;**[!UICONTROL ロイヤルティチャレンジ（Beta）]**&#x200B;を使用して、課題、タスク、コンテンツ、メッセージをデザインします。ロイヤルティ管理者は、報酬のフルフィルメントとイベントマッピングを個別に1回設定します。

お客様がチャレンジを完了した場合（または報酬のマイルストーンに到達した場合）、Journey Optimizerは、ここで設定した報酬プロバイダーを呼び出して、ポイントやその他の報酬を提供します。 課題&#x200B;**[!UICONTROL コンテンツ]**、**[!UICONTROL メッセージング]**、**[!UICONTROL オーディエンス]**&#x200B;の設定は、ロイヤルティ管理者設定の影響を受けません。

## ロイヤルティ管理者へのアクセス {#access-loyalty-admin}

ロイヤルティ管理者を開くには、Journey Optimizerにログインし、左側のナビゲーションで「**[!UICONTROL ロイヤルティ管理者]**」を選択します。

<!-- SCREENSHOT: Loyalty Admin entry in the left navigation -->

管理者インターフェイスはタブで構成されています。 組織によっては、**[!UICONTROL グローバル設定]**、**[!UICONTROL 報酬プロバイダー]**、**[!UICONTROL イベント定義]**、**[!UICONTROL 製品インベントリ]**&#x200B;が表示される場合があります。

## グローバル設定 {#global-settings}

>[!CONTEXTUALHELP]
>id="ajo_loyalty_admin_global_settings"
>title="グローバル設定"
>abstract="ロイヤルティプログラムのAdobe Experience Platform ID名前空間を選択し、設定IDをコピーします。 これらの組織レベルの設定は、リワードプロバイダーが報酬を正しく果たすために必要です。"

**[!UICONTROL グローバル設定]**&#x200B;を使用して、ロイヤルティの課題に対する組織全体のオプションを設定します。

1. 「**[!UICONTROL グローバル設定]**」タブを開きます。

1. **[!UICONTROL 名前空間]** ドロップダウンで、ロイヤルティプログラムが使用するAdobe Experience Platformの[ID名前空間](https://experienceleague.adobe.com/ja/docs/experience-platform/identity/features/namespaces)を選択します。 組織のロイヤルティチャレンジ設定の名前空間を更新するには、**[!UICONTROL 保存]**&#x200B;を選択します。

1. 実装チームまたは外部システムと共有する必要がある場合は、**[!UICONTROL 設定ID]**&#x200B;をコピーします。

<!-- SCREENSHOT: Global settings tab showing namespace drop-down, Save, and Configuration ID -->

## ポイントプロバイダー {#reward-providers}

**報酬プロバイダー**&#x200B;は、チャレンジの進捗状況が記録されたり、チャレンジが完了したりしたときに、フルフィルメントコールを送信する場所をJourney Optimizerに伝えます。例えば、ロイヤルティポイントやスターをメンバーアカウントにクレジットするAPIです。

特典プロバイダーには以下が含まれます。

* 基本的な接続の詳細（名前、説明、API URL、ヘッダー）
* **[!UICONTROL 報酬定義]** – このプロバイダーが発行できる報酬タイプ（星やマイルなど）
* **[!UICONTROL 報酬プロキシ]** （オプション） – エンドポイントに直接ではなく、プロキシ経由で呼び出しをルーティングします
* **[!UICONTROL 認証トークンジェネレーター]** — Journey OptimizerがAPIを呼び出す前にアクセストークンを取得する方法

### 報酬プロバイダーの作成 {#create-reward-provider}

新しい報酬プロバイダーとその関連リソースを登録するには、次の手順に従います。

1. **[!UICONTROL 報酬プロバイダー]** タブを開き、プロバイダーの作成を開始します。

1. **[!UICONTROL 名前]**&#x200B;と&#x200B;**[!UICONTROL 説明]**&#x200B;を入力し、フルフィルメント要求が送信される&#x200B;**[!UICONTROL API URL]**&#x200B;を入力します。

1. API用に必要に応じて&#x200B;**[!UICONTROL ヘッダー]**&#x200B;を追加します（API キーやコンテンツタイプなど）。 UIでヘッダー行を追加または削除できます。

1. **[!UICONTROL 報酬定義]**&#x200B;を設定します。

   * プロバイダーがサポートする各報酬タイプ（プログラムポイントやスターなど）を定義します。
   * オプションで、1つの定義を、そのプロバイダーの&#x200B;**default**&#x200B;としてマークします。
   * 各定義のフルフィルメント呼び出しで送信される&#x200B;**ペイロード**&#x200B;を指定します。

1. オプションで&#x200B;**[!UICONTROL 報酬プロキシ]**&#x200B;を設定します。

   * **[!UICONTROL ホスト]**、**[!UICONTROL ポート]**&#x200B;および資格情報
   * **[!UICONTROL 名前]**、**[!UICONTROL 説明]**、およびプロキシが&#x200B;**有効**&#x200B;であるかどうか

1. APIが各呼び出しの前にトークンを必要とする場合は、**[!UICONTROL 認証トークンジェネレーター]**&#x200B;を設定します。

   * トークンエンドポイント URLとHTTP メソッド（OAuth スタイルのフローの場合は&#x200B;**POST**&#x200B;など）
   * 応答の&#x200B;**[!UICONTROL トークンキー]** （例：`access_token`）
   * トークンエンドポイントに必要なヘッダー

   Journey Optimizerは、報酬APIを呼び出す前に、この設定からトークンをリクエストするため、呼び出しは現在の資格情報を使用します。

1. **[!UICONTROL 報酬プロバイダーの作成]**&#x200B;を選択します。 プロバイダーとその子リソース（定義、プロキシ、トークンジェネレーター）が一緒に作成されます。

<!-- SCREENSHOT: Reward provider creation form with definitions, proxy, and auth token sections -->

作成後、プロバイダは報酬プロバイダ リストに表示されます。 マーケターは、[ チャレンジ報酬の設定時](create-challenges.md#rewards)にこのプロバイダーを選択します。

### 報酬プロバイダーの編集 {#edit-reward-provider}

1. 「**[!UICONTROL 特典プロバイダー]**」タブを開き、プロバイダーを選択します。

1. 必要に応じて、プロバイダーの名前、説明、URL、ヘッダーを更新します。

1. **[!UICONTROL 報酬定義]**、**[!UICONTROL 報酬プロキシ]**、または&#x200B;**[!UICONTROL 認証トークンジェネレーター]**&#x200B;を変更するには、対応するセクションを開いてフィールドを編集します。 これらの子リソースに対する変更は、その場で更新すると保存されます。

<!-- SCREENSHOT: Reward provider detail view with child resource sections -->

>[!NOTE]
>
>タスクと報酬が完全にデータ統合から得られる&#x200B;**[!UICONTROL 独自のデータを持ち込む]**&#x200B;の課題については、ここで設定した報酬プロバイダーは適用されない場合があります。 [独自のデータ課題の解決について詳しく見る](create-challenges.md#create-the-challenge)。

## イベント定義 {#event-definitions}

**[!UICONTROL イベント定義]**&#x200B;は、ブランドの形式の受信エクスペリエンスイベントを、ロイヤルティチャレンジが使用できるアクティビティ（特に&#x200B;**[!UICONTROL カスタムイベント]** タスク）にマッピングします。 Journey Optimizerでは、チャネルからデータが届いたときに、これらの定義を使用してイベントが関連性があるかどうかを判断し、それを解釈する方法を決定します。 どの定義にも一致しないイベントは無視されます。

### イベント定義の作成 {#create-event-definition}

1. 「**[!UICONTROL イベント定義]**」タブを開き、新しい定義を作成します。

1. イベントの&#x200B;**[!UICONTROL 名前]**&#x200B;を入力します（例：`Coffee purchase`）。 この名前は、マーケターが&#x200B;**[!UICONTROL カスタムイベント]** タスクを設定するときに選択する名前です。

1. 受信ペイロードでイベントを識別する方法を指定します。

   * **[!UICONTROL 識別子パス]** — イベントまたはメンバーを識別するフィールドへのJSON パス （例：`data.memberId`）
   * **[!UICONTROL 識別子値]** – この定義が一致するために存在する必要がある値

1. オプションで&#x200B;**[!UICONTROL XDM スキーマ ID]**&#x200B;を指定するか、**[!UICONTROL スキーマ]**&#x200B;および&#x200B;**[!UICONTROL トランスフォーマ]** フィールドを使用して、チームが処理前に受信JSONを解析および検証するために使用するスキーマおよび変換文字列を貼り付けます。

   イベントの構造化方法に応じて、XDM スキーマ ID、識別子パス、またはその両方を指定できます。

1. イベント定義を保存します。

<!-- SCREENSHOT: Event definition form with identifier path, values, and schema fields -->

多くの企業は、追跡するアクティビティごとに1つのイベント定義を作成します（購入、チェックイン、サイト訪問など）。 [課題でカスタムイベントタスクを使用する方法を学ぶ](create-tasks.md#choose-activity)。

## 製品インベントリ {#product-inventory}

「**[!UICONTROL 製品インベントリ]**」タブでは、CSV ファイルをアップロードして、タスクの適格性で使用される製品グループに製品または品目の識別子（MPG IDなど）をマッピングできます。 これにより、タスクが手動で入力された個々のSKUではなく、グループ化された製品を参照するシナリオをサポートします。

1. 「**[!UICONTROL 製品インベントリ]**」タブを開きます。

1. マッピングファイルをアップロード領域にドラッグするか、参照して選択して、マッピングファイルをアップロードします。

1. インベントリリストで読み込んだマッピングを確認します。 製品グループを選択すると、そのグループ内のすべてのアイテムが表示されます。 検索を使用して、名前またはIDでアイテムを検索します。

1. **[!UICONTROL アップロード履歴]**&#x200B;を使用して、以前のアップロードを確認します。

<!-- SCREENSHOT: Product inventory list after CSV upload -->

>[!NOTE]
>
>製品インベントリの&#x200B;**[!UICONTROL グローバル除外]**&#x200B;は、今後のリリースで予定されており、ここでは文書化されていません。

## 課題に対するロイヤルティ管理者の対応 {#how-admin-relates-to-challenges}

| 面グラフ | Loyalty Adminで設定 | ロイヤルティの課題に対応 |
|------|----------------------------|----------------------------------|
| Rewards Fulfillment API | はい – 報酬プロバイダー | いいえ – プロバイダーと金額のみを選択します |
| カスタムアクティビティのイベントマッピング | はい – イベント定義 | いいえ – カスタムイベントタスクでイベント名を選択します |
| 製品グループマッピング | はい – 製品在庫 | いいえ – 購入/支出タスクのオーサリング時にグループを使用します |
| 課題構造、コンテンツ、オーディエンス | × | ○ |

一般的な設定順序：

1. Loyalty Adminで&#x200B;**[!UICONTROL グローバル設定]**&#x200B;と少なくとも1つの&#x200B;**[!UICONTROL 報酬プロバイダー]**&#x200B;を設定します。
1. プログラムでカスタムイベントまたはCSV ベースの製品グループを使用している場合は、オプションで&#x200B;**[!UICONTROL イベント定義]**&#x200B;と&#x200B;**[!UICONTROL 製品インベントリ]**&#x200B;を追加します。
1. **[!UICONTROL ロイヤルティチャレンジ（Beta）]**&#x200B;で[ タスク ](create-tasks.md)と[課題](create-challenges.md)を作成し、設定した報酬プロバイダーと定義を選択します。

Adobe Journey Optimizerでは、顧客が特典を獲得すると、プロバイダーにフルフィルメントコールが送信されます。ロイヤルティプラットフォームは、会員のアカウントのクレジットを所有します。

## 前提条件 {#prerequisites}

ロイヤルティ管理者は、組織内の少数の管理者を対象としています。 [ ロイヤルティチャレンジ ](get-started.md#prerequisites)に必要な権限に加えて、組織レベルのロイヤルティ設定を設定するためのアクセス権が必要です。

**[!UICONTROL ロイヤルティ管理者]**&#x200B;が左側のナビゲーションに表示されない場合、またはグローバル設定や報酬プロバイダーを保存できない場合は、管理者にお問い合わせください。
