---
solution: Journey Optimizer
product: journey optimizer
title: ジャーニーへの組み込みチャネルアクションの追加
description: ジャーニーに組み込みのチャネルアクションを追加する方法について説明します。
feature: Journeys, Activities, Channels Activity
topic: Content Management
role: User
level: Intermediate
keywords: ジャーニー, メッセージ, プッシュ, sms, メール, アプリ内, web, コンテンツカード, コードベースのエクスペリエンス
exl-id: 4db07a9e-c3dd-4873-8bd9-ac34c860694c
source-git-commit: 47482adb84e05fe41eb1c50479a8b50e00469ec4
workflow-type: ht
source-wordcount: '1268'
ht-degree: 100%

---

# 組み込みのチャネルアクションの使用 {#add-a-message-in-a-journey}

>[!CONTEXTUALHELP]
>id="ajo_message_activity"
>title="組み込みのチャネルアクション"
>abstract="Journey Optimizer には、チャネルアクション機能が組み込まれています。アウトバウンド（メール、SMS や MMS テキストメッセージ、プッシュ）またはインバウンド（アプリ内、web、コードベースのエクスペリエンス、コンテンツカード）アクティビティをジャーニーに追加し、設定とコンテンツを定義するだけです。その後、メッセージアクティビティがジャーニーのコンテキストで実行および送信されます。"

[!DNL Journey Optimizer] には、チャネルアクション機能が組み込まれています。アウトバウンド（メール、SMS や MMS テキストメッセージ、プッシュ）またはインバウンド（アプリ内、web、コードベースのエクスペリエンス、コンテンツカード）アクティビティをジャーニーに追加し、設定とコンテンツを定義するだけです。その後、メッセージアクティビティがジャーニーのコンテキストで実行および送信されます。

>[!NOTE]
>
>また、メッセージを送信する特定のアクションを設定することもできます。[詳細情報](#recommendation)

ジャーニーに組み込みのチャネルアクションを追加するには、次の手順に従います。

1. ジャーニーを[イベント](general-events.md)または[オーディエンスを読み取り](read-audience.md)アクティビティで開始します。

1. パレットの「**アクション**」セクションで、アウトバウンド（**メール**、**プッシュ**、**SMS**）またはインバウンド（**アプリ内**、**web**、**コードベースのエクスペリエンス**、**コンテンツカード**）アクティビティをキャンバスにドラッグ＆ドロップします。

   ![](assets/journey-web-activity.png)

1. アクティビティを設定します。

   * メッセージコンテンツを作成する手順について詳しくは、次を参照してください。

     <table style="table-layout:fixed">
      <tr style="border: 0;">
      <td>
      <a href="../email/create-email.md">
      <img alt="リード" src="../assets/do-not-localize/email.jpg">
      </a>
      <div><a href="../email/create-email.md"><strong>メールの作成</strong>
      </div>
      <p>
      </td>
      <td>
      <a href="../push/create-push.md">
      <img alt="低頻度" src="../assets/do-not-localize/push.jpg">
      </a>
      <div>
      <a href="../push/create-push.md"><strong>プッシュ通知の作成<strong></a>
      </div>
      <p>
      </td>
      <td>
      <a href="../sms/create-sms.md">
      <img alt="検証" src="../assets/do-not-localize/sms.jpg">
      </a>
      <div>
      <a href="../sms/create-sms.md"><strong>テキストメッセージ（SMS／MMS）の作成</strong></a>
      </div>
      <p>
      </td>
      </tr>
      </table>

   * インバウンドアクションを作成する方法を次に説明します。

     <table style="table-layout:fixed">
      <tr style="border: 0;">
      <td>
      <a href="../in-app/create-in-app.md">
      <img alt="リード" src="../assets/do-not-localize/in-app.jpg">
      </a>
      <div><a href="../in-app/create-in-app.md"><strong>アプリ内メッセージの作成</strong>
      </div>
      <p>
      </td>
      <td>
      <a href="../web/create-web.md">
      <img alt="リード" src="../assets/do-not-localize/web-create.jpg">
      </a>
      <div><a href="../web/create-web.md"><strong>Web エクスペリエンスの作成</strong>
      </div>
      <p>
      </td>
      <td>
      <a href="../content-card/create-content-card.md">
      <img alt="リード" src="../assets/do-not-localize/sms-config.jpg">
      </a>
      <div><a href="../content-card/create-content-card.md"><strong>コンテンツカードの作成</strong>
      </div>
      <p>
      </td>
      <td>
      <a href="../code-based/create-code-based.md">
      <img alt="低頻度" src="../assets/do-not-localize/web-design.jpg">
      </a>
      <div>
      <a href="../code-based/create-code-based.md"><strong>コードベースのエクスペリエンスの作成<strong></a>
      </div>
      <p>
      </td>
      </tr>
      </table>

     >[!NOTE]
     >
     >各インバウンドメッセージアクティビティには、3 日間の&#x200B;**待機**&#x200B;アクティビティが付属しています。[詳細情報](../building-journeys/wait-activity.md#auto-wait-node)

## レコメンデーション {#recommendation}

[!DNL Journey Optimizer] には、メッセージ機能がビルトインされています。ただし、カスタムアクションを使用すると、メッセージや API 呼び出しを送信するサードパーティシステムの接続を設定できます。

* サードパーティのシステムを使用してメッセージを送信する場合は、カスタムアクションを作成できます。[詳細情報](../action/action.md)

* Campaign と Journey Optimizer の連携について詳しくは、次の節を参照してください。

   * [[!DNL Journey Optimizer] と Campaign v7/v8](../action/acc-action.md)
   * [[!DNL Journey Optimizer] と Campaign Standard](../action/acs-action.md)

## ライブコンテンツの更新{#update-live-content}

ライブジャーニーで組み込みのチャネルアクションのコンテンツを更新できます。

それには、ライブジャーニーを開き、チャネルアクティビティを選択して、「**コンテンツを編集**」をクリックします。

![](assets/add-a-message2.png)

ただし、パーソナライゼーションで使用されている属性は、プロファイル属性であるかコンテキストデータ（イベントプロパティまたはジャーニープロパティから得られるもの）であるかにかかわらず、変更できません。

コンテキストデータを変更すると、次のエラーメッセージが表示されます：ERR_AUTHORING_JOURNEYVERSION_201

プロファイル属性を変更すると、次のエラーメッセージが表示されます：ERR_AUTHORING_JOURNEYVERSION_202

アプリ内アクティビティの場合、ジャーニーのライブ中にコンテンツを変更できますが、アプリ内トリガーは変更できません。

## 送信時間の最適化{#send-time-optimization}

>[!CONTEXTUALHELP]
>id="jo_bestsendtime_disabled"
>title="送信時間の最適化について"
>abstract="Adobe Journey Optimizer の送信時間最適化機能（アドビの AI サービスを利用）は、メールまたはプッシュメッセージの送信に最適な時間を予測し、過去の開封率とクリック率に基づいてエンゲージメントを最大化できます。"

>[!NOTE]
>
>この機能は、デフォルトでは有効になっていません。アクティブにするには、アドビ担当者にお問い合わせください。
>
>送信時間の最適化機能は、メールチャネルとプッシュチャネルにのみ適用されます。

### 送信時間の最適化について {#about-send-time}

Adobe Journey Optimizer の送信時間最適化機能（アドビの AI サービスを利用）は、**メール**&#x200B;または&#x200B;**プッシュメッセージ**&#x200B;の送信に最適な時間を予測し、過去の開封率とクリック率に基づいてエンゲージメントを最大化できます。機械学習モデルを使用して、ユーザーごとにパーソナライズされた送信時間をスケジュールし、メッセージの開封率やクリック率を高めます。

送信時間最適化モデルは、Adobe Journey Optimizer のデータを取り込み、ユーザーレベルの開封率（メールとプッシュの場合）およびクリック率（メールの場合）を調べて、顧客がメッセージングに関与する可能性が最も高いタイミングを判断します。送信時間の最適化では、情報に基づいたレコメンデーションを行うために、1 か月以上のメッセージトラッキングデータが必要です。ユーザーごとに、次のスコアを使用して最適な時間が自動的に選択されます。

* エンゲージメントを最大化するための各曜日の最適な時間帯
* エンゲージメントを最大化するのに最適な曜日
* エンゲージメントを最大化するための最適な曜日の最適な時間

モデルは、スコアリングとトレーニングのどちらに注目しているかによって異なります。トレーニングは、最初は毎週、その後は四半期ごとに実施されます。スコアリングは、最初は毎週、その後は毎月行われます。

* トレーニング - スコアを付けるために使用するアルゴリズムの開発
* スコアリング - トレーニング済みモデルに基づく個々のプロファイルへのスコアの適用

この情報はユーザーのプロファイルと共に保存され、ジャーニーの実行時に参照されて、メッセージを送信するタイミングを Adobe Journey Optimizer に指示します。

### よくある質問 {#faq-send-time}

+++ 送信時間の最適化では何ができますか？新規プロファイルはどのように処理されますか？送信を 6／12／24 時間にわたって実行されますか？

送信時間の最適化では、顧客との関わり合いに最適な時間の予測し、メールの開封率やクリック率の最適化を試みます。スコアは、各プロファイルの `3*7*24` 属性の形式になります。`7*24` 属性は、受信者にメールを送信するのに最適な予測時間のランクを表し、3 はメールの開封率、メールのクリック率およびプッシュ開封率を最適化するためのものです。

+++

+++各プロファイルの予想送信時間はどこで確認できますか？

全体的なスコアは、**プロファイル**&#x200B;インターフェイスに表示されます。3 組の 168 スコアのそれぞれに対して、ランクは -83 から 84 になります。ランクが高いほど、受信者とのやり取りに適した時間が選択されたことになります。ジャーニーの開始と期間を定義できるので、ベストランク（84）はその時間枠には含まれない場合があります。この場合、ランクの値が最も高い時間を選択することをお勧めします。

+++


+++どのレポートの種類を使用できますか？

ジャーニーにアクセスし、「**レポートを表示**」ボタンをクリックし、左側の「**ジャーニー**」タブを選択します。[詳細情報](../reports/journey-global-report-cja.md)

+++

+++送信時間の最適化データは、プロファイルリッチネスにどのように影響しますか？

送信時間の最適化では、各プロファイルにスコアや属性が追加されますが、新規プロファイルは作成されません。

+++

### 送信時間最適化の有効化{#activate-send-time-optimization}

>[!CONTEXTUALHELP]
>id="jo_bestsendtime_email"
>title="送信時間最適化の有効化"
>abstract="適切なラジオボタンを選択して、メールの開封数とクリックスルー数のどちらを最適化するかを選択します。また、「次のオプション内で送信」に値を入力して、システムで使用される送信時間を区切ることもできます。"

>[!CONTEXTUALHELP]
>id="jo_bestsendtime_push"
>title="送信時間最適化の有効化"
>abstract="プッシュメッセージではクリック数が適用されないため、デフォルトは「開封数」オプションになります。また、「次のオプション内で送信」に値を入力して、システムで使用される送信時間を区切ることもできます。"

アクティビティのパラメーターから&#x200B;**送信時間の最適化**&#x200B;スイッチを選択して、メールまたはプッシュメッセージの送信時間の最適化を有効にします。

![](../building-journeys/assets/jo-message5.png)

メールメッセージの場合は、適切なラジオボタンを選択して、メールの開封数とクリックスルー数のどちらを最適化するかを選択します。プッシュメッセージではクリック数が適用されないため、デフォルトは「開封数」オプションになります。

また、「**次の時間内に送信**」オプションの値を入力することで、システムで使用される送信時間を区切ることもできます。値として「6 時間」を選択した場合、[!DNL Journey Optimizer] は各ユーザープロファイルを確認し、ジャーニーの実行時刻から 6 時間以内の最適な送信時刻を選択します。

**最適な時間が期間外にある場合はどうなりますか？**

次の設定を例に取ります。

* クリック時に最適化
* アクションは午前 10 時に起動される予定
* 期間は 3 時間

プロファイルには、期間外に最適なオープン時間を設定できます。例えば、John の最適なクリックオープンが午後 5 時であるといった具合です。

プロファイルレベルでは、1 週間の時間ごとのスコアがあります。この例では、メールは常に期間内に送信されます。実行時に、その期間（午前 10 時から 3 時間）内のスコアのリストがシステムにより確認されます。 次に、午前 10 時、午前 11 時および正午のスコアが比較され、最も高いスコアが選択されます。その時点でメールが送信されます。
