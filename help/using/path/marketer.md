---
title: Journey Optimizer Marketers はじめに
description: ジャーニー実行者として、Journey Optimizerの操作方法の詳細を学ぶ
level: Intermediate
exl-id: 34304142-3ee8-4081-94b9-e914968c75ba
source-git-commit: f0c5b42984b76fee005fe0c0e10312d47f9d10e8
workflow-type: tm+mt
source-wordcount: '461'
ht-degree: 56%

---

# マーケター向けスタートガイド

![マーケター](assets/do-not-localize/user-3.png)

As a **マーケター** または **ジャーニー実習者**&#x200B;に値を入力する場合、メッセージ、オファー、ジャーニーの作成を担当します。 以下の作業を開始する前に、 [!DNL Adobe Journey Optimizer] を [システム管理者](administrator.md) そして [データエンジニア](data-engineer.md) により、アクセス権が付与され、環境が準備されました。

最初のジャーニーの設定、オファーとアセットの追加、メッセージの送信については、以下の節を参照してください。

1. **セグメントの作成**. Journey Optimizerでは、 **セグメント** メニューで使用し、ジャーニーで活用できます。  セグメントの詳細 [このページ](../segment/about-segments.md). セグメントの作成方法の確認 [このサンプル](../segment/creating-a-segment.md).

1. **メッセージの作成**. Journey Optimizerで電子メールおよびプッシュ通知を作成する方法を説明します [このページ](../create-message.md).

   ![](../assets/email_designer_7.png)

1. **パーソナライゼーションの追加**. Journey Optimizerのパーソナライゼーション機能を活用して、メッセージをオーディエンスに合わせて調整します。 パーソナライゼーションの詳細 [この節](../personalization/personalize.md).

   ![](../personalization/assets/perso_ee2.png)

1. **アセットの作成と管理**. [!DNL Adobe Experience Manager Assets Essentials] は、メッセージへのアセットの入力に使用できる一元的なアセットリポジトリを提供します。詳しくは、[この節](../assets-essentials.md)を参照してください。

1. **オファーの追加**. [!DNL Journey Optimizer] を使用すると、すべてのタッチポイントをまたいで、適切なタイミングで最高のオファーとエクスペリエンスを顧客に提供できます。デザインが完了すると、パーソナライズされたオファーを使用してオーディエンスをターゲットに設定できます。判定管理の詳細を説明します [この節](../../using/offers/get-started/starting-offer-decisioning.md).

   ![](../assets/offers-e2e-offers-displayed.png)

1. **メッセージのテストと検証**. メッセージコンテンツを定義したら、テストプロファイルを使用してプレビューとテストをおこなうことができます。[パーソナライズされたコンテンツ](../personalization/personalize.md)を挿入している場合は、テストプロファイルデータを利用して、その内容がメッセージにどのように表示されるかを確認できます。さらに、**Litmus** アカウントを [!DNL Journey Optimizer] に活用すると、よく使うメールクライアントで、**メールのレンダリング**&#x200B;を即座にプレビューすることができます。すべてのインボックスでメールコンテンツが適切に表示され、正しく機能することを確認できます。メッセージのテストと検証の方法を説明します [この節](../preview.md).

1. **カスタマージャーニーの設計** パーソナライズされたコンテキストエクスペリエンスを提供する [!DNL Journey Optimizer] では、イベントやデータソースに保存されたコンテキストデータを活用して、リアルタイムオーケストレーションのユースケースを構築できます。次の機能を活用して、複数のステップから成る詳細なシナリオを設計できます。

   * イベントの受信をトリガーにしてリアルタイムに&#x200B;**単一メッセージ**&#x200B;を送信したり、Adobe Experience Platform のセグメントを使用してメッセージを&#x200B;**一括で**&#x200B;送信したりできます。

   * イベント、Adobe Experience Platform の情報、サードパーティの API サービスのデータなどの&#x200B;**コンテキストデータ**&#x200B;を活用できます。

   * **組み込みのアクション**&#x200B;を使用して [!DNL Journey Optimizer] でデザインしたメッセージを送信したり、サードパーティのシステムを使用している場合は&#x200B;**カスタムアクション**&#x200B;を作成してメッセージを送信したりできます。

   * **ジャーニーデザイナー**&#x200B;を使用すると、エントリイベントやセグメントの読み取りアクティビティを簡単にドラッグ＆ドロップして、条件を追加し、パーソナライズされたメッセージを送信するなど、複数の手順から成るユースケースを作成できます。

   ![](../assets/copy-paste3.png)

   ジャーニーの設計と実行方法を説明します [この節](../building-journeys/journey-gs.md)

1. **メッセージとジャーニーの監視**. メッセージが正常に実行、送信、および配信されていることを確認するため、[!DNL Journey Optimizer] では、現在公開およびトリガーされているメッセージを監視する機能を提供しています。パフォーマンスの監視方法を学ぶ [この節](../message-monitoring.md).
