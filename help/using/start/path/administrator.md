---
solution: Journey Optimizer
product: journey optimizer
title: Journey Optimizer の基本を学ぶ（システム管理者向け）
description: システム管理者向けに Journey Optimizer の操作方法の詳細について説明します
feature: Get Started
role: Admin
level: Intermediate
exl-id: 24f85ced-aa45-493f-b2c4-7c7b58351b38
source-git-commit: 344a5509731b455ee283af22bfdd8c67e028b83e
workflow-type: tm+mt
source-wordcount: '1012'
ht-degree: 48%

---

# システム管理者向けの基礎知識 {#get-started-sys-admins}

**システム管理者** は、Journey Optimizer環境を設定し、アクセスを管理して、チームが効率的かつ安全に作業できるようにします。 [ データエンジニア ](data-engineer.md)、[ 開発者 ](developer.md)、[ マーケター ](marketer.md) が [!DNL Adobe Journey Optimizer] の使用を開始できるように、重要な設定手順を実行します。

主な役割には、ユーザーグループと権限の設定、異なるユーザーグループのデータとジャーニーを分割するためのサンドボックスの作成と管理、Journey Optimizerを介して配信される様々なメッセージとアセットに対して一貫したブランディングを確保するための配信チャネルとメッセージプリセットの設定などがあります。 セキュリティとガバナンスを維持しながら、適切なユーザーが適切な機能にアクセスできるようにします。

これらの機能は、権限製品にアクセスできる&#x200B;**[!UICONTROL 製品管理者]**&#x200B;が管理できます。[詳しくは、権限を参照してください](../../administration/permissions.md){target="_blank"}。

## アクセスと権限の設定

アクセス管理を設定するには、次の手順に従います。

1. **サンドボックスを作成**&#x200B;して、インスタンスを個別の独立した仮想環境に分割します。**サンドボックス** は、[!DNL Journey Optimizer] で作成します。詳しくは、[サンドボックス](../../administration/sandboxes.md)の節を参照してください。

   >[!NOTE]
   >**システム管理者**&#x200B;として、[!DNL Journey Optimizer] に&#x200B;**[!UICONTROL サンドボックス]**&#x200B;メニューが表示されない場合は、権限を更新する必要があります。役割を更新する方法について詳しくは、[このページ](../../administration/permissions.md#edit-product-profile)を参照してください。

1. **役割を把握します**。役割は、ユーザーがインターフェイス内の特定の機能やオブジェクトにアクセスできるようにするための、一連の単一の権利です。詳しくは、[標準の役割](../../administration/ootb-product-profiles.md)の節を参照してください。

1. **サンドボックス**&#x200B;を含む役割の&#x200B;**権限を設定**&#x200B;し、チームメンバーに様々な役割を割り当てることでアクセス権を付与します。権限は、**[!UICONTROL 役割]**&#x200B;に割り当てる許可を定義できるようにするための単一の権利です。各権限は、機能群（[!DNL Journey Optimizer] のさまざまな機能やオブジェクトに相当するジャーニー、オファーなど）の下に集められています。詳しくは、[権限レベル](../../administration/high-low-permissions.md)の節を参照してください。

1. **オブジェクトレベルのアクセス制御を使用する** （オプション）。 ジャーニー、キャンペーン、チャネル設定などのオブジェクトにアクセスラベルを適用して、特定のリソースにアクセスできるユーザーを制御します。 詳細情報 [ オブジェクトレベルのアクセス制御（OLAC） ](../../administration/object-based-access.md)。

さらに、Assets Essentials にアクセスする必要のあるユーザーを **Assets Essentials コンシューマーユーザー**&#x200B;または／および **Assets Essentialsユーザー**&#x200B;の役割に追加する必要があります。[詳しくは、Assets Essentials ドキュメントを参照してください](https://experienceleague.adobe.com/docs/experience-manager-assets-essentials/help/deploy-administer.html?lang=ja){target="_blank"}。

[!DNL Journey Optimizer] に初めてアクセスすると、実稼動サンドボックスがプロビジョニングされ、契約に応じて一定数の IP が割り当てられます。

## チャネルとメッセージの設定

[ マーケター ](marketer.md) がメッセージを作成および送信できるようにするには、**管理** メニューにアクセスします。 **[!UICONTROL チャネル]** メニューを参照して、チャネル設定を指定します。

>[!NOTE]
>**システム管理者**&#x200B;として、[!DNL Journey Optimizer] に&#x200B;**[!UICONTROL チャネル]**&#x200B;メニューが表示されない場合は、[権限](../../administration/permissions.md){target="_blank"}製品で権限を更新してください。

次の手順に従います。

1. **チャネル設定をセットアップ** します。 メール、SMS、プッシュ通知およびその他のチャネルに必要なすべての技術パラメーターを定義します。

   * **とAdobe Experience Platform Data Collection の両方で** プッシュ通知の設定 [!DNL Adobe Experience Platform] を定義します。 [詳細情報](../../push/push-gs.md)

   * **チャネル設定** を作成して、メール、SMS、プッシュ、アプリ内、web およびその他のチャネルに必要なすべての技術パラメーターを設定します。 [詳細情報](../../configuration/channel-surfaces.md)

   * **SMS チャネル** を設定して、SMS に必要なすべての技術パラメーターを設定します。 [詳細情報](../../sms/sms-configuration.md)

   * 抑制リストにメールアドレスを送信するまでに&#x200B;**再試行**&#x200B;を実行する日数を管理します。[詳細情報](../../configuration/manage-suppression-list.md)

1. **サブドメインをデリゲート**：Journey Optimizer で新規サブドメインを使用する場合、最初の手順としてそのサブドメインをデリゲートします。[詳細](../../configuration/about-subdomain-delegation.md)

   ![](../assets/subdomain.png)

1. **IP プールの作成**：インスタンスでプロビジョニングされた IP アドレスをグループ化することで、メールの配信品質と評判を向上させます。[詳細](../../configuration/ip-pools.md)

   ![](../assets/ip-pool.png)

1. **抑制リストと許可リストを管理**：抑制リストと許可リストを使用して配信品質を向上させます。

   * [抑制リスト](../../reports/suppression-list.md)は、配信から除外するメールアドレスの一覧です。これらのアドレスに送信すると、送信の評判や配信率が低下する可能性があるなどの理由から対象外にします。無効なアドレス、絶えずソフトバウンスしメールの評判に悪影響を与える可能性のあるアドレス、送信したメールメッセージに対して何らかのスパム苦情を出す受信者など、ジャーニーでの送信から自動的に除外されるすべてのメールアドレスを監視できます。[抑制リスト](../../configuration/manage-suppression-list.md)と[再試行](../../configuration/retries.md)の管理方法については、それぞれのページを参照してください。

   ![](../assets/suppression-list-filtering-example.png)

   * [許可リスト](../../configuration/allow-list.md)を使用すると、個々のメールアドレスまたはドメインを指定して、これらの受信者またはドメインでのみ、特定のサンドボックスから送信するメールの受信が許可されるようにすることができます。これにより、テスト環境で実際の顧客アドレスに誤ってメールを送信するのを防ぐことができます。許可リストを有効にする方法については、[こちら](../../configuration/allow-list.md)を参照してください。

   [!DNL Adobe Journey Optimizer] での配信品質管理について詳しくは、[このページ](../../reports/deliverability.md)を参照してください。

## その他の機能

組織のニーズが拡大するにつれて、次の高度な機能を検討します。

* **同意ポリシー**：組織が Healthcare Shield またはプライバシーとセキュリティシールドを購入している場合、チャネルをまたいで顧客の好みを尊重するために同意ポリシーを作成します。 [詳細情報](../../action/consent.md)

* **データガバナンスポリシー**：データ使用ラベルとポリシーを適用して、マーケティングアクションでのデータの使用方法を制御します。 [詳細情報](../../action/action-privacy.md)

* **IP ウォームアッププラン**：メール送信量を徐々に増やして、メールプロバイダーとの送信者の評判を構築します。 [詳細情報](../../configuration/ip-warmup-gs.md)

## 他の役割との共同作業

管理作業により、すべてのチームが成功します。

* **サポート [ データエンジニア](data-engineer.md)**：データ管理の権限の付与、サンドボックスアクセスの承認、データ保持ポリシーの調整

* **[Developers](developer.md)** を有効にする：API 資格情報を入力し、テスト用にサンドボックス環境を設定して、チャネル設定を承認します。

* **権限 [ マーケター](marketer.md)**：ジャーニーとキャンペーンを作成し、使用するチャネルを設定し、テスト環境をサポートする適切な権限を割り当てます

## 最新情報を入手

Journey Optimizer プラットフォームの最新のアップデートと管理上の変更について説明します。

* **[リリースノート](../../rn/release-notes.md)**：毎月リリースされる新機能、プラットフォーム更新、セキュリティパッチ、設定の変更を確認する
* **[ドキュメントの更新](../../rn/documentation-updates.md)**：設定ガイド、権限の更新、新しい管理機能に対する最近の変更を追跡します
* **製品通知**:[Adobe Experience Cloud プロファイル ](https://experience.adobe.com/preferences){target="_blank"} で通知を有効にして、次の重要なアラートを受信できるようにします。
   * システムメンテナンスウィンドウと予定されたダウンタイム
   * セキュリティアップデートとパッチ
   * 新しい管理機能と権限の変更
   * ライセンスと使用権限の更新
   * 製品に関する重要なお知らせ

  通知を有効にするには、Adobe Experience Cloudの右上にあるプロファイルアイコンをクリックして、**環境設定/通知** に移動し、Journey Optimizer通知の環境設定を指定します。 管理者は、重要なシステム通知をすべて有効にする必要があります。

## 次の手順

環境を設定したら、次の手順を実行します。

1. **設定を確認**：すべてのチームメンバーが必要な機能にアクセスできることを確認します
2. **使用状況の監視**：管理ダッシュボードを使用してシステムの使用状況を追跡し、問題を特定します
3. **権限の管理**：チームの役割の進化に合わせて、定期的に権限を確認および更新します
