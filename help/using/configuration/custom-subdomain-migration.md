---
solution: Journey Optimizer
product: journey optimizer
title: メールサブドメインをCNAMEからカスタム委任に移行する
description: Journey Optimizerで、CNAME デリゲーションからカスタムデリゲーションにメールまたはランディングページサブドメインを移行する方法を説明します。
feature: Subdomains, Deliverability
topic: Administration
role: Admin
level: Intermediate
keywords: サブドメイン、デリゲーション、移行、CNAME、カスタムデリゲーション
badge: label="限定提供" type="Informative"
exl-id: f74139cf-640f-4b7b-a0b1-6eae9c75e7e4
source-git-commit: d7d9c371f4b0d8b4ea51e1f23eb9a2f665711fce
workflow-type: tm+mt
source-wordcount: '1251'
ht-degree: 18%

---

# メールサブドメインをCNAMEからカスタム委任に移行する {#migrate-cname-to-custom}

>[!AVAILABILITY]
>
>この機能は、限定提供で使用できます。アクセス権を取得するには、アドビ担当者にお問い合わせください。

サブドメインが現在[CNAMEs](about-subdomain-delegation.md#cname-subdomain-setup)で設定されている場合は、**[!UICONTROL カスタム委任]** メソッドに移行して、会社のセキュリティポリシーを満たすことができます。 これにより、[!DNL Journey Optimizer]内のサブドメインと証明書に対する完全な所有権と制御が得られます。 [ カスタムサブドメインについて詳しく見る](delegate-custom-subdomain.md)

このプロセスの一環として、次のことが必要です。

* [既存のDNS レコード ](#delete-dns)をホスティング ソリューションから削除する
* [認証局から取得したSSL証明書](#upload-ssl-certificate)をアップロードします
* ドメインの所有権と電子メールアドレスを確認して、[ フィードバックループの手順](#feedback-loop)を完了します
* [Adobeによって生成された新しいDNS レコードのセット ](#create-dns-records)をホスティングプラットフォームに作成します

サブドメインを移行するには、次の手順に従います。

## 始める前に {#before-you-begin}

移行プロセスを開始する前に、以下の重要な情報を確認してください。

>[!IMPORTANT]
>
>[CNAME メソッド ](delegate-subdomain.md#cname-subdomain-setup)で設定されたサブドメインのみを移行できます。

* お客様の組織で&#x200B;**カスタム委任方法が有効になっていることを確認してください** （この機能は現在、使用制限があります。アクセス権を取得するには、Adobe担当者にお問い合わせください）。 [詳細情報](delegate-custom-subdomain.md)
* アクティブなチャネル設定がこのサブドメインを使用していないことを確認します。 移行プロセスは機能を中断します。

  >[!NOTE]
  >
  >移行を開始する前にチャネル設定を非アクティブ化した場合は、移行ワークフローが完了した後で、チャネル設定をアクティブ状態に戻すことができます。

* このサブドメインにリンクされたチャネル設定を使用しているアクティブなキャンペーンやジャーニーがないことを確認してください。これにより、配信が中断される可能性があります。
* ダウンタイムは、移行フローに入るとすぐに開始されます。 プロセス中にサブドメインが&#x200B;**[!UICONTROL ドラフト]**&#x200B;に移動し、設定が完了するまで使用できません。
* したがって、SSL証明書の準備を整え、ダウンタイムを減らすために、移行プロセスを開始する前に&#x200B;**移行前の手順を実行することをお勧めします**。 [詳細情報](#start-migration)

## 移行の開始 {#start-migration}

特定のサブドメインの移行を開始するには、次の手順に従います。

1. **[!UICONTROL 管理]** > **[!UICONTROL チャネル]** > **[!UICONTROL 電子メール設定]** > **[!UICONTROL サブドメイン]**&#x200B;に移動します。

1. CNAMEで設定されたサブドメインを選択して開きます。

1. **[!UICONTROL 移行前CSR生成]** セクションを使用して、認証局に送信するためのCSRを生成し、移行プロセスの開始時にSSL証明書を準備できます。 [詳細情報](#send-csr-to-ca)

   >[!IMPORTANT]
   >
   >この段階では、移行前の手順はオプションですが、強くお勧めします。 移行を開始する&#x200B;**前**&#x200B;に移行を完了すると、ダウンタイムが減少し、移行をスムーズに行うことができます。

   ![](assets/subdomain-migrate-pre-migration-csr.png){width="70%"}

1. 専用セクションで「**[!UICONTROL 今すぐ移行]**」を選択します。

   <!--![](assets/subdomain-migrate-to-custom.png){width=90%}-->

1. 表示された[情報](#before-you-begin)を確認します。

   >[!WARNING]
   >
   >ダウンタイムは、移行フローに入るとすぐに開始されるので、アクティブなキャンペーンやジャーニーに影響を与えないようにしてください。

1. **[!UICONTROL はい]**&#x200B;をクリックします。 サブドメインは&#x200B;**[!UICONTROL ドラフト]** ステータスに移動し、設定が完了するまで使用できません。

## CSRを生成して認証局に送信する {#send-csr-to-ca}

移行を完了するには、認証局（CA）によって発行されたSSL証明書が必要です。 このSSL証明書を受け取るには、まず証明書署名要求（CSR）を生成してCAに送信する必要があります。

移行プロセスを既に開始しているかどうかにかかわらず、次の手順に従って新しいCSRを生成して送信します。

1. 「**[!UICONTROL CSRを再生成]**」をクリックします。

1. 表示されるフォームに入力し、証明書署名要求（CSR）を再生成します。

   ![](assets/subdomain-migrate-regenerate-csr.png){width="60%"}

   >[!NOTE]
   >
   >キーの長さは 2048 または 4096 ビットのみです。 サブドメインが送信された後は変更できません。

1. 「**[!UICONTROL CSR をダウンロード]**」をクリックして、フォームをローカルコンピュータに保存します。

1. これを認証局（CA）に送信して、SSL 証明書を取得します。この CSR を署名のために CA に送信する前に、考慮すべき重要な点がいくつかあります。

   * 手順 3 でダウンロードした CSR は、data.subdomain.com 専用です。

   * ただし、証明書は、単一の証明書内のサブジェクト代替名（SAN）エントリとして、data.subdomain.com と cdn.subdomain.com の両方に対応している必要があります。例えば、example.adobe.com をデリゲートしている場合、data.subdomain.com は data.example.adobe.com に対応し、cdn.subdomain.com は cdn.example.adobe.com に対応します。

   * データ（data.example.adobe.com）とCDN （cdn.example.adobe.com）の両方のサブドメインを、同じ証明書のピアエントリとして追加する必要があります。 この証明書に追加のサブドメインを追加する必要はありません。

   * ほとんどの CA では、署名プロセス中に SAN（CDN サブドメインなど）を追加できます

      * CA ポータル経由（使用可能な場合は推奨）、または
      * ポータルオプションが使用できない場合は、サポートチームに手動でリクエストすることで追加できます。

   * 署名が完了すると、CA はデータドメインと CDN サブドメインの両方に対応する単一の証明書を発行します。

## 既存のDNS レコードの削除 {#delete-dns}

移行プロセスを開始したら、ホスティングソリューションから既存のDNS レコードを削除する必要があります。 次の手順に従います。

1. DNS サーバーで現在設定されているレコードのリストが表示されます。

1. ドメインホスティングソリューションに移動し、DNS ホスティングから既存のCNAME エントリを削除します。

1. すべてのDNS レコードが削除されていることを確認します。 完了したら、「ホスティングサイトから必要なレコードを削除したことを確認します」チェックボックスをオンにします。

   ![](assets/subdomain-migrate-delete-dns.png){width="75%"}

## SSL証明書のアップロード {#upload-ssl-certificate}

**[!UICONTROL SSL証明書]** セクションで、新しいSSL証明書を[!DNL Journey Optimizer]にアップロードする必要があります。

その前に、次の点を確認します。

* [移行前の手順](#start-migration)の一環としてCSRを認証局に送信済みの場合は、SSL証明書を受信していることを確認してください。

* まだ実行していない場合は、[生成、ダウンロード、CSRの送信](#send-csr-to-ca)の手順に従ってください。

<!--
    * Click **[!UICONTROL Regenerate CSR]** and fill the form to generate the Certificate Signing Request.

    * Click **[!UICONTROL Download CSR]** to save the form to your local computer.

    * Send the CSR to the Certificate Authority to get your SSL certificate.
-->

1. SSL証明書を取得したら、**[!UICONTROL 証明書をアップロード]**&#x200B;をクリックします。

   ![](assets/subdomain-migrate-ssl-certificate.png){width="75%"}

1. 完全な証明書チェーンを使用して、SSL証明書を.pem形式の[!DNL Journey Optimizer]にアップロードします。 .pem ファイル形式のサンプルを以下に示します。

   ```
   -----BEGIN CERTIFICATE-----
   MIIDXTCCAkWgAwIBAgIJALc3... (base64 encoded data)
   -----END CERTIFICATE-----
   ```

1. 「SSL証明書をアップロードしたことを確認します」チェックボックスをオンにします。

## 包括的なフィードバックループ {#feedback-loop}

次に、フィードバックループの手順を完了して、ドメインの所有権とメールアドレスのレポートを確認します。

![](assets/subdomain-migrate-feedback-loop.png){width="75%"}

このプロセスは、新しいカスタムサブドメインを設定する場合と同じです。 「[ カスタムサブドメインの設定](delegate-custom-subdomain.md#feedback-loop-steps)」ページで説明されている手順に従います。


## DNS レコードの新しいセットの作成 {#create-dns-records}

移行プロセスを完了するには、ホスティングプラットフォームでAdobeによって生成された新しいDNS レコードのセットを作成します。

1. フィードバックループの手順を完了したら、画面の右上にある「**[!UICONTROL 続行]**」ボタンをクリックします。

   この手順では、以前のレコードが削除され、SSL証明書が正しくアップロードされたことが確認されます。 エラーが発生した場合は、[ トラブルシューティング チェックリスト ](#troubleshooting)を参照してください。

1. すべての検証が成功すると、**[!UICONTROL 作成されるレコード]** セクションが表示されます。

   ![](assets/subdomain-migrate-records-to-create.png){width="100%"}

1. ホスティングプラットフォームで必要なレコードをすべて作成します。

1. すべてのレコードを作成したら、**[!UICONTROL 送信]**&#x200B;をクリックします。

   >[!NOTE]
   >
   >リストされているすべてのレコードが作成されない場合は、エラーが表示されます。 必ず、必要なレコードをすべて作成してください。

送信後、Adobeが必要なチェックを実行するまで待つ必要があります。これには最大3時間かかる場合があります。 [詳細情報](delegate-subdomain.md#submit-subdomain)

サブドメインが再びアクティブになると、それを使用する既存のチャネル設定に変更を加える必要がなくなり、以前と同じように機能し続けます。

## チェックリストのトラブルシューティング {#troubleshooting}

カスタムサブドメインの送信中にエラーが発生した場合は、以下にリストされているトラブルシューティングアクションを実行します。

* _リソースを検証できませんでした。 DNSは引き続き存在し、削除する必要があります。_ — ホスティングソリューションからすべてのレコードを削除してください。 [詳細情報](#delete-dns)
* _リソースを検証できませんでした。 SSL証明書をアップロードして、もう一度やり直してください。_ — SSL証明書がアップロードされませんでした。 必ずアップロードしてください。 [詳細情報](#upload-ssl-certificate)
* _証明書のサブジェクト代替名（SAN）に予期しないドメインが含まれています。_ – 正しいSSL証明書をアップロードしてください。 [詳細情報](#upload-ssl-certificate)
* _証明書のサブジェクト代替名（SAN）に、次の必須ドメインがありません。_ – 正しいSSL証明書をアップロードしてください。 [詳細情報](#upload-ssl-certificate)

**関連トピック**

* [カスタムサブドメインの設定](delegate-custom-subdomain.md)
* [サブドメインのデリゲーション方法](about-subdomain-delegation.md#subdomain-delegation-methods)
