---
solution: Journey Optimizer
product: journey optimizer
title: システム管理のために、旅のオプティマイザーが開始されます。
description: システム管理者は、旅オプティマイザーの操作方法について学習します。
level: Intermediate
exl-id: 24f85ced-aa45-493f-b2c4-7c7b58351b38
source-git-commit: 020c4fb18cbd0c10a6eb92865f7f0457e5db8bc0
workflow-type: tm+mt
source-wordcount: '709'
ht-degree: 0%

---

# システム管理者向けの作業の開始 {#get-started-sys-admins}

を使用して [!DNL Adobe Journey Optimizer] 作業を開始する前に、環境を準備するためのいくつかの手順が必要です。  これらの手順を実行して、Data 技師 ](data-engineer.md) および [ 旅の [ Practicionner ](marketer.md) を使用 [!DNL Adobe Journey Optimizer] できるようにする必要があります。


これは **、システム管理者** によって製品プロファイルが理解され、サンドボックスの管理およびチャネル設定に対するアクセス許可 **が割り当てられていることが必要** です。また、サンドボックスを設定して、使用可能な製品プロファイル用にそれを管理する必要もあります。 これにより、チームメンバーを製品プロファイルに割り当てることができます。

これらの機能を使用して **[!UICONTROL Product administrators]** 管理コンソールにアクセスすることができます。 [Adobe Admin Console ](https://helpx.adobe.com/enterprise/admin-guide.html) について詳しくは、{target = &quot;_blank 「}」を参照してください。

以下のページで、アクセス管理について説明します。

1. **サンド** ボックスを作成して、インスタンスを個別の独立した仮想環境に分割します。 **サンド** ボックスは、に [!DNL Journey Optimizer] 作成されます。 詳しくは、「サンド ](../../administration/sandboxes.md) ボックス」の項を参照して [ ください。

   >[!NOTE]
   >**システム管理者** として、に [!DNL Journey Optimizer] メニューが **[!UICONTROL Sandboxes]** 表示されない場合は、Admin Console ](https://adminconsole.adobe.com/) {_blank} の権限 [ を更新してください。このページ ](../../administration/permissions.md#edit-product-profile) で [ プロダクトプロファイルを更新する方法について説明します。

1. **製品プロファイル** について説明します。 製品プロファイルは、ユーザーがインターフェイス内の特定の機能またはオブジェクトにアクセスできるようにするための一連の一連の一連の権限を持っています。 「製品プロファイル ](../../administration/ootb-product-profiles.md) 」セクションで [ 詳しく説明しています。

1. **サンド** ボックスを含む **製品プロファイルのアクセス許可** を設定し、それらのプロファイルを別の製品プロファイルに割り当てることによって、チームメンバーにアクセス権を付与します。このステップは、 [ Admin Console ](https://adminconsole.adobe.com/) {_blank} で行います。 アクセス許可は、割り当てられた認証を **[!UICONTROL Product profile]** 定義できる、ユニタリ権限です。 各パーミッションは、の [!DNL Journey Optimizer] 様々な機能またはオブジェクトを表す「旅」や「申し出」などの機能によって収集されます。 詳しくは、「アクセス許可レベル ](../../administration/high-low-permissions.md) 」の項を参照して [ ください。

さらに、「アセット essentials コンシューマ Users Users **」や** 「アセット Essentials **ユーザー向け製品プロフィール」の** 「アセット essentials」にアクセスする必要があるユーザーを追加する必要があります。[アセットの基礎ドキュメント ](https://experienceleague.adobe.com/docs/experience-manager-assets-essentials/help/deploy-administer.html) の詳細を確認 {target = &quot;_blank&quot;}。

>[!NOTE]
>2022年1月6日より前に購入した、旅オプティマイザー製品については、組織で展開 [!DNL Adobe Experience Manager Assets Essentials] する必要があります。 詳しくは、アセットの展開の要点 ](https://experienceleague.adobe.com/docs/experience-manager-assets-essentials/help/deploy-administer.html) {target = &quot;_blank&quot;} セクションを参照して [ ください。

初めてアクセス [!DNL Journey Optimizer] するときには、実働サンドボックスが提供され、契約によっては一定数の IPs が割り当てられます。

Journeys を作成したり、メッセージを送信したりするには、管理 **メニューにアクセス** してください。**[!UICONTROL Channels]**&#x200B;メニューを参照して、メッセージおよびチャンネルのサーフェスを設定します (メッセージプリセット)。

>[!NOTE]
>**システム管理者** として、に [!DNL Journey Optimizer] メニューが **[!UICONTROL Channels]** 表示されない場合は、Admin Console ](https://adminconsole.adobe.com/) {_blank} の権限 [ を更新してください。このページ ](../../administration/permissions.md#edit-product-profile) で [ プロダクトプロファイルを更新する方法について説明します。

以下に示す手順に従います。

1. **メッセージとチャネル** の設定: サーフェスの定義、電子メール、sms、メッセージの設定のカスタマイズ

   * プッシュ通知設定 **は、および [!DNL Adobe Experience Platform Launch] の両方 [!DNL Adobe Experience Platform] で定義** します。[詳細情報](../../push/push-gs.md)

   * チャネルサーフェス **(メッセージプリセット) を作成** して、電子メール、sms、push notification に必要なすべての技術パラメーターを設定します。[詳細情報](../../configuration/channel-surfaces.md)

   * **Sms チャンネル** を設定して、sms に必要なすべての技術パラメーターを設定します。[詳細情報](../../sms/sms-configuration.md)

   * 電子メールアドレスを抑制リストに送信する前にリトライ **が実行される** 日数を管理します。[詳細情報](../../configuration/manage-suppression-list.md)

1. **サブドメイン** の委任: 新しいサブドメインに対して、旅のオプティマイザーで使用されるようにするには、まずこれを委任する必要があります。 [詳細情報](../../configuration/about-subdomain-delegation.md)

   ![](../assets/subdomain.png)

1. **IP プール** の作成: インスタンスにプロビジョニングされた ip アドレスをグループ化することによって、電子メールの deliverability と評判を向上させることができます。 [詳細情報](../../configuration/ip-pools.md)

   ![](../assets/ip-pool.png)

1. **抑制および許可リスト** の管理: 抑制と許可リストを使用した deliverability の改善

   * 抑制リスト ](../../reports/suppression-list.md) には [ 、配信から除外する電子メールアドレスが含まれています。これにより、これらの連絡先を送信すると、送信される評判と配信率が低下する可能性があります。自動的に除外された電子メールアドレスはすべて、無効なアドレス、一貫したソフトバウンス、電子メールの評判に悪影響を与える可能性があります。また、何らかの電子メールメッセージに悪影響を与える可能性があります。 抑制リスト ](../../configuration/manage-suppression-list.md) と [ リトライ ](../../configuration/retries.md) を管理 [ する方法について説明します。
   ![](../assets/suppression-list-filtering-example.png)

   * [許可リスト ](../../configuration/allow-list.md) を使用すると、特定のサンドボックスから送信する電子メールの受信を承認された受信者またはドメインとして、個々の電子メールアドレスまたはドメインを指定することができます。これにより、テスト環境で使用している場合は、実際のお客様の住所に電子メールを送信することができなくなります。 許可リスト ](../../configuration/allow-list.md) を有効にする方法を [ 参照してください。
   Deliverability の管理について詳しくは [!DNL Adobe Journey Optimizer] [ 、このページ ](../../reports/deliverability.md) を参照してください。
