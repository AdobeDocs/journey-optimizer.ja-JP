---
title: Journey Optimizer Get Started for System Admin
description: システム管理者として、Journey Optimizerの使用方法の詳細を学ぶ
level: Intermediate
source-git-commit: a27a6d7ab96bd08e7a2601c2e86d1d9f0fc4be0a
workflow-type: tm+mt
source-wordcount: '693'
ht-degree: 21%

---

# システム管理者向けの基本を学ぶ

![administrator](assets/do-not-localize/user-2.png)

[!DNL Adobe Journey Optimizer] の使用を開始する前に、環境の準備にいくつかの手順が必要です。次の手順を実行して、 [データエンジニア](data-engineer.md) および [ジャーニー実習者](marketer.md) を使用して、 [!DNL Adobe Journey Optimizer].


As a **システム管理者**、 **製品プロファイルと権限の割り当てについて** サンドボックス管理とチャネル設定の場合。 また、サンドボックスをセットアップし、使用可能な製品プロファイル用にサンドボックスを管理する必要もあります。
その後、チームメンバーを製品プロファイルに割り当てることができます。

これらの機能は、 **[!UICONTROL 製品管理者]** Admin Console にアクセスできる [Adobe Admin Consoleの詳細](https://helpx.adobe.com/jp/enterprise/admin-guide.html){target=&quot;_blank&quot;}。

アクセス管理については、次のページを参照してください。

1. **サンドボックスの作成** を使用して、インスタンスを個別の独立した仮想環境に分割します。 **サンドボックス** 次で作成： [!DNL Journey Optimizer]. 詳しくは、 [サンドボックス](../administration/sandboxes.md) 」セクションに入力します。

   >[!NOTE]
   >As a **システム管理者**&#x200B;が表示されない場合は、 **[!UICONTROL サンドボックス]** メニュー [!DNL Journey Optimizer]、 [Admin Console](https://adminconsole.adobe.com/){_blank}. で製品プロファイルを更新する方法を説明します。 [このページ](../administration/permissions.md#edit-product-profile).

1. **製品プロファイルについて**. 製品プロファイルは、ユーザーがインターフェイス内の特定の機能やオブジェクトにアクセスできるようにする、一元的な権限のセットです。 詳しくは、 [標準の製品プロファイル](../administration/ootb-product-profiles.md) 」セクションに入力します。

1. **権限の設定** 製品プロファイルの **サンドボックス**&#x200B;を参照し、異なる製品プロファイルに割り当てることで、チームメンバーにアクセス権を付与します。 この手順は、 [Admin Console](https://adminconsole.adobe.com/){_blank}. 権限は、割り当てる権限を定義できる単一の権限です。 **[!UICONTROL 製品プロファイル]**. 各権限は、機能群（[!DNL Journey Optimizer] のさまざまな機能やオブジェクトに相当するジャーニー、メッセージ、オファーなど）の下に集められています。詳しくは、 [権限レベル](../administration/high-low-permissions.md) 」セクションに入力します。


さらに、 **デプロイ[!DNL Adobe Experience Manager Assets Essentials]** メッセージ内のアセットと画像を管理するには：アクセスを必要とするユーザー [!DNL Assets Essentials] は、 **Assets Essentials Consumer Users** または/および **Assets Essentials Users** 製品プロファイル。 [詳しくは、 Assets Essentialsのドキュメントを参照してください](https://experienceleague.adobe.com/docs/experience-manager-assets-essentials/help/deploy-administer.html?lang=ja){target=&quot;_blank&quot;}。

[!DNL Journey Optimizer]に初めてアクセスする際には、実稼動用サンドボックスがプロビジョニングされ、契約に応じて一定数の IP が割り当てられます。

ジャーニーを作成してメッセージを送信するには、 **管理** メニュー 次を参照： **[!UICONTROL チャネル]** メニューを使用して、電子メールメッセージとプリセットを設定します。

>[!NOTE]
>As a **システム管理者**&#x200B;が表示されない場合は、 **[!UICONTROL チャネル]** メニュー [!DNL Journey Optimizer]、 [Admin Console](https://adminconsole.adobe.com/){_blank}. で製品プロファイルを更新する方法を説明します。 [このページ](../administration/permissions.md#edit-product-profile).

次の手順に従います。

1. **メッセージとチャネルの設定**:プリセットの定義、電子メールおよびプッシュメッセージの設定の調整とカスタマイズ

   * 定義 **プッシュ通知設定** 両方 [!DNL Adobe Experience Platform] および [!DNL Adobe Experience Platform Launch]. [詳細情報](../push-gs.md)

   * 作成 **メッセージプリセット** :e メールおよびプッシュ通知メッセージに必要なすべての技術パラメーターを設定します。 [詳細情報](../configuration/message-presets.md)

   * 期間を管理 **再試行** は、抑制リストに電子メールアドレスを送信する前に実行されます。 [詳細](../configuration/manage-suppression-list.md)

1. **サブドメインをデリゲート**：Journey Optimizer で新規サブドメインを使用する場合、最初の手順としてそのサブドメインをデリゲートします。[詳細](../configuration/about-subdomain-delegation.md)

   ![](../assets/subdomain.png)

1. **IP プールの作成**：インスタンスでプロビジョニングされた IP アドレスをグループ化することで、E メールの配信品質と評判を向上させます。[詳細](../configuration/ip-pools.md)

   ![](../assets/ip-pool.png)

1. **抑制と許可リストの管理**:抑制と許可リストを使用して配信品質を向上させる

   * A [抑制リスト](../suppression-list.md) は、配信から除外する e メールアドレスで構成されます。これらの連絡先に送信すると、送信のレピュテーションと配信率が低下する可能性があるのでです。 無効なアドレス、一貫してソフトバウンスし、E メールの評判に悪影響を与える可能性のあるアドレス、E メールメッセージの 1 つに対してスパムの苦情を発行する受信者など、ジャーニーでの送信から自動的に除外されるすべての E メールアドレスを監視できます。 を管理する方法を学ぶ [抑制リスト](../configuration/manage-suppression-list.md) および [再試行](../configuration/retries.md).

   ![](../assets/suppression-list-filtering-example.png)

   * この [許可リスト](../allow-list.md) では、特定のサンドボックスから送信される電子メールを受信する権限を持つ唯一の受信者またはドメインとなる、個々の電子メールアドレスまたはドメインを指定できます。 これにより、テスト環境で実際の顧客アドレスに誤ってメールを送信するのを防ぐことができます。方法を学ぶ [許可リスト](../allow-list.md).
   での配信品質の管理の詳細を説明します [!DNL Adobe Journey Optimizer] [このページ](../deliverability.md).

