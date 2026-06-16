---
solution: Journey Optimizer
product: journey optimizer
title: ライブアクティビティの基本を学ぶ
description: Journey Optimizer でライブアクティビティを送信する方法について説明します
topic: Content Management
role: User
level: Beginner
exl-id: c9766603-df19-4efd-8319-27e9764254b4
TQID: https://experienceleague.adobe.com/IB00r0QSfCthvgvyqubGwsaUoiJKBL-E96duLn4R5i0
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2:
  - id: b49ca41f-eb7a-4f4b-abeb-a97c06fd0c04
  - id: d0a62d3c-b79e-47e4-929e-40ef3cffa037
subfeature_v2:
  - id: c96d2aa5-76a2-443d-8d23-5de95577c909
  - id: ed2fba79-65cb-4680-96d2-2ad5d851714d
  - id: e30b0a1a-b594-47b8-af94-1e3a2be6df11
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 0977b7c36d8556d4aaed43f4b94abb4ccacd2305
workflow-type: tm+mt
source-wordcount: 449
ht-degree: 89%

---

# ライブアクティビティの基本を学ぶ {#get-started-mobile-live}

>[!BEGINSHADEBOX]

**このページでは、** iPhoneのロック画面とダイナミックアイランドで、ライブアクティビティによって永続的かつリアルタイムに更新される方法を説明します。これにより、継続的なイベント中もユーザーの関心を維持し、Adobe Journey Optimizerを使用してユーザーに送信するために必要な設定とAPI トリガーのキャンペーンを計画できます。

>[!ENDSHADEBOX]

ライブアクティビティは、デバイスのロック画面に表示される、永続的で一目で確認できる UI 要素です。 これにより、アプリはリアルタイムで最新の情報を提供できます。ユーザーはアプリを開いたり、プッシュ通知を繰り返し受信することなく、進行中のイベントを通じて常に最新の情報を取得できます。

>[!AVAILABILITY]
>
>Adobe Journey Optimizer のライブアクティビティは、Apple iOS とのみ互換性があります。

従来のプッシュ通知とは異なり、ライブアクティビティは&#x200B;**状態ベースのエンゲージメント**&#x200B;を表します。1 回限りのアラートを配信する代わりに、イベントの進化に応じて動的に更新される、継続的なコンテキストに沿ったプレゼンスを維持します。


<table style="table-layout:fixed"><tr style="border: 0;">
<td>
<img alt="ロック画面と Dynamic Island での iOS ライブアクティビティ" src="assets/do-not-localize/live-activity.jpeg">
</td>
<td>
<p><strong>主なメリット</strong></p>
<p>ライブアクティビティは、モバイルエンゲージメントを通知ベースから状態ベースへと移行させ、ブランドに以下のメリットをもたらします。</p>
<ul>
<li>価値の高いイベントを通じて、ロック画面に<strong>継続的なプレゼンス</strong>を維持</li>
<li>繰り返し通知でユーザーに負担をかけずに、<strong>情報を動的に更新</strong></li>
<li>実際のイベントに関連づけられた、<strong>よりリッチでコンテキストに沿った</strong>モバイルエクスペリエンスを提供</li>
<li>アクティブなトランザクションやライブエクスペリエンス中の<strong>エンゲージメントと保持を向上</strong></li>
</ul>
</td>
</tr>
</table>

Adobe Journey Optimizer を使用すると、個人ベースとオーディエンスベースの両方のユースケースを大規模にサポートする、API トリガーキャンペーンを通じて、ライブアクティビティのリモートでの&#x200B;**開始**、**更新**、**終了**&#x200B;をプログラムで実行できます。

ライブアクティビティは、**API トリガー**&#x200B;キャンペーン経由で&#x200B;**のみ**&#x200B;開始できるので、カスタムペイロードを提供し、独自のペイロードを通じてすべてのパーソナライゼーションを実行できます。
意図したライブアクティビティのユースケースに応じて、適切な **API トリガー**&#x200B;キャンペーンのタイプを選択する必要があります。

* オーディエンスに基づいた更新を大規模に送信するブロードキャストのユースケースには、「**API トリガーマーケティング**」を選択します。

   * スポーツのスコアとライブイベントのカウントダウン
   * ルート上のすべての搭乗客に対するフライトステータスの更新
   * ユーザーセグメント全体で共有されるエクスペリエンス

* ユーザーごとに 1:1 でリアルタイムで更新される個別のユースケースには、「**API トリガートランザクション**」を選択します。

   * 注文のトラッキングと配送の進行状況
   * 乗車またはサービスのステータス更新
   * リアルタイムの予約とアポイントメントの確認

## クイックスタートガイド

アプリケーションでライブアクティビティを設定して実装するには、次の操作を実行します。

1. **[Adobe Journey Optimizer を設定](mobile-live-configuration.md)**

   モバイル設定を作成して環境を設定します。

1. **[Adobe Experience Platform Mobile SDK を統合](mobile-live-configuration-sdk.md)**

   Adobe Experience Platform Mobile SDK との統合により、ロック画面と Dynamic Island でリアルタイムでの動的な変更が可能になります。

1. **[Journey Optimizer でライブアクティビティを作成](create-mobile-live.md)**

   Journey Optimizer で API トリガーキャンペーンを使用して、ライブアクティビティを開始します。

1. **[キャンペーンを追跡](../reports/campaign-global-report-cja-activity.md)**

   ビルトインのレポートを使用して、ライブアクティビティの影響の測定を開始します。

## チュートリアルビデオ

iOS ライブアクティビティを Adobe Journey Optimizer と連携して設定し、iPhone のロック画面と Dynamic Island でリッチなリアルタイム更新を提供する方法について説明します。

>[!VIDEO](https://video.tv.adobe.com/v/3479865/?captions=jpn&learn=on)
