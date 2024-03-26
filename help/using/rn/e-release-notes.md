---
solution: Journey Optimizer
product: journey optimizer
title: リリースノート
description: Journey Optimizer 早期リリースノート
feature: Release Notes
topic: Content Management
exl-id: 6e7d1300-8efd-4fdc-90e3-3ccdc3babd2f
hide: true
hidefromtoc: true
source-git-commit: f957737aa741cc8b854912414d15154489d1b0b0
workflow-type: ht
source-wordcount: '311'
ht-degree: 100%

---

# 早期リリースノート {#e-release-notes}

[!DNL Adobe Journey Optimizer] は、新機能、既存機能の強化、およびバグ修正を継続的に提供します。[リリースノート](release-notes.md)では、各月の終わりにすべての変更がまとめられます。

以下の早期リリースノートは、リリースの公開日まで予告なく変更される場合があります。リンク、画面、更新されたドキュメントは、リリース日に[リリースノート](release-notes.md)で公開されます。

## 2024年3月早期リリースノート {#e-2024}

**リリース日**：2024年3月19～20日（PT）

### 新機能 {#e-features}

このリリースでは、以下に示す新機能が導入されています。

<table>
<thead>
<tr>
<th><strong>コードベースのエクスペリエンス</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>新しいコードベースのエクスペリエンスチャネルでは、Adobe Journey Optimizer を使用して、あらゆるインバウンドプロパティに対して高度なパーソナライゼーションとテストを行うことができ、web アプリ、モバイルアプリ、デスクトップアプリ、ビデオコンソール、TV 接続デバイス、スマート TV、キオスク、ATM、IoT デバイスなど、多様なタッチポイントに合わせたエクスペリエンスをシームレスに配信できます。</p>
<P>主な機能は次のとおりです。</p>
<ul><li> ユニバーサルパーソナライゼーション：すべてのタッチポイントにわたってパーソナライズされたエクスペリエンスを拡張し、一貫性のある調整されたユーザージャーニーを保証します</li>
<li>きめ細かい編集精度：アプリまたは web ページ内の個々の場所で特定のコンテンツを編集します</li>
<li>汎用性の高い実装：サーバーサイド、API ベースまたは SDK ベースの実装方法をサポートし、開発環境とシームレスに統合します。</li></ul></p>
<p>詳しくは、 <a href="../code-based/get-started-code-based.md">詳細なドキュメント</a>を参照してください。</p>
<img src="assets/do-not-localize/code-based.gif">
</tr>
</tbody>
</table>

### 機能強化 {#e-improvements}

このリリースでは、以下に示す機能強化が含まれています。

**コンテンツテンプレート**

* **サムネール** - **グリッド表示**&#x200B;モードがコンテンツテンプレートに対して使用できるようになり、サムネールを表示して視覚的なアクセスが向上しました。現在、メール HTML コンテンツテンプレートのみがサポートされています。[詳細情報](../content-management/content-templates.md#template-thumbnails)

  >[!AVAILABILITY]
  >
  >この機能は、少数の顧客向けに限定提供（LA）でリリースされています。

**ジャーニー**

新しい中間ステータスが次のジャーニーオーサリングライフサイクルに追加されました。

* **ドラフト**&#x200B;ステータスと&#x200B;**ライブ**&#x200B;ステータスの間の&#x200B;**公開**&#x200B;ステータス
* **ライブ**&#x200B;ステータスと&#x200B;**停止**&#x200B;ステータスの間の&#x200B;**停止**&#x200B;ステータス
* **ドラフト**&#x200B;ステータスと&#x200B;**ドラフト（テスト）**&#x200B;ステータスの間の&#x200B;**テストモードのアクティブ化**&#x200B;または&#x200B;**テストモードの非アクティブ化**

ジャーニーが中間状態にある場合は、読み取り専用です。