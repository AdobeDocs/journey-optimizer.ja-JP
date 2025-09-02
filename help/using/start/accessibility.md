---
solution: Journey Optimizer
product: journey optimizer
title: Journey Optimizer のアクセシビリティ機能
description: Journey Optimizer のユーザーインターフェイスのアクセシビリティに関する詳細情報
feature: Accessibility
role: User
level: Beginner
exl-id: d971c04c-9b37-4cd7-8a2d-b915e394079b
source-git-commit: 95e50386d4190d0b967d133a327c25ab1681b5c1
workflow-type: tm+mt
source-wordcount: '486'
ht-degree: 96%

---

# Journey Optimizer のアクセシビリティ{#accessibility}

アクセシビリティとは、視覚、聴覚、認知、運動など、様々な障害のあるユーザーが、可能な限り少ない労力でソフトウェア製品を使用できるようにするための一連の機能を指します。アドビは、アクセシビリティにおいて業界をリードする企業です。すべてのユーザーにとって利用しやすいリッチで魅力的なコンテンツを作成するよう開発者を促すことで、卓越した web エクスペリエンスの作成をサポートします。アドビのアクセシビリティへの取り組みについて詳しくは、[アドビのアクセシビリティのページ](https://www.adobe.com/accessibility.html){target="_blank"}を参照してください。

アクセシビリティ準拠の目標を達成するために、[!DNL Journey Optimizer] では、Web Content Accessibility Guidelines（WCAG）2.1 Level A および Level AA で国際的に認められたベストプラクティスに従っています。詳しくは、最新の [Adobe Journey Optimizer のアクセシビリティ適合性レポート](https://www.adobe.com/accessibility/compliance/adobe-journey-optimizer.html){target="_blank"}を参照してください。

>[!NOTE]
>
>詳しくは、メールおよびランディングページ用のアクセシブルなコンテンツの設計に関するガイドラインを参照してください [ この節 ](../email/accessible-content.md)。

[!DNL Adobe Journey Optimizer] のアクセシビリティ機能は、Adobe Experience Platform から継承したものです。

* キーボードアクセシビリティ
* カラーコントラスト
* 必須フィールドの検証

Adobe Experience Platform のアクセシビリティ機能について詳しくは、[このドキュメント](https://experienceleague.adobe.com/docs/experience-platform/accessibility/features.html?lang=ja){target="_blank"}を参照してください。

[!DNL Journey Optimizer] では、次の一般的なキーボードショートカットが使用できます。

| アクション | ショートカット |
| --- | --- |
| ユーザインターフェイス要素、セクションおよびメニューグループ間を移動する | Tab |
| ユーザインターフェイス要素、セクションおよびメニューグループ間を後方に移動する | Shift + Tab |
| セクション内を移動して個々の要素にフォーカスを設定する | 矢印 |
| フォーカスされている要素を選択またはクリアする | Enter またはスペースバー |
| 選択をキャンセル、パネルを折りたたむまたはダイアログボックスを閉じる | Esc |

これらのショートカットは、[!DNL Journey Optimizer] ユーザー インターフェイスの特定の領域で使用できます。

<table>
  <thead>
    <tr>
      <th>インターフェイス要素</th>
      <th>アクション</th>
      <th>ショートカット</th>
    </tr>
  </thead>
  <tr>
    <td rowspan="8">ドラフトステータスのジャーニーキャンバス</td>
    <td>左側のパレットから、使用可能な最初の位置に上から下に向かってアクティビティを追加する</td>
    <td>アクティビティをダブルクリック</td>
  </tr>
  <tr>
    <td>すべてのアクティビティを選択する</td>
    <td>CTRL + A（Windows）<br/>CMD + A（Mac）</td>
  </tr>
  <tr>
    <td>選択されたアクティビティを削除する</td>
    <td>Delete キーまたは Backspace キーを押したあと Enter キーを押して削除を確認</td>
  </tr>
  <tr>
    <td>ズームイン／ズームアウトする（キャンバスまたはその子要素にフォーカス）</td>
    <td>CTRL +/-（Windows）または CMD +/-（Mac）</td>
  </tr>  
  <tr>
    <td>各アクティビティとパスの間を移動する（キャンバスにフォーカス）、またはツールバーボタン間を移動する（ツールバーにフォーカス）</td>
    <td>矢印キー</td>
  </tr>   
  <tr>
    <td>キャンバス上の次にアクションにつながる要素（最初の要素はツールバー）にフォーカスを移動</td>
    <td>Tab</td>
  </tr>  
  <tr>
    <td>適切な設定パネルを開く（アクティビティにフォーカス）</td>
    <td>Enter</td>
  </tr>   
  <tr>
    <td>キャンバスでアクティビティを移動する（アクティビティにフォーカス）</td>
    <td>Shift + 矢印キー</td>
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
