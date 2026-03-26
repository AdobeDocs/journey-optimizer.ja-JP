---
solution: Journey Optimizer
product: journey optimizer
title: ランディングページの基本を学ぶ
description: Journey Optimizer のランディングページについて学ぶ
feature: Landing Pages, Subscriptions
topic: Content Management
role: User
level: Beginner
keywords: ランディング, ランディングページ, 開始, 開始
exl-id: 0da96e32-52ad-4cc3-bac4-844b1f39ed16
source-git-commit: d0dd382521aeb2c7e18dc547c2ec55fa1472ab8d
workflow-type: tm+mt
source-wordcount: '698'
ht-degree: 14%

---

# ランディングページの基本を学ぶ {#get-started-lp}

ランディングページは、メール、web サイト、広告、またはその他のデジタル化された場所からユーザーがクリックスルーした後に表示されるスタンドアロン web ページです。

[!DNL Journey Optimizer]を使用すると、ユーザーがコミュニケーションやニュースレターなどの特定のサービスの受信をオプトインまたはオプトアウトできるオンラインフォームにユーザーを誘導するランディングページを作成およびデザインできます。

➡️ [購読の設定とランディングページの作成について詳しくは、このビデオを参照してください。](#video)

## ランディングページの用途 {#when-to-use}

ランディングページは、次のような場合に使用します。

* メールまたはキャンペーンのリンクから、マーケティングコミュニケーションまたは特定のサービスまたはニュースレターの&#x200B;**オプトインまたはオプトアウト**&#x200B;を顧客に許可します（対象サービスのサブスクリプションリストを含む）。 [詳細情報](lp-use-cases.md#subscription-to-a-service)
* **メールを送信する前に同意**&#x200B;を収集し、オプトインまたはオプトアウト時に&#x200B;**確認メール**&#x200B;を送信します。 [詳細情報](lp-use-cases.md#send-confirmation-email)
* **プログレッシブプロファイリング、環境設定、登録などのシナリオ用に、** データキャプチャ **[!UICONTROL ランディングページのフォームを使用して、プロファイルデータ]**&#x200B;をキャプチャまたは更新します。 [詳細情報](#data-capture-lp)
* **以外の外部ページを作成せずに、ユーザーを**&#x200B;専用のweb フォーム [!DNL Journey Optimizer]にリダイレクトします
* **のコンテンツデザイン機能を使用して** レスポンシブランディングページ [!DNL Journey Optimizer]を作成する

### ランディングページによるデータキャプチャ {#data-capture-lp}

**[!UICONTROL データキャプチャ]**&#x200B;のランディングページを使用すると、公開されたフォームを埋め込むことができ、訪問者は、フォームプリセットで設定されたストリーミング接続を介して[!DNL Adobe Experience Platform] データセットに書き込まれた属性を送信できます。 [&#x200B; ランディングページにフォームを作成して埋め込む方法を学ぶ](lp-forms.md)

>[!NOTE]
>
>ランディングページフォームによるデータキャプチャは、**既知のプロファイル** （[!DNL Adobe Experience Platform]で識別された既存のプロファイル）でサポートされています。 ランディングページを開くには、**パーソナライズされたリンク** （メールキャンペーンなど）を使用して、ページの読み込み時にプロファイル IDを解決できるようにする必要があります。

次に、使用例を示します。

1. **プログレッシブプロファイルの強化** — パーソナライズされたランディングページを通じて、電話番号、生年月日、場所などの既知の顧客から追加の属性を収集し、セグメント化とパーソナライゼーションのために既存の[!DNL Experience Platform] プロファイルを強化します。

2. **プリファレンスセンターの更新** – 既知の購読者がランディングページを介してコミュニケーションの好み（チャネル、トピックへの関心）を管理できるようにします。通常、約15分以内に[!DNL Experience Platform]のプロファイルに変更が反映されます。

3. **イベントまたはウェビナーの登録** – 登録ページの既知のプロファイルからイベント固有のデータを取得し、登録属性を使用してプロファイルを更新し、確認ジャーニーをトリガーします。

4. **ロイヤルティまたはプログラム登録** – 既存の顧客がランディングページを通じて追加の詳細を送信して、ロイヤルティプログラムまたはメンバーシップ階層に登録できるようにし、ダウンストリームのターゲティング用にプロファイルを強化します。

5. **競合またはコンテストのエントリ** – 既知の顧客がランディングページフォームを使用して競合または懸賞に参加できるようにします。エントリ固有の詳細（回答、好み、または宣言）を取得し、プロファイルに書き込んで、適格性、勝者の選択、およびフォローアップジャーニーをサポートします。

<table style="table-layout:fixed"><tr style="border: 0;">
<td>
<a href="create-lp.md">
<img alt="リード" src="../assets/do-not-localize/lp-subscription.jpeg">
</a>
<div><a href="create-lp.md"><strong>ランディングページの作成</strong>
</div>
<p>
</td>
<td>
<a href="subscription-list.md">
<img alt="低頻度" src="../assets/do-not-localize/lp-list.jpg">
</a>
<div>
<a href="subscription-list.md"><strong>購読リストの作成</strong></a>
</div>
<p></td>
<td>
<a href="lp-forms.md">
<img alt="Journey Optimizerのランディングページ用Forms リスト" src="../assets/do-not-localize/lp-design.jpg">
</a>
<div>
<a href="lp-forms.md"><strong> ランディングページでのフォームの使用</strong></a>
</div>
<p>
</td>
<td>
<a href="../reports/lp-report-live.md">
<img alt="検証" src="../assets/do-not-localize/lp-reporting.jpg">
</a>
<div>
<a href="../reports/lp-report-live.md"><strong>レポート</strong></a>
</div>
<p>
</td>
</tr></table>

## 始める前に {#prerequisites}

ランディングページを作成する前に、次の設定手順を実行します。

1. **サブドメインの設定** — ランディングページのホスティング専用のサブドメインを設定します。 [詳細情報](lp-subdomains.md)
1. **ランディングページプリセットを作成** — プリセットは、ランディングページに適用されるサブドメインおよびその他の設定を定義します。 [詳細情報](lp-presets.md#lp-create-preset)
1. **購読リストを作成** （購読ユースケース向け） – 顧客が特定のサービスを購読または購読解除する場合に必要です。 [詳細情報](subscription-list.md)
1. **フォームを作成** （データキャプチャのユースケース用） — **[!UICONTROL データキャプチャ]**&#x200B;のランディングページにフォームを埋め込み、[!DNL Experience Platform]に送信する場合に必要です。 [詳細情報](lp-forms.md)

## 仕組み {#how-it-works}

ランディングページの作成とデプロイは、次の順序で行われます。

1. **ランディングページの作成と設定** — プリセットを選択し、プライマリページを設定し、必要なサブページを追加します。 [詳細情報](create-lp.md#create-landing-page)
1. **ページをデザイン** — [!DNL Journey Optimizer]のドラッグ&amp;ドロップ エディターを使用して、ページのコンテンツとフォームを作成します。 [詳細情報](design-lp.md)
1. **ランディングページをテストして公開する** — ページをプレビューし、フォームの動作をテストしてから公開して公開します。 [詳細情報](create-lp.md#test-landing-page)
1. **メッセージまたはジャーニー内のリンク** – 顧客がアクセスできるように、ランディングページのURLをメール、キャンペーン、ジャーニーアクションに追加します。 [詳細情報](../email/message-tracking.md#insert-links)

## チュートリアルビデオ{#video}

次のビデオでは、購読リストの作成、サービスのオプトインまたはオプトアウトを行うためのランディングページの設定、メッセージへのオプトイン/オプトアウトオプションの統合、関連するジャーニーの設定を行う方法を示します。

>[!VIDEO](https://video.tv.adobe.com/v/341280?quality=12&learn=on)
