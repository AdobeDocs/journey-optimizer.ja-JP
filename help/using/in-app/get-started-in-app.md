---
title: アプリ内メッセージの基本を学ぶ
description: Journey Optimizer でアプリ内通知を送信する方法を学ぶ
feature: In App
topic: Content Management
role: User
level: Beginner
keywords: アプリ内, メッセージ, 作成, 開始
exl-id: 51562843-7b50-4eb5-bf79-5ce03f7549cb
TQID: https://experienceleague.adobe.com/b139LQsPe3HwKe1O5cyBx4Nj4jpW3GXCFIVIWTAIlbg
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2:
  - id: d0a62d3c-b79e-47e4-929e-40ef3cffa037
subfeature_v2:
  - id: b3a93754-a8b8-46eb-9421-7eccaeeb3dff
  - id: cc5c44e2-54a1-4927-b794-442cd87d8f74
  - id: c96d2aa5-76a2-443d-8d23-5de95577c909
  - id: e30b0a1a-b594-47b8-af94-1e3a2be6df11
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: 75ebd043971ce40e2da0f627622441a46a8e667c
workflow-type: tm+mt
source-wordcount: 601
ht-degree: 44%

---

# アプリ内チャネルの基本を学ぶ {#gs-in-app}

>[!BEGINSHADEBOX]

**このページ：** Adobe Journey Optimizer のアプリ内メッセージチャネルの基本を学びます。これにより、機能、オファー、オンボーディングをプロモートする通知で、アプリユーザーのエンゲージメントを向上させることができます。

>[!ENDSHADEBOX]

アプリ内メッセージとは、特定の目標地点に向かって、アプリ内でユーザーに送信できる通知です。 これらの通知は、新機能の宣伝、特別オファーの提示、ユーザーのオンボーディングの促進など、様々な目的に使用できます。 アプリ内メッセージを活用することで、オーディエンスと効果的に関わり、アプリケーションの重要な側面に向けることができます。

Journey Optimizer を使用すると、アプリ内通知を作成し、メッセージのレイアウトと表示、テキスト、ボタンオプションなどのエクスペリエンスオプションを設定できます。

</br>

<table style="table-layout:fixed"><tr style="border: 0;">
<td>
<a href="inapp-configuration.md">
<img alt="検証" src="../assets/do-not-localize/inapp-config.jpg">
</a>
<div>
<a href="inapp-configuration.md"><strong>アプリ内チャネルの設定</strong></a>
</div>
<p>
</td>
<td>
<a href="create-in-app.md">
<img alt="リード" src="../assets/do-not-localize/inapp-create.jpeg">
</a>
<div><a href="create-in-app.md"><strong>アプリ内メッセージの作成</strong>
</div>
<p>
</td>
<td>
<a href="design-in-app.md">
<img alt="低頻度" src="../assets/do-not-localize/inapp-design.jpg">
</a>
<div>
<a href="design-in-app.md"><strong>アプリ内コンテンツのデザイン</strong></a>
</div>
<p></td>
<td>
<a href="../reports/campaign-global-report-cja-inapp.md">
<img alt="検証" src="../assets/do-not-localize/inapp-report.jpg">
</a>
<div>
<a href="../reports/campaign-global-report-cja-inapp.md"><strong>アプリ内レポートへのアクセス</strong></a>
</div>
<p>
</td>
</tr></table>

## ユースケース

アプリ内メッセージは、オーディエンスが既にアプリとエンゲージしている間に、その瞬間に注意を払って誘導したり影響を与えたりしたい場合に最も効果を発揮します。

| 利点 | 理由 | ユースケースの例 |
| --- | --- | --- |
| ユーザーエンゲージメントの向上 | ユーザーがアプリセッション内でアクティブにリーチする | 機能のお知らせ、オンボーディングのヒント |
| コンテクストに即したトリガー | アプリ内の行動や位置情報にもとづいてトリガーできます | 利用者が関連画面にアクセスした直後に、その機能をハイライト表示 |
| リアルタイム配信 | プッシュトークンや外部配信サービスに依存しない | 現在のセッション中に表示される時間依存プロンプト |
| 外部チャネルに依存しない | 他のチャネルのオプトインステータスとは関係なく、アプリ内で完全に機能します | プッシュ通知をオプトアウトしたユーザーにリーチ |
| コンバージョンの可能性の向上 | 常に注意を払っている状態で提供されるため、応答率が向上します | アップセル/クロスセルのオファー、アンケートプロンプト |
| カスタマイズとセグメンテーション | レイアウト、テキスト、ボタンは特定のオーディエンスに合わせてカスタマイズできます | 様々なユーザーセグメント向けにパーソナライズされたオンボーディングフロー |
| 邪魔にならないデザイン | ユーザーエクスペリエンスを中断することなく、補完するように設計できる | アプリのUIに沿ったバナーやモーダル |

## 使用しない場合

アプリ内メッセージはアクティブなセッションに依存するため、すべてのシナリオに適しているわけではありません。 次のような状況では、別のチャネルを検討してください。

* メッセージは表示されないので、ユーザーはアプリを積極的に使用していません
* メッセージは、システム停止やセキュリティアラートなど、アプリ外のユーザーに連絡する必要がある、重要な問題または時間的制約のある問題です
* このコミュニケーションは規制または合法であり、アプリ内メッセージでは提供できないことを確認する必要があります
* 目標は、アカウントの再アクティブ化またはアプリを開く可能性が低い非アクティブなユーザーのウィンバック施策です
* メッセージは、注文確認などの大量のトランザクションアップデートで、メールやSMSに適しています
* メッセージを過剰に使用すると、バナーが盲目になり、表示され過ぎるメッセージを無視しがちです
* メッセージを配信する場合、ユーザーがオフラインであるか、アプリに接続されていない可能性があります



## その他のリソース

* **[アプリ内メッセージの作成](create-in-app.md)** - モバイルアプリケーションのアプリ内メッセージを作成および設定する方法について説明します。
* **[アプリ内チャネルの設定](inapp-configuration.md)** - 適切なモバイルアプリ設定を使用して、アプリ内メッセージチャネルを設定します。
* **[アプリ内コンテンツのデザイン](design-in-app.md)** - アプリ内メッセージのレイアウト、スタイル、ボタン、インタラクティブ要素をカスタマイズします。
* **[Web 用のアプリ内](create-in-app-web.md)** - web アプリケーション用のアプリ内メッセージを作成および配信する方法について説明します。
* **[アプリ内チャネルのチュートリアル &#x200B;](https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/channels/in-app-channel/in-app-messages-overview){target="_blank"}**- アプリ内メッセージ機能とベストプラクティスに関するステップバイステップのビデオチュートリアルを参照してください。

