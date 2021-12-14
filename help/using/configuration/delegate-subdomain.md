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
source-git-commit: c548852b976100935271afafd5267fd7f32a9b50
workflow-type: tm+mt
source-wordcount: '1435'
ht-degree: 59%

---

# サブドメインのデリゲート

ドメイン名のデリゲーションによって、ドメイン名（技術的には DNS ゾーン）の所有者はその一部（技術的にはその配下の DNS ゾーン。サブゾーンと呼ばれることもあります）を別のエンティティにデリゲートできます。基本的に、お客様が「example.com」ゾーンを扱う場合、サブゾーン「marketing.example.com」をアドビにデリゲートできます。

[!DNL Journey Optimizer] で使用するサブドメインをデリゲートすると、クライアントはメールマーケティングに関する業界標準の配信品質要件を満たすために必要な、DNS インフラストラクチャの管理をアドビに依存しながら、自分たちで社内メール用ドメインの DNS を管理および制御することができます。

## 完全なサブドメインのデリゲーション {#full-subdomain-delegation}

[!DNL Journey Optimizer] では、サブドメインを製品インターフェイスから直接アドビに、完全にデリゲートできます。アドビは、メールキャンペーンの配信、レンダリング、トラッキングに必要な DNS のあらゆる側面を制御および管理することで、メッセージをマネージドサービスとして提供できます。

>[!NOTE]
>
>デフォルトでは、[!DNL Journey Optimizer] ライセンス契約で、最大 10 個のサブドメインをデリゲートできます。この制限を引き上げる場合は、アドビの担当者にお問い合わせください。

新しいサブドメインをデリゲートするには、次の手順に従います。

1. 次にアクセス： **[!UICONTROL 管理]** > **[!UICONTROL チャネル]** > **[!UICONTROL サブドメイン]** メニュー、次に「 **[!UICONTROL サブドメインの設定]**.

   ![](../assets/subdomain-delegate.png)

1. 選択 **[!UICONTROL 完全に委任済み]** から **[!UICONTROL メソッドの設定]** 」セクションに入力します。

   ![](../assets/subdomain-method-full.png)

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

1. 完全なサブドメインデリゲーションが送信されると、サブドメインがリストに表示され、 **[!UICONTROL 処理中]** ステータス。 サブドメインのステータスについて詳しくは、[この節](access-subdomains.md)を参照してください。

   ![](../assets/subdomain-processing.png)

   そのサブドメインを使用してメッセージを送信できるようになるには、必要なチェックがアドビで実行されるまで待つ必要があります（最大で 3 時間かかることがあります）。詳しくは、[この節](#subdomain-validation)を参照してください。

   >[!NOTE]
   >
   >見つからないレコード（ホスティングソリューションでまだ作成されていないレコード）が表示されます。

1. チェックが正常に完了すると、サブドメインのステータスが&#x200B;**[!UICONTROL 成功]**&#x200B;になります。 メッセージの配信に使用する準備が整いました。

   >[!NOTE]
   >
   >サブドメインは **[!UICONTROL 失敗]** ホスティングソリューション上に検証レコードを作成できない場合。

   <!-- later on, users will be notified in Pulse -->

サブドメインがのAdobeにデリゲートされた後 [!DNL Journey Optimizer]を指定すると、PTR レコードが自動的に作成され、このサブドメインに関連付けられます。 [詳細情報](ptr-records.md)

>[!CAUTION]
>
>現在、サブドメインの並列実行は、 [!DNL Journey Optimizer]. 別のドメインに **[!UICONTROL 処理中]** のステータスに値を指定すると、エラーメッセージが表示されます。

## CNAME サブドメインのデリゲーション {#cname-subdomain-delegation}

ドメイン固有の制限ポリシーがあり、Adobeが DNS を部分的に制御する必要がある場合は、自分の側で DNS 関連のすべてのアクティビティを実行するように選択できます。

CNAME サブドメインデリゲーションを使用すると、サブドメインを作成し、CNAME を使用してAdobe固有のレコードを指定できます。 この設定を使用すると、ユーザーとAdobeの両方が、E メールの送信、レンダリング、トラッキングの環境を設定するために、DNS の維持に関する責任を共有します。

>[!CAUTION]
>
>組織のポリシーで完全なサブドメインデリゲーション方法が制限されている場合は、この方法をお勧めします。 このアプローチでは、DNS レコードを自分で管理および管理する必要があります。 Adobeは、CNAME メソッドを使用して設定されたサブドメインの DNS の変更、保守または管理をサポートできなくなります。

CNAME を使用してサブドメインをデリゲートするには、次の手順に従います。

1. 次にアクセス： **[!UICONTROL 管理]** > **[!UICONTROL チャネル]** > **[!UICONTROL サブドメイン]** メニュー、次に「 **[!UICONTROL サブドメインの設定]**.

1. を選択します。 **[!UICONTROL CNAME の設定]** メソッド。

   ![](../assets/subdomain-method-cname.png)

   <!--The steps to specify the name of the subdomain to delegate and to generate the DNS records into your domain hosting solution are the same as for full subdomain delegation. See **steps 3 to 5** of the [Full subdomain delegation](#full-subdomain-delegation) section.)-->

1. デリゲートするサブドメインの名前を指定します。

   >[!CAUTION]
   >
   >無効なサブドメインをアドビにデリゲートすることはできません。組織が所有する有効なサブドメイン（marketing.yourcompany.com など）を入力してください。
   >
   >email.marketing.yourcompany.com などマルチレベルのサブドメインは、現在サポートされていません。

1. DNS サーバーに配置するレコードのリストが表示されます。これらのレコードを 1 つずつコピーするか、CSV ファイルをダウンロードしてから、ドメインのホスティングソリューションに移動して、一致する DNS レコードを生成します。

1. ドメインをホストするソリューションに、すべての DNS レコードが生成されていることを確認してください。すべてが正しく設定されている場合は、「確認中…」チェックボックスをオンにします。

   ![](../assets/subdomain-create-dns-confirm.png)

   >[!NOTE]
   >
   >後で **[!UICONTROL ドラフトとして保存]** 」ボタンをクリックします。 その後、この段階でサブドメインデリゲーションをサブドメインリストから開くことで、再開できます。

1. Adobeが、これらのレコードがエラーなしでホスティングソリューションで生成されたことを確認するまで待ちます。 この処理には最大 2 分かかる場合があります。

   >[!NOTE]
   >
   >見つからないレコード（ホスティングソリューションでまだ作成されていないレコード）が表示されます。

1. Adobeが SSL CDN URL 検証レコードを生成します。 この検証レコードをホスティングプラットフォームにコピーします。 ホスティングソリューションでこのレコードを適切に作成している場合は、「確認する」チェックボックスをオンにし、 **[!UICONTROL 送信]**.

   ![](../assets/subdomain-cdn-url-validation.png)

   >[!NOTE]
   >
   >また、後で **[!UICONTROL ドラフトとして保存]** 」ボタンをクリックします。 その後、サブドメインリストからサブドメインのデリゲーションを開くことで、再開できます。

1. CNAME サブドメインデリゲーションが送信されると、サブドメインがリストに表示され、 **[!UICONTROL 処理中]** ステータス。 サブドメインのステータスについて詳しくは、[この節](access-subdomains.md)を参照してください。

   そのサブドメインを使用してメッセージを送信する前に、Adobeが必要なチェックを実行するまで待つ必要があります。通常は、2 ～ 3 時間かかります。 詳しくは、[この節](#subdomain-validation)を参照してください。

1. チェックが正常に完了したら、<!--i.e Adobe validates the record you created and installs it-->に値を指定しない場合、サブドメインは **[!UICONTROL 成功]** ステータス。 メッセージの配信に使用する準備が整いました。

   >[!NOTE]
   >
   >サブドメインは **[!UICONTROL 失敗]** ホスティングソリューション上に検証レコードを作成できない場合。

レコードを検証し、証明書をインストールすると、Adobeは CNAME サブドメインの PTR レコードを自動的に作成します。 [詳細情報](ptr-records.md)

>[!CAUTION]
>
>現在、サブドメインの並列実行は、 [!DNL Journey Optimizer]. 別のドメインに **[!UICONTROL 処理中]** のステータスに値を指定すると、エラーメッセージが表示されます。

## サブドメインの検証 {#subdomain-validation}

サブドメインの検証が完了しサブドメインを使用してメッセージを送信できるようになるまで、以下のチェックとアクションが実行されます。

>[!NOTE]
>
>これらの手順はアドビによって実行され、最大で 3 時間かかることがあります。

1. **事前検証** : サブドメインが Adobe DNS（NS レコード、SOA レコード、ゾーン設定、所有権レコード）にデリゲートされているかどうかをアドビが確認します。事前検証の手順が失敗した場合は、エラーと該当理由が返され、それ以外の場合は、アドビが次の手順に進みます。

1. **ドメインの DNS の設定**：

   * **MX レコード** : メール交換レコード - サブドメインに送信されたインバウンドメールを処理するメールサーバーレコード。
   * **SPF レコード** : 送信者ポリシーフレームワークレコード - サブドメインからメールを送信できるメールサーバーの IP をリストします。
   * **DKIM レコード** : DomainKeys Identified Mail の標準レコード - 公開キー／秘密キーの暗号化を使用してメッセージを認証し、スプーフィングを防止します。
   * **A** : デフォルトの IP マッピング。
   * **CNAME**:正規名または CNAME レコードは、エイリアス名を true または正規のドメイン名にマッピングする DNS レコードの一種です。

1. **トラッキング URL とミラー URL の作成** : ドメインが email.example.com の場合、トラッキング／ミラードメインは data.email.example.com になります。SSL 証明書をインストールすることで保護されます。

1. **CDN CloudFront のプロビジョニング** : CDN がまだセットアップされていない場合は、アドビが IMS 組織用に CDN をプロビジョニングします。

1. **CDN ドメインの作成** : ドメインが email.example.com の場合、CDN ドメインは cdn.email.example.com になります。

1. **CDN SSL 証明書の作成とアタッチ** : アドビが CDN ドメイン用の CDN 証明書を作成して CDN ドメインにアタッチします。

1. **転送 DNS の作成** : これが最初にデリゲートするサブドメインである場合は、PTR レコードの作成に必要な転送 DNS をアドビが IP ごとに 1 つ作成します。

1. **PTR レコードの作成** : PTR レコード（リバース DNS レコードとも呼ばれます）は、メールをスパムとしてマークしないようにするために ISP に必要になるものです。Gmail では、IP ごとに PTR レコードを用意することも推奨しています。Adobeは、サブドメインを初めてデリゲートしたときにのみ PTR レコードを作成します（IP ごとに 1 つ、そのサブドメインを指すすべての IP）。 例えば、IP が *192.1.2.1* で、サブドメインが *email.example.com* の場合、PTR レコードは *192.1.2.1 PTR r1.email.example.com* のようになります。PTR レコードを後で更新して、新しいデリゲートドメインを指すようにすることができます。[PTR レコードの詳細を表示](ptr-records.md)
