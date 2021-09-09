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
feature: Application Settings
topic: Administration
role: Admin
level: Intermediate
exl-id: 8021f66e-7725-475b-8722-e6f8d74c9023
source-git-commit: 7138e1f031bd26caf9379c3ff19d79ac29442bc6
workflow-type: tm+mt
source-wordcount: '768'
ht-degree: 55%

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

   >[!CAUTION]
   >
   >無効なサブドメインをアドビにデリゲートすることはできません。組織が所有する有効なサブドメイン（marketing.yourcompany.com など）を入力してください。
   >
   >email.marketing.yourcompany.com などマルチレベルのサブドメインは、現在サポートされていません。

1. DNS サーバーに配置するレコードのリストが表示されます。これらのレコードを 1 つずつコピーするか、CSV ファイルをダウンロードしてから、ドメインのホスティングソリューションに移動して、一致する DNS レコードを生成します。

1. ドメインをホストするソリューションに、すべての DNS レコードが生成されていることを確認してください。すべてが正しく設定されている場合は、「確認しました」チェックボックスをオンにし、「**[!UICONTROL 送信]**」をクリックします。

   ![](../assets/subdomain-submit.png)

   >[!NOTE]
   >
   >後から「**[!UICONTROL ドラフトとして保存]**」ボタンを使用してレコードを作成し、サブドメイン設定を送信できます。 その後、サブドメインリストからサブドメインのデリゲーションを開くことで、再開できます。

1. サブドメインのデリゲーションが送信されると、そのサブドメインは「**[!UICONTROL 処理中]**」ステータスでリストに表示されます。サブドメインのステータスについて詳しくは、[この節](access-subdomains.md)を参照してください。

   ![](../assets/subdomain-processing.png)

   そのサブドメインを使用してメッセージを送信する前に、Adobeが必要なチェックを実行するまで待つ必要があります（最大3時間かかります）。 詳しくは、[この節](#subdomain-validation)を参照してください。

1. チェックが正常に完了すると、サブドメインのステータスが&#x200B;**[!UICONTROL 成功]**&#x200B;になります。 メッセージの配信に使用する準備が整いました。

   <!-- later on, users will be notified in Pulse -->

   ![](../assets/subdomain-notification.png)

## サブドメインの検証 {#subdomain-validation}

以下のチェックとアクションは、サブドメインが検証され、サブドメインを使用してメッセージを送信できる状態になるまで実行されます。

>[!NOTE]
>
>これらの手順はAdobeが実行し、最大3時間かかります。

1. **事前検証**:Adobeは、サブドメインがAdobeDNS（NSレコード、SOAレコード、ゾーン設定、所有権レコード）にデリゲートされたかどうかを確認します。検証前の手順が失敗した場合は、対応する理由と共にエラーが返され、失敗した場合は次の手順にAdobeが進みます。

1. **ドメインのDNSの設定**:

   * **MXレコード**:Mail eXchange record — サブドメインに送信されるインバウンドEメールを処理するメールサーバーレコード。
   * **SPFレコード**:送信者ポリシーフレームワークレコード — サブドメインからEメールを送信できるメールサーバーのIPを一覧表示します。
   * **DKIMレコード**:DomainKeys Identified Mail standard record — 公開鍵と秘密鍵の暗号化を使用して、スプーフィングを避けるためにメッセージを認証します。
   * **A**:デフォルトのIPマッピング。

1. **トラッキングURLとミラーURLの作成**:ドメインがemail.example.comの場合、tracking/mirrorドメインはdata.email.example.comになります。SSL証明書をインストールすることで保護されます。

1. **CDN CloudFrontのプロビジョニング**:CDNがまだ設定されていない場合、AdobeはそのCDNをインソーグ用にプロビジョニングします。

1. **CDNドメインの作成**:ドメインがemail.example.comの場合、CDNドメインはcdn.email.example.comになります。

1. **CDN SSL証明書の作成と添付**:Adobeは、CDNドメイン用のCDN証明書を作成し、その証明書をCDNドメインに添付します。

1. **転送DNSの作成**:これが最初にデリゲートするサブドメインである場合、Adobeは、PTRレコードを作成するために必要な転送DNSを作成します。PTRレコードは、各IPに対して1つずつ作成されます。

1. **PTRレコードの作成**:PTRレコード（逆引きDNSレコードとも呼ばれます）は、Eメールをスパムとしてマークしないように、ISPに必要です。また、Gmailでは、各IPにPTRレコードを持つことを推奨します。 Adobeは、最初のサブドメインをデリゲートした場合にのみPTRレコードを作成します。各IPに対して1つずつ、最初のサブドメインを指すすべてのIPがデリゲートされます。 例えば、IPが&#x200B;*192.1.2.1*&#x200B;で、サブドメインが&#x200B;*email.example.com*&#x200B;の場合、PTRレコードは次のようになります。*192.1.2.1 PTR r1.email.example.com* 後でPTRレコードを更新して、新しいデリゲートドメインを指すことができます。
