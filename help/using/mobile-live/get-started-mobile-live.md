---
solution: Journey Optimizer
product: journey optimizer
title: ライブアクティビティの基本を学ぶ
description: Journey Optimizerでライブアクティビティを送信する方法を説明します
topic: Content Management
role: User
level: Beginner
exl-id: c9766603-df19-4efd-8319-27e9764254b4
source-git-commit: df4183e15b2907bfb669e7e2e8eb88771627dcf4
workflow-type: tm+mt
source-wordcount: '388'
ht-degree: 21%

---

# ライブアクティビティの基本を学ぶ {#get-started-mobile-live}


ライブアクティビティは、デバイスのロック画面に表示される、永続的で一意のUI要素です。 アプリを通じて最新の情報をリアルタイムで提供できます。これにより、アプリを開いたり、プッシュ通知を繰り返し受け取ったりすることなく、継続的なイベントを通じて顧客に情報を提供できます。

>[!AVAILABILITY]
>
>Adobe Journey Optimizerのライブアクティビティは、Apple iOSとのみ互換性があります。

従来のプッシュ通知とは異なり、ライブアクティビティは&#x200B;**状態ベースのエンゲージメント**&#x200B;を表します。1回限りのアラートを配信する代わりに、イベントの進化に応じて動的に更新される、継続的なコンテキストに沿ったプレゼンスを維持します。


![](assets/do-not-localize/live-activity.jpeg){width="30%" align="left"}

Adobe Journey Optimizerを使用すると、API トリガーのキャンペーンを通じて、**start**、**update**、**end** ライブアクティビティをリモートでプログラムで実行できます。これは、個人とオーディエンスベースの両方のユースケースを大規模にサポートします。

ライブアクティビティは、**API トリガー** キャンペーンを介して&#x200B;**のみ**&#x200B;開始できます。これにより、カスタムペイロードを提供し、独自のペイロードを介してすべてのパーソナライズを実行できます。
目的のライブアクティビティのユースケースに基づいて、適切な&#x200B;**API トリガー** キャンペーンタイプを選択する必要があります。

* ブロードキャストのユースケースで&#x200B;**API トリガーマーケティング**&#x200B;を選択 – オーディエンスベースの更新を大規模に送信：

   * スポーツスコアとライブイベントのカウントダウン
   * ルート上のすべての乗客のフライトステータスの更新
   * ユーザーセグメント全体で共有されたエクスペリエンス

* 個々のユースケースに対して&#x200B;**API トリガーのトランザクション**&#x200B;を選択します – ユーザーごとに1:1のリアルタイム更新：

   * 注文の追跡と配送の進捗状況
   * ライドまたはサービスのステータスの更新
   * リアルタイムの予約と予約の確認

## 主なメリット

ライブアクティビティは、モバイルエンゲージメントを通知ベースから州ベースに移行し、企業は次のことを実現できます。

* 価値の高いイベントを通じて、ロック画面で&#x200B;**継続的なプレゼンス**&#x200B;を維持する
* **繰り返し通知でユーザーに負担をかけずに情報を動的に**&#x200B;更新します
* 実際のイベントに関連した、より充実したコンテキストの&#x200B;**のモバイルモーメントを**&#x200B;配信
* アクティブなトランザクションまたはライブ エクスペリエンス中に&#x200B;**エンゲージメントとリテンションを増加**

## クイックスタートガイド

アプリケーションでライブアクティビティを設定および実装するには、次の手順を実行します。

1. **[Adobe Journey Optimizer を設定](mobile-live-configuration.md)**

   モバイル設定を作成して環境を設定します。

1. **[Adobe Experience Platform Mobile SDK を統合](mobile-live-configuration-sdk.md)**

   Adobe Experience Platform Mobile SDK との統合により、ロック画面と Dynamic Island でリアルタイムでの動的な変更が可能になります。

1. **[Journey Optimizerでライブアクティビティを作成](create-mobile-live.md)**

   Journey OptimizerでAPI トリガーによるキャンペーンを使用して、ライブアクティビティを開始します。

1. **[キャンペーンを追跡](../reports/campaign-global-report-cja-activity.md)**

   組み込みレポートを使用して、ライブアクティビティの影響の測定を開始します。

## チュートリアルビデオ

iOS Live アクティビティをAdobe Journey Optimizerと連携して設定し、iPhoneのロック画面と Dynamic Island でリッチなリアルタイム更新を提供する方法について説明します。

>[!VIDEO](https://video.tv.adobe.com/v/3479865/?captions=jpn&learn=on)
