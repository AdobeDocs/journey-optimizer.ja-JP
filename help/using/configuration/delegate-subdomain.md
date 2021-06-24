---
title: サブドメインのデリゲート
description: サブドメインのデリゲート方法を学ぶ
page-status-flag: never-activated
uuid: null
contentOwner: null
products: null
audience: administrators
content-type: reference
topic-tags: null
discoiquuid: null
internal: n
snippet: y
feature: アプリケーション設定
topic: 管理
role: Administrator
level: Intermediate
source-git-commit: b58c5b527e594c03f3b415549e6b7cd15b050139
workflow-type: tm+mt
source-wordcount: '446'
ht-degree: 100%

---


# サブドメインのデリゲート

ドメイン名のデリゲーションによって、ドメイン名（技術的には DNS ゾーン）の所有者はその一部（技術的にはその配下の DNS ゾーン。サブゾーンと呼ばれることもあります）を別のエンティティにデリゲートできます。基本的に、「example.com」ゾーンを扱う顧客は「marketing.example.com」というサブゾーンをアドビにデリゲートできます。

[!DNL Journey Optimizer] で使用するサブドメインをデリゲートすると、クライアントはメールマーケティングに関する業界標準の配信品質要件を満たすために必要な、DNS インフラストラクチャの管理をアドビに依存しながら、自分たちで社内メール用ドメインの DNS を管理および制御することができます。

[!DNL Journey Optimizer] では、サブドメインを製品インターフェイスから直接アドビに、完全にデリゲートできます。アドビは、メールキャンペーンの配信、レンダリング、トラッキングに必要な DNS のあらゆる側面を制御および管理することで、メッセージをマネージドサービスとして提供できます。

>[!NOTE]
>
>デフォルトでは、[!DNL Journey Optimizer] ライセンス契約で、最大 10 個のサブドメインをデリゲートできます。この制限を引き上げる場合は、アドビの担当者にお問い合わせください。
>
>サブドメインのデリゲーションに対する CNAME の使用は、現在 Journey Optimizer ではサポートされていません。

新しいサブドメインをデリゲートするには、次の手順に従います。

1. **[!UICONTROL チャネル]**／**[!UICONTROL サブドメイン]**&#x200B;メニューにアクセスし、「**[!UICONTROL サブドメインをデリゲート]**」をクリックします。

   ![](../assets/subdomain-delegate.png)

1. デリゲートするサブドメインの名前を指定します。

   ![](../assets/subdomain-name.png)

1. DNS サーバーに配置するレコードのリストが表示されます。これらのレコードを 1 つずつコピーするか、CSV ファイルをダウンロードしてから、ドメインのホスティングソリューションに移動して、一致する DNS レコードを生成します。

   ドメインをホストするソリューションに、すべての DNS レコードが生成されていることを確認してください。すべてが正しく設定されている場合は、「確認しました」チェックボックスをオンにし、「**[!UICONTROL 送信]**」をクリックします。

   ![](../assets/subdomain-submit.png)

   >[!NOTE]
   >
   >後から「**[!UICONTROL ドラフトとして保存]**」ボタンを使用してレコードを作成し、サブドメイン設定を送信できます。 その後、サブドメインリストからサブドメインのデリゲーションを開くことで、再開できます。

1. サブドメインのデリゲーションが送信されると、そのサブドメインは「**[!UICONTROL 処理中]**」ステータスでリストに表示されます。サブドメインのステータスについて詳しくは、[この節](access-subdomains.md)を参照してください。

   以下のチェックとアクションは、サブドメインが検証され、サブドメインを使用してメッセージを送信できる状態になるまで実行されます。

   この手順はアドビが実行し、最大 3 時間かかります。

   1. サブドメインがアドビ DNS（NS レコード、SOA レコード、ゾーン設定、所有権レコード）にデリゲートされているかどうかを確認します。
   1. ドメインの DNS を設定します。
   1. トラッキング URL とミラー URL の作成
   1. CDN Cloud Front のプロビジョニング。
   1. CDN SSL 証明書を作成、検証および添付する。
   1. 転送 DNS を作成する。
   1. PTR レコードを作成する。

   ![](../assets/subdomain-processing.png)

1. チェックが正常に完了すると、サブドメインは「**[!UICONTROL 成功]**」ステータスを取得します。 メッセージの配信に使用する準備が整いました。

   <!-- later on, users will be notified in Pulse -->

   ![](../assets/subdomain-notification.png)


