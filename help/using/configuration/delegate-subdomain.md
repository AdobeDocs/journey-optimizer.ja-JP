---
title: サブドメインのデリゲート
description: サブドメインのデリゲート方法を説明します
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
ht-degree: 17%

---


# サブドメインのデリゲート

ドメイン名の委任によって、ドメイン名（技術的には DNS ゾーン）の所有者はその一部（技術的には、その下にある DNS ゾーンで、サブゾーンと呼ばれることもあります）を別のエンティティに委任できます。基本的に、顧客がゾーン「example.com」を処理する場合、サブゾーン「marketing.example.com」をAdobeにデリゲートできます。

[!DNL Journey Optimizer]で使用するサブドメインをデリゲートすることで、クライアントは、社内EメールドメインのDNSの維持管理を続けながら、Eメールマーケティング送信ドメインの業界標準の配信品質要件を満たすために必要なDNSインフラストラクチャをAdobeに依存できます。

[!DNL Journey Optimizer] では、サブドメインを製品インターフェイスから直接Adobeに完全にデリゲートできます。これにより、Adobeは、Eメールキャンペーンの配信、レンダリング、トラッキングに必要なDNSのあらゆる側面を制御し、維持することで、メッセージを管理対象サービスとして配信できます。

>[!NOTE]
>
>デフォルトでは、[!DNL Journey Optimizer]ライセンス契約では、最大10個のサブドメインをデリゲートできます。 この制限を引き上げる場合は、Adobeの担当者にお問い合わせください。
>
>サブドメインデリゲーションに対するCNAMEの使用は、現在、Journey Optimizerではサポートされていません。

新しいサブドメインをデリゲートするには、次の手順に従います。

1. **[!UICONTROL チャネル]** / **[!UICONTROL サブドメイン]**&#x200B;メニューにアクセスし、「**[!UICONTROL サブドメインをデリゲート]**」をクリックします。

   ![](../assets/subdomain-delegate.png)

1. デリゲートするサブドメインの名前を指定します。

   ![](../assets/subdomain-name.png)

1. DNS サーバーに配置するレコードのリストが表示されます。これらのレコードを 1 つずつコピーするか、CSV ファイルをダウンロードしてから、ドメインのホスティングソリューションに移動して、一致する DNS レコードを生成します。

   すべてのDNSレコードが、ドメインホスティングソリューションで生成されていることを確認します。 すべてが正しく設定されている場合は、「I confirm...」チェックボックスをオンにし、「**[!UICONTROL 送信]**」をクリックします。

   ![](../assets/subdomain-submit.png)

   >[!NOTE]
   >
   >後で「**[!UICONTROL ドラフトとして保存]**」ボタンを使用して、レコードを作成し、サブドメイン設定を送信できます。 その後、サブドメインリストからサブドメインデリゲーションを開くことで、再開できます。

1. サブドメインデリゲーションが送信されると、そのサブドメインが「**[!UICONTROL 処理]**」ステータスでリストに表示されます。 サブドメインのステータスについて詳しくは、[この節](access-subdomains.md)を参照してください。

   以下のチェックとアクションは、サブドメインが検証され、を使用してメッセージを送信できる状態になるまで実行されます。

   この手順はAdobeが実行し、最大3時間かかります。

   1. サブドメインがAdobeDNS（NSレコード、SOAレコード、ゾーン設定、所有権レコード）にデリゲートされているかどうかを確認します。
   1. ドメインのDNSを設定します。
   1. トラッキングURLとミラーURLの作成
   1. CDNクラウドフロントのプロビジョニング
   1. CDN SSL証明書の作成、検証および添付
   1. 転送DNSの作成
   1. PTRレコードを作成します。

   ![](../assets/subdomain-processing.png)

1. チェックが正常に完了すると、サブドメインは&#x200B;**[!UICONTROL 成功]**&#x200B;ステータスを取得します。 メッセージの配信に使用する準備が整いました。

   <!-- later on, users will be notified in Pulse -->

   ![](../assets/subdomain-notification.png)


