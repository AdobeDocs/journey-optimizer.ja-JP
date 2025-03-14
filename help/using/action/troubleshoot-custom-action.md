---
solution: Journey Optimizer
product: journey optimizer
title: カスタムアクションのトラブルシューティング
description: カスタムアクションのトラブルシューティング方法を学ぶ
feature: Journeys, Actions, Custom Actions
topic: Administration
role: Data Engineer, Data Architect, Admin
level: Experienced
keywords: アクション, サードパーティ, カスタム, ジャーニー, API
exl-id: c0bb473a-82dc-4604-bd8a-020447ac0c93
source-git-commit: 4367e39013e87b12848fc172df9b68cd637fc802
workflow-type: tm+mt
source-wordcount: '559'
ht-degree: 1%

---

# カスタムアクションのトラブルシューティング {#troubleshoot-a-custom-action}

Journey Optimizer ユーザーインターフェイスの管理セクションから API 呼び出しを送信することで、カスタムアクションをテストできます。 この機能は、ジャーニーでカスタムアクションを使用する前または後にカスタムアクションのトラブルシューティングを行うのに役立ちます。

管理者は、「**[!UICONTROL テストリクエストを送信]** 機能を使用して、Adobe Journey Optimizerから直接実際の API 呼び出しを行い、カスタムアクション設定を検証します。 この機能により、ジャーニーで使用する前に、リクエスト構造、ヘッダー、認証およびペイロードが正しくフォーマットされます。

![](assets/send-test-request.png){width="70%" align="left"}

この機能を使用すると、テストおよび検証プロセスが合理化され、ライブジャーニーでカスタムアクションが正しく機能するようになります。

## 前提条件 {#troubleshoot-custom-action-prereq}

**[!UICONTROL テストリクエストを送信]** 機能を使用するには、URL、ヘッダー、認証設定を使用して **カスタムアクション** を事前設定する必要があります。

管理者がこの機能を使用するには、次の権限が必要です。

* ユーザーには **[!DNL Manage journeys events, data sources and actions]** 権限が必要です。
* この権限は *ジャーニー管理者* の役割に含まれています。
* **[!DNL View journeys events]** の権限だけでは不十分です。

ジャーニーの権限について詳しくは、[ この節 ](../administration/high-low-permissions.md#journey-capability) を参照してください。

## テストリクエスト送信機能の使用方法 {#troubleshoot-custom-action-use}

カスタムアクションをテストするには、次の手順に従います。

1. **アクション** 設定画面に移動し、カスタムアクションを選択します。
1. アクション設定画面の下部にある「**[!UICONTROL テストリクエストを送信]**」ボタンをクリックします。
   ![ アクション設定パネルの「テストリクエストを送信」ボタン ](assets/test-request.png){width="70%" align="left"}
1. ポップアップウィンドウで、リクエストパラメーターを指定できます。

   * **カスタムアクションメソッドがGET** の場合、ペイロードは必要ありません。
   * **カスタムアクションメソッドが POST** の場合、JSON ペイロードを指定する必要があります。

     >[!NOTE]
     >
     >この JSON の構造が正しくない場合は、Adobe Journey Optimizerでエラーが発生しますが、データタイプに不一致がある場合は発生しません。 例えば、文字列であるべきものに整数パラメーターが使用されている場合、エラーは発生しません。

   * 認証が定義されている場合は、認証の詳細を入力するように求められます。

1. 「**送信**」をクリックしてリクエストを実行します。
1. ヘッダーやステータスコードなど、API からの応答がインターフェイスに表示されます。

## 認証処理 {#troubleshoot-custom-action-auth}

カスタムアクションに認証が含まれる場合、Adobe Journey Optimizerでは、各テストリクエストに対して、認証の詳細を入力することをユーザーに求めます。

* **基本認証：** ユーザーは *パスワード* を指定する必要があります。
* **API キー認証：** ユーザーは、API キー *値* を入力する必要があります。
* **カスタム認証：** ユーザーは、リクエスト *bodyParam* で認証パラメーターを指定する必要があります。 この場合、**認証要求** と **認証応答** の 2 つの節が追加されます。

## 主なメリット {#troubleshoot-custom-action-benefits}

Journey Optimizerの管理者は、外部ツール（Postmanなど）を使用してカスタムアクションをテストすることもできます。 外部テストと比較した製品内トラブルシューティング機能の主なメリットを以下に示します。

* テストリクエストは、**AJO ジャーニー** によって実行されます。つまり、

   * 正確なリクエスト構造（Adobe Journey Optimizer固有のヘッダーを含む）が使用されます。
   * ソース IP とヘッダーは、ライブジャーニーで使用される IP とヘッダーに一致します。

* **[!UICONTROL テストリクエストを送信]** 機能は、カスタムアクションが既にデプロイされているので、**ライブジャーニー** のトラブルシューティングに使用できます。

* この製品内テスト機能により、ツール間で設定の詳細を手動でコピーする必要がなくなり、エラーのリスクが軽減されます。

## トラブルシューティング {#troubleshoot-custom-action-check}

リクエストが失敗した場合は、次の項目を確認できます。

* テストに入力された認証資格情報。
* リクエストメソッド（GETと POST）および対応するペイロード。
* カスタムアクションで定義される API エンドポイントとヘッダー。
* 応答データを使用して、潜在的な設定ミスを特定します。
