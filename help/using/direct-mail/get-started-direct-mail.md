---
solution: Journey Optimizer
product: journey optimizer
title: ダイレクトメールの基本を学ぶ
description: Journey Optimizer でダイレクトメールメッセージを作成する方法について説明します。
feature: Direct Mail
topic: Content Management
role: User
level: Beginner
keywords: ダイレクトメール, メッセージ, キャンペーン
exl-id: bb52f400-6289-4a7f-a34f-98eb5d27c76a
TQID: https://experienceleague.adobe.com/Gmtr-7HW70-cg7va8iHfR5xKdYts-ZdDCm6CeQHJ0tg
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2:
  - id: d0a62d3c-b79e-47e4-929e-40ef3cffa037
subfeature_v2:
  - id: b3a93754-a8b8-46eb-9421-7eccaeeb3dff
  - id: cb1f1586-9fb4-4de2-8332-02cebb88d42d
  - id: e30b0a1a-b594-47b8-af94-1e3a2be6df11
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
source-git-commit: e7702a4706509a8181ee39cccc510656c5230a16
workflow-type: tm+mt
source-wordcount: 487
ht-degree: 89%

---

# ダイレクトメールの基本を学ぶ {#create-direct}

>[!BEGINSHADEBOX]

**このページ：** ダイレクトメールチャネルの仕組みを理解して、サードパーティプロバイダーが顧客に物理的なメールを送信するために使用する抽出ファイルを生成できます。

>[!ENDSHADEBOX]

ダイレクトメールは、サードパーティのダイレクトメールプロバイダーが顧客にメールを送信するために必要な抽出ファイルをパーソナライズおよび生成できるオフラインチャネルです。

ダイレクトメールキャンペーンやジャーニーを作成すると、すべてのターゲットプロファイルと選択したデータ（住所やプロファイル属性など）を含むファイルが、Journey Optimizer によって自動的に生成されます。 このファイルは選択したサーバーに送信されるので、選択したサードパーティ（実際のメール送信プロセスを処理する）のダイレクトメールプロバイダーからアクセスできるようになります。

該当する場合は、顧客がメールを受信できるように、選択したサードパーティのダイレクトメールプロバイダーと協力して、顧客から必要な同意を取得する必要があります。

メールサービスを使用した場合、該当するサードパーティのダイレクトメールプロバイダーが定める追加の利用条件に同意したとみなされます。  サードパーティ製品の使用について、アドビは一切関係せず、責任も負いません。 ダイレクトメールキャンペーンの送付に関する問題やサポートのリクエストについては、選択したサードパーティのダイレクトメールプロバイダーにお問い合わせください。

## 事前準備 {#before-you-start}

ダイレクトメールメッセージを作成する前に、[ファイルルーティングとダイレクトメールチャネル設定](direct-mail-configuration.md)を指定します。 また、Adobe Experience Platform には、オーディエンスデータとプロファイルデータ（郵便番号など）も必要です。

ダイレクトメールメッセージを送信する主な手順は、次のとおりです。

![設定から配信までのダイレクトメール作成ワークフロー](assets/dm-creation-process.png)

>[!AVAILABILITY]
>
>ダイレクトメールメッセージは、ジャーニーやキャンペーンのコンテキストで作成できます。 API トリガーキャンペーンでは使用できません。

![Journey Optimizer のダイレクトメールチャネルのアニメートした概要](../rn/assets/do-not-localize/gif-dm.gif)

## その他のリソース {#additional-resources}

* **[ダイレクトメールの作成](create-direct-mail.md)** - ダイレクトメール配信を作成し、オフラインチャネル用の抽出ファイルを設定する方法について説明します。
* **[ダイレクトメールチャネルの設定](direct-mail-configuration.md)** - ダイレクトメールサーフェスとファイルルーティング設定を指定します。
* **[ダイレクトメールでのバッチ決定](../experience-decisioning/batch-decisioning-direct-mail.md)** - ダイレクトメール用に抽出ファイルをパーソナライズしたり、下流システム用に決定データを書き出したりするために決定を使用します。
* **[ダイレクトメールのテストと送信](test-send-direct-mail.md)** - ダイレクトメール配信をテスト、検証、公開する方法について説明します。
* **[ダイレクトメールのチュートリアル](https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/channels/direct-mail-channel/direct-mail){target="_blank"}** - ダイレクトメールの機能とベストプラクティスに関するステップバイステップのビデオチュートリアルを参照してください。

## チュートリアルビデオ {#how-to-video}

Adobe Journey Optimizer のダイレクトメールチャネルを活用して、ジャーニー内のダイレクトメールの配信を自動化およびスケジュールする方法について説明します。

+++ こちらのビデオをご覧ください

>[!VIDEO](https://video.tv.adobe.com/v/3479163?captions=jpn&quality=12)

+++

同じ手順の書き込み済みのチュートリアルについて詳しくは、[ダイレクトメールチャネルのチュートリアル](https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/channels/direct-mail-channel/direct-mail){target="_blank"}を参照してください。

ダイレクトメールに関するよくある質問について詳しくは、上記の[その他のリソース](#additional-resources)の節を参照してください。
