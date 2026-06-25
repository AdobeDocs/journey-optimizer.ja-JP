---
title: インボックスの作成
description: 継続的かつ押し付けがましくないメッセージをユーザーに配信する Adobe Journey Optimizer のインボックスの基本について説明します。
feature: Content Cards
topic: Content Management
role: User
level: Beginner
exl-id: 60190d0b-d8e7-4a78-9924-d948f2769f6c
source-git-commit: c2bb6cf702a14b4eef8f2209082e39cd73338378
workflow-type: ht
source-wordcount: '453'
ht-degree: 100%

---

# インボックスの基本を学ぶ {#inbox-gs}

>[!BEGINSHADEBOX]

**このページ：**&#x200B;インボックスチャネルでマーケティングメッセージをアプリや web サイト内の永続的な場所に保持する仕組みについて説明します。これにより、ユーザーが自分の都合に合わせて、これらのメッセージに戻り、アクションを実行できます。

>[!ENDSHADEBOX]

インボックスは、モバイルアプリや web サイト内で、永続的で低フリクションのメッセージを 1 か所で配信します。 アプリ内やプッシュはスワイプやタップの後に消えますが、インボックスはメッセージを使用できるので、ユーザーは都合の良いときにメッセージを開き、読み取り、操作できます。

インボックスは、コンテンツカードチャネル上に作成され、次の機能が追加されます。

* **永続メッセージ**：コンテンツは、ユーザーが削除するか有効期限が切れるまでインボックスに留まるので、ユーザーは通知を閉じたりアプリを終了したりした後でも、インボックスに戻ることができます。
* **一元的された場所**：関連性の高いマーケティングメッセージ用のアプリまたはサイト内の単一のメールボックス。
* **柔軟な実装**：既製のインボックスコンテナを使用するか、独自の UI でエクスペリエンスをカスタマイズします。
* **読み取りステータス**：メッセージは、メッセージを開いたデバイス上で既読または未読としてマークできます。

## クイックスタートガイド

インボックスを設定して使用するには、次の手順に従います。

1. [Adobe Journey Optimizer を設定](inbox-configuration.md)

   インボックスが実行される場所と仕組み（web ページまたはルールや、モバイルアプリサーフェス）を Journey Optimizer が認識できるように、**チャネル設定**&#x200B;の下に&#x200B;**インボックス**&#x200B;チャネル設定を追加します。

1. [Journey Optimizer でインボックスを作成](inbox-create.md)

   **コンテンツカード**&#x200B;アクションを使用するキャンペーンを作成し、配信場所として「**インボックス**」を選択します。配信は UI からスケジュールするか、API によりトリガーされます。

1. [インボックスをデザイン](inbox-design.md)

   メッセージをブランドや UX と一致させるために、インボックスのテンプレートとリストレイアウトまたは拡張レイアウトを選択します。

1. [コンテンツカードを作成し、インボックスにリンク](../content-card/create-content-card.md)

   デザイナーでカードコンテンツを作成し、インボックス固有のオプションを終了したら、キャンペーンをアクティブ化してメッセージがインボックスに届くようにします。

## その他のリソース

* [インボックス UI（iOS）](https://developer.adobe.com/client-sdks/edge/adobe-journey-optimizer/inbox-ui/iOS)：Adobe Experience Platform Mobile SDK（iOS 15 以降、Xcode 15 以降、Swift 5.1 以降）を使用して iOS アプリに Journey Optimizer インボックスを実装するための要件、公開 API サーフェス、インボックス設定、チュートリアルへのリンク。

* [インボックスの取得と表示](https://developer.adobe.com/client-sdks/edge/adobe-journey-optimizer/inbox-ui/Android/tutorial/displaying-inbox)：Journey Optimizer のインボックスメッセージを読み込み、Android 上でインボックス UI をレンダリングします（Adobe Developer ドキュメント）。

* [インボックスのカスタマイズ](https://developer.adobe.com/client-sdks/edge/adobe-journey-optimizer/inbox-ui/Android/tutorial/customizing-inbox)：Android アプリのインボックスのレイアウト、スタイル、インタラクションの動作を調整します（Adobe Developer ドキュメント）。

* [インボックスイベントのリッスン](https://developer.adobe.com/client-sdks/edge/adobe-journey-optimizer/inbox-ui/Android/tutorial/listening-inbox-events)：Android 上でユーザーアクションとライフサイクル更新に関するインボックスコールバックを登録します（Adobe Developer ドキュメント）。
