---
solution: Journey Optimizer
product: journey optimizer
title: コンポーネントのリスト
description: ライブレポートのデータの使用方法について説明します。
feature: Reporting
topic: Content Management
role: User
level: Intermediate
exl-id: 12168cdf-f517-49b5-958b-ba689ade6982
source-git-commit: 428e08ca712724cb0b3453681bee1c7e86ce49dc
workflow-type: ht
source-wordcount: '775'
ht-degree: 100%

---

# コンポーネントのリスト {#list-of-components-live}

>[!AVAILABILITY]
>
>現在のレポートエクスペリエンスは、10 月リリースの時点で廃止されます。この日以降、新しいレポートエクスペリエンスが標準となります。スムーズに移行できるように、新機能を理解しておくことをお勧めします。[Journey Optimizer の新しいレポートインターフェイスの基本を学ぶ。](report-gs-cja.md)

次の表に、レポートで使用される指標のリストと、配信タイプに応じた定義を示します。

## ジャーニー指標 {#journey-metrics}

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

## メールおよび SMS のディメンションと指標 {#email-and-sms-metrics}

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
   <td> 配信中および自動返信処理中のエラーの累計。<br/> </td> 
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
   <td> 正常に送信されたメッセージ数。<br/></td> 
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
   <td> 購読解除リンクのクリック数。<br/> </td> 
</tr> 
 </tbody> 
</table>

## ランディングページの指標 {#landing-page-metrics}

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
  <tr> 
   <td>クリック数<br/> </td> 
   <td>ランディングページでコンテンツがクリックされた回数。<br/> </td> 
</tr>
<tr>
<td>コンバージョン<br/> </td> 
   <td>ランディングページでインタラクション（フォームの購読など）を行ったユーザーの数。<br/> </td> 
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

## プッシュ通知指標 {#push-notification-metrics}

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
   <td> 配信中および自動返信処理中のエラーの累計。<br/> </td> 
</tr> 
  <tr> 
   <td> 配信済み<br/> </td> 
   <td> 正常に送信されたメッセージの数。<br/> </td> 
</tr> 
  <tr> 
   <td>エンゲージメント<br/> </td> 
   <td> このプッシュ通知に対する開封数とアクション数（プロファイルによるプッシュの開封や、ボタンのクリックなど）の合計。<br/> </td> 
</tr> 
  <tr> 
   <td> エラー<br/> </td> 
   <td> 配信中に発生し、プロファイルに送信できなかったエラーの合計数。<br/> </td> 
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
## In-app metrics {#inapp-metrics}
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
