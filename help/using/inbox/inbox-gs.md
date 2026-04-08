---
title: 受信トレイの作成
description: Adobe Journey Optimizerの受信トレイを使用して、永続的で邪魔にならないメッセージをユーザーに配信します。
feature: Content Cards
topic: Content Management
role: User
level: Beginner
exl-id: 60190d0b-d8e7-4a78-9924-d948f2769f6c
source-git-commit: f7f303685e954614b44a9b62368460e9b07b26b3
workflow-type: tm+mt
source-wordcount: '363'
ht-degree: 1%

---

# 受信トレイの設定 {#inbox-gs}

インボックスは、モバイルアプリやweb サイト内で、永続的でスムーズなメッセージを一元的に配信します。 スワイプやタップの後、アプリ内メッセージやプッシュ通知が消えてしまうことがあります。Inboxでは、メッセージを利用可能な状態に保つことで、オーディエンスが自分に合ったときにメッセージを開いて読み、操作できるようにしています。

インボックスは、コンテンツカードチャネル上に構築され、次のように追加されます。

* **永続的なメッセージ**：コンテンツは、削除するか期限切れになるまで受信トレイに残ります。ユーザーは、通知を閉じたりアプリを終了したりした後でも、受信トレイに戻ることができます。
* **一元的な場所**：関連するマーケティングメッセージ用のアプリまたはサイト内の単一のメールボックス。
* **柔軟な実装**：既製の受信トレイ コンテナを使用するか、独自のUIでエクスペリエンスをカスタマイズします。
* **読み取り状態**: メッセージを開いたデバイスで読み取り済みまたは未読としてマークできます。

## クイックスタートガイド

受信トレイを設定して使用するには、次の手順に従います。

1. [Adobe Journey Optimizerの設定](inbox-configuration.md)

   **チャネル設定**&#x200B;の下に&#x200B;**受信トレイ** チャネル設定を追加して、Journey Optimizerが受信トレイの実行場所と実行方法（web ページ、ルール、モバイルアプリサーフェス）を把握できるようにします。

1. [Journey Optimizerでの受信トレイの作成](inbox-create.md)

   **コンテンツカード** アクションを使用するキャンペーンを作成し、配信の場所として&#x200B;**受信トレイ**&#x200B;を選択します（UIからスケジュールまたはAPIによってトリガー）。

1. [受信トレイをデザイン](inbox-design.md)

   ブランドやUXに合わせて、受信トレイのテンプレートとリストレイアウトまたは拡張レイアウトを選択できます。

1. [コンテンツカードを作成し、インボックスにリンクします](../content-card/create-content-card.md)

   デザイナーでカードコンテンツを作成し、「受信トレイ固有のオプション」を終了してからキャンペーンをアクティブ化して、メッセージを受信トレイに届けます。

## その他のリソース

* [受信トレイ UI （iOS） &#x200B;](https://developer.adobe.com/client-sdks/edge/adobe-journey-optimizer/inbox-ui/iOS/)：要件、公開API サーフェス、受信トレイ設定、およびAdobe Experience Platform Mobile SDK（iOS 15以降、Xcode 15以降、Swift 5.1以降）を使用してiOS アプリにJourney Optimizer インボックスを実装するためのチュートリアルへのリンク。

* [受信トレイを取得して表示](https://developer.adobe.com/client-sdks/edge/adobe-journey-optimizer/inbox-ui/Android/tutorial/displaying-inbox/): Journey Optimizerの受信トレイ メッセージを読み込み、Androidで受信トレイ UIをレンダリングします（Adobe Developer ドキュメント）。

* [受信トレイのカスタマイズ &#x200B;](https://developer.adobe.com/client-sdks/edge/adobe-journey-optimizer/inbox-ui/Android/tutorial/customizing-inbox/):Android アプリの受信トレイのレイアウト、スタイル、インタラクションの動作を調整します（Adobe Developer ドキュメント）。

* [受信トレイ イベントのリッスン &#x200B;](https://developer.adobe.com/client-sdks/edge/adobe-journey-optimizer/inbox-ui/Android/tutorial/listening-inbox-events/): Androidのユーザーアクションとライフサイクルの更新に関する受信トレイ コールバックの購読（Adobe Developer ドキュメント）。
