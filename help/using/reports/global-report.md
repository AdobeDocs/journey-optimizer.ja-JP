---
solution: Journey Optimizer
product: journey optimizer
title: グローバルレポート
description: グローバルレポートのデータの使い方を学ぶ
feature: Reporting
topic: Content Management
role: User
level: Intermediate
exl-id: ec15e700-7659-4dbf-8446-6534ea48c5c8
source-git-commit: e7431d1b69e460471b01439c9bd2577fd69944ed
workflow-type: tm+mt
source-wordcount: '1441'
ht-degree: 100%

---

# グローバルレポートの基本を学ぶ {#global-report}

>[!NOTE]
>
> クエリサービスを使用する際に API を通じてカスタムクエリを作成すると、レポートに多少の遅延が生じる可能性があります。

**[!UICONTROL グローバルレポート]**&#x200B;を使用すると、選択した期間におけるジャーニーと配信の効果を測定できます。

* ジャーニーまたはジャーニーのコンテキストの配信をターゲットする場合は、**[!UICONTROL ジャーニー]**&#x200B;メニューからジャーニーにアクセスし、「**[!UICONTROL レポートを表示]**」ボタンをクリックします。そうすれば、ジャーニー、メール、SMS およびプッシュの各グローバルレポートが見つかります。

   ![](assets/report_journey.png)

* キャンペーンをターゲットにする場合は、**[!UICONTROL キャンペーン]**&#x200B;メニューからキャンペーンにアクセスし、「**[!UICONTROL レポート]**」ボタンをクリックします。

   ![](assets/report_campaign.png)

* 配信を&#x200B;**[!UICONTROL ライブレポート]**&#x200B;から&#x200B;**[!UICONTROL グローバルレポート]**&#x200B;に切り替える場合は、タブスイッチャーで「**[!UICONTROL すべての時間]**」をクリックします。

   ![](assets/report_5.png)

Adobe Journey Optimizer で使用可能なすべての指標の詳細なリストについては、[このページ](#list-of-components-global)を参照してください。

## ダッシュボードのカスタマイズ {#modify-dashboard}

各レポートダッシュボードは、期間を変更し、ウィジェットのサイズを変更または削除することで変更できます。ウィジェットを変更して影響を受けるのは、現在のユーザーのダッシュボードのみです。他のユーザーには、各自のダッシュボードまたはデフォルトで設定されたダッシュボードが表示されます。

1. グローバルレポートから、開始および終了時間を選択して特定のデータをターゲットにします。

   ![](assets/report_modify_1.png)

1. 切り替えバーを使用して、レポートからテストイベントを除外する場合に選択します。テストイベントについて詳しくは、[このページ](../building-journeys/testing-the-journey.md)を参照してください。

   「**[!UICONTROL テストイベントの除外]**」オプションは、ジャーニーレポートでしか使用できません。

   ![](assets/report_modify_2.png)

1. 「**[!UICONTROL 変更]**」をクリックして、ダッシュボードのカスタマイズを開始します。

   ![](assets/report_modify_3.png)

1. ウィジェットの右下隅をドラッグして、ウィジェットのサイズを調整します。

   ![](assets/report_modify_4.png)

1. 「**[!UICONTROL 削除]**」をクリックして、不要なウィジェットを削除します。

   ![](assets/report_modify_5.png)

1. ウィジェットの表示順とサイズが定まったら、「**[!UICONTROL 保存]**」をクリックします。

ダッシュボードが保存されました。様々な変更は、後でライブレポートを使用する際にも再度適用されます。必要に応じて、「**[!UICONTROL リセット]**」オプションを使用して、デフォルトのウィジェットとそれらのデフォルト順序に戻します。

## コンポーネントのリスト {#list-of-components-global}

次の表に、レポートで使用される指標のリストと、配信タイプに応じた定義を示します。

### ジャーニー指標 {#journey-metrics}

<table> 
 <thead> 
  <tr> 
   <th> 指標<br/> </th> 
   <th> 定義<br/> </th> 
</tr>
 </thead> 
 <tbody> 
  <tr> 
   <td>正常に実行されたアクション<br/> </td> 
   <td> ジャーニーで正常に実行されたアクションの合計数。<br/> </td> 
</tr> 
  <tr> 
   <td> エントリしたプロファイル<br/> </td> 
   <td> ジャーニーのエントリイベントに到達した個人の合計数。<br/> </td> 
</tr>
  <tr> 
   <td> アクションのエラー<br/> </td> 
   <td>アクションで発生したエラーの合計数。<br/> </td> 
</tr> 
  <tr> 
   <td> 退出したプロファイル<br/> </td> 
   <td> ジャーニーから退出した個人の合計数。<br/> </td> 
</tr> 
  <tr> 
   <td> 失敗した個人のジャーニー<br/> </td> 
   <td> 正常に実行されなかった個人のジャーニーの合計数。<br/> </td> 
</tr> 
 </tbody> 
</table>

### メールと SMS の指標 {#email-and-sms-metrics}

<table> 
 <thead> 
  <tr> 
   <th> 指標<br/> </th> 
   <th> 定義<br/> </th> 
</tr>
 </thead> 
 <tbody>
  <tr> 
   <td> バウンス<br/> </td> 
   <td> 送信されたメッセージの総数に対して、配信と自動返信の処理中に発生したエラーの累計。<br/> </td> 
</tr> 
  <tr> 
   <td> バウンス率<br/> </td> 
   <td> 送信メールに対するバウンスメールの割合。<br/> </td> 
</tr>
  <tr> 
   <td> クリック数<br/> </td> 
   <td> メールのコンテンツがクリックされた回数。<br/> </td> 
</tr> 
  <tr> 
   <td> 配信済み <br/> </td> 
   <td> 送信されたメッセージの総数に対して、正常に送信されたメッセージの数。<br/></td> 
</tr> 
  <tr> 
   <td> 配信率<br/> </td> 
   <td> 正常に送信されたメッセージの割合。<br/> </td> 
</tr>
  <tr> 
   <td> エラー<br/> </td> 
   <td> 配信中に発生し、プロファイルに送信できなかったエラーの合計数。<br/> </td> 
</tr> 
  <tr> 
   <td> エラー率<br/> </td> 
   <td> 送信されたメールに対して、配信中にエラーが発生して送信できなかったメールの割合。<br/> </td> 
</tr>
  <tr> 
   <td> 除外済み<br/> </td> 
   <td> Adobe Journey Optimizer によって除外されたプロファイルの数。<br/> </td> 
</tr>
  <tr> 
   <td> ハードバウンス<br/> </td> 
   <td> 永続的なエラー（メールアドレスの間違いなど）の合計数。このエラーは、アドレスが無効であることを明示的に示すエラーメッセージ（例：「不明なユーザー」）を伴います。<br/> </td>
</tr>
  <tr> 
   <td> 無視<br/> </td> 
   <td> 一時的なエラー（不在など）や技術的なエラー（送信者のタイプが postmaster の場合など）の合計数。<br/> </td> 
</tr>
   <tr> 
   <td>オファークリック率<br/> </td> 
   <td>オファーに対してインタラクションを行ったユーザーの割合。<br/> </td> 
</tr>
   <tr> 
   <td>オファーのインプレッション率<br/> </td> 
   <td>送信されたオファーの数に対する、開封されたオファーの割合。<br/> </td> 
</tr>
   <tr> 
   <td>オファー名<br/> </td> 
   <td> 配信に追加されたオファーの名前。プレースメントについて詳しくは、この<a href="../offers/offer-library/creating-personalized-offers.md">ページ</a>を参照してください。<br/> </td> 
</tr>
   <tr> 
   <td>送信されたオファー<br/> </td> 
   <td>オファーの送信の総数。<br/> </td> 
</tr> 
  <tr>
   <td>開封数<br/> </td> 
   <td> メッセージが開封された回数。<br/> </td> 
</tr> 
  <tr> 
   <td> 開封率<br/> </td> 
   <td> 配信されたメール数に対する、開封されたメールの総数の割合。<br/> </td> 
</tr>
  <tr> 
   <td>プレースメント名<br/> </td> 
   <td> オファーの表示に使用するプレースメントの名前。プレースメントについて詳しくは、この<a href="../offers/offer-library/creating-placements.md">ページ</a>を参照してください。 </td> 
</tr> 
  <tr> 
   <td> 再試行<br/> </td> 
   <td> 再試行のキュー内のメール数。<br/> </td> 
</tr> 
  <tr> 
   <td> 送信済み<br/> </td> 
   <td> 配信の送信の合計数。<br/> </td> 
</tr>
  <tr> 
   <td> ソフトバウンス<br/> </td> 
   <td> 一時的なエラー（インボックスがいっぱいであるなど）の合計数。<br/> </td> 
</tr>
  <tr> 
   <td> スパムの苦情数<br/> </td> 
   <td> メッセージがスパムまたはジャンクとして宣言された回数。<br/> </td> 
</tr>
  <tr> 
   <td> ターゲット<br/> </td> 
   <td> 配信の分析中に処理されたメッセージの合計数。<br/> </td> 
</tr> 
  <tr> 
   <td> ユニーククリック数<br/> </td> 
   <td> メールのコンテンツをクリックした受信者の数。<br/> </td> 
</tr> 
  <tr> 
   <td>ユニーククリック率<br/> </td> 
   <td> 配信とインタラクションを行ったユーザーの割合。<br/> </td> 
</tr>
  <tr> 
   <td> ユニーク開封数<br/> </td> 
   <td>配信を開いた受信者の数。<br/> </td> 
</tr> 
  <tr> 
   <td> 購読解除<br/> </td> 
   <td> 購読解除リンクがクリックされた回数。<br/> </td> 
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

### プッシュ通知指標 {#push-notification-metrics}

<table> 
 <thead> 
  <tr> 
   <th> 指標<br/> </th> 
   <th> 定義<br/> </th> 
</tr>
 </thead> 
 <tbody>
 <tr> 
   <td>アクション<br/> </td> 
   <td> 配信されたプッシュ通知に対するアクション（ボタンのクリックや解除など）の合計数。<br/> </td> 
</tr>
  <tr> 
   <td>バウンス<br/> </td> 
   <td> 送信されたメッセージの総数に対して、配信と自動返信の処理中に発生したエラーの累計。<br/> </td> 
</tr> 
  <tr> 
   <td> バウンス率<br/> </td> 
   <td> 送信されたプッシュ通知と比較した、バウンスしたプッシュ通知の割合。<br/> </td>
</tr>
  <tr> 
   <td> 配信済み<br/> </td> 
   <td> 送信されたメッセージの総数に対する、正常に送信されたメッセージの数。<br/> </td> 
</tr> 
  <tr> 
   <td> 配信率<br/> </td> 
   <td> 正常に送信されたプッシュ通知の割合。<br/> </td> 
</tr>
  <tr> 
   <td>エンゲージメント<br/> </td> 
   <td> このプッシュ通知に対する開封数とアクション数（プロファイルによるプッシュの開封や、ボタンのクリックなど）の合計。<br/> </td> 
</tr> 
  <tr> 
   <td> エンゲージメント率<br/> </td> 
   <td> このプッシュ通知の開封とアクションの割合（プロファイルによるプッシュの開封や、ボタンのクリックなど）。<br/> </td> 
</tr>
  <tr> 
   <td> エラー<br/> </td> 
   <td> 配信中に発生し、プロファイルに送信できなかったエラーの合計数。<br/> </td> 
</tr>
  <tr> 
   <td> エラー率<br/> </td> 
   <td> 送信済みのプッシュ通知に対する、配信中に発生して送信の妨げとなったエラーの割合。<br/> </td> 
</tr> 
  <tr> 
   <td> 除外済み<br/> </td> 
   <td> Adobe Journey Optimizer によって除外されたプロファイルの数。<br/> </td> 
</tr>
  <tr> 
   <td> 開封数<br/> </td> 
   <td> デバイスに配信され、ユーザーがクリックしてアプリを起動したプッシュ通知の合計数。これは、プッシュクリックと似ていますが、通知が閉じられた場合にプッシュオープンがトリガーされない点が異なります。<br/> </td> 
</tr> 
  <tr> 
   <td> 開封率<br/> </td> 
   <td> 開封されたプッシュ通知の割合。<br/> </td> 
</tr> 
  <tr> 
   <td> 送信済み<br/> </td> 
   <td> 配信に対する送信の合計数。<br/> </td> 
</tr> 
  <tr> 
   <td> ターゲット<br/> </td> 
   <td> 配信の分析中に処理されたプッシュメッセージの合計数。<br/> </td> 
</tr>  
 </tbody> 
</table>

### ランディングページの指標 {#landing-page-metrics}

<table> 
 <thead> 
  <tr> 
   <th> 指標<br/> </th> 
   <th> 定義<br/> </th> 
</tr>
 </thead> 
 <tbody>
 <tr> 
  <td>バウンス<br/> </td> 
   <td>ランディングページでインタラクションを行わず、購読のアクションを完了しなかったユーザーの数。<br/> </td> 
</tr>
 <tr> 
   <td>バウンス率<br/> </td> 
   <td>訪問の合計回数に対する、ランディングページでインタラクションを起こさず、購読のアクションを完了していない人数の割合。<br/> </td> 
</tr>
 <tr>
  <tr> 
   <td>クリック数<br/> </td> 
   <td>ランディングページでコンテンツがクリックされた回数。<br/> </td> 
</tr>
 <tr> 
   <td>クリック率<br/> </td> 
   <td>ランディングページでのクリック率。<br/> </td>
</tr>
<tr>
<td>コンバージョン<br/> </td> 
   <td>ランディングページでインタラクション（フォームの購読など）を行ったユーザーの数。<br/> </td> 
</tr>
<tr>
   <td>コンバージョン率<br/> </td> 
   <td>訪問の合計回数に対する、ランディングページでインタラクション（フォームの購読など）を起こした人数の割合。<br/> </td> 
</tr>
 <tr> 
   <td>ジャーニー<br/> </td> 
   <td>ジャーニーからのランディングページへの訪問回数。<br/> </td> 
</tr>
 <tr> 
   <td>その他のソース<br/> </td> 
   <td>ジャーニーではなく外部ソースからのランディングページへの訪問回数。<br/> </td> 
</tr>
 <tr> 
   <td>合計訪問回数<br/> </td> 
   <td> ジャーニーまたは外部ソースからのランディングページに訪問した合計回数（1 人の受信者が複数回訪問した場合を含みます）。<br/> </td> 
</tr>
 <tr> 
   <td>ユニーク訪問者<br/> </td> 
   <td>ランディングページを訪問した人数。1 人の受信者が複数回訪問しても、それは考慮されません。<br/> </td> 
</tr>
 <tr> 
   <td>訪問回数<br/> </td> 
   <td>ランディングページへの訪問回数（1 人の受信者による複数回の訪問を含みます）。<br/> </td> 
</tr>
 </tbody> 
</table>

### プッシュ通知指標 {#push-notification-metrics}

<table> 
 <thead> 
  <tr> 
   <th> 指標<br/> </th> 
   <th> 定義<br/> </th> 
</tr>
 </thead> 
 <tbody>
 <tr> 
   <td>アクション<br/> </td> 
   <td> 配信されたプッシュ通知に対するアクション（ボタンのクリックや解除など）の合計数。<br/> </td> 
</tr>
  <tr> 
   <td>バウンス<br/> </td> 
   <td> 送信されたメッセージの総数に対して、配信と自動返信の処理中に発生したエラーの累計。<br/> </td> 
</tr> 
  <tr> 
   <td> バウンス率<br/> </td> 
   <td> 送信されたプッシュ通知と比較した、バウンスしたプッシュ通知の割合。<br/> </td>
</tr>
  <tr> 
   <td> 配信済み<br/> </td> 
   <td> 送信されたメッセージの総数に対する、正常に送信されたメッセージの数。<br/> </td> 
</tr> 
  <tr> 
   <td> 配信率<br/> </td> 
   <td> 正常に送信されたプッシュ通知の割合。<br/> </td> 
</tr>
  <tr> 
   <td>エンゲージメント<br/> </td> 
   <td> このプッシュ通知に対する開封数とアクション数（プロファイルによるプッシュの開封や、ボタンのクリックなど）の合計。<br/> </td> 
</tr> 
  <tr> 
   <td> エンゲージメント率<br/> </td> 
   <td> このプッシュ通知の開封とアクションの割合（プロファイルによるプッシュの開封や、ボタンのクリックなど）。<br/> </td> 
</tr>
  <tr> 
   <td> エラー<br/> </td> 
   <td> 配信中に発生し、プロファイルに送信できなかったエラーの合計数。<br/> </td> 
</tr>
  <tr> 
   <td> エラー率<br/> </td> 
   <td> 送信済みのプッシュ通知に対する、配信中に発生して送信の妨げとなったエラーの割合。<br/> </td> 
</tr> 
  <tr> 
   <td> 除外済み<br/> </td> 
   <td> Adobe Journey Optimizer によって除外されたプロファイルの数。<br/> </td> 
</tr>
  <tr> 
   <td> 開封数<br/> </td> 
   <td> デバイスに配信され、ユーザーがクリックしてアプリを起動したプッシュ通知の合計数。これは、プッシュクリックと似ていますが、通知が閉じられた場合にプッシュオープンがトリガーされない点が異なります。<br/> </td> 
</tr> 
  <tr> 
   <td> 開封率<br/> </td> 
   <td> 開封されたプッシュ通知の割合。<br/> </td> 
</tr> 
  <tr> 
   <td> 送信済み<br/> </td> 
   <td> 配信に対する送信の合計数。<br/> </td> 
</tr> 
  <tr> 
   <td> ターゲット<br/> </td> 
   <td> 配信の分析中に処理されたプッシュメッセージの合計数。<br/> </td> 
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
