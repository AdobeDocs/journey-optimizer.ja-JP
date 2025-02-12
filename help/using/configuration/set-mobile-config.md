---
solution: Journey Optimizer
product: journey optimizer
title: モバイルと web の設定
description: モバイルチャネルと web チャネルを設定および監視する方法について説明します
feature: Channel Configuration
topic: Administration
role: Admin
level: Experienced
keywords: チャネル, サーフェス, 技術, パラメーター, Optimizer
exl-id: 846e0d11-798b-4f3b-80db-848a17d32830
source-git-commit: f916d91ffd2c41261612f2127f35c41275c9d013
workflow-type: tm+mt
source-wordcount: '770'
ht-degree: 100%

---

# ガイド付きチャネル設定の基本を学ぶ {#set-mobile-config}

>[!CONTEXTUALHELP]
>id="ajo_mobile_web_setup_name"
>title="モバイルと web の設定名"
>abstract="モバイルまたは web 設定の名前を入力します。この名前は、ガイド付きチャネル設定で自動的に作成されるすべてのリソースに使用されます。"

>[!CONTEXTUALHELP]
>id="ajo_mobile_web_setup_validate_assurance"
>title="Assurance での検証"
>abstract="Adobe Experience Platform Assurance は、このワークフローに組み込まれており、SDK 実装の検査や、アプリケーションイベントのシミュレートと検証に役立ちます。"
>additional-url="https://experienceleague.adobe.com/ja/docs/experience-platform/assurance/home" text="Adobe Experience Platform Assurance の概要"

この設定により、マーケティングチャネルの迅速な設定が容易になり、Experience Platform、Journey Optimizer およびデータ収集内で必要なすべてのリソースがすぐに使用できるようになります。これにより、マーケティングチームはキャンペーンとジャーニーの作成を開始できます。

ガイド付きチャネル設定は、次のプラットフォームとチャネルをサポートしています。

* プラットフォームと SDK：

   * Apple の Swift、iOS

   * Kotlin、Android

   * JavaScript、Web

* チャネル：

   * モバイルアプリ内

   * モバイルプッシュメッセージ

   * Web 基本


設定するプラットフォームごとに、個別の設定を作成する必要があります。これは、各アプリに一意のチャネル設定が必要であり、これにより各プラットフォームに必要なチャネルを柔軟に決定できるからです。

## 前提条件 {#prereq}

* これを効果的に実装するには、web サイトまたはモバイルコードを変更する権限と技術的能力を持つ組織のメンバーが設定を監視することが不可欠です。

  ガイド付きチャネル設定を実行するために必要な権限を以下に示します。

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
            <li>会社権限／プロパティ</li>
            <li>プロパティ権限：拡張機能と環境の開発、公開、管理</li>
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
           <li>サンドボックス：サンドボックスへのアクセス権の付与</li>
            <li>セグメントを管理：セグメント定義の読み取り、作成、編集、削除</li>
            <li>プロファイルを管理：プロファイルの読み取り、作成、編集、削除</li>
            <li>データセットを読み取り：データセットに対する読み取り専用アクセス</li>
            <li>スキーマを読み取り：スキーマに対する読み取り専用アクセス</li>
            <li>ID 名前空間を読み取り：ID 名前空間に対する読み取り専用アクセス</li>
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

* 既存の設定オプションを使用している場合は、次の Adobe Experience Platform Mobile SDK 拡張機能バージョンを使用していることを確認してください。必要な依存関係や初期化コードを含む SDK 設定について詳しくは、[次のドキュメント](https://experienceleague.adobe.com/ja/docs/platform-learn/implement-mobile-sdk/app-implementation/install-sdks)を参照してください。

  Android の場合

   * Mobile Core v3.1.0 以降
   * Adobe Journey Optimizer v3.1.0 以降

  iOS の場合

   * Mobile Core v5.2.0 以降
   * Adobe Journey Optimizer v5.1.1 以降

## 自動作成されたリソース {#auto-create-resources}

ガイド付きチャネル設定により、マーケティングチャネルの迅速な設定が簡単になり、Experience Platform、Journey Optimizer およびデータ収集アプリですべての重要なリソースがすぐに使用できるようになります。これにより、マーケティングチームはキャンペーンとジャーニーの作成をすぐに開始できます。ガイド付きチャネル設定の一部として自動生成および設定されるリソースのリストを以下に示します。

自動生成されるすべてのリソースの包括的なリストにアクセスするには、以下のタブを参照してください。

>[!BEGINTABS]

>[!TAB iOS]

**初期設定**&#x200B;の場合、「**リソースを自動作成**」をクリックした際に&#x200B;**設定の詳細**&#x200B;画面で作成されるすべてのリソースの包括的なリストを以下に示します。

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
  <li>同意（デフォルトの同意ポリシーを有効にする場合）</li>
  <li>ID（デフォルトの ECID とデフォルトのステッチルールを使用する場合）</li>
  <li>Mobile Core</li>
  </ul>
  </td>
  </tr>
  <tr>
  <td>
  <p>Assurance</p>
  </td>
  <td>
  <p>Assurance セッション</p>
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

**チャネル設定**&#x200B;の場合、**チャネルを追加**&#x200B;画面で作成されるすべてのリソースの包括的なリストを以下に示します。

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
  <li>プッシュ資格情報をアップロード（モバイルプッシュメッセージのみ）</li>
  </ul>
  </td>
  </tr>
  </tbody>
  </table>

>[!TAB Android]

**初期設定**&#x200B;の場合、「**リソースを自動作成**」をクリックした際に&#x200B;**設定の詳細**&#x200B;画面で作成されるすべてのリソースの包括的なリストを以下に示します。

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
  <li>同意（デフォルトの同意ポリシーを有効にする場合）</li>
  <li>ID（デフォルトの ECID とデフォルトのステッチルールを使用する場合）</li>
  <li>Mobile Core</li>
  </ul>
  </td>
  </tr>
  <tr>
  <td>
  <p>Assurance</p>
  </td>
  <td>
  <p>Assurance セッション</p>
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

**チャネル設定**&#x200B;の場合、**チャネルを追加**&#x200B;画面で作成されるすべてのリソースの包括的なリストを以下に示します。

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
  <li>プッシュ資格情報をアップロード（モバイルプッシュメッセージのみ）</li>
  </ul>
  </td>
  </tr>
  </tbody>
  </table>

>[!TAB Web]

**初期設定**&#x200B;の場合、「**リソースを自動作成**」をクリックした際に&#x200B;**設定の詳細**&#x200B;画面で作成されるすべてのリソースの包括的なリストを以下に示します。

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
  <li>同意（デフォルトの同意ポリシーを有効にする場合）</li>
  <li>ID（デフォルトの ECID とデフォルトのステッチルールを使用する場合）</li>
  <li>Mobile Core</li>
  </ul>
  </td>
  </tr>
  <tr>
  <td>
  <p>Assurance</p>
  </td>
  <td>
  <p>Assurance セッション</p>
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

