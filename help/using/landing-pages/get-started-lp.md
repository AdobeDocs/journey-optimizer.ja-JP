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
TQID: https://experienceleague.adobe.com/wr4XGNostKoN8jZ50VRAQPoGg9tsNhMOyJGEt1mASso
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2:
  - id: d998adac-2f81-400b-a669-d07bb196e4eb
  - id: dc22c819-3f29-4e91-8b7d-5c6719831141
  - id: fe338112-e2ce-4876-8989-fc4d497613f1
subfeature_v2:
  - id: b19d9237-76be-466d-a869-aacf2d72205f
  - id: fb9a80eb-bebc-492f-a0e9-584595621ebb
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: 1e0a06dddba6c5ca4c53e4b143eb7fa7763ded6b
workflow-type: tm+mt
source-wordcount: 735
ht-degree: 96%

---

# ランディングページの基本を学ぶ {#get-started-lp}

ランディングページは、メール、web サイト、広告、またはその他のデジタル化された場所からユーザーがクリックスルーした後に表示されるスタンドアロン web ページです。

[!DNL Journey Optimizer] を使用すると、ランディングページを作成およびデザインして、ユーザーはオンラインフォームにアクセスし、コミュニケーションやニュースレターなどの特定のサービスの受信のオプトイン／オプトアウトを行うことができます。

➡️ [購読の設定とランディングページの作成について詳しくは、このビデオを参照してください。](#video)

## ランディングページを使用するタイミング {#when-to-use}

ランディングページは、次の操作が必要な場合に使用します。

* 顧客がメールやキャンペーン内のリンクからマーケティングコミュニケーション、特定のサービス、ニュースレターを&#x200B;**オプトインまたはオプトアウト**&#x200B;できるようにする。これには、ターゲットにするサービスの購読リストも含まれます。 [詳細情報](lp-use-cases.md#subscription-to-a-service)
* コミュニケーションを送信する前に&#x200B;**同意を収集**&#x200B;し、オプトインまたはオプトアウト時に&#x200B;**確認メール**&#x200B;を送信します。 [詳細情報](lp-use-cases.md#send-confirmation-email)
* **[!UICONTROL データキャプチャ]**&#x200B;ランディングページのフォームを使用して&#x200B;**プロファイルデータを取得または更新**&#x200B;します。これは、プログレッシブプロファイリング、環境設定、登録、類似のシナリオ用です。 [詳細情報](#data-capture-lp)
* [!DNL Journey Optimizer] 以外の外部ページを作成せずに、ユーザーを&#x200B;**専用の web フォーム**&#x200B;にリダイレクトします。
* [!DNL Journey Optimizer] のコンテンツデザイン機能を使用して、**レスポンシブなランディングページ**&#x200B;を作成する

### ランディングページによるデータキャプチャ {#data-capture-lp}

**[!UICONTROL データキャプチャ]**&#x200B;ランディングページでは、公開済みのフォームを埋め込むことができるので、訪問者はフォームプリセットで設定されたストリーミング接続を通じて [!DNL Adobe Experience Platform] データセットに書き込まれる属性を送信できます。 [ランディングページのフォームの作成および埋め込み方法の詳細情報](lp-forms.md)

>[!NOTE]
>
>ランディングページフォームによるデータキャプチャは、**既知のプロファイル**（[!DNL Adobe Experience Platform] で特定された既存のプロファイル）に対してサポートされています。 ランディングページは、**パーソナライズされたリンク**（例：メールキャンペーンのリンク）から開く必要があります。これにより、ページ読み込み時にプロファイル ID を解決できます。

次に、ユースケースの例を示します。

1. **プログレッシブなプロファイルエンリッチメント** - パーソナライズされたランディングページを通じて、電話番号、生年月日、場所など、既知の顧客から追加の属性を収集し、セグメント化とパーソナライゼーション用に既存の [!DNL Experience Platform] プロファイルを強化します。

2. **環境設定センターの更新** - 既知の購読者がランディングページ経由でコミュニケーション環境設定（チャネル、関心のあるトピック）を管理できるようにします。変更は通常、約 15 分以内に [!DNL Experience Platform] プロファイルに反映されます。

3. **イベントまたはウェビナーの登録** - 登録ページで既知のプロファイルからイベント固有のデータをキャプチャし、登録属性でプロファイルを更新し、確認ジャーニーをトリガーします。

4. **ロイヤルティまたはプログラムの登録** - 既存の顧客がランディングページを通じて追加の詳細を送信することで、ロイヤルティプログラムやメンバーシップ層に登録できるようにし、ダウンストリームのターゲティング用にプロファイルを強化します。

5. **競合またはコンテストのエントリ** - 既知の顧客がランディングページフォームを通じて競合または懸賞にエントリできるようにします。エントリ固有の詳細（回答、好み、宣言など）をキャプチャし、実施要件、勝者の選択、フォローアップジャーニーをサポートするためにプロファイルに書き込みます。

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
<img alt="Journey Optimizer のランディングページ用フォームリスト" src="../assets/do-not-localize/lp-design.jpg">
</a>
<div>
<a href="lp-forms.md"><strong>ランディングページでのフォームの使用</strong></a>
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

## 事前準備 {#prerequisites}

ランディングページを作成する前に、次の設定手順を実行します。

1. **サブドメインの設定** - ランディングページのホスティング専用のサブドメインを設定します。 [詳細情報](lp-subdomains.md)
1. **ランディングページプリセットの作成** - プリセットは、ランディングページに適用されるサブドメインやその他の設定を定義します。 [詳細情報](lp-presets.md#lp-create-preset)
1. **サブスクリプションリストの作成**（購読ユースケース向け）- 顧客が特定のサービスを購読または登録解除する場合に必要です。 [詳細情報](subscription-list.md)
1. **フォームの作成**（データキャプチャのユースケース向け）- **[!UICONTROL データキャプチャ]**&#x200B;のランディングページにフォームを埋め込み、[!DNL Experience Platform] に送信する場合に必要です。 [詳細情報](lp-forms.md)

## 仕組み {#how-it-works}

ランディングページの作成とデプロイは、次の順序で行います。

1. **ランディングページの作成と設定** - プリセットを選択し、プライマリページを設定し、必要なサブページを追加します。 [詳細情報](create-lp.md#create-landing-page)
1. **ページのデザイン** - [!DNL Journey Optimizer] のドラッグ＆ドロップエディターを使用して、ページのコンテンツとフォームを作成します。 [詳細情報](design-lp.md)
1. **ランディングページのテストと公開** - ページをプレビューし、フォームの動作をテストしてから公開します。 [詳細情報](create-lp.md#test-landing-page)
1. **メッセージまたはジャーニー内のリンク** – 顧客がアクセスできるように、ランディングページの URL をメール、キャンペーン、ジャーニーアクションに追加します。 [詳細情報](../email/message-tracking.md#insert-links)

## チュートリアルビデオ{#video}

次のビデオでは、サブスクリプションリストの作成方法、サービスのオプトインまたはオプトアウトを行うためのランディングページの設定方法、メッセージへのオプトイン／オプトアウトのオプションの統合方法、関連するジャーニーの設定方法について説明します。

>[!VIDEO](https://video.tv.adobe.com/v/341280?quality=12&learn=on)

➡️ **実際に見る：** サブスクリプション管理、確認メール、データキャプチャのシナリオをカバーするステップバイステップの例については、[&#x200B; ランディングページのユースケース &#x200B;](lp-use-cases.md)を確認してください。
