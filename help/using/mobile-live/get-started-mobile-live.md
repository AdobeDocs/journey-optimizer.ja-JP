---
solution: Journey Optimizer
product: journey optimizer
title: ライブアクティビティの基本を学ぶ
description: Journey Optimizer でライブアクティビティを送信する方法について説明します
topic: Content Management
role: User
level: Beginner
exl-id: c9766603-df19-4efd-8319-27e9764254b4
source-git-commit: 1a5a69b9c2907e18a4649543ac0ddf6fdd486491
workflow-type: tm+mt
source-wordcount: '388'
ht-degree: 20%

---

# ライブアクティビティの基本を学ぶ {#get-started-mobile-live}


ライブアクティビティは、デバイスのロック画面に表示される、永続的で一目で確認できるUI要素です。 アプリを通じて最新の情報をリアルタイムで提供できます。これにより、アプリを開いたり、プッシュ通知を繰り返し受け取ったりすることなく、継続的なイベントを通じて顧客に情報を提供できます。

>[!AVAILABILITY]
>
>Adobe Journey Optimizerのライブアクティビティは、Apple iOSとのみ互換性があります。

従来のプッシュ通知とは異なり、ライブアクティビティは&#x200B;**状態ベースのエンゲージメント**&#x200B;を表します。1回限りのアラートを配信する代わりに、イベントの進化に応じて動的に更新される、継続的なコンテキストに沿ったプレゼンスを維持します。


<table style="table-layout:fixed"><tr style="border: 0;">
<td>
<img alt="ロックスクリーンとダイナミックアイランドでのiOSライブアクティビティ" src="assets/do-not-localize/live-activity.jpeg">
</td>
<td>
<p>Adobe Journey Optimizerを使用すると、API トリガーキャンペーンを通じて、リモートで<strong>start</strong>、<strong>update</strong>、<strong>end</strong> ライブアクティビティをプログラムで実行できます。これは、個人とオーディエンスベースの両方のユースケースを大規模にサポートします。</p>
<p>ライブアクティビティは、<strong>API トリガー</strong> キャンペーンを介して<strong>のみ</strong>開始できます。これにより、カスタムペイロードを提供し、独自のペイロードを介してすべてのパーソナライズを実行できます。 目的のライブアクティビティのユースケースに基づいて、適切なキャンペーンタイプを選択する必要があります。</p>
<ul>
<li><strong>API トリガーマーケティング </strong> — スポーツスコアとライブイベントのカウントダウン、フライト状況の更新、ユーザーセグメント間での共有体験など、ブロードキャストのユースケース、オーディエンスベースのアップデートを大規模に送信します。</li>
<li><strong>API トリガーのトランザクション </strong> – 個々のユースケース、ユーザーごとに1:1のリアルタイム更新：注文の追跡と配信の進捗状況、乗り物またはサービスのステータスの更新、リアルタイムの予約と予約の確認。</li>
</ul>
</td>
</tr>
</table>

## 主なメリット

ライブアクティビティは、モバイルエンゲージメントを通知ベースから州ベースに移行し、企業は次のことを実現できます。

* 価値の高いイベントを通じて、ロック画面で&#x200B;**継続的なプレゼンス**&#x200B;を維持する
* **繰り返し通知でユーザーに負担をかけずに情報を動的に**&#x200B;更新します
* 実際のイベントに関連した、より充実したコンテキストの&#x200B;**のモバイルモーメントを**&#x200B;配信
* アクティブなトランザクションまたはライブ エクスペリエンス中に&#x200B;**エンゲージメントとリテンションを増加**

## クイックスタートガイド

アプリケーションでライブアクティビティを設定して実装するには、次の操作を実行します。

1. **[Adobe Journey Optimizer を設定](mobile-live-configuration.md)**

   モバイル設定を作成して環境を設定します。

1. **[Adobe Experience Platform Mobile SDK を統合](mobile-live-configuration-sdk.md)**

   Adobe Experience Platform Mobile SDK との統合により、ロック画面と Dynamic Island でリアルタイムでの動的な変更が可能になります。

1. **[Journey Optimizerでライブアクティビティを作成](create-mobile-live.md)**

   Journey OptimizerでAPI トリガーによるキャンペーンを使用して、ライブアクティビティを開始します。

1. **[キャンペーンを追跡](../reports/campaign-global-report-cja-activity.md)**

   組み込みレポートを使用して、ライブアクティビティの影響の測定を開始します。

## チュートリアルビデオ

Adobe Journey Optimizerを使用してiOSのライブアクティビティを設定し、iPhoneのロック画面とダイナミックアイランドでリッチなリアルタイム更新を配信する方法を説明します。

>[!VIDEO](https://video.tv.adobe.com/v/3479864/?learn=on)
