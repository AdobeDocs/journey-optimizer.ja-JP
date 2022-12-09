---
solution: Journey Optimizer
product: journey optimizer
title: IP プールの作成
description: IP プールの管理方法について説明しています。
feature: Application Settings
topic: Administration
role: Admin
level: Intermediate
exl-id: 606334c3-e3e6-41c1-a10e-63508a3ed747
source-git-commit: 3a932747de33ced59d68835a96386b7ac560e4fe
workflow-type: tm+mt
source-wordcount: '598'
ht-degree: 0%

---

# IP プールの作成 {#create-ip-pools}

>[!CONTEXTUALHELP]
>id="ajo_admin_ip_pool_header"
>title="IP プールの設定"
>abstract="IP プールは、電子メール deliverability を改善するために、サブドメインの IP アドレスを収集します。"

>[!CONTEXTUALHELP]
>id="ajo_admin_ip_pool"
>title="IP プールの設定"
>abstract="このような場合は、ドメインの IP アドレスをグループ化するための IP プールを作成することができます。 これにより、他のサブドメインの評判が他のサブドメインに影響しないようにすることができるので、電子メールの deliverability を大幅に向上させることができます。"

## IP プールについて {#about-ip-pools}

で [!DNL Journey Optimizer] は、ドメインの ip アドレスをグループ化するために ip プールを作成することができます。

電子メールの deliverability については、IP プールを作成することを強くお勧めします。 これにより、他のサブドメインの評判が他のサブドメインに影響しないようにすることができます。

1つは、マーケティングメッセージに1つの IP プールを設定し、もう1つはトランザクションメッセージに使用することです。 この方法では、マーケティングメッセージに問題がなく、顧客からスパムとして宣言された場合でも、同じユーザーに送信されるトランザクションメッセージには影響しません。これは、トランザクションメッセージ (購入確認書、パスワードの回復メッセージなど) を受け取ることになります。

>[!CAUTION]
>
>IP プール設定は、すべての環境で共通です。 そのため、IP プールの作成またはエディションも、実働サンドボックスに影響を与えることになります。

## IP プールの作成 {#create-ip-pool}

IP プールを作成するには、次の手順を実行します。

1. **[!UICONTROL Administration]**> **[!UICONTROL Channels]** > **[!UICONTROL IP pools]** メニューにアクセスし、をクリック **[!UICONTROL Create IP Pool]** します。

   ![](assets/ip-pool-create.png)

1. IP プールの名前と説明を入力します (オプション)。

   >[!NOTE]
   >
   >名前は英字 (A ~ Z) で始め、英数字または特殊文字 (_,.,-) のみを使用する必要があります。

1. ドロップダウンリストからプールに含める IP アドレスを選択し、をクリック **[!UICONTROL Submit]** します。

   ![](assets/ip-pool-config.png)

   >[!NOTE]
   >
   >インスタンスを使用してプロビジョニングしたすべての IP アドレスがリストに表示されます。

これで、IP プールが作成され、リストに表示されるようになりました。 このオプションを選択して、プロパティにアクセスし、関連するチャンネルサーフェス (メッセージプリセット) を表示することができます。 チャネルサーフェスを IP プールに関連付ける方法について詳しくは、ここを [ ](channel-surfaces.md) 参照してください。

![](assets/ip-pool-created.png)

## IP プールの編集 {#edit-ip-pool}

IP プールを編集するには、次の手順に従います。

1. リストから、IP プール名をクリックして開きます。

   ![](assets/ip-pool-list.png)

1. 必要に応じて、プロパティを編集します。 この説明は、IP アドレスを変更することも、追加または削除することもできます。

   >[!NOTE]
   >
   >IP プール名は編集できません。 これを変更する場合は、IP プールを削除してから、もう1つを選択して名前を付けて作成する必要があります。

   ![](assets/ip-pool-edit.png)

   >[!CAUTION]
   >
   >IP アドレスを削除することを検討する場合は、additionnal の負荷が他の IPs に追加されるので、deliverability に深刻な影響を与える可能性があります。 ご不明な点がある場合は、deliverability のエキスパートまでお問い合わせください。

1. 変更内容を保存します。

チャネルサーフェス ](channel-surfaces.md) に [ 関連付けられているかどうかに応じて、アップデートは直ちに、または非同期に実行されます。

* IP プールが **どのチャネルサーフェスにも関連付けられていない場合は、更新は即時に行わ** れます ( **[!UICONTROL Success]** 状態)。
* IP プール **が** チャンネルサーフェスに関連付けられている場合、更新には最大3時間 ( **[!UICONTROL Processing]** 状態) かかります。

>[!NOTE]
>
>チャンネルサーフェス ](channel-surfaces.md#create-channel-surface) を作成するとき [ に、「エディション ( **[!UICONTROL Processing]** ステータス)」にある IP プールを選択し、そのサーフェスに選択されたサブドメインに決して関連付けられていない場合は、サーフェスを作成することはできません。[詳細情報](channel-surfaces.md#subdomains-and-ip-pools)

IP プールの更新状態を確認するには、「」ボタンをクリック **[!UICONTROL More actions]** して、「」を選択 **[!UICONTROL Recent updates]** します。

![](assets/ip-pool-recent-update.png)

>[!NOTE]
>
>IP プールが正常に更新されると、次の処理が完了するまで待つ必要があります。
>* 数分前に、ユニタリメッセージによって使用されます。
>* IP プールの次のバッチがバッチメッセージに効果的に機能するまでの間


このボタンを使用して **[!UICONTROL Delete]** 、IP プールを削除することもできます。 チャネルサーフェスに関連付けられた IP プールを削除することはできません。

