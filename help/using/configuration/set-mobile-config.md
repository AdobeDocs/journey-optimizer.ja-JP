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
exl-id: 846e0d11-798b-4f3b-80db-848a17d32830
source-git-commit: 06f79b7af3fe3c5ca556e2226d7e241a9c5b56d3
workflow-type: tm+mt
source-wordcount: '770'
ht-degree: 17%

---

# ガイド付きチャネル設定の基本を学ぶ {#set-mobile-config}

>[!CONTEXTUALHELP]
>id="ajo_mobile_web_setup_name"
>title="モバイルと web の設定名"
>abstract="モバイルまたは web 設定の名前を入力します。 この名前は、ガイド付きチャネルの設定で自動的に作成されたすべてのリソースで使用されます。"

>[!CONTEXTUALHELP]
>id="ajo_mobile_web_setup_validate_assurance"
>title="Assurance での検証"
>abstract="Adobe Experience Platform Assurance は、SDK 実装を調べたり、アプリケーションイベントをシミュレートおよび検証したりするのに役立つように、このワークフローに組み込まれています。"
>additional-url="https://experienceleague.adobe.com/en/docs/experience-platform/assurance/home" text="Adobe Experience Platform Assurance の概要"

この設定により、マーケティングチャネルの迅速な設定が容易になり、Experience Platform、Journey Optimizer およびデータ収集内で必要なすべてのリソースがすぐに使用できるようになります。これにより、マーケティングチームはキャンペーンとジャーニーの作成から開始できます。

ガイド付きチャネルの設定は、次のプラットフォームとチャネルをサポートしています。

* プラットフォームと SDK:

   * スウィフト バイ Apple iOS

   * Android・コトリン

   * Javascript, Web

* チャネル：

   * モバイルのアプリ内

   * モバイルプッシュメッセージ

   * Web Basic

設定するプラットフォームごとに、個別の設定を作成する必要があります。 これは、各アプリが一意のチャネル設定を必要とし、これにより各プラットフォームに必要なチャネルを柔軟に決定できるためです。

## 前提条件 {#prereq}

* これを効果的に実装するには、web サイトやモバイルコードを変更する権限と技術的能力を持つ組織のメンバーが、設定を監督する必要があります。

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

* 「既存の設定」オプションを使用している場合は、次のAdobe Experience Platform Mobile SDK 拡張機能バージョンを使用していることを確認してください。 必要な依存関係や初期化コードなど、SDK 設定の詳細については、[ 次のドキュメント ](https://experienceleague.adobe.com/en/docs/platform-learn/implement-mobile-sdk/app-implementation/install-sdks?lang=en) を参照してください。

  Android用

   * Mobile Core v3.1.0 以降
   * Adobe Journey Optimizer v3.1.0 以降

  iOS用

   * Mobile Core v5.2.0 以降
   * Adobe Journey Optimizer v5.1.1 以降

## 自動作成されたリソース {#auto-create-resources}

ガイド付きチャネルの設定は、マーケティングチャネルの迅速な設定を簡素化し、すべての重要なリソースをExperience Platform、Journey Optimizerおよび Data Collection アプリで簡単に使用できるようにします。 これにより、マーケティングチームはキャンペーンとジャーニーの作成をすばやく開始できます。 自動生成され、ガイド付きチャネル設定の一部として設定されるリソースのリストを以下に示します。

以下のタブを参照して、自動生成されるすべてのリソースの包括的なリストにアクセスします。

>[!BEGINTABS]

>[!TAB iOS]

**初期設定** については、「**リソースの自動作成**」をクリックすると **設定の詳細** 画面に作成されるすべてのリソースの一覧を以下に示します。

<table>
  <thead>
  <tr>
  <th><strong>ソリューション</strong></th>
  <th><strong>自動作成されたリソース</strong></th>
  </tr>
  </thead>
  <tbody>
  <tr>
  <td>
  <p>タグ</p>
  </td>
  <td>
  <ul>
  <li>モバイルタグプロパティ</li>
  <li>ルール</li>
  <li>データ要素</li>
  <li>ライブラリ</li>
  <li>環境（ステージング、実稼動、開発）</li>
  </ul>
  </td>
  </tr>
  <tr>
  <td>
  <p>タグ拡張機能</p>
  </td>
  <td>
  <ul>
  <li>Adobe Experience Platform Edge Network</li>
  <li>Adobe Journey Optimizer</li>
  <li>AEP Assurance</li>
  <li>同意（デフォルトの同意ポリシーを有効にした場合）</li>
  <li>ID （デフォルトの ECID とデフォルトのステッチルール）</li>
  <li>Mobile Core</li>
  </ul>
  </td>
  </tr>
  <tr>
  <td>
  <p>Assurance</p>
  </td>
  <td>
  <p>アシュランスセッション</p>
  </td>
  </tr>
  <tr>
  <td>
  <p>データストリーム</p>
  </td>
  <td>
  <p>サービスを使用したデータストリーム</p>
  </td>
  </tr>
  <tr>
  <td>
  <p>Experience Platform</p>
  </td>
  <td>
  <ul>
  <li>データセット</li>
  <li>スキーマ</li>
  </ul>
  </td>
  </tr>
  </tbody>
  </table>

**チャネル設定** の場合、**チャネルを追加** 画面で作成されたすべてのリソースの包括的なリストを以下に示します。

<table>
  <thead>
  <tr>
  <th><strong>ソリューション</strong></th>
  <th><strong>自動作成されたリソース</strong></th>
  </tr>
  </thead>
  <tbody>
  <tr>
  <td>
  <p>Journey Optimizer</p>
  </td>
  <td>
  <ul>
  <li>チャネル設定</li>
  <li>プッシュ資格情報のアップロード（モバイルプッシュメッセージのみ）</li>
  </ul>
  </td>
  </tr>
  </tbody>
  </table>

>[!TAB Android]

**初期設定** については、「**リソースの自動作成**」をクリックすると **設定の詳細** 画面に作成されるすべてのリソースの一覧を以下に示します。

<table>
  <thead>
  <tr>
  <th><strong>ソリューション</strong></th>
  <th><strong>自動作成されたリソース</strong></th>
  </tr>
  </thead>
  <tbody>
  <tr>
  <td>
  <p>タグ</p>
  </td>
  <td>
  <ul>
  <li>モバイルタグプロパティ</li>
  <li>ルール</li>
  <li>データ要素</li>
  <li>ライブラリ</li>
  <li>環境（ステージング、実稼動、開発）</li>
  </ul>
  </td>
  </tr>
  <tr>
  <td>
  <p>タグ拡張機能</p>
  </td>
  <td>
  <ul>
  <li>Adobe Experience Platform Edge Network</li>
  <li>Adobe Journey Optimizer</li>
  <li>AEP Assurance</li>
  <li>同意（デフォルトの同意ポリシーを有効にした場合）</li>
  <li>ID （デフォルトの ECID とデフォルトのステッチルール）</li>
  <li>Mobile Core</li>
  </ul>
  </td>
  </tr>
  <tr>
  <td>
  <p>Assurance</p>
  </td>
  <td>
  <p>アシュランスセッション</p>
  </td>
  </tr>
  <tr>
  <td>
  <p>データストリーム</p>
  </td>
  <td>
  <p>サービスを使用したデータストリーム</p>
  </td>
  </tr>
  <tr>
  <td>
  <p>Experience Platform</p>
  </td>
  <td>
  <ul>
  <li>データセット</li>
  <li>スキーマ</li>
  </ul>
  </td>
  </tr>
  </tbody>
  </table>

**チャネル設定** の場合、**チャネルを追加** 画面で作成されたすべてのリソースの包括的なリストを以下に示します。

<table>
  <thead>
  <tr>
  <th><strong>ソリューション</strong></th>
  <th><strong>自動作成されたリソース</strong></th>
  </tr>
  </thead>
  <tbody>
  <tr>
  <td>
  <p>Journey Optimizer</p>
  </td>
  <td>
  <ul>
  <li>チャネル設定</li>
  <li>プッシュ資格情報のアップロード（モバイルプッシュメッセージのみ）</li>
  </ul>
  </td>
  </tr>
  </tbody>
  </table>

>[!TAB Web]

**初期設定** については、「**リソースの自動作成**」をクリックすると **設定の詳細** 画面に作成されるすべてのリソースの一覧を以下に示します。

<table>
  <thead>
  <tr>
  <th><strong>ソリューション</strong></th>
  <th><strong>自動作成されたリソース</strong></th>
  </tr>
  </thead>
  <tbody>
  <tr>
  <td>
  <p>タグ</p>
  </td>
  <td>
  <ul>
  <li>モバイルタグプロパティ</li>
  <li>ルール</li>
  <li>データ要素</li>
  <li>ライブラリ</li>
  <li>環境（ステージング、実稼動、開発）</li>
  </ul>
  </td>
  </tr>
  <tr>
  <td>
  <p>タグ拡張機能</p>
  </td>
  <td>
  <ul>
  <li>Adobe Experience Platform Edge Network</li>
  <li>Adobe Journey Optimizer</li>
  <li>AEP Assurance</li>
  <li>同意（デフォルトの同意ポリシーを有効にした場合）</li>
  <li>ID （デフォルトの ECID とデフォルトのステッチルール）</li>
  <li>Mobile Core</li>
  </ul>
  </td>
  </tr>
  <tr>
  <td>
  <p>Assurance</p>
  </td>
  <td>
  <p>アシュランスセッション</p>
  </td>
  </tr>
  <tr>
  <td>
  <p>データストリーム</p>
  </td>
  <td>
  <p>サービスを使用したデータストリーム</p>
  </td>
  </tr>
  <tr>
  <td>
  <p>Experience Platform</p>
  </td>
  <td>
  <ul>
  <li>データセット</li>
  <li>スキーマ</li>
  </ul>
  </td>
  </tr>
  </tbody>
  </table>

>[!ENDTABS]
