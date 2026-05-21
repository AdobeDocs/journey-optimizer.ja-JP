---
solution: Journey Optimizer
product: journey optimizer
title: ロイヤルティプログラムの設定
description: Adobe Journey Optimizerでロイヤルティプログラムの報酬プロバイダー、イベント定義、組織レベルの設定を行う方法について説明します。
feature: Journeys
topic: Content Management
role: Admin
level: Intermediate
hide: true
badge: label="Private Beta" type="Informative"
mini-toc-levels: 1
exl-id: f8a3b2c1-4d5e-6f7a-8b9c-0d1e2f3a4b5c
source-git-commit: a4ad533e54f3692eb0483138a8cfd1cee0e77ba1
workflow-type: tm+mt
source-wordcount: '1128'
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

**[!UICONTROL ロイヤルティ管理者]** セクションでは、Journey Optimizerを外部ロイヤルティシステムに接続する方法を設定します。 マーケターは&#x200B;**[!UICONTROL ロイヤルティチャレンジ（Beta）]**&#x200B;を使用して、課題、タスク、コンテンツ、メッセージをデザインします。 **[!UICONTROL ロイヤルティ管理者]**&#x200B;は、報酬のフルフィルメント、イベントマッピング、および製品インベントリ用の個別の管理者専用エリアです。

お客様がチャレンジを完了するか、報酬のマイルストーンに到達すると、Journey Optimizerは、ポイントまたはその他の報酬を提供するように設定された報酬プロバイダーを呼び出します。 **[!UICONTROL Loyalty Admin]**&#x200B;の設定は、チャレンジ **[!UICONTROL Content]**、**[!UICONTROL Messaging]**、**[!UICONTROL Audience]**&#x200B;の設定には影響しません。これらはマーケターの管理下に残ります。

## ここで設定する内容とロイヤルティの課題の違い {#scope}

| 面グラフ | Loyalty Adminで設定 | ロイヤルティの課題に対応 |
|------|----------------------------|----------------------------------|
| Rewards Fulfillment API | はい – 報酬プロバイダー | いいえ – プロバイダーと金額のみを選択します |
| カスタムアクティビティのイベントマッピング | はい – イベント定義 | いいえ – カスタムイベントタスクでイベント名を選択します |
| 製品グループマッピング | はい – 製品在庫 | いいえ – 購入/支出タスクのオーサリング時にグループを使用します |
| 課題構造、コンテンツ、オーディエンス | × | ○ |

Adobe Journey Optimizerでは、顧客が特典を獲得すると、特典プロバイダーにフルフィルメントコールが送信されます。 ロイヤルティプラットフォームは、会員のアカウントをクレジットする責任があります。

## 前提条件 {#prerequisites}

**[!UICONTROL ロイヤルティ管理者]**&#x200B;は、組織ごとの少数の管理者を対象としています。 [ ロイヤルティチャレンジ ](get-started.md#prerequisites)に必要な権限に加えて、Journey Optimizer インスタンスに対する管理者レベルのアクセス権が必要です。 アクセスをリクエストするには、Adobe管理者にお問い合わせください。

## ロイヤルティ管理者へのアクセス {#access-loyalty-admin}

**[!UICONTROL Loyalty Admin]**&#x200B;を開くには、Journey Optimizerの左側のナビゲーションから選択します。

<!-- SCREENSHOT: Loyalty Admin entry in the left navigation -->

**[!UICONTROL ロイヤルティ管理者]**&#x200B;がタブに整理されています：**[!UICONTROL グローバル設定]**、**[!UICONTROL 報酬プロバイダー]**、**[!UICONTROL イベント定義]**、および&#x200B;**[!UICONTROL 製品インベントリ]**。 使用できるタブは、組織の権限と機能設定によって異なります。

## グローバル設定 {#global-settings}

>[!CONTEXTUALHELP]
>id="ajo_loyalty_admin_global_settings"
>title="グローバル設定"
>abstract="ロイヤルティプログラムのAdobe Experience Platform ID名前空間を選択し、設定IDをコピーします。 これらの組織レベルの設定は、リワードプロバイダーが報酬を正しく果たすために必要です。"

**[!UICONTROL グローバル設定]**&#x200B;を使用して、ロイヤルティの課題に対する組織全体のオプションを設定します。

1. 「**[!UICONTROL グローバル設定]**」タブを開きます。

1. **[!UICONTROL 名前空間]** ドロップダウンで、ロイヤルティプログラムで使用する[ID名前空間](https://experienceleague.adobe.com/ja/docs/experience-platform/identity/features/namespaces)を選択します。

1. **[!UICONTROL 保存]**&#x200B;を選択して、ロイヤルティチャレンジ設定に名前空間を適用します。

1. インバウンドイベント配信を設定する場合など、実装チームまたは外部システムと共有する必要がある場合は、**[!UICONTROL 設定ID]**&#x200B;をコピーします。

<!-- SCREENSHOT: Global settings tab showing namespace drop-down, Save, and Configuration ID -->

## ポイントプロバイダー {#reward-providers}

**報酬プロバイダー**&#x200B;は、チャレンジの進捗状況が記録されたり、チャレンジが完了したりしたときに、フルフィルメントコールを送信する場所をJourney Optimizerに伝えます。例えば、ロイヤルティポイントやスターをメンバーアカウントにクレジットするAPIです。

報酬プロバイダーの設定には、次のものが含まれます。

* 基本的な接続の詳細（名前、説明、API URL、ヘッダー）
* **[!UICONTROL 報酬定義]** – このプロバイダーが発行できる報酬タイプ（星やマイルなど）
* **[!UICONTROL 報酬プロキシ]** （オプション） – エンドポイントではなく呼び出しが直接ルーティングされる中間プロキシ
* **[!UICONTROL 認証トークンジェネレーター]** — Journey OptimizerがAPIを呼び出す前にアクセストークンを取得するために使用するメカニズム

### 報酬プロバイダーの作成 {#create-reward-provider}

1. **[!UICONTROL 報酬プロバイダー]** タブを開き、**[!UICONTROL 報酬プロバイダーの作成]**&#x200B;を選択します。

1. フルフィルメント要求を受け取る&#x200B;**[!UICONTROL 名前]**、**[!UICONTROL 説明]**&#x200B;および&#x200B;**[!UICONTROL API URL]**&#x200B;を入力します。

1. API用に必要に応じて&#x200B;**[!UICONTROL ヘッダー]**&#x200B;を追加します（API キーやコンテンツタイプなど）。

1. **[!UICONTROL 報酬の定義]**&#x200B;を設定する – プロバイダーがサポートする報酬タイプごとに1つのエントリ（プログラムポイントやスターなど）。 定義ごとに：

   * フルフィルメント呼び出しで送信された&#x200B;**ペイロード**&#x200B;を指定します。
   * オプションで、このプロバイダーの&#x200B;**default**&#x200B;として1つの定義をマークします。

1. オプションで&#x200B;**[!UICONTROL 報酬プロキシ]**&#x200B;を設定して、中間サーバー経由でフルフィルメント呼び出しをルーティングします。

   * **[!UICONTROL 名前]**、**[!UICONTROL 説明]**、およびプロキシが&#x200B;**有効**&#x200B;であるかどうか
   * **[!UICONTROL ホスト]**、**[!UICONTROL ポート]**&#x200B;および資格情報

1. APIで認証にベアラートークンが必要な場合は、**[!UICONTROL 認証トークンジェネレーター]**&#x200B;を設定します。

   * トークンエンドポイント URLとHTTP メソッド（OAuth スタイルのフローの場合は&#x200B;**POST**&#x200B;など）
   * 応答の&#x200B;**[!UICONTROL トークンキー]** （例：`access_token`）
   * トークンエンドポイントに必要なヘッダー

   Journey Optimizerでは、この設定を使用して、報酬APIを呼び出す前に新しいトークンを取得します。

1. **[!UICONTROL 報酬プロバイダーの作成]**&#x200B;を選択します。 プロバイダーと設定されたすべての子リソースが一緒に保存されます。

<!-- SCREENSHOT: Reward provider creation form with definitions, proxy, and auth token sections -->

保存すると、プロバイダーが報酬プロバイダーのリストに表示されます。 マーケターは、[ チャレンジ報酬の設定時](create-challenges.md#rewards)にこのプロバイダーを選択します。

既存の報酬プロバイダーを編集するには、「**[!UICONTROL 報酬プロバイダー]**」タブを開き、プロバイダーを選択して、フィールドを更新します。 子リソース（報酬定義、プロキシ、認証トークンジェネレーター）の変更は、更新すると保存されます。

<!-- SCREENSHOT: Reward provider detail view with child resource sections -->

>[!NOTE]
>
>**[!UICONTROL 独自のデータを持ち込む]**&#x200B;課題は、独自のデータ統合を通じて報酬を実現します。 ここで設定した報酬プロバイダーは、これらの課題には適用されません。 [独自のデータ課題の解決について詳しく見る](create-challenges.md#create-the-challenge)。

## イベント定義（オプション） {#event-definitions}

**[!UICONTROL イベント定義]**&#x200B;は、ブランドが使用するJSONまたはXDM形式を問わず、システムからのエクスペリエンスイベントを、ロイヤルティチャレンジが行動できるアクティビティ（特に&#x200B;**[!UICONTROL カスタムイベント]** タスク）にマッピングします。 イベントが到着すると、Journey Optimizerはこれらの定義を使用して、イベントを処理するかどうかを決定します。 どの定義にも一致しないイベントは無視されます。

### イベント定義の作成 {#create-event-definition}

1. 「**[!UICONTROL イベント定義]**」タブを開き、新しい定義を作成します。

1. イベントの&#x200B;**[!UICONTROL 名前]**&#x200B;を入力します（例：`Coffee purchase`）。これは、**[!UICONTROL カスタムイベント]** タスクを設定する際にマーケターに表示される名前です。

1. 受信ペイロードでイベントを識別する方法を指定します。

   * **[!UICONTROL 識別子パス]** — イベントまたはメンバーを識別するフィールドへのJSON パス （例：`data.memberId`）
   * **[!UICONTROL 識別子値]** – この定義が一致するために存在する必要がある値

1. イベントペイロードがExperience Platform スキーマに準拠している場合は、オプションで&#x200B;**[!UICONTROL XDM スキーマ ID]**&#x200B;を指定します。

1. 必要に応じて、**[!UICONTROL スキーマ]**&#x200B;および&#x200B;**[!UICONTROL トランスフォーマ]** フィールドを使用して、受信JSONを解析および検証するためのカスタムスキーマおよび変換文字列を指定します。

   イベントの構造化方法に応じて、XDM スキーマ ID、識別子パス、またはその両方を指定できます。

1. イベント定義を保存します。

<!-- SCREENSHOT: Event definition form with identifier path, values, and schema fields -->

多くの企業は、追跡するアクティビティごとに1つのイベント定義を作成します（購入、チェックイン、サイト訪問など）。 [課題でカスタムイベントタスクを使用する方法を学ぶ](create-tasks.md#choose-activity)。

## 製品インベントリ（オプション） {#product-inventory}

「**[!UICONTROL 製品インベントリ]**」タブを使用して、製品または品目の識別子（MPG IDなど）を製品グループにマッピングするCSV ファイルをアップロードします。 マーケターは、個々のSKUを入力する代わりに、タスクの適格性ルールでこれらのグループを参照できます。

1. 「**[!UICONTROL 製品インベントリ]**」タブを開きます。

1. マッピングファイルをアップロードします。

1. インベントリリストで読み込んだマッピングを確認します。 製品グループを選択すると、そのグループ内のすべてのアイテムが表示されます。検索を使用すると、名前またはIDでアイテムを検索できます。

1. **[!UICONTROL アップロード履歴]**&#x200B;を使用して、以前のアップロードを確認します。

<!-- SCREENSHOT: Product inventory list after CSV upload -->

>[!NOTE]
>
>製品インベントリの&#x200B;**[!UICONTROL グローバル除外]**&#x200B;は、今後のリリースで予定されており、ここでは文書化されていません。
