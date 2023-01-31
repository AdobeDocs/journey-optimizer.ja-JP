---
solution: Journey Optimizer
product: journey optimizer
title: Journey Optimizerのアクセシビリティ機能
description: Journey Optimizer User Interface でのアクセシビリティの詳細
feature: Overview
role: User
level: Beginner
source-git-commit: 78675ca22d8ee9a93d9af128d5708c305523da78
workflow-type: tm+mt
source-wordcount: '545'
ht-degree: 66%

---

# Journey Optimizerのアクセシビリティ{#accessibility}

アクセシビリティとは、視覚、聴覚、認知、運動など、様々な障害のあるユーザーが、可能な限り少ない労力でソフトウェア製品を使用できるようにするための一連の機能を指します。アドビは、アクセシビリティにおいて業界をリードする企業です。すべてのユーザーにとって利用しやすいリッチで魅力的なコンテンツを作成するよう開発者を促すことで、卓越した Web エクスペリエンスの作成をサポートします。アクセシビリティに対するAdobeの取り組みについて詳しくは、 [Adobeアクセシビリティページ](https://www.adobe.com/accessibility.html){target="_blank"}.

アクセシビリティ準拠の目標を満たすのに役立つように、 [!DNL Journey Optimizer] は、「Web Content Accessibility Guidelines(WCAG)2.1 Level A」および「Level AA」で国際的に認識されているベストプラクティスに従います。 最新の [Adobe Journey Optimizer Accessibility Conformance レポート](https://www.adobe.com/accessibility/compliance/adobe-journey-optimizer-2022.html){target="_blank"}.


[!DNL Adobe Journey Optimizer] のアクセシビリティ機能は、Adobe Experience Platform から継承したものです。

* キーボードアクセシビリティ
* カラーコントラスト
* 必須フィールドの検証

Adobe Experience Platformのアクセシビリティ機能の詳細は次のとおりです [このドキュメント](https://experienceleague.adobe.com/docs/experience-platform/accessibility/features.html?lang=ja){target="_blank"}.

では、次の一般的なキーボードショートカットを使用できます。 [!DNL Journey Optimizer]:

| アクション | ショートカット |
| --- | --- |
| ユーザインターフェイス要素、セクションおよびメニューグループ間を移動する | Tab |
| ユーザインターフェイス要素、セクションおよびメニューグループ間を後方に移動する | Shift + Tab |
| セクション内を移動して個々の要素にフォーカスを設定する | 矢印 |
| フォーカスされている要素を選択またはクリアする | Enter またはスペースバー |
| 選択をキャンセル、パネルを折りたたむまたはダイアログボックスを閉じる | Esc |

これらのショートカットは、 [!DNL Journey Optimizer] ユーザーインターフェイス：

<table>
  <thead>
    <tr>
      <th>インターフェイス要素</th>
      <th>アクション</th>
      <th>ショートカット</th>
    </tr>
  </thead>
  <tr>
    <td>ジャーニー、アクション、データソース、イベントのリスト</td>
    <td>ジャーニー、アクション、データソースまたはイベントを作成する</td>
    <td>C</td>
  </tr>
  <tr>
    <td rowspan="3">ドラフトステータスのジャーニーキャンバス</td>
    <td>左側のパレットから、使用可能な最初の位置に上から下に向かってアクティビティを追加する</td>
    <td>アクティビティをダブルクリック</td>
  </tr>
  <tr>
    <td>すべてのアクティビティを選択する</td>
    <td>Ctrl + A(Windows)<br/>CMD + A (Mac)</td>
  </tr>
  <tr>
    <td>選択されたアクティビティを削除する</td>
    <td>Delete キーまたは Backspace キーを押したあと Enter キーを押して削除を確認</td>
  </tr>
  <tr>
    <td>ズームイン/ズームアウト（キャンバスまたはその子要素にフォーカス）</td>
    <td>Ctrl +/-(Windows) または Command +/-(Mac)</td>
  </tr>  
  <tr>
    <td>各アクティビティとパスの間を移動（キャンバスにフォーカス）するか、ツールバーボタン間を移動（ツールバーにフォーカス）</td>
    <td>矢印キー</td>
  </tr>   
  <tr>
    <td>キャンバス上の次にアクションにつながる要素（ツールバーが最初のもの）にフォーカスを移動する。</td>
    <td>Tab</td>
  </tr>  
  <tr>
    <td>適切な設定ペインを開く（アクティビティにフォーカス）</td>
    <td>ENTER</td>
  </tr>   
  <tr>
    <td>キャンバスでのアクティビティの移動（アクティビティに焦点を当てる）</td>
    <td>Shift +矢印キー</td>
  </tr>  
  <tr>
  <td rowspan="3">

次の要素の設定ペイン：

<ul>
  <li>ジャーニーのアクティビティ</li>
  <li>イベント</li>
  <li>データソース</li>
  <li>アクション</li>
</ul>

</td>
    <td>設定する次のフィールドに移動する</td>
    <td>Tab</td>
  </tr>
  <tr>
    <td>変更内容を保存し設定ペインを閉じる</td>
    <td>Enter</td>
  </tr>
  <tr>
    <td>変更内容を破棄して設定ペインを閉じる</td>
    <td>Esc</td>
  </tr>
  <tr>
    <td rowspan="4">テストモードのジャーニー</td>
    <td>テストモードを有効または無効にする</td>
    <td>T</td>
  </tr>
  <tr>
    <td>イベントベースのジャーニーでイベントをトリガーする</td>
    <td>E</td>
  </tr>
  <tr>
    <td>

「**[!UICONTROL 一度に 1 つのプロファイル]**」オプションがオンになっているセグメントベースのジャーニーでイベントをトリガーする

</td>
    <td>P</td>
  </tr>
  <tr>
    <td>テストログを表示する</td>
    <td>L</td>
  </tr>
<!-- //Ajouter ce raccourci quand il marchera (actuellement, le raccourci Ctrl/Cmd+F du navigateur a priorité sur celui de AJO).//
  <tr>
    <td>Page with a search bar</td>
    <td>Select the search bar</td>
    <td>Ctrl/Command + F</td>
  </tr>
-->
  <tr>
    <td>テキストフィールド</td>
    <td>選択されたフィールド内のすべてのテキストを選択する</td>
    <td>Ctrl + A（Windows）<br/>Command + A（Mac）</td>
  </tr>
  <tr>
    <td rowspan="2">ポップアップウィンドウ</td>
    <td>変更内容を保存するかアクションを確認する</td>
    <td>Enter</td>
  </tr>
  <tr>
    <td>ウィンドウを閉じる</td>
    <td>Esc</td>
  </tr>
  <tr>
    <td>シンプルな式エディター</td>
    <td>フィールドを選択し追加する</td>
    <td>フィールドをダブルクリック</td>
  </tr>
  <tr>
    <td>XDM フィールドのブライジング</td>
    <td>ノードのすべてのフィールドを選択する</td>
    <td>親ノードを選択</td>
  </tr>
  <tr>
    <td>ペイロードのプレビュー</td>
    <td>ペイロードを選択する</td>
    <td>Ctrl + A（Windows）<br/>Command + A（Mac）</td>
  </tr>
</table>
