---
solution: Journey Optimizer
product: journey optimizer
title: IP プールの作成
description: IP プールの管理方法を学ぶ
feature: Subdomains, Channel Configuration
topic: Administration
role: Admin
level: Experienced
keywords: IP, プール, グループ, サブドメイン, 配信品質
exl-id: 606334c3-e3e6-41c1-a10e-63508a3ed747
TQID: https://experienceleague.adobe.com/z-91TIrSp9KXlFcJRG9wmTRNRA2RU-AaEoMtaLcmNWM
product_v2: id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2: id: bb359667-ec7d-4d4b-8663-5850fc219d32id: d556b755-390a-43f0-be32-a08cf6236126id: fe338112-e2ce-4876-8989-fc4d497613f1
subfeature_v2: id: d2e8a157-b3b0-4143-9ff3-809bf400be56id: e5329d1b-e590-4e24-a3fb-ef3fe0f2c721id: cf64c7f6-7428-4ae5-b158-8df9771f38f4
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 0d9c480cc48c4352e82d1f4624c65fc16a60b959
workflow-type: tm+mt
source-wordcount: 725
ht-degree: 78%

---

# IP プールの作成 {#create-ip-pools}

>[!BEGINSHADEBOX]

**このページでは、**&#x200B;電子メールの配信品質を向上させ、送信者のレピュテーションを保護するために、サブドメイン IP アドレスをグループ化するIP プールを作成、編集、および削除する方法について説明します。

>[!ENDSHADEBOX]

>[!CONTEXTUALHELP]
>id="ajo_admin_ip_pool_header"
>title="IP プールの設定"
>abstract="IP プールは、サブドメインの IP アドレスを収集して、メールの配信品質を向上させます。"

>[!CONTEXTUALHELP]
>id="ajo_admin_ip_pool"
>title="IP プールの設定"
>abstract="Journey Optimizer では、IP プールを作成して、サブドメインの IP アドレスをグループ化できます。 これにより、サブドメインの評価が他のサブドメインに影響を与えるのを防ぐことができるので、メールの配信品質が大幅に向上する可能性があります。"

## IP プールについて {#about-ip-pools}

[!DNL Journey Optimizer] では、IP プールを作成して、サブドメインの IP アドレスをグループ化できます。

メールの配信品質を高めるには、IP プールの作成を強くお勧めします。 これにより、サブドメインの評判が他のサブドメインに影響を与えるのを防ぐことができます。

例えば、マーケティングメッセージ用に 1 つの IP プールを用意し、トランザクションメッセージ用に別の IP プールを用意することをお勧めします。 こうすることで、マーケティングメッセージの 1 つがうまく機能せず、顧客によってスパムと指定された場合でも、この顧客に送信されるトランザクションメッセージには影響せず、顧客は引き続きトランザクションメッセージ（購入確認、パスワード回復メッセージなど）を受信します。

>[!CAUTION]
>
>IP プールの設定は、すべての環境に共通です。 したがって、IP プールの作成や編集は、本番稼働用サンドボックスにも影響を与えます。

## IP プールの作成 {#create-ip-pool}

IP プールを作成するには、次の手順に従います。

1. **[!UICONTROL 管理]**／**[!UICONTROL チャネル]**／**[!UICONTROL メール設定]**／**[!UICONTROL IP プール]**&#x200B;メニューにアクセスし、「**[!UICONTROL IP プールを作成]**」をクリックします。

   ![](assets/ip-pool-create.png)

1. IP プールの名前と説明（オプション）を入力します。

   >[!NOTE]
   >
   >名前は文字（A～Z）で始め、英数字または特殊文字（_, ., - ）のみを使用してください。

1. プールに含める IP アドレスをドロップダウンリストから選択し、「**[!UICONTROL 送信]**」をクリックします。 インスタンスでプロビジョニングされたすべてのIP アドレスがリストに表示されます。

   ![](assets/ip-pool-config.png)

IP を選択すると、IP に関連付けられた PTR レコードがリストから表示されます。 これにより、IP プールを作成する際に各 IP のブランディング情報を検証し、例えば同じブランディング情報を持つ IP を選択できます。 [PTR レコードについての詳細情報](ptr-records.md)

![](assets/ip-pool-ptr-record.png)

>[!NOTE]
>
>IP に対して PTR レコードが設定されていない場合は、その IP を選択できません。 その IP の PTR レコードを設定するには、アドビ担当者にお問い合わせください。<!--Now this only happens when first subdomain delegated to Adobe is with CNAME method.-->

IP プールが作成された後、IP プールのドロップダウンリストの下に表示される IP アドレスにカーソルを合わせると、PTR 情報が表示されます。

![](assets/ip-pool-ptr-record-tooltip.png)

IP プールが作成され、リストに表示されるようになりました。 選択してプロパティにアクセスし、関連するチャネル設定（メッセージプリセットなど）を表示することができます。 チャネル設定と IP プールを関連付ける方法について詳しくは、[この節](channel-surfaces.md)を参照してください。

## IP プールの編集 {#edit-ip-pool}

IP プールを編集するには、次の手順に従います。

1. リストで IP プール名をクリックして開きます。

1. その IP プールのプロパティを必要に応じて編集します。 説明を変更し、IP アドレスを追加または削除できます。 IP プール名は編集できないことに注意してください。名前を変更するには、プールを削除して新しいプールを作成します。

   ![](assets/ip-pool-edit.png)

   >[!CAUTION]
   >
   >IPの削除を検討する際は、他のIPに追加の負荷がかかり、配信品質に深刻な影響を与える可能性があるため、慎重に進めてください。 不明な点がある場合は、配信品質のエキスパートにお問い合わせください。

1. 変更を保存します。

更新は、IP プールが[チャネル設定](channel-surfaces.md)に関連付けられているかどうかに応じて、直ちにまたは非同期に有効になります。

* IP プールがチャネル設定に関連付けられて&#x200B;**いない**&#x200B;場合、更新は直ちに行われます（**[!UICONTROL 成功]**&#x200B;ステータス）。
* IP プールがチャネル設定に関連付けられて&#x200B;**いる**&#x200B;場合、更新には最大 3 時間かかることがあります（**[!UICONTROL 処理中]**&#x200B;ステータス）。

>[!NOTE]
>
>* [ チャネル設定を作成する場合](channel-surfaces.md#create-channel-surface)、選択したサブドメインに関連付けられていない&#x200B;**[!UICONTROL 処理]**&#x200B;状態のIP プールを選択すると、設定の作成を続行できません。 [詳細情報](channel-surfaces.md#create-channel-surface)
>* IP プールが正常に更新されたら、リアルタイムメッセージに反映されるまでに数分かかるか、バッチメッセージに対して次のバッチジョブが実行されるまで待ちます。

IP プールの更新ステータスを確認するには、「**[!UICONTROL その他のアクション]**」ボタンをクリックし、「**[!UICONTROL 最近の更新]**」を選択します。

![](assets/ip-pool-recent-update.png)

「**[!UICONTROL 削除]**」ボタンを使用して IP プールを削除することもできます。 チャネル設定に関連付けられている IP プールは削除できません。

