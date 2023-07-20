---
solution: Journey Optimizer
product: journey optimizer
title: リリースノート
description: Journey Optimizerの早期リリースノート
hide: true
hidefromtoc: true
source-git-commit: c9e8088cd460992b0c84e3e14e63c2388fa94fd1
workflow-type: tm+mt
source-wordcount: '617'
ht-degree: 27%

---

# 早期リリースノート {#e-release-notes}

[!DNL Adobe Journey Optimizer] は、新機能、既存機能の強化、およびバグ修正を継続的に提供します。すべての変更は、 [リリースノート](release-notes.md).

以下の先行リリースノートは、リリースの提供日まで予告なく変更される可能性があります。 リンク、画面、更新されたドキュメントは、 [リリースノート](release-notes.md)、リリース日。


## 2023 年 7 月初期リリースノート {#july-rn-2023}

**リリース日**:7 月 26～27 日

### 新機能{#july-2023-features}

このリリースでは、以下に示す新機能が導入されています。

<table>
<thead>
<tr>
<th><strong>オーディエンスの構成</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>合成ワークフローを作成して、既存のAdobe Experience Platformオーディエンスを視覚的なキャンバスに組み合わせ、様々なアクティビティ（分割、エンリッチメントなど）を活用して新しいオーディエンスを作成できるようになりました。 新しく作成したオーディエンスは、既存のオーディエンスと共にAdobe Experience Platformに保存され、Journey Optimizerキャンペーンで顧客をターゲットに設定するために利用できます。</p>
<img src="../audience/assets/audiences-publish.png"/>
<p>詳しくは、<a href="../audience/get-started-audience-orchestration.md">詳細なドキュメント</a>を参照してください。</p>
<p>オーディエンス構成は、新しいAdobe Experience Platformの「オーディエンス」メニューに完全に統合され、オーディエンスの一元化されたポータルとして機能します。 セグメントのトレンドと重複を含む新しいダッシュボードを含む参照ページを使用して、新しいインサイトを見つけ、フォルダー化やタグ付けのための組織ツールを探すことができるようになりました。 このエクスペリエンス内には、標準化されたオーディエンスのラベル付け用のガバナンスコントロールと、アクティベーションワークフローを管理するオーディエンスのライフサイクル管理機能が組み込まれています。 この新しい管理エクスペリエンスにより、1 か所から簡単かつ安全にオーディエンスを管理できるようになりました。 詳しくは、 <a href="https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html?lang=ja" target="_blank">Adobe Experience Platformドキュメント</a>.</p></p>
</td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr>
<th><strong>ダイレクトメールチャネル</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>キャンペーンおよびジャーニーにダイレクトメールメッセージを追加できるようになりました。 ダイレクトメールは、ダイレクトメールプロバイダーが顧客にメールを送信するために必要なファイルをパーソナライズし、生成できるオフラインチャネルです。</p>
<p>ダイレクトメール配信を準備すると、Journey Optimizerによって、すべてのターゲットプロファイルと選択した連絡先情報（例えば、郵送先住所）を含むファイルが生成されます。 その後、このファイルを実際の発送処理をおこなうダイレクトメールプロバイダーに送信できます。</p>
<img src="../direct-mail/assets/direct-mail-properties.png">
<p>詳しくは、<a href="../direct-mail/create-direct-mail.md">詳細なドキュメント</a>を参照してください。</p>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>E メールデザイナー用にHTMLコンテンツを変換する</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizerの E メールエディターで、任意のHTMLコンテンツを読み込んで変換できるようになりました。 コンテンツブロックは自動的に識別され、E メールデザイナーで使用できます。強力なデザイン機能を使用して、更新とパーソナライズをおこないます。</p>
<img src="../email/assets/html-imported_2.png">
<!--p>For more information, refer to the <a href="../audience/get-started-audience-orchestration.md">detailed documentation</a>.</p-->
</td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr>
<th><strong>Journey Optimizerでのタグの使用</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>キャンペーンやジャーニーに加えて、Adobe Experience Platform統合タグをランディングページ、テンプレート、コンテンツフラグメント、購読リストに割り当てることができるようになりました。 これにより、簡単に分類でき、すべてのリストでの検索とナビゲーションを改善できます。 </p>
<img src="assets/do-not-localize/campaigns-tag.gif"/>
<p>詳しくは、 <a href="../start/search-filter-categorize.md#tags">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>


### 機能強化 {#july-2023-improvements}

このリリースでは、次の機能強化がおこなわれます。

**ジャーニー**

* カスタムアクションで API 呼び出し応答を活用し、これらの応答に基づいてジャーニーを調整できるようになりました。


**キャンペーン**

* キャンペーンに関連するコンテキストイベントを、パーソナライゼーションエディターの「コンテキスト属性」メニューで使用できるようになりました。


**オーディエンス**

ジャーニーまたはキャンペーンのオーディエンスピッカーが強化され、オリジンとオーディエンスの更新頻度を表示する新しい列が追加されました。

Audience Composition ポータルのリリースに伴い、Adobe Experience PlatformとAdobe Journey Optimizerは、システムおよびドキュメント内での「オーディエンス」と「セグメント」の使用を更新しました。

* オーディエンス：共通の特徴や行動を共有する人物、アカウント、世帯、その他のエンティティのセットです。
* セグメント定義：Adobe Experience Platform では、ターゲットオーディエンスの重要な特徴や行動の説明に使用される一連のルールです。この用語は、以前は「セグメント」と呼ばれていました。

その結果、Adobe Journey Optimizer と Adobe Experience Platform UI 内では、この新しいオーディエンスの作成と管理のパスを反映して、「セグメント」が「オーディエンス」に置き換えられるようになります。


