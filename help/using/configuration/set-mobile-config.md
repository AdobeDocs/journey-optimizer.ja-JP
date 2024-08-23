---
solution: Journey Optimizer
product: journey optimizer
title: モバイルと Web の設定
description: モバイルチャネルと web チャネルを設定および監視する方法について説明します
feature: Surface, Channel Configuration
topic: Administration
role: Admin
level: Experienced
keywords: チャネル, サーフェス, 技術, パラメーター, Optimizer
hide: true
hidefromtoc: true
source-git-commit: 8fb87d2e2085d98dd8b014df6aa4d734bab4e997
workflow-type: tm+mt
source-wordcount: '269'
ht-degree: 10%

---

# ガイド付きチャネル設定の基本を学ぶ {#set-mobile-config}

>[!CONTEXTUALHELP]
>id="ajo_mobile_web_setup_name"
>title="モバイルと web の設定名"
>abstract="モバイルまたは web 設定の名前を入力します。 この名前は、ガイド付きチャネルの設定で自動的に作成されたすべてのリソースで使用されます。"

>[!CONTEXTUALHELP]
>id="ajo_mobile_web_setup_validate_assurance"
>title="Assurance での検証"
>abstract="Assurance を使用してモバイルアプリのデータ収集とユーザーエクスペリエンスの品質を確保します。 このツールは、詳細な分析、検証、最適化を提供します。 さらに、アプリを直接接続して、正確な SDK 統合を検証できます。"
>additional-url="https://experienceleague.adobe.com/en/docs/platform-learn/implement-mobile-sdk/app-implementation/assurance" text="Assurance ドキュメントを参照してください"


この設定により、マーケティングチャネルの迅速な設定が容易になり、必要なすべてのリソースがExperience Platform、Journey Optimizerおよびデータ収集ですぐに使用できるようになります。 これにより、マーケティングチームはキャンペーンとジャーニーの作成をすぐに開始できます。

これを効果的に実装するには、web サイトやモバイルコードを変更する権限と技術的能力を持つ組織のメンバーが、設定を監督する必要があります。

ガイド付きチャネルのセットアップを実行するために必要な権限は次のとおりです。

+++ 必要な権限

<table>
  <thead>
    <tr>
      <th><strong>ソリューション</strong></th>
      <th><strong>権限</strong></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>
        <p>データ収集</p>
      </td>
      <td>
        <ul>
          <li>会社権限/ プロパティ</li>
          <li>プロパティ権限：拡張機能と環境を開発、公開、管理します</li>
          <li>アプリサーフェス：アプリ設定の管理</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td>
        <p>Adobe Experience Platform</p>
      </td>
      <td>
        <ul>
          <li>データ収集：データストリームの管理</li>
          <li>サンドボックス：サンドボックスへのアクセスの許可</li>
          <li>セグメントの管理：セグメント定義の読み取り、作成、編集、削除をおこなう</li>
          <li>プロファイルの管理：プロファイルを読み取り、作成、編集、削除する</li>
          <li>データセットの読み取り：データセットの読み取り専用アクセス権</li>
          <li>スキーマの読み取り：スキーマの読み取り専用アクセス権</li>
          <li>ID 名前空間の読み取り：ID 名前空間の読み取り専用アクセス権</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td>
        <p>Adobe Journey Optimizer</p>
      </td>
      <td>
        <p>キャンペーン：キャンペーンの管理と公開</p>
      </td>
    </tr>
  </tbody>
</table>
+++

<table style="table-layout:fixed"><tr style="border: 0;">
<td>
<a href="set-mobile-android.md">
<img alt="リード" src="assets/do-not-localize/config-android.jpeg">
</a>
<div><a href="set-mobile-android.md"><strong>Android モバイル設定のセットアップ </strong>
</div>
<p>
</td>
<td>
<a href="set-mobile-ios.md">
<img alt="低頻度" src="assets/do-not-localize/config-ios.jpeg">
</a>
<div>
<a href="set-mobile-ios.md"><strong>iOS モバイル設定のセットアップ </strong></a>
</div>
<p></td>
<td>
<a href="set-mobile-web.md">
<img alt="検証" src="assets/do-not-localize/config-web.jpeg">
</a>
<div>
<a href="set-mobile-web.md"><strong>Web 設定のセットアップ </strong></a>
</div>
<p>
</td>
</tr></table>
