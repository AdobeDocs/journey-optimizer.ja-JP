---
title: PTR レコード
description: PTR レコードの管理方法の詳細
audience: administrators
feature: Application Settings
topic: Administration
role: Admin
level: Intermediate
exl-id: 4c930792-0677-4ad5-a46c-8d40fc3c4d3a
source-git-commit: 1e62715f35b50bba639657a1bef37aa61922c715
workflow-type: tm+mt
source-wordcount: '460'
ht-degree: 25%

---

# PTR レコード

## PTR レコードについて

ポインタレコード（PTR）は、IP アドレスと関連付けたドメイン名を提供する DNS（Domain Name System）レコードの一種です。

PTR レコードを使用すると、受信メールサーバーは、送信メールサーバーの IP アドレスが接続先の名前に対応しているかどうかを識別することにより、送信メールサーバーの信頼性を確認できます。

## サブドメインの PTR レコードへのアクセス

Adobe Journey Optimizerでサブドメインがデリゲートされると、PTR レコードが自動的に作成され、このサブドメインに関連付けられます。 これには、 **[!UICONTROL チャネル]** > **[!UICONTROL 電子メール設定]** > **[!UICONTROL PTR レコード]** メニュー

![](../assets/ptr-records.png)

このリストには、以下の構文を使用して、デリゲートされたサブドメインごとに生成された PTR レコードが表示されます。

* レコードの場合は「r」。
* IP アドレスの最後の 2 桁には「xx」。
* サブドメイン名。

リストから PTR レコードを開くと、関連するサブドメイン名と IP アドレスを表示できます。

## PTR レコードを編集する {#edit-ptr-record}

PTR レコードを変更して、IP アドレスに関連付けられたサブドメインを編集できます。

1. リストで、PTR レコード名をクリックして開きます。

   ![](../assets/ptr-record-select.png)

1. 必要に応じてサブドメインを編集します。

   ![](../assets/ptr-record-subdomain.png)

   >[!NOTE]
   >
   >この **[!UICONTROL IP]** および **[!UICONTROL PTR レコード]** フィールド。

1. クリック **[!UICONTROL SAve]** 変更を確定します。

An **[!UICONTROL 更新中]** リスト内の PTR レコードの名前の横にアイコンが表示されます。

![](../assets/ptr-record-updating.png)

PTR レコードの更新の詳細を確認するには、 **[!UICONTROL 更新中]** または **[!UICONTROL 最近の更新]** アイコン

![](../assets/ptr-record-recent-update.png)

更新ステータスや、要求された変更などの情報を確認できます。

![](../assets/ptr-record-updates.png)

## ステータスを更新

PTR レコードの更新には、次のステータスを使用できます。

* **[!UICONTROL 処理中]**:PTR レコードの更新が送信され、検証プロセスを実行中です。
* **[!UICONTROL 成功]**:更新された PTR レコードが検証され、新しいサブドメインが IP アドレスに関連付けられました。
* **[!UICONTROL 失敗]**:PTR レコードの更新の検証中に、1 つ以上のチェックが失敗しました。

### Processing

IP アドレスに関連付ける新しいサブドメインが有効であることを検証するために、複数の配信品質チェックが実行されます。 <!--The processing time is around **48h-72h**, and can take up to **7-10 days**. Learn more on the checks performed during the validation cycle in [this section](#create-message-preset).-->

>[!NOTE]
>
>更新中は、PTR レコードを変更できません。 名前はクリックできますが、 **[!UICONTROL サブドメイン]** フィールドが灰色表示になっている。 変更は、更新が正常に完了するまで反映されません。

検証プロセス中も、古いサブドメインは IP アドレスに関連付けられます。

### 成功

検証プロセスが成功すると、新しいサブドメインが IP アドレスに自動的に関連付けられます。

### Failed

検証プロセスが失敗した場合は、古い PTR レコードが表示されます。 以前に IP アドレスに関連付けられていた有効なサブドメインは、変更されません。

更新エラーのタイプは次のとおりです。
* PTR レコードの新しい転送 DNS を作成できませんでした
* レコードを更新できませんでした
* アフィニティの再オンボーディングの失敗

更新が失敗すると、PTR レコードが再び編集可能になります。 その名前をクリックして、サブドメインを再度更新できます。
