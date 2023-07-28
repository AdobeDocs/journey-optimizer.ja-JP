---
title: ダイレクトメールの概要
description: Journey Optimizerでダイレクトメールメッセージを作成する方法を説明します
feature: Overview
topic: Content Management
role: User
level: Beginner
keywords: ダイレクトメール, メッセージ, キャンペーン
source-git-commit: 40cd058475b37b8fa7d5c0286ad230422e027cf8
workflow-type: tm+mt
source-wordcount: '205'
ht-degree: 49%

---

# ダイレクトメールメッセージの作成 {#create-direct}

>[!AVAILABILITY]
>
>現時点では、AdobeHealthcare Shield アドオン機能を購入した組織では、ダイレクトメールチャネルは利用できません。

ダイレクトメールは、ダイレクトメールプロバイダーが顧客にメールを送信するために必要な抽出ファイルをパーソナライズおよび生成できるオフラインチャネルです。

ダイレクトメールキャンペーンを作成する際、Journey Optimizerは、すべてのターゲットプロファイルと、選択したデータ（郵送先住所、プロファイル属性など）を含むファイルを自動的に生成します。 このファイルは、選択したサーバーに送信され、選択したダイレクトメールプロバイダーがアクセスできるようになります。このプロバイダーは、実際の郵送プロセスを処理します。

ダイレクトメールメッセージを送信する主な手順は次のとおりです。

![](assets/dm-creation-process.png)

ダイレクトメールメッセージは、スケジュールされたキャンペーンのコンテキストでのみ作成できます。API トリガーキャンペーンやジャーニーでは使用できません。

>[!IMPORTANT]
>
>ダイレクトメールメッセージを送信する前に、次の設定が完了していることを確認します。
>
>1. [ファイルのルーティング設定](../direct-mail/direct-mail-configuration.md#file-routing-configuration)：抽出ファイルをアップロードして保存するサーバーを指定します。
>1. [ダイレクトメールメッセージサーフェス](../direct-mail/direct-mail-configuration.md#direct-mail-surface)：ファイルのルーティング設定を参照します。
