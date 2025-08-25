---
solution: Journey Optimizer
product: journey optimizer
title: ジャーニーでのインバウンドアクションのトラブルシューティングガイド
description: Adobe Journey Optimizer でジャーニーでのインバウンドアクションに関連する問題をデバッグして解決する方法について説明します。
feature: Journeys
topic: Content Management
role: User
level: Intermediate
keywords: インバウンドアクション, トラブルシューティング, ジャーニー, デバッグ, セルフヘルプ, チェック, エラー
exl-id: 5c56786f-da22-4558-b2ae-01f762175a7f
source-git-commit: d89eb9e569cb6de2edc5f20bdcf669972ccc8a8b
workflow-type: tm+mt
source-wordcount: '1654'
ht-degree: 100%

---

# ジャーニーでのインバウンドアクションのトラブルシューティング {#troubleshooting-inbound-actions}

アプリ内、web、コードベースのエクスペリエンスなどのインバウンドアクションは、ユーザーのジャーニー中にパーソナライズされたエンゲージメントを可能にするので、[!DNL Journey Optimizer] の重要なコンポーネントです。ただし、インバウンドコンテンツの欠落や、プロファイルがジャーニーから離脱した後に配信が継続されるなど、予期しない動作が発生する場合があります。

このガイドでは、サポートに連絡する前に、ジャーニーでのインバウンドアクションに関連する問題をデバッグするための手順について段階的に説明し、問題を独自に特定して解決できるようにします。

<!--This guide addresses the two most common scenarios with inbound actions in a journey. They are as follows:

* A profile enters the inbound step, but the user does not receive the expected inbound content.
* A user continues to receive inbound content even after the profile exits the journey.
-->

## 前提条件 {#prerequisites}

トラブルシューティングを開始する前に、以下を確認します。

1. **Assurance** セッションを設定します。方法について詳しくは、[Adobe Experience Platform Assurance ドキュメント](https://experienceleague.adobe.com/ja/docs/experience-platform/assurance/tutorials/using-assurance){target="_blank"}を参照してください。

1. インバウンドアクションを含むジャーニーに移動して、ジャーニー名とバージョン ID を取得します。

   >[!NOTE]
   >
   >ジャーニーバージョン ID は、URL の「journey/」の後にあります（例：*86232fb1-2932-4036-8198-55dfec606fd7*）。

   ![](assets/troubleshoot-inbound-retrieve-journey-id.png)

1. インバウンドアクションをクリックして、その詳細を表示します。インバウンドアクションのラベルと ID を取得します。

   ![](assets/troubleshoot-inbound-retrieve-action-id.png)

1. プロファイルの名前空間と ID を取得して、問題の発生したプロファイルを識別します。設定に基づいて、名前空間は ECID、メール、顧客 ID などになります。プロファイルを検索する方法について詳しくは、[Experience Platform ドキュメント](https://experienceleague.adobe.com/ja/docs/experience-platform/profile/ui/user-guide#browse-identity){target="_blank"}を参照してください。

## シナリオ 1：ユーザーがインバウンドコンテンツを受信していない {#scenario-1}

このシナリオでは、あるプロファイルがジャーニーでのインバウンドアクションにエントリしましたが、30 分経過しても、対応するインバウンドコンテンツが設定トリガーステップでデバイス／クライアントに表示されません。


### 事前確認 {#pre-checks}

1. **ジャーニーインバウンドデータセットがプロファイルの取り込みに対して有効になっている**

   インバウンドアクションでは、実行中にプロファイルの更新に&#x200B;**ジャーニーインバウンド**&#x200B;データセットを使用します。現在のサンドボックスのプロファイルに対してデータセットが有効になっていることを確認します。[データセットの詳細](../data/get-started-datasets.md)

2. **Platform ID で定義された「joai」ID**

   インバウンドアクションでは、インバウンドステップでプロファイルのアクティブ化にプロファイル `segmentMembership` の **joai** 名前空間を使用します。サンドボックスの Platform ID で定義されていることを確認します。詳しくは、[Experience Platform ID サービス](https://experienceleague.adobe.com/ja/docs/experience-platform/identity/home){target="_blank"}を参照してください

### デバッグ手順 {#debugging-steps}

次のグラフには、実行できるデバッグ手順のシーケンスを示します。

![](assets/troubleshoot-inbound-scenario-1-steps.png){width="70%" align="center"}

### 手順 1：デバイス／クライアントが Edge Network からコンテンツを受信しているかどうかを確認する {#step-1}

まず、デバイス／クライアントが期待どおりのコンテンツを取得しているかどうかを確認します。

>[!BEGINTABS]

>[!TAB アプリ内チャネル]

1. [Assurance](https://experienceleague.adobe.com/ja/docs/experience-platform/assurance/tutorials/using-assurance){target="_blank"} セッションに移動し、左側のパネルから「**[!UICONTROL アプリ内メッセージ]**」セクションを選択します。

1. 「**[!UICONTROL デバイスでのメッセージ]**」タブで、**[!UICONTROL メッセージ]**&#x200B;ドロップダウンリストをクリックします。

   ![](assets/troubleshoot-inbound-assurance-in-app.png){width="80%"}

1. ジャーニー名の後に「- アプリ内メッセージ」が付いたメッセージを探します。このようなメッセージがあった場合、アプリ内メッセージがデバイス／クライアントに存在し、問題がアプリ内トリガーに関連している可能性があります。

1. メッセージが見つからない場合、アプリ内メッセージはデバイス／クライアントによって受信されませんでした。<!--Go to the [next step](#step-2) for further debugging.-->

>[!TAB Web チャネル]

ページを訪問してネットワークタブを調べるか、[Assurance](https://experienceleague.adobe.com/ja/docs/experience-platform/assurance/tutorials/using-assurance){target="_blank"} セッションの「**[!UICONTROL Edge Delivery]**」セクションで Edge 応答ペイロードを確認します。

>[!TAB コードベースのエクスペリエンスチャネル]

[アドビの API](https://developer.adobe.com/data-collection-apis/docs/api/) を使用して cURL リクエストを実行し、[Assurance](https://experienceleague.adobe.com/ja/docs/experience-platform/assurance/tutorials/using-assurance){target="_blank"} セッションの「**[!UICONTROL Edge Delivery]**」セクションで Edge 応答ペイロードを確認します。

>[!ENDTABS]

### 手順 2：Edge Network がコンテンツを返しているかどうかを確認する {#step-2}

この手順では、Edge Network がデバイス／クライアントでレンダリングされる期待どおりのインバウントコンテンツを返していることを確認します。

プロファイルがジャーニーのインバウンドアクションにエントリすると、インバウンドジャーニーアクションに対応する特別なオーディエンスセグメント（**joai** 名前空間内）に自動的に選定されます。

クライアントが特定のプロファイルとサーフェスについて Edge Network にリクエストを行うと、そのプロファイルが現在対応する **joai** セグメントのメンバーである場合に限り、そのサーフェスをターゲティングするインバウンドジャーニーアクションのコンテンツを受信する資格がプロファイルに選定されます。

Edge Network の動作をデバッグするには、次の手順に従います。

1. Assurance セッションで **[!UICONTROL Edge Delivery]** ビューを開きます。このビューには、Edge Network サーバーでのインバウンドアクションの実行に関する情報が表示されます。詳しくは、[Experience Platform ドキュメント](https://experienceleague.adobe.com/ja/docs/experience-platform/assurance/view/edge-delivery){target="_blank"}を参照してください。

1. インバウンドアクションに対応する Edge アクティビティが「**[!UICONTROL 選定アクティビティ]**」セクションまたは「**[!UICONTROL 未選定アクティビティ]**」セクションにリストされているかどうかを確認します。

   ![](assets/troubleshoot-inbound-edge-delivery.png)

   * 「**選定アクティビティ**」セクションの場合、プロファイルはインバウンドジャーニーアクションに選定され、コンテンツを返す必要があります。
   * 「**未選定アクティビティ**」セクションの場合、プロファイルはインバウンドジャーニーアクションに選定されません。詳しくは、除外の理由を参照してください。
   * **いずれのセクションでもない**&#x200B;場合は、Edge Network へのインバウンドジャーニーアクションの公開で問題が発生するか、リクエストしたサーフェス URI がインバウンドアクションのチャネル設定と一致しません。

   >[!NOTE]
   >
   >**Assurance** セッションで Edge アクティビティを見つけるには、**[!UICONTROL audienceNamespace]** が **joai** で、**[!UICONTROL audienceSegmentId]** が &lt;*JourneyVersionID*>_&lt;*JourneyActionID*> であるアクティビティを探します（例：*86232fb1-2932-4036-8198-55dfec606fd7_708f718d-8503-4427-ad8d-8e28979b554c*）。

   ![](assets/troubleshoot-inbound-edge-delivery-unqualified.png){width="70%"}

1. アクティビティが「**[!UICONTROL 未選定アクティビティ]**」セクションにあり、除外の理由が&#x200B;*「セグメントがアクティブではありません」*&#x200B;である場合、Edge Network 配信サーバーは、プロファイルが関連する **joai** オーディエンスセグメントの一部ではないと判断します。

   「プロファイル」セクションの **segmentsMap** 要素を開き、**joai** セグメント ID の存在を探すことで、Edge Network 配信サーバーのプロファイルのビューに **joai** セグメントが存在するかどうかを再確認できます。

1. Edge Network 配信サーバーがプロファイルを関連する **joai** セグメント内にあると表示しない場合は、次の手順に進みます。<!--use the Platform Profile viewer UI to check if the expected **joai** segment is in a realized state in the Edge profile. Learn more in the [Experience Platform Profile UI documentation](https://experienceleague.adobe.com/en/docs/experience-platform/profile/ui/user-guide){target="_blank"}-->

### 手順 3：「joai」オーディエンスメンバーシップが Edge Network に生成されているかどうかを確認する {#step-3}

この手順では、プロファイルがインバウンドジャーニーアクションにエントリし、対応する **joai** セグメントにプロファイルが選定された際に、Edge プロファイルが正しく更新されたことを確認します。

プロファイルが **joai** セグメントに選定されると、まずハブでプロファイルが更新され、次にセグメントメンバーシップが Edge プロファイルに投影されて、Edge Network 配信サーバーで使用できるようになります。

>[!NOTE]
>
>ハブから Edge への生成には、ハブでプロファイルが更新されてから最大 15～30 分かかる場合があります。

Edge プロファイルの `segmentMembership` 属性に **joai** セグメントが存在するかどうかを確認するには、次の手順に従います。

1. [!DNL Journey Optimizer] の左側のナビゲーションパネルにある&#x200B;**[!UICONTROL 顧客]**／**[!UICONTROL プロファイル]**&#x200B;メニューに移動し、名前空間と ID を使用してプロファイルを参照します。詳しくは、[リアルタイム顧客プロファイル](../audience/get-started-profiles.md)を参照してください

1. 「**[!UICONTROL 属性]**」タブを選択し、**[!UICONTROL Edge]** ビューを選択します。

1. 「**[!UICONTROL JSON を表示]**」をクリックして、プロファイルの JSON ビューを開きます。

   ![](assets/troubleshoot-inbound-profile-view-json.png){width="80%"}

1. `segmentMembership` 属性に移動し、セグメント ID &lt;*JourneyVersionID>*_&lt;*JourneyActionID*> が **joai** 名前空間に存在し、「**[!UICONTROL 適合]**<!--or existing?-->」ステータスになっているかどうかを確認します。

   ![](assets/troubleshoot-inbound-profile-json-realized.png){width="90%"}

   * 存在する場合、インバウンドジャーニーアクションに対応する **joai** セグメントが Edge プロファイルに正しく生成されます。

   * Edge Network 配信サーバーのプロファイルビューに表示されない場合は、配信サーバーが Edge プロファイルを読み込む方法に問題がある可能性があります。

1. **joai** セグメント ID が存在しないか&#x200B;**[!UICONTROL 離脱]**&#x200B;状態の場合、Edge に（まだ）生成されていません。

   `segmentMembership` の値がハブから Edge に生成されるまで 15～30 分待機します。まだ表示されない場合は、次の手順に進みます。

<!--The next step is to check whether the audience segment is present in the profile on the Hub.-->

### 手順 4：「joai」オーディエンスメンバーシップがハブのプロファイルに存在するかどうかを確認する {#step-4}

この手順では、プロファイルがインバウンドジャーニーアクションにエントリし、対応する **joai** セグメントにプロファイルが選定された際に、ハブプロファイルが正しく更新されたことを確認します。

>[!NOTE]
>
>**joai** セグメントメンバーシップのハブプロファイルへの取り込みには、プロファイルがインバウンドジャーニーアクションにエントリしてから最大 15～30 分かかる場合があります。

ハブプロファイルの `segmentMembership` 属性に **joai** セグメントが存在するかどうかを確認するには、次の手順に従います。

1. [!DNL Journey Optimizer] の左側のナビゲーションパネルにある&#x200B;**[!UICONTROL 顧客]**／**[!UICONTROL プロファイル]**&#x200B;メニューに移動し、名前空間と ID を使用してプロファイルを参照します。詳しくは、[リアルタイム顧客プロファイル](../audience/get-started-profiles.md)を参照してください

1. 「**[!UICONTROL 属性]**」タブを選択し、**[!UICONTROL ハブ]**&#x200B;ビューを選択します。

1. 「**[!UICONTROL JSON を表示]**」をクリックして、プロファイルの JSON ビューを開きます。

1. **[!UICONTROL segmentMembership]** 属性に移動し、セグメント ID &lt;*JourneyVersionID>*_&lt;*JourneyActionID*> が **joai** 名前空間に存在し、「**[!UICONTROL 適合]**<!--or existing?-->」ステータスになっているかどうかを確認します。

   * 存在する場合、インバウンドジャーニーアクションに対応する **joai** セグメントがハブプロファイルに正しく取り込まれます。

   * 30 分以上経過しても Edge プロファイルに見つからない場合、Edge 投影システムに問題がある可能性があります。

1. **joai** セグメント ID が存在しないか&#x200B;**[!UICONTROL 離脱済み]**&#x200B;状態の場合、プロファイルは、対応するインバウンドジャーニーアクションへのエントリ時に特別な **joai** オーディエンスセグメントに（まだ）正しく選定されていません。

   `segmentMembership` の値がハブのプロファイルに取り込まれるまで 15 ～ 30 分待機します。まだ表示されない場合は、次の手順に進みます。

### 手順 5：クライアント／デバイスがまだ期待どおりのコンテンツを取得していない場合する {#step-5}

上記の手順をすべて実行し、セグメントメンバーシップが Edge Network に生成されるまで 30～60 分待機しても期待どおりの動作が見られない場合は、アドビカスタマーケアまたはアドビ担当者にお問い合わせください。

次のようなデバッグ手順の詳細をできるだけ多く含めます。

* 予期しない動作が見られるステップ。
* ジャーニーバージョン ID。
* ジャーニーアクション ID。
* Assurance の完全なトレース。
* Edge プロファイルの JSON ビュー。
* ハブプロファイルの JSON ビュー。
* その他。

## シナリオ 2：ユーザーがインバウンドコンテンツを引き続き受信する {#scenario-2}

このシナリオは[シナリオ 1](#scenario-1) の逆です。プロファイルはジャーニーから離脱していますが、ユーザーはインバウンドコンテンツを引き続き受信しています。

ただし、プロファイルがジャーニーから離脱すると、ジャーニーのインバウンドアクションに対応する **joai** オーディエンスセグメントに選定されなくなります。

[シナリオ 1](#debugging-steps) と同じデバッグ手順を実行して、ハブプロファイル、Edge プロファイル、Edge Network 配信サーバーが関連する **joai** セグメントのセグメントメンバーシップステータスを正しく反映しているかどうか、およびクライアントがインバウンドコンテンツを受信しなくなっているかどうかを確認します。

<!--

## Reference Section {#reference-section}

- [Assurance Setup Guide](https://experienceleague.adobe.com/en/docs/experience-platform/assurance/tutorials/using-assurance)
- [Adobe Experience Platform Documentation](https://experienceleague.adobe.com/docs/experience-platform/home.html)
- [Streaming Ingestion APIs Troubleshooting](https://experienceleague.adobe.com/docs/experience-platform/ingestion/streaming/troubleshooting.html)

-->
