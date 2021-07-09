---
title: 一般的なメッセージ設定
description: メールアドレスの設定方法を学ぶ
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
source-git-commit: 4be1d6f4034a0bb0a24fe5e4f634253dc1ca798e
workflow-type: ht
source-wordcount: '123'
ht-degree: 100%

---


# プライマリメールアドレスの変更

プロファイルをターゲットにする場合、使用できるメールアドレスがデータベース内に複数ある（個人用、仕事用のメールアドレスなど）場合があります。

Journey Optimizer では、プロファイルサービスから使用するメールアドレスを決定し、複数のアドレスが使用可能な場合に優先順位を付けることができます。 それをおこなうには、次の手順に従います。

1. **[!UICONTROL チャネル]** `>` **[!UICONTROL 一般]**&#x200B;メニューにアクセスします。
1. プロファイルのメールアドレスを判断するために、現在デフォルトで使用されているフィールドがこの画面に表示されます。 「**[!UICONTROL 編集]**」をクリックして変更します。

   ![](../assets/primary-address.png)

1. 「変更」ボタンをクリックし、プライマリメールアドレスとして使用する新しいフィールドを選択します。

   ![](../assets/primary-address-edit.png)

1. 使用可能なメールタイプの XDM フィールドのリストが表示されます。 使用するフィールドを選択し、「**[!UICONTROL 保存]**」をクリックします。

   ![](../assets/primary-address-field.png)

<!--1. You can also select an additional field to use as secondary email address. This allows you to determine which field to use if the primary field is empty for a profile. >> will be done later on-->
