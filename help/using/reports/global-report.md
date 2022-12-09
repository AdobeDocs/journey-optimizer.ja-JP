---
solution: Journey Optimizer
product: journey optimizer
title: グローバルレポート
description: グローバルレポートのデータを使用する方法について説明します。
feature: Reporting
topic: Content Management
role: User
level: Intermediate
exl-id: ec15e700-7659-4dbf-8446-6534ea48c5c8
source-git-commit: 7c7faa5e672d5ed6d7a083db50b206d11ecc4184
workflow-type: tm+mt
source-wordcount: '1421'
ht-degree: 0%

---

# グローバルレポートを使用した作業の開始 {#global-report}

>[!NOTE]
>
> Query service を使用するときに Api を使用してカスタムクエリーを実行する場合、レポートに多少の遅延が発生します。

は、を使用して、 **[!UICONTROL Global report]** 選択した期間内の journeys と配達の影響を測定します。

* 移動または配信の対象を指定する場合は、メニューから **[!UICONTROL Journeys]** フライトにアクセスし、ボタンをクリック **[!UICONTROL View report]** します。 これにより、旅、電子メール、SMS、グローバルレポートが作成されます。

   ![](assets/report_journey.png)

* キャンペーンを対象とする場合は、メニューから **[!UICONTROL Campaigns]** キャンペーンにアクセスし、ボタンをクリック **[!UICONTROL Reports]** します。

   ![](assets/report_campaign.png)

* から **[!UICONTROL Live report]** **[!UICONTROL Global report]** に切り替える場合は、タブの切り替えをクリック **[!UICONTROL All time]** します。

   ![](assets/report_5.png)

アドビシステムズ社のオプティマイザーで利用可能なすべてのメトリックスのリストについては、このページを [ 参照してください。](#list-of-components-global)

## ダッシュボードのカスタマイズ {#modify-dashboard}

各レポートダッシュボードは、期間の変更や、widget のサイズ変更や削除によって変更することができます。 変更した widget は、現在のユーザーのダッシュボードに対してのみ適用されます。 他のユーザーには、独自のダッシュボードが表示されるか、デフォルトで設定されたものになります。

1. グローバルレポートから、特定のデータをターゲットとして指定する開始時間と終了時間を選択します。

   ![](assets/report_modify_1.png)

1. 切り替えバーを使用して、レポートからテストイベントを除外するかどうかを選択します。 テストイベントについて詳しくは、このページ ](../building-journeys/testing-the-journey.md) を [ 参照してください。

   このオプションは、 **[!UICONTROL Exclude test events]** 旅のレポートにのみ適用されます。

   ![](assets/report_modify_2.png)

1. クリック **[!UICONTROL Modify]** すると、ダッシュボードのカスタマイズが開始されます。

   ![](assets/report_modify_3.png)

1. Widget の右下隅をドラッグして、ウィジェットのサイズを調整します。

   ![](assets/report_modify_4.png)

1. クリック **[!UICONTROL Remove]** すると、不要な widget が削除されます。

   ![](assets/report_modify_5.png)

1. 表示順序と widget のサイズに問題がなければ、をクリック **[!UICONTROL Save]** します。

これで、ダッシュボードが保存されます。 ライブレポートを後で使用するために、異なる変更が再適用されます。 必要に応じて、オプションを使用 **[!UICONTROL Reset]** して、初期設定の widget とウィジェットの順序を復元します。

## コンポーネントのリスト {#list-of-components-global}

以下の表では、配信タイプに応じて、レポートとその定義に使用されるメトリックのリストを示します。

### 旅メトリック {#journey-metrics}

<table> 
 <thead> 
  <tr> 
   <th> 指標<br/> </th> 
   <th> 精細<br/> </th> 
</tr>
 </thead> 
 <tbody> 
  <tr> 
   <td>正常に実行された操作<br/> </td> 
   <td> 1つのフライト中に正常に実行された操作の合計数。<br/> </td> 
</tr> 
  <tr> 
   <td> 入力されたプロファイル<br/> </td> 
   <td> この旅の入場イベントに達した人物の総数です。<br/> </td> 
</tr>
  <tr> 
   <td> アクションでエラーが発生します。<br/> </td> 
   <td>アクションについて発生したエラーの合計数。<br/> </td> 
</tr> 
  <tr> 
   <td> 終了したプロファイル<br/> </td> 
   <td> 旅に出た人物の合計数です。<br/> </td> 
</tr> 
  <tr> 
   <td> 個々の旅に失敗<br/> </td> 
   <td> 正常に実行されなかった個々の journeys の合計数。<br/> </td> 
</tr> 
 </tbody> 
</table>

### 電子メールと SMS メトリック {#email-and-sms-metrics}

<table> 
 <thead> 
  <tr> 
   <th> 指標<br/> </th> 
   <th> 精細<br/> </th> 
</tr>
 </thead> 
 <tbody>
  <tr> 
   <td> バウンス<br/> </td> 
   <td> 配信中に発生したエラーの合計数が、送信メッセージの総数に対する相対処理で累積されます。<br/> </td> 
</tr> 
  <tr> 
   <td> バウンスレート<br/> </td> 
   <td> 送信された電子メールのうち、送信された電子メールのパーセンテージです。<br/> </td> 
</tr>
  <tr> 
   <td> が<br/> </td> 
   <td> 電子メールのコンテンツがクリックされた回数です。<br/> </td> 
</tr> 
  <tr> 
   <td> 有益 <br/> </td> 
   <td> 送信されたメッセージの合計数を基準として、送信されたメッセージの数を指定します。<br/></td> 
</tr> 
  <tr> 
   <td> 配信レート<br/> </td> 
   <td> 送信が成功したメッセージの割合。<br/> </td> 
</tr>
  <tr> 
   <td> 誤り<br/> </td> 
   <td> 配布中に発生したエラーのうち、プロファイルに送信されていないエラーの合計数です。<br/> </td> 
</tr> 
  <tr> 
   <td> エラーレート<br/> </td> 
   <td> 配信中に発生したエラーのうち、送信された電子メールと比較して送信されたものを防ぐことができます。<br/> </td> 
</tr>
  <tr> 
   <td> 対象<br/> </td> 
   <td> Adobe の旅オプティマイザーによって除外されたプロファイルの数です。<br/> </td> 
</tr>
  <tr> 
   <td> ハードバウンス<br/> </td> 
   <td> 電子メールアドレスが間違っているなどの永続的なエラーの合計数です。 これには、不明なユーザーなど、アドレスが無効であることを示すエラーメッセージが表示されます。<br/> </td>
</tr>
  <tr> 
   <td> れる<br/> </td> 
   <td> 不在時のような一時的な合計数、または送信者の種類がポストマスターである場合などの技術的なエラー。<br/> </td> 
</tr>
   <tr> 
   <td>クリックレートを提供<br/> </td> 
   <td>このオファーを使用して相互に連携した場合のユーザー数。<br/> </td> 
</tr>
   <tr> 
   <td>インプレッションレートの提供<br/> </td> 
   <td>「送信されたキャンペーンの数」と比較した場合の、オープンな割引率。<br/> </td> 
</tr>
   <tr> 
   <td>オファー名<br/> </td> 
   <td> 出荷に追加された申し出の名前。 配置について詳しくは、この <a href="../offers/offer-library/creating-personalized-offers.md"> ページ </a> を参照してください。<br/> </td> 
</tr>
   <tr> 
   <td>送信された申し出<br/> </td> 
   <td>申し出の合計数。<br/> </td> 
</tr> 
  <tr>
   <td>開い<br/> </td> 
   <td> メッセージが開かれた回数を指定します。<br/> </td> 
</tr> 
  <tr> 
   <td> オープンレート<br/> </td> 
   <td> 配信された電子メールの数と比較して開かれた電子メールの合計数。<br/> </td> 
</tr>
  <tr> 
   <td>配置名<br/> </td> 
   <td> 申し出を表示するために使用した位置の名前を指定します。 配置について詳しくは、この <a href="../offers/offer-library/creating-placements.md"> ページ </a> を参照してください。 </td> 
</tr> 
  <tr> 
   <td> 再送<br/> </td> 
   <td> 再生待ちのキューにある電子メールの数です。<br/> </td> 
</tr> 
  <tr> 
   <td> 送り<br/> </td> 
   <td> 配信に使用された送信の合計数です。<br/> </td> 
</tr>
  <tr> 
   <td> ソフトバウンス<br/> </td> 
   <td> 完全な受信ボックスなど、一時的なエラーの合計数です。<br/> </td> 
</tr>
  <tr> 
   <td> スパムの苦情<br/> </td> 
   <td> メッセージがスパムまたは迷惑メールとして宣言された回数を指定します。<br/> </td> 
</tr>
  <tr> 
   <td> 絞り<br/> </td> 
   <td> 配信分析中に処理されたメッセージの合計数。<br/> </td> 
</tr> 
  <tr> 
   <td> ユニークなクリック回数<br/> </td> 
   <td> 電子メールのコンテンツをクリックした受取人の数です。<br/> </td> 
</tr> 
  <tr> 
   <td>一意のクリックレート<br/> </td> 
   <td> 配信によって対話したユーザーの数です。<br/> </td> 
</tr>
  <tr> 
   <td> 一意の開き<br/> </td> 
   <td>配信を開いた受信者の数です。<br/> </td> 
</tr> 
  <tr> 
   <td> 非定期購入<br/> </td> 
   <td> Unsubscription リンクのクリック回数<br/> </td> 
</tr> 
 </tbody> 
</table>

<!--
### Experimentation metrics {#experimentation-metrics}
<table> 
 <thead> 
  <tr> 
   <th> Metric<br/> </th> 
   <th> Definition<br/> </th> 
</tr>
 </thead> 
 <tbody>
  <tr> 
   <td>App installs<br/> </td> 
   <td><br/> </td> 
</tr>
  <tr> 
   <td>App launches<br/> </td> 
   <td><br/> </td> 
</tr>
 <tr> 
   <td>Average lift<br/> </td> 
   <td> Percentage improvement in conversion rate of a given treatment over the baseline.<a href="../campaigns/experiment-calculations.md#understand-lift">Learn more</a>.<br/> </td> 
  </tr>
  <tr> 
   <td>Confidence<br/> </td> 
   <td>Evidence that a given treatment is the same as the baseline treatment. <a href="../campaigns/experiment-calculations.md#understand-confidence">Learn more</a>.<br/> </td> 
</tr>
  <tr> 
   <td>Confidence interval<br/> </td> 
   <td>Percentage difference in performance between the baseline and the best performing treatment. <a href="../campaigns/experiment-calculations.md#understand-intervals">Learn more</a>.<br/> </td> 
</tr> 
  <tr> 
   <td>Count per profile<br/> </td> 
   <td>Total value of the Experiment objective metric divided by the number of profiles.<br/> </td> 
</tr>
  <tr> 
   <td>Email Opens<br/> </td> 
   <td>.<br/> </td> 
</tr>
  <tr> 
   <td>Email Unsubscribes<br/> </td> 
   <td><br/> </td> 
</tr>
  <tr> 
   <td>First app launches<br/> </td> 
   <td><br/> </td> 
</tr>
  <tr> 
   <td>Outbound Clicks<br/> </td> 
   <td><br/> </td> 
</tr>
  <tr> 
   <td>Profiles<br/> </td> 
   <td>Number of profiles targeted for this treatment.<br/> </td> 
</tr>
  <tr> 
   <td>Unique email opens<br/> </td> 
   <td><br/> </td>
<tr>
  <tr> 
   <td>Unique email unsubscribes<br/> </td> 
   <td><br/> </td>
</tr>
  <tr> 
   <td>Unique installs<br/> </td> 
   <td><br/> </td> 
</tr>
  <tr> 
   <td>Unique launches<br/> </td> 
   <td><br/> </td> 
</tr> 
  <tr> 
   <td>Unique outbound clicks<br/> </td> 
   <td><br/> </td> 
</tr>
  <tr> 
   <td>Unique upgrades<br/> </td> 
   <td><br/> </td> 
</tr>
   <td>Upgrades<br/> </td> 
   <td><br/> </td> 
</tr> 
</tbody> 
</table>
-->

### プッシュ通知メトリック

<table> 
 <thead> 
  <tr> 
   <th> 指標<br/> </th> 
   <th> 精細<br/> </th> 
</tr>
 </thead> 
 <tbody>
 <tr> 
   <td>活動<br/> </td> 
   <td> プッシュ通知で配信されたアクションの合計数 (例: ボタンクリック dismissal)。<br/> </td> 
</tr>
  <tr> 
   <td>バウンス<br/> </td> 
   <td> 配信中に発生したエラーの合計数が、送信メッセージの総数に対する相対処理で累積されます。<br/> </td> 
</tr> 
  <tr> 
   <td> バウンスレート<br/> </td> 
   <td> プッシュ通知が送信されたときにバウンスされたプッシュ通知の割合。<br/> </td>
</tr>
  <tr> 
   <td> 有益<br/> </td> 
   <td> 送信されたメッセージの合計数を基準として、送信されたメッセージの数を指定します。<br/> </td> 
</tr> 
  <tr> 
   <td> 配信レート<br/> </td> 
   <td> 送信が成功したプッシュ通知の割合。<br/> </td> 
</tr>
  <tr> 
   <td>幅広く<br/> </td> 
   <td> このプッシュ通知のオープン数とアクション数の合計。つまり、プロファイルがプッシュを開いたか、ボタンがクリックされた場合に表示されます。<br/> </td> 
</tr> 
  <tr> 
   <td> 契約レート<br/> </td> 
   <td> このプッシュ通知のオープン数とアクション数、つまり、プロファイルがプッシュを開いたか、ボタンがクリックされたかどうか。<br/> </td> 
</tr>
  <tr> 
   <td> 誤り<br/> </td> 
   <td> 配布中に発生したエラーのうち、プロファイルに送信されていないエラーの合計数です。<br/> </td> 
</tr>
  <tr> 
   <td> エラーレート<br/> </td> 
   <td> 配信中に発生したエラーのうち、プッシュ通知が送信されたときに発生したエラーに対する割合です。<br/> </td> 
</tr> 
  <tr> 
   <td> 対象<br/> </td> 
   <td> Adobe の旅オプティマイザーによって除外されたプロファイルの数です。<br/> </td> 
</tr>
  <tr> 
   <td> 開い<br/> </td> 
   <td> デバイスに配信され、ユーザーによって選択されたプッシュ通知の合計数です。これにより、アプリケーションが開かれます。 これは、通知が閉じられたときにプッシュが実行されることはありませんが、プッシュクリックと似ています。<br/> </td> 
</tr> 
  <tr> 
   <td> オープンレート<br/> </td> 
   <td> 開かれたプッシュ通知の割合。<br/> </td> 
</tr> 
  <tr> 
   <td> 送り<br/> </td> 
   <td> 配信に使用された送信の合計数です。<br/> </td> 
</tr> 
  <tr> 
   <td> 絞り<br/> </td> 
   <td> 配信分析中に処理されたプッシュメッセージ数の合計です。<br/> </td> 
</tr>  
 </tbody> 
</table>

### ランディングページのメトリックス {#landing-page-metrics}

<table> 
 <thead> 
  <tr> 
   <th> 指標<br/> </th> 
   <th> 精細<br/> </th> 
</tr>
 </thead> 
 <tbody>
 <tr> 
  <td>バウンス<br/> </td> 
   <td>着陸ページを操作せず、購読の操作を完了していない人物の人数<br/> </td> 
</tr>
 <tr> 
   <td>バウンスレート<br/> </td> 
   <td>ランディングページにアクセスしていない場合や、訪問数に関係なく、サブスクライビング操作を完了していない人物の数です。<br/> </td> 
</tr>
 <tr>
  <tr> 
   <td>が<br/> </td> 
   <td>コンテンツがクリックされたときのランディングページの回数です。<br/> </td> 
</tr>
 <tr> 
   <td>「レート」をクリックします。<br/> </td> 
   <td>ランディングページのクリックに対する割合です。<br/> </td>
</tr>
<tr>
<td>処理<br/> </td> 
   <td>ランディングページを使用して相互に連携していた人数 (例: フォームの購読)<br/> </td> 
</tr>
<tr>
   <td>変換レート<br/> </td> 
   <td>1つのフォームを購読し、訪問数の合計数に対するジャンプページを使用した人物の数。<br/> </td> 
</tr>
 <tr> 
   <td>旅<br/> </td> 
   <td>1つの旅に出たジャンプページへの訪問数です。<br/> </td> 
</tr>
 <tr> 
   <td>その他のソース<br/> </td> 
   <td>外部ソースから読み込まれたランディングページにジャンプするのではなく、ジャンプページへの訪問数を指定します。<br/> </td> 
</tr>
 <tr> 
   <td>合計訪問数<br/> </td> 
   <td> Journeys および外部ソースから読み込まれたランディングページへの訪問数の合計です。1つの受信者の複数の訪問が含まれています。<br/> </td> 
</tr>
 <tr> 
   <td>ユニークビジター<br/> </td> 
   <td>待ち受けページを訪問した人物は、1人の受信者に複数回訪問することは考慮されません。<br/> </td> 
</tr>
 <tr> 
   <td>同<br/> </td> 
   <td>1つの受信者に複数の訪問がある場合を含め、ジャンプページへの訪問数です。<br/> </td> 
</tr>
 </tbody> 
</table>

### プッシュ通知メトリック

<table> 
 <thead> 
  <tr> 
   <th> 指標<br/> </th> 
   <th> 精細<br/> </th> 
</tr>
 </thead> 
 <tbody>
 <tr> 
   <td>活動<br/> </td> 
   <td> プッシュ通知で配信されたアクションの合計数 (例: ボタンクリック dismissal)。<br/> </td> 
</tr>
  <tr> 
   <td>バウンス<br/> </td> 
   <td> 配信中に発生したエラーの合計数が、送信メッセージの総数に対する相対処理で累積されます。<br/> </td> 
</tr> 
  <tr> 
   <td> バウンスレート<br/> </td> 
   <td> プッシュ通知が送信されたときにバウンスされたプッシュ通知の割合。<br/> </td>
</tr>
  <tr> 
   <td> 有益<br/> </td> 
   <td> 送信されたメッセージの合計数を基準として、送信されたメッセージの数を指定します。<br/> </td> 
</tr> 
  <tr> 
   <td> 配信レート<br/> </td> 
   <td> 送信が成功したプッシュ通知の割合。<br/> </td> 
</tr>
  <tr> 
   <td>幅広く<br/> </td> 
   <td> このプッシュ通知のオープン数とアクション数の合計。つまり、プロファイルがプッシュを開いたか、ボタンがクリックされた場合に表示されます。<br/> </td> 
</tr> 
  <tr> 
   <td> 契約レート<br/> </td> 
   <td> このプッシュ通知のオープン数とアクション数、つまり、プロファイルがプッシュを開いたか、ボタンがクリックされたかどうか。<br/> </td> 
</tr>
  <tr> 
   <td> 誤り<br/> </td> 
   <td> 配布中に発生したエラーのうち、プロファイルに送信されていないエラーの合計数です。<br/> </td> 
</tr>
  <tr> 
   <td> エラーレート<br/> </td> 
   <td> 配信中に発生したエラーのうち、プッシュ通知が送信されたときに発生したエラーに対する割合です。<br/> </td> 
</tr> 
  <tr> 
   <td> 対象<br/> </td> 
   <td> Adobe の旅オプティマイザーによって除外されたプロファイルの数です。<br/> </td> 
</tr>
  <tr> 
   <td> 開い<br/> </td> 
   <td> デバイスに配信され、ユーザーによって選択されたプッシュ通知の合計数です。これにより、アプリケーションが開かれます。 これは、通知が閉じられたときにプッシュが実行されることはありませんが、プッシュクリックと似ています。<br/> </td> 
</tr> 
  <tr> 
   <td> オープンレート<br/> </td> 
   <td> 開かれたプッシュ通知の割合。<br/> </td> 
</tr> 
  <tr> 
   <td> 送り<br/> </td> 
   <td> 配信に使用された送信の合計数です。<br/> </td> 
</tr> 
  <tr> 
   <td> 絞り<br/> </td> 
   <td> 配信分析中に処理されたプッシュメッセージ数の合計です。<br/> </td> 
</tr>  
 </tbody> 
</table>

<!--
### In-app metrics {#inapp-metrics}
<table> 
 <thead> 
  <tr> 
   <th> Metric<br/> </th> 
   <th> Definition<br/> </th> 
</tr>
 </thead> 
 <tbody>
 <tr> 
   <td>Clicks<br/> </td> 
   <td>Total number of recipients who interacted with the buttons included in the In-app message.<br/> </td> 
</tr>
  <tr> 
   <td>Click rate<br/> </td> 
   <td>Percentage of users who interacted with the buttons included in the In-app message compared to users who saw the message.<br/> </td> 
</tr> 
  <tr> 
   <td>Dismiss rate<br/> </td> 
   <td> Percentage of In-app messages that recipients dismissed.<br/> </td> 
</tr> 
  <tr> 
   <td>Impressions<br/> </td> 
   <td> Total number of In-app messages delivered to all users.<br/> </td>
</tr>
  <tr> 
   <td>Unique impressions<br/> </td> 
   <td>Number of unique users to whom the In-app message was delivered.<br/> </td>
</tr>
 </tbody> 
</table>
-->
