---
solution: Journey Optimizer
product: journey optimizer
title: コンポーネントのリスト
description: レポートのデータの使用方法を学ぶ
feature: Reporting
topic: Content Management
role: User
level: Intermediate
exl-id: aa060d8e-23e2-4bab-b709-636077eb5d20
source-git-commit: 5849d1d52f3b1b075e804efbd3473d83cbac9fbe
workflow-type: tm+mt
source-wordcount: '1829'
ht-degree: 39%

---

# コンポーネントのリスト {#list-of-components-global}

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
<td>ジャーニーエンゲージメント</td> 
<td>ジャーニーを通じて送信されたメッセージを受信した一意の個人の合計数。ジャーニーの指定されたアクションポイントに到達した個別のプロファイルを表します。</td> 
</tr> 
<tr> 
<td>ジャーニーエントリ</td> 
<td>ジャーニーのエントリイベントに到達した個人の合計数。</td> 
</tr>
<tr> 
<td>ジャーニーが終了</td> 
<td>ジャーニーから退出した個人の合計数。</td> 
</tr>
<tr> 
<td>ジャーニーエラー</td> 
<td>正常に実行されなかった個人のジャーニーの合計数。</td> 
</tr>
<tr> 
<td>ユニークジャーニーエントリ数</td> 
<td>ジャーニーのエントリイベントに到達し、同じプロファイルの複数のインタラクションが考慮されない個人の合計数。</td> 
</tr>
<tr> 
<td>一意のジャーニー出口</td> 
<td>同じプロファイルでの複数のインタラクションは考慮されず、ジャーニーから退出した個人の合計数。</td> 
</tr>
<tr> 
<td>一意のジャーニーエラー</td> 
<td>同じプロファイルの複数のインタラクションが考慮されない中で、正常に実行されなかった個人のジャーニーの合計数。</td> 
</tr>
 </tbody> 
</table>

## メール指標 {#email-metrics}

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
   <td> 送信されたメッセージの合計数に対して、送信プロセスおよび自動返信処理の間に累積したエラーの合計数。<br/> </td> 
  </tr> 
  <tr> 
   <td> クリックスルー開封率（CTOR） <br/> </td> 
   <td> 電子メールが開封された回数。<br/> </td> 
  </tr>
  <tr> 
   <td> クリックスルー率（CTR） <br/> </td> 
   <td> メールでインタラクションを行ったユーザーの割合。<br/> </td> 
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
   <td> エラー理由<br/> </td> 
   <td> エラーの特定の元の原因名。<a href="exclusion-list.md">詳しくは、エラー理由を参照してください</a>。<br/> </td> 
  </tr>
  <tr> 
   <td> オファークリック率<br/> </td> 
   <td> オファーに対してインタラクションを行ったユーザーの割合。<br/> </td> 
  </tr>
  <tr> 
   <td> オファーのインプレッション率<br/> </td> 
   <td> 送信されたオファーの数に対する、開封されたオファーの割合。<br/> </td> 
  </tr>
  <tr> 
   <td> オファー名<br/> </td> 
   <td> 配信に追加されたオファーの名前。プレースメントについて詳しくは、この<a href="../offers/offer-library/creating-personalized-offers.md">ページ</a>を参照してください。<br/> </td> 
  </tr>
  <tr> 
   <td> 送信されたオファー<br/> </td> 
   <td> オファーの送信の総数。<br/> </td> 
  </tr> 
  <tr> 
   <td> 開封数<br/> </td> 
   <td> メッセージが開封された回数。<br/> </td> 
  </tr> 
  <tr> 
   <td> アウトバウンドエラー <br/> </td> 
   <td> 送信プロセス中に発生し、プロファイルへの送信の妨げとなったエラーの合計数。<br/> </td> 
  </tr> 
  <tr> 
   <td> アウトバウンド除外 <br/> </td> 
   <td> Adobe Journey Optimizer によって除外されたプロファイルの数。<br/> </td> 
  </tr>
  <tr> 
   <td> プレースメント名<br/> </td> 
   <td> オファーの表示に使用するプレースメントの名前。プレースメントについて詳しくは、この<a href="../offers/offer-library/creating-placements.md">ページ</a>を参照してください。 </td> 
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
   <td> メールのコンテンツをクリックしたプロファイルの数。<br> ユニーククリック数を計算する際は、過去 10 日間が考慮されます。あるプロファイルが 10 日以内に複数回のクリックを登録した場合、それらはユニーククリック数としてカウントされます。ただし、あるプロファイルが 10 日以上間隔をあけて 2 回クリックした場合、それらのクリックはユニーククリックとは見なされません。<br/> </td> 
  </tr>
  <tr> 
   <td> ユニークメール配信停止数 <br/> </td> 
   <td> メールの購読を解除したプロファイルの数。<br/> </td> 
  </tr>
  <tr> 
   <td> ユニーク開封数<br/> </td> 
   <td> 配信を開いたプロファイルの数。 <br> ユニーク開封数を計算する際には、過去 10 日間が考慮されます。あるプロファイルが 10 日以内に複数の開封数を登録した場合、それらはユニーク開封数としてカウントされます。ただし、あるプロファイルが 10 日以上間隔をあけて 2 回開封した場合、それらはユニーク開封とは見なされません。<br/> </td> 
  </tr> 
  <tr> 
   <td> 購読解除 <br/> </td> 
   <td> 購読解除リンクのクリック数。<br/> </td> 
  </tr> 
 </tbody> 
</table>

## SMS 指標

<table> 
  <thead> 
    <tr> 
      <th> SMS 指標 </th> 
      <th> 定義 </th> 
    </tr>
  </thead> 
  <tbody> 
    <tr> 
      <td>配信済み</td> 
      <td>SMS メッセージの合計数に対して、正常に送信された SMS メッセージの数。</td> 
    </tr>
    <tr> 
      <td>クリック数</td> 
      <td>SMS メッセージ内のリンクがクリックされた回数。</td> 
    </tr>
    <tr> 
      <td>アウトバウンド SMS メッセージのバウンス</td> 
      <td>送信プロセスおよび自動返信処理の間に、送信された SMS メッセージの合計数に関して蓄積されたエラーの合計数。</td> 
    </tr>
    <tr> 
      <td>アウトバウンド SMS エラー</td> 
      <td>発生し、SMS メッセージが受信者に送信できなかったエラーの合計数。</td> 
    </tr>
    <tr> 
      <td>アウトバウンド SMS の除外</td> 
      <td>Adobe Journey Optimizerによって SMS メッセージの受信から除外されたプロファイルの数。</td> 
    </tr>
    <tr> 
      <td>ユニーククリック数</td> 
      <td>SMS メッセージ内のリンクをクリックしたユニーク受信者の数。</td> 
    </tr>
    <tr> 
      <td>表示数</td> 
      <td>SMS メッセージが表示または開封された回数。</td> 
    </tr>
    <tr> 
      <td>ユニーク表示数</td> 
      <td>SMS メッセージを開いた一意の受信者の数（同じユーザーからの複数のインタラクションを除く）。</td> 
    </tr>
    <tr> 
      <td>People</td> 
      <td>SMS メッセージを受信または操作した一意のユーザープロファイルの数。</td> 
    </tr>
  </tbody> 
</table>

<!--
## Experimentation metrics {#experimentation-metrics}
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
   <td>Number of times the email was opened.<br/> </td> 
</tr>
  <tr> 
   <td>Email Unsubscribes<br/> </td> 
   <td>Number of clicks on the unsubscription link.<br/> </td> 
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
   <td>Number of profiles who opened the email.<br/> </td>
<tr>
  <tr> 
   <td>Unique email unsubscribes<br/> </td> 
   <td>Number of profiles who clicked on the unsubscription link.<br/> </td>
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

## アプリ内指標 {#inapp-metrics}

<table> 
 <thead> 
  <tr> 
   <th> 指標<br/> </th> 
   <th> 定義<br/> </th> 
  </tr>
 </thead> 
 <tbody>
  <tr> 
   <td>クリック数<br/> </td> 
   <td>アプリ内メッセージに含まれるボタンを操作したプロファイルの合計数。<br/> </td> 
  </tr>
  <tr> 
   <td>クリック率<br/> </td> 
   <td>メッセージを表示したユーザーと比較して、アプリ内メッセージに含まれるボタンを操作したユーザーの割合。<br/> </td> 
  </tr>
  <tr> 
   <td>解除率<br/> </td> 
   <td>プロファイルが解除されたアプリ内メッセージの割合。<br/> </td> 
  </tr>
  <tr> 
   <td>インプレッション<br/> </td> 
   <td>すべてのユーザーに配信されたアプリ内メッセージの合計数。<br/> </td>
  </tr>
  <tr> 
   <td>ユニークインプレッション数<br/> </td> 
   <td>アプリ内メッセージが配信されたユニークユーザーの数。<br/> </td>
  </tr>
  <tr> 
   <td>表示 <br/> </td>
   <td>アプリ内メッセージが開かれた回数。<br/> </td>
  </tr>
  <tr> 
   <td>ユニーク表示 <br/> </td>
   <td>同じプロファイルからの複数のインタラクションを除いて、アプリ内メッセージが開かれた回数。<br/> </td>
  </tr>
  <tr> 
   <td>ユニーククリック数<br/> </td>
   <td>アプリ内メッセージのコンテンツをクリックしたプロファイルの数。<br/> </td>
  </tr>
  <tr> 
   <td>クリック数<br/> </td>
   <td>アプリ内メッセージでコンテンツがクリックされた回数。<br/> </td>
  </tr>
  <tr> 
   <td>クリックスルー率（CTR） <br/> </td>
   <td>アプリ内メッセージを操作したユーザーの割合。<br/> </td>
  </tr>
  <tr> 
   <td>クリックスルー開封率（CTOR） <br/> </td>
   <td>アプリ内メッセージが開かれた回数。<br/> </td>
  </tr>
  <tr> 
   <td>送信数<br/> </td>
   <td>送信されたアプリ内メッセージの合計数。<br/> </td>
  </tr>
  <tr> 
   <td>インバウンドトリガー <br/> </td>
   <td>ユーザーのインタラクションまたは事前定義済みイベントによってアプリ内メッセージがトリガーされた回数。<br/> </td>
  </tr>
  <tr> 
   <td>インバウンド解除数 <br/> </td>
   <td>ユーザーがアプリ内メッセージを操作せずに解除した回数。<br/> </td>
  </tr>
 </tbody> 
</table>

## プッシュ通知指標

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
   <td> エラー理由<br/> </td> 
   <td> エラーの特定の元の原因名。<a href="exclusion-list.md">詳しくは、エラー理由を参照してください</a>。<br/> </td> 
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
   <td> プッシュカスタムアクション <br/> </td> 
   <td>プッシュ通知に応答してプロファイルが実行したカスタムアクションの数。<br/> </td> 
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
   <td>バウンス率<br/> </td> 
   <td>訪問の合計回数に対する、ランディングページを表示したが、インタラクションまたは購読を行わなかったユーザーの割合。<br/> </td> 
</tr>
 <tr> 
   <td>クリック数<br/> </td> 
   <td>ランディングページでコンテンツがクリックされた回数。<br/> </td> 
</tr>

<tr> 
   <td>ランディングページのコンバージョン <br/> </td> 
   <td>ランディングページでインタラクション（フォームの購読など）を行ったユーザーの数。<br/> </td> 
</tr>
<tr> 
   <td>ランディングページのコンバージョン率 <br/> </td> 
   <td>訪問の合計回数に対する、ランディングページでインタラクション（フォームの購読など）を起こしたユーザーの割合。<br/> </td> 
</tr>
 <tr> 
   <td>ランディングページビュー数 <br/> </td> 
   <td>ジャーニーまたは他のソースからランディングページを訪問した合計回数（同じプロファイルからの複数回の訪問を含む）。<br/> </td> 
</tr>
<tr> 
   <td>一意のランディングページのコンバージョン <br/> </td> 
   <td>ランディングページでインタラクションを行い、同じプロファイルからの複数のインタラクションを除いた一意のユーザーの数。<br/> </td> 
</tr>
 <tr> 
   <td>一意のランディングページビュー <br/> </td> 
   <td>ランディングページを訪問した一意のユーザーの数（同じプロファイルからの複数回の訪問を除く）。<br/> </td> 
</tr>
 </tbody> 
</table>

## ダイレクトメール {#direct-mail}

<table> 
 <thead> 
  <tr> 
   <th> 指標<br/> </th> 
   <th> 定義<br/> </th> 
  </tr>
 </thead> 
 <tbody>
<tr> 
   <td>配信済み<br/> </td> 
   <td>受信者に正常に配信されたダイレクトメールメッセージの数。<br/> </td> 
</tr>
<tr> 
   <td>アウトバウンドエラー <br/> </td> 
   <td>処理中または送信中にエラーが発生し、配信が成功しなかったダイレクトメールメッセージの数。<br/> </td> 
</tr>
<tr> 
   <td>アウトバウンド除外 <br/> </td> 
   <td>事前定義済みの条件またはAdobe Journey Optimizerによるフィルタリングが原因でダイレクトメールの受信から除外されたプロファイルの数。<br/> </td> 
</tr>
<tr> 
   <td>プロファイル<br/> </td> 
   <td>ダイレクトメールキャンペーンのターゲットオーディエンスとして識別されたユーザープロファイルの数。<br/> </td> 
</tr>
<tr> 
   <td>送信済み<br/> </td> 
   <td>キャンペーンの一部として正常に送信されたダイレクトメールメッセージの合計数。<br/> </td> 
</tr>
<tr> 
   <td>ターゲット<br/> </td> 
   <td>送信用に準備および処理されたダイレクトメールメッセージの合計数。<br/> </td> 
</tr>
 </tbody> 
</table>


## コンテンツカードの指標 {#content-based}

<table> 
 <thead> 
  <tr> 
   <th> 指標<br/> </th> 
   <th> 定義<br/> </th> 
  </tr>
 </thead> 
 <tbody>
<tr> 
   <td>クリックスルー率（CTR） <br/> </td> 
   <td>コンテンツカードを操作したユーザーの割合。<br/> </td> 
</tr>
<tr> 
   <td>クリック数<br/> </td> 
   <td>コンテンツカードでコンテンツがクリックされた回数。<br/> </td> 
</tr>
<tr> 
   <td>表示 <br/> </td> 
   <td>メッセージが開封された回数。<br/> </td> 
</tr>
<tr> 
   <td>人物 <br/> </td> 
   <td>コンテンツカードのターゲットプロファイルとして認定されるユーザープロファイルの数。<br/> </td> 
</tr>
<tr> 
   <td>ユニーククリック数<br/> </td> 
   <td>コンテンツカードのコンテンツをクリックしたプロファイルの数。<br/> </td> 
</tr>
<tr> 
   <td>ユニーク表示 <br/> </td> 
   <td>メッセージが開かれた回数。1 つのプロファイルの複数のインタラクションは考慮されません。<br/> </td> 
</tr>
 </tbody> 
</table>

## Web ページの指標 {#web}

<table> 
 <thead> 
  <tr> 
   <th> 指標<br/> </th> 
   <th> 定義<br/> </th> 
  </tr>
 </thead> 
 <tbody>
<tr> 
   <td>クリック数<br/> </td> 
   <td>Web ページでコンテンツがクリックされた回数。<br/> </td> 
</tr>
<tr> 
   <td>クリックスルー率（CTR） <br/> </td> 
   <td>Web ページを操作したユーザーの割合。<br/> </td> 
</tr>
<tr> 
   <td>表示 <br/> </td> 
   <td>Web ページが開かれた回数。<br/> </td> 
</tr>
<tr> 
   <td>人物 <br/> </td> 
   <td>Web ページのターゲットプロファイルとして認定されるプロファイルの数。<br/> </td> 
</tr>
<tr> 
   <td>ユニーククリック数<br/> </td> 
   <td>Web ページのコンテンツをクリックしたプロファイルの数。<br/> </td> 
</tr>
<tr> 
   <td>ユニーク表示 <br/> </td> 
   <td>Web ページが開かれ、1 つのプロファイルに対する複数のインタラクションが考慮されない回数。<br/> </td> 
</tr>
 </tbody> 
</table>

## コードベースのエクスペリエンス指標 {#code-based}

<table> 
 <thead> 
  <tr> 
   <th> 指標<br/> </th> 
   <th> 定義<br/> </th> 
  </tr>
 </thead> 
 <tbody>
<tr> 
   <td>クリック数<br/> </td> 
   <td>パーソナライズされたエクスペリエンスをクリックし、ユーザーに表示された合計回数。<br/> </td> 
</tr>
<tr> 
   <td>クリックスルー率（CTR） <br/> </td> 
   <td>リンク、広告またはレコメンデーションをクリックしたユーザーの、表示回数に対する割合。<br/> </td> 
</tr>
<tr> 
   <td>コンバージョン率<br/> </td> 
   <td>ユーザーのアクション（クリックなど）を引き起こし、モデルがユーザーのエンゲージメントを成功したことを示すディスプレイの割合。<br/> </td> 
</tr>
<tr> 
   <td>決定項目のパフォーマンス <br/> </td> 
   <td>各アイテムがユーザーを引き付け、購入、クリック、その他の応答など、目的のアクションを推進するパフォーマンスを評価します。<br/> </td> 
</tr>
<tr> 
   <td>意思決定 KPI<br/> </td> 
   <td>合計項目、合計クリック数、合計表示数、フォールバック率など、訪問者のエクスペリエンスへのエンゲージメントに関する主なインサイト。<br/> </td> 
</tr>
<tr> 
   <td>表示 <br/> </td> 
   <td>パーソナライズされたエクスペリエンスが、様々なタッチポイントを介してユーザーに表示または提示された合計回数。<br/> </td> 
</tr>
<tr> 
   <td>エンゲージメントファネル <br/> </td> 
   <td>ファネルの各ステージがユーザーのインタラクションをどの程度促進しているかを評価することにより、パーソナライズされたエクスペリエンスのパフォーマンスを監視します。<br/> </td> 
</tr>
<tr> 
   <td>選択戦略別のエンゲージメントファネル <br/> </td> 
   <td>様々な選択戦略が、パーソナライズされたエクスペリエンスでユーザーを引き付けている効果を監視し分析します。<br/> </td> 
</tr>
<tr> 
   <td>人物 <br/> </td> 
   <td>コードベースのエクスペリエンスのターゲットプロファイルとして認定されるユーザープロファイルの数。<br/> </td> 
</tr>
<tr> 
   <td>ランキング戦略 <br/> </td> 
   <td>モデル主導と除外の 2 つのトラフィックタイプを比較した、AI 主導のランキングモデルのパフォーマンスに関するインサイト <br/> </td> 
</tr>
<tr> 
   <td>CTR<br/> 別の上位の決定項目 </td> 
   <td>クリックスルー率（CTR）に基づいて個々の項目のパフォーマンスをハイライト表示し、ユーザーを引き付けるのに最も効果的な項目を評価します。<br/> </td> 
</tr>
<tr> 
   <td>ユニーククリック数<br/> </td> 
   <td>コードベースのエクスペリエンスのコンテンツをクリックしたプロファイルの数。<br/> </td> 
</tr>
<tr> 
   <td>ユニーク表示 <br/> </td> 
   <td>エクスペリエンスが開かれた回数。1 つのプロファイルによる複数のインタラクションは考慮されません。<br/> </td> 
</tr>
 </tbody> 
</table>
