---
solution: Journey Optimizer
product: journey optimizer
title: リリースノート
description: Journey Optimizer 早期リリースノート
feature: Release Notes
topic: Content Management
hide: true
hidefromtoc: true
exl-id: 6e7d1300-8efd-4fdc-90e3-3ccdc3babd2f
source-git-commit: 4f7a62cdfbd90b2d33341342f6fba769e8bf0132
workflow-type: tm+mt
source-wordcount: '289'
ht-degree: 26%

---

# 早期リリースノート {#e-release-notes}

[!DNL Adobe Journey Optimizer] は、新機能、既存機能の強化、およびバグ修正を継続的に提供します。すべての変更は、 [リリースノート](release-notes.md).

以下の早期リリースノートは、リリースの公開日まで予告なく変更される場合があります。リンク、画面、更新されたドキュメントは、リリース日に[リリースノート](release-notes.md)で公開されます。

## 2024 年 3 月初期リリースノート {#e-2024}

**リリース日**:2024 年 3 月 19～20 日

### 新しい機能 {#e-features}

このリリースでは、以下に説明する新しい機能が導入されています。

<table>
<thead>
<tr>
<th><strong>コードベースのエクスペリエンス</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>新しいコードベースのエクスペリエンスチャネルでは、Adobe Journey Optimizerを使用して、Web アプリ、モバイルアプリ、デスクトップアプリ、ビデオコンソール、TV 接続デバイス、スマート TV、キオスク、ATM、IoT デバイスなど、様々なタッチポイントでカスタマイズされたエクスペリエンスをシームレスに配信できます。</p>
<P>主な機能は次のとおりです。</p>
<ul><li> ユニバーサルパーソナライゼーション：すべてのタッチポイントにわたってパーソナライズされたエクスペリエンスを拡張し、統合されたカスタマイズされたユーザージャーニーを確保します。</li>
<li>詳細な編集精度：アプリまたは Web ページ内の個々の場所で特定のコンテンツを編集します。</li>
<li>汎用性の高い実装：開発環境とシームレスに統合するための、サーバー側、API ベース、SDK ベースの実装方法のサポート。</li></ul></p>
<p>詳しくは、 <a href="../code-based/get-started-code-based.md">詳細なドキュメント</a>を参照してください。</p>
<img src="assets/do-not-localize/code-based.gif">
</tr>
</tbody>
</table>

### 機能強化 {#e-improvements}

このリリースでは、以下に示す機能強化が含まれています。

**コンテンツテンプレート**

* **サムネール** - A **サムネール表示** は、視覚的アクセスを改善するために、コンテンツテンプレートとフラグメントで使用できるようになりました。 [詳細情報](../content-management/content-templates.md#template-thumbnails)

**ジャーニー**

ジャーニーオーサリングライフサイクルに、新しい中間ステータスが追加されました。

* **公開** 次の間のステータス **ドラフト** ステータスと **ライブ** ステータス
* **停止中** 次の間のステータス **ライブ** ステータスと **停止** ステータス
* **テストモードの有効化** または **テストモードの無効化** 次の間のステータス： **ドラフト** ステータスと **ドラフト（テスト）** ステータス

ジャーニーが中間状態の場合は、読み取り専用です。