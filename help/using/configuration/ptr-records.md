---
title: PTR レコード
description: PTR レコードの管理方法について説明します
audience: administrators
feature: Application Settings
topic: Administration
role: Admin
level: Intermediate
exl-id: 4c930792-0677-4ad5-a46c-8d40fc3c4d3a
source-git-commit: 6c200f4a162ea1a3763b353b01ce5fef74ed8462
workflow-type: tm+mt
source-wordcount: '479'
ht-degree: 91%

---

# PTR レコード

## PTR レコードについて

ポインタレコード（PTR）は、IP アドレスと関連付けたドメイン名を提供する DNS（Domain Name System）レコードの一種です。

PTR レコードを使用すると、受信メールサーバーは、送信メールサーバーの IP アドレスが接続先の名前に対応しているかどうかを識別することにより、送信メールサーバーの信頼性を確認できます。

## サブドメインの PTR レコードへのアクセス

1 回 [サブドメインがデリゲートされます](delegate-subdomain.md) Adobe Journey Optimizerでは、PTR レコードが自動的に作成され、このサブドメインに関連付けられます。 **[!UICONTROL チャネル]**／**[!UICONTROL メール設定]**／**[!UICONTROL PTR レコード]**&#x200B;メニューからアクセスできます。

![](../assets/ptr-records.png)

このリストには、以下の構文を使用して、デリゲートされたサブドメインごとに生成された PTR レコードが表示されます。

* レコードの場合は「r」。
* IP アドレスの最後の 2 桁には「xx」。
* サブドメイン名。

リストから PTR レコードを開くと、関連するサブドメイン名と IP アドレスを表示できます。

## PTR レコードの編集 {#edit-ptr-record}

PTR レコードを編集して、IP アドレスに関連付けられたサブドメインを変更できます。

>[!CAUTION]
>
>を使用して、Adobeにデリゲートされたサブドメインに関連付けられた PTR レコードを変更することはできません。 [CNAME メソッド](delegate-subdomain.md#cname-subdomain-delegation).

1. リストから、PTR レコード名をクリックして開きます。

   ![](../assets/ptr-record-select.png)

1. サブドメインを必要に応じて編集します。

   ![](../assets/ptr-record-subdomain.png)

   >[!NOTE]
   >
   >「**[!UICONTROL IP]**」フィールドと「**[!UICONTROL PTR レコード]**」フィールドは変更できません。

1. 「 **[!UICONTROL 保存]**」をクリックして変更を確定します。

「**[!UICONTROL 更新中]**」アイコンがリスト内の PTR レコード名の横に表示されます。

![](../assets/ptr-record-updating.png)

PTR レコードの更新の詳細を確認するには、「**[!UICONTROL 更新中]**」アイコンまたは「**[!UICONTROL 最近の更新]**」アイコンをクリックします。

![](../assets/ptr-record-recent-update.png)

更新ステータスやリクエストされた変更などの情報が表示されます。

![](../assets/ptr-record-updates.png)

## 更新ステータス

PTR レコードの更新には、次のステータスがあります。

* **[!UICONTROL 処理中]**：PTR レコードの更新が送信され、検証中です。
* **[!UICONTROL 成功]**：更新された PTR レコードが検証され、新しいサブドメインが IP アドレスに関連付けられました。
* **[!UICONTROL 失敗]**：PTR レコードの更新を検証中に、1 つまたは複数の検査に失敗しました。

### 処理中

IP アドレスに関連付ける新しいサブドメインが有効であることを検証するために、いくつかの配信品質チェックが実行されます。 <!--The processing time is around **48h-72h**, and can take up to **7-10 days**. Learn more on the checks performed during the validation cycle in [this section](#create-message-preset).-->

>[!NOTE]
>
>更新中は、PTR レコードを変更できません。名前はクリックできますが、「**[!UICONTROL サブドメイン]**」フィールドは灰色表示になります。変更は、更新が正常に完了するまで反映されません。

検証中は、古いサブドメインがまだ IP アドレスに関連付けられています。

### 成功

検証が成功すると、新しいサブドメインが IP アドレスに自動的に関連付けられます。

### 失敗

検証プロセスが失敗した場合は、古い PTR レコードが表示されます。以前に IP アドレスに関連付けられていた有効なサブドメインは変更されません。

考えられる更新エラーのタイプは次のとおりです。
* PTR レコードの新しい転送 DNS の作成に失敗
* レコードの更新に失敗
* アフィニティの再オンボーディングに失敗

更新に失敗すると、PTR レコードが再び編集可能になります。レコードの名前をクリックして、サブドメインを再度更新できます。
