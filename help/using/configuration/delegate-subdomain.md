---
solution: Journey Optimizer
product: journey optimizer
title: サブドメインの委任
description: サブドメインを委任する方法について説明します。
feature: Application Settings
topic: Administration
role: Admin
level: Intermediate
exl-id: 8021f66e-7725-475b-8722-e6f8d74c9023
source-git-commit: 61c90f39fa2bddb384e5581e3935c43d4691c355
workflow-type: tm+mt
source-wordcount: '1704'
ht-degree: 0%

---

# サブドメインの委任 {#delegate-subdomain}

>[!CONTEXTUALHELP]
>id="ajo_admin_subdomainname"
>title="サブドメイン委任"
>abstract="旅のオプティマイザーを使用すると、サブドメインをアドビシステムズ社に委任することができます。 サブドメインを Adobe に完全に委任することもできます。これは推奨される方法です。 また、Cgi 名を使用して Adobe 特定のレコードを参照するサブドメインを作成することもできますが、この方法では、自分で DNS レコードを管理および管理する必要があります。"
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/configuration/delegate-subdomains/about-subdomain-delegation.html#subdomain-delegation-methods" text="サブドメインの設定方法"

>[!CONTEXTUALHELP]
>id="ajo_admin_subdomainname_header"
>title="サブドメイン委任"
>abstract="電子メール送信を開始するには、サブドメインを Adobe に委任します。 この操作を実行すると、DNS レコード、受信トレイ、送信者、応答、バウンスの各アドレスが設定されます。"

ドメイン名の委任とは、ドメイン名 (厳密には DNS ゾーン) の所有者が、その下位にある、他のエンティティに対して、下位にある DNS ゾーンを委任するためのメソッドです。 基本的に、「example.com」ゾーンを扱う場合は、「marketing.example.com」サブゾーンを Adobe に委任することもできます。 サブドメインの委任に関する [ 詳細情報](about-subdomain-delegation.md)

>[!NOTE]
>
>デフォルトでは、 [!DNL Journey Optimizer] ライセンス契約により最大10個のサブドメインを委任することができます。 この制限を大きくする場合は、Adobe の連絡先に移動してください。

サブドメインを完全に委任することも、Adobe 名を使用して Adobe 特定のレコードを指し示すサブドメインを作成することもできます。

>[!CAUTION]
>
>完全なサブドメインの委任が推奨される方法です。 サブドメインの設定方法 ](about-subdomain-delegation.md#subdomain-delegation-methods) の違い [ について詳しくは、ここを参照してください。
>
>サブドメインの設定はすべての環境で共通です。 そのため、サブドメインに変更を加えると、実働サンドボックスにも影響します。

## 完全なサブドメインの委任 {#full-subdomain-delegation}

>[!CONTEXTUALHELP]
>id="ajo_admin_subdomain_dns"
>title="一致する DNS レコードの生成"
>abstract="新しいサブドメインを Adobe に完全に委任するには、旅のオプティマイザーインターフェイスに表示されている Adobe nameserver 情報を、ドメインホストソリューションにコピー &amp; ペーストして、一致する DNS レコードを作成する必要があります。 CNAMEs を使用してサブドメインを委任するには、SSL CDN URL 検証レコードもコピー &amp; ペーストする必要があります。 チェックが成功すると、サブドメインを使用してメッセージを配信できるようになります。"
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/configuration/delegate-subdomains/delegate-subdomain.html#cname-subdomain-delegation" text="CNAME サブドメイン委任"

[!DNL Journey Optimizer] では、製品インターフェイスから直接サブドメインを Adobe に委任することができます。 これにより、Adobe では、電子メールキャンペーンの配信、レンダリングおよび追跡に必要な DNS のあらゆる局面を制御し、管理することによって、管理対象サービスとしてのメッセージを配信できるようになります。

アドビシステムズ社にお任せいただくと、社内の電子メールドメイン用に DNS を維持して管理することはできますが、業界標準の deliverability 要件に対応するために必要な DNS インフラストラクチャを、電子メールマーケティング用のドメインとして管理することができます。

新しいサブドメインを Adobe に完全に委任するには、次の手順に従います。

1. **[!UICONTROL Administration]**> **[!UICONTROL Channels]** > **[!UICONTROL Subdomains]** メニューにアクセスし、をクリック **[!UICONTROL Set up subdomain]** します。

   ![](assets/subdomain-delegate.png)

1. セクションから **[!UICONTROL Set up method]** を選択 **[!UICONTROL Fully delegated]** します。

   ![](assets/subdomain-method-full.png)

1. 委任するサブドメインの名前を指定します。

   ![](assets/subdomain-name.png)

   >[!CAUTION]
   >
   >無効なサブドメインをアドビシステムズ社に委任することはできません。 Marketing.yourcompany.com のように、組織が所有している有効なサブドメインを入力してください。
   >
   >ただし、email.marketing.yourcompany.com などのマルチレベルサブドメインは、現在サポートされていません。

   <!--Capital letters are not allowed in subdomains. TBC by PM-->

1. DNS サーバーに配置されるレコードの一覧が表示されます。 1つずつ、または CSV ファイルをダウンロードすることによって、これらのレコードをコピーします。次に、一致する DNS レコードを生成するために、ドメインのホスティングソリューションに移動します。

1. すべての DNS レコードが、ドメインのホスティングソリューションに作成されていることを確認してください。 すべてが正しく設定されている場合は、「確認します」チェックボックスをオンにし、をクリック **[!UICONTROL Submit]** します。

   ![](assets/subdomain-submit.png)

   >[!NOTE]
   >
   >このボタンを使用 **[!UICONTROL Save as draft]** すると、レコードを作成して、後でサブドメインの設定を送信することができます。 これにより、サブドメインリストからサブドメインを開くことによって、ドメインの委任を再開することができます。

1. 完全なサブドメインの委任が送信されると、そのドメインの一覧 **[!UICONTROL Processing]** に状態が表示されます。 サブドメインの状態について詳しくは、この節 ](about-subdomain-delegation.md#access-delegated-subdomains) を [ 参照してください。

   ![](assets/subdomain-processing.png)

   サブドメインを使用してメッセージを送信する前に、Adobe が必要なチェックを実行するまで待つ必要があります。これは最大3時間かかります。 詳しくは、ここを [ ](#subdomain-validation) 参照してください。

   >[!NOTE]
   >
   >ホストソリューションにはまだ作成されていない、失われたレコードがリストに表示されます。

1. チェックが成功すると、サブドメインが状態を取得 **[!UICONTROL Success]** します。 このような場合は、メッセージを配信するために使用することができます。

   >[!NOTE]
   >
   >ホストソリューションに検証レコードを作成しない場合は、サブドメインにマーク **[!UICONTROL Failed]** が付けられます。

サブドメインが Adobe [!DNL Journey Optimizer] に委任されると、PTR レコードが自動的に作成され、このサブドメインに関連付けられます。 [詳細情報](ptr-records.md)

>[!CAUTION]
>
>サブドメインの並列実行は、で [!DNL Journey Optimizer] は現在サポートされていません。 他のユーザーが **[!UICONTROL Processing]** 同じ状態のときにサブドメインを送信しようとすると、エラーメッセージが表示されます。

## CNAME サブドメイン委任 {#cname-subdomain-delegation}

>[!CONTEXTUALHELP]
>id="ajo_admin_subdomain_dns_cname"
>title="一致する DNS および検証レコードの生成"
>abstract="CNAMEs を使用してサブドメインを委任するには、旅オプティマイザーのインターフェイスに表示される Adobe nameserver 情報と SSL CDN URL 検証レコードをコピーして、ホスティングプラットフォームに保存する必要があります。 チェックが成功すると、サブドメインを使用してメッセージを配信できるようになります。"

ドメイン固有の制限ポリシーを使用している場合に、Adobe で DNS に対する部分的な制御のみを行うには、そのサイドですべての DNS 関連の操作を実行することを選択できます。

CNAME サブドメイン委任を使用すると、サブドメインを作成して、Cgi 名を使用して Adobe 特有のレコードを指し示すことができます。 この構成を使用すると、電子メールの送信、レンダリングおよび追跡のために、環境設定のために DNS を管理するという責務があることになります。

>[!CAUTION]
>
>組織のポリシーによって完全なサブドメインの委任方法が制限されている場合は、CNAME メソッドをお勧めします。 この方法では、DNS レコードを独自に管理し、管理する必要があります。 Adobe では、CNAME メソッドを使用して設定されているサブドメインの DNS の変更、メンテナンスまたは管理を支援することはできません。

➡️ [ このビデオでは、CNAME を使用して Adobe 特有のレコードを指し示すサブドメインを作成する方法について説明しています。](#video)

CNAMEs を使用してサブドメインを委任するには、次の手順に従います。

1. **[!UICONTROL Administration]**> **[!UICONTROL Channels]** > **[!UICONTROL Subdomains]** メニューにアクセスし、をクリック **[!UICONTROL Set up subdomain]** します。

1. **[!UICONTROL CNAME set up]**&#x200B;メソッドを選択します。

   ![](assets/subdomain-method-cname.png)

1. 委任するサブドメインの名前を指定します。

   >[!CAUTION]
   >
   >無効なサブドメインをアドビシステムズ社に委任することはできません。 Marketing.yourcompany.com のように、組織が所有している有効なサブドメインを入力してください。
   >
   >ただし、email.marketing.yourcompany.com などのマルチレベルサブドメインは、現在サポートされていません。

   <!--Capital letters are not allowed in subdomains. TBC by PM-->

1. DNS サーバーに配置されるレコードの一覧が表示されます。 1つずつ、または CSV ファイルをダウンロードすることによって、これらのレコードをコピーします。次に、一致する DNS レコードを生成するために、ドメインのホスティングソリューションに移動します。

1. すべての DNS レコードが、ドメインのホスティングソリューションに作成されていることを確認してください。 すべてが正しく設定されている場合は、「確認する」チェックボックスをオンにします。

   ![](assets/subdomain-create-dns-confirm.png)

   >[!NOTE]
   >
   >ボタンを使用して **[!UICONTROL Save as draft]** 後でレコードを作成することができます。 これにより、サブドメインリストからサブドメインを開くことによって、この段階でサブドメインの委任を再開することができます。

1. このようなレコードが、ホスティングソリューションでエラーが発生しないように生成されていることが検証されるまで待ちます。 この処理には最大2分間かかります。

   >[!NOTE]
   >
   >ホストソリューションにはまだ作成されていない、失われたレコードがリストに表示されます。

1. SSL CDN URL 検証レコードが生成されます。 この検証レコードをホスティングプラットフォームにコピーします。 ホスティングソリューション上でこのレコードが適切に作成されている場合は、「確認します」というチェックボックスをオンにして、をクリック **[!UICONTROL Submit]** します。

   ![](assets/subdomain-cdn-url-validation.png)

   >[!NOTE]
   >
   >また、検証レコードを作成して、後 **[!UICONTROL Save as draft]** でサブドメインの設定を送信することもできます。 これにより、サブドメインリストからサブドメインを開くことによって、ドメインの委任を再開することができます。

1. CNAME サブドメインの委任が送信されると、ドメインの一覧に状態と共 **[!UICONTROL Processing]** にドメインが表示されます。 サブドメインの状態について詳しくは、この節 ](about-subdomain-delegation.md#access-delegated-subdomains) を [ 参照してください。

   サブドメインを使用してメッセージを送信するには、Adobe が必要なチェックを行う前に 2 ~ 3 時間かかることになります。 詳しくは、ここを [ ](#subdomain-validation) 参照してください。

1. チェックが成功 <!--i.e Adobe validates the record you created and installs it--> すると、サブドメインが状態を取得 **[!UICONTROL Success]** します。 このような場合は、メッセージを配信するために使用することができます。

   >[!NOTE]
   >
   >ホストソリューションに検証レコードを作成しない場合は、サブドメインにマーク **[!UICONTROL Failed]** が付けられます。

レコードを検証し、証明書をインストールするときに、CNAME サブドメインの PTR レコードは自動的に作成されます。 [詳細情報](ptr-records.md)

>[!CAUTION]
>
>サブドメインの並列実行は、で [!DNL Journey Optimizer] は現在サポートされていません。 他のユーザーが **[!UICONTROL Processing]** 同じ状態のときにサブドメインを送信しようとすると、エラーメッセージが表示されます。

## サブドメインの検証 {#subdomain-validation}

以下のチェックとアクションは、サブドメインが検証されるまで実行され、それを使用してメッセージを送信できます。

>[!NOTE]
>
>これらの手順は、アドビシステムズ社によって実行され、最大3時間になることがあります。

1. **事前検証** : サブドメインが ADOBE DNS に委任されているかどうかを確認します (NS レコード、SOA レコード、ゾーン設定、所有権の記録)。 事前検証のステップが失敗した場合は、対応する理由とともにエラーが返されます。それ以外の場合は、次の手順に進みます。

1. **ドメイン** に DNS を設定します。

   * **MX レコード** : Mail eXchange レコード-サブドメインに送信された受信メールを処理するメールサーバーレコード
   * **SPF レコード** : Sender Policy Framework レコード-サブドメインから電子メールを送信することができるメールサーバーの Ip アドレスを一覧表示します。
   * **DKIM レコード** は、ドメインを指定することを示しています。メール標準の記録-公開キーを使用してメッセージを認証し、スプーフィングを回避します。
   * **A: デフォルトの** IP マッピング
   * **CNAME** : 正式な名前または cname レコードは、エイリアス名を true または正式ドメイン名にマップする DNS レコードの一種です。

1. **トラッキングおよびミラー Url** の作成: ドメインが email.example.com の場合、追跡/ミラードメインは data.email.example.com になります。 SSL 証明書をインストールすることによってセキュリティが保護されます。

1. **CDN CloudFront** のプロビジョニング: cdn が既に設定されていない場合は、によって組織の ID にプロビジョニングされます。

1. **CDN ドメイン** の作成: ドメインが email.example.com の場合は、cdn ドメインが cdn.email.example.com されます。

1. **CDN SSL 証明書** の作成およびアタッチ: cdn ドメインの cdn 証明書を作成し、その証明書を cdn ドメインに関連付けます。

1. **転送 DNS** の作成: これが最初に委任するサブドメインである場合は、PTR レコードを作成するために必要な「フォワード DNS」が作成されます。これにより、各 IPs に1つずつ作成されます。

1. **PTR レコード** の作成: ptr レコードは逆引き DNS レコードとも呼ばれ、isp によって必要になります。これにより、isp では電子メールがスパムとしてマークされなくなります。 Gmail は、各 IP に対する PTR レコードの格納についてもお勧めします。 Adobe では、1回ずつ委任した場合にのみ、PTR レコードが作成されます。これは、IP に1つずつ、1つはサブドメインを指しているすべての ip アドレスです。 例えば、「IP」が *「192.1.2.1* 」で、サブドメインが *email.example.com* の場合、PTR レコード *は 192.1.2.1 ptr r1.email.example.com* になります。 PTR レコードを更新した後、新しく委任されたドメインを指すようにすることができます。 [PTR レコードについて詳しくは、](ptr-records.md)

## 操作方法のビデオ{#video}

「CNAME」を使用して Adobe 特定のレコードを指し示すサブドメインを作成する方法について説明します。

>[!VIDEO](https://video.tv.adobe.com/v/339484?quality=12)
