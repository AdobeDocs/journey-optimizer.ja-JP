---
title: サブドメインのデリゲート
description: サブドメインのデリゲート方法を説明します
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
feature: アプリケーション設定
topic: 管理
role: Administrator
level: Intermediate
source-git-commit: f4b36903b7b961dd20442acaf446e2ce99cc2b31
workflow-type: tm+mt
source-wordcount: '170'
ht-degree: 5%

---


# デリゲートされたサブドメインへのアクセス

すべてのデリゲートサブドメインが&#x200B;**[!UICONTROL チャネル]** / **[!UICONTROL サブドメイン]**&#x200B;メニューに表示されます。 フィルターを使用して、リスト（委任日、ユーザー、ステータス）を絞り込むことができます。

![](../assets/subdomain-list.png)

**[!UICONTROL ステータス]**&#x200B;列には、サブドメインのデリゲーションプロセスに関する情報が表示されます。

* **[!UICONTROL ドラフト]**:サブドメインデリゲーションはドラフトとして保存されました。サブドメイン名をクリックして、デリゲーションプロセスを再開します。
* **[!UICONTROL 処理]**:サブドメインを使用する前に、いくつかの設定チェックが行われます。
* **[!UICONTROL 成功]**:サブドメインはチェックを正常に実行し、メッセージの配信に使用できます。
* **[!UICONTROL 失敗]**:サブドメインのデリゲーションが送信された後、1つ以上の確認が失敗しました。

サブドメインに関する詳細情報にアクセスするには、リストからサブドメインを開きます。 次のことができます。

* デリゲーションプロセス中に設定されたサブドメイン名（読み取り専用）と、生成されたURL（リソース、ミラーページ、トラッキングURL）を取得します。

* Googleサイト検証TXTレコードをサブドメインに追加して、検証済みであることを確認します（[サブドメインにGoogle TXTレコードを追加する](google-txt.md)を参照）。

![](../assets/subdomain-delegated.png)
