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
source-git-commit: 4b779d297769bd7a0b6913a0142ee7be7775ba04
workflow-type: tm+mt
source-wordcount: '651'
ht-degree: 37%

---

# 早期リリースノート {#e-release-notes}

[!DNL Adobe Journey Optimizer] は、新機能、既存機能の強化、およびバグ修正を継続的に提供します。[リリースノート](release-notes.md)では、各月の終わりにすべての変更がまとめられます。

以下の早期リリースノートは、リリースの公開日まで予告なく変更される場合があります。リンク、画面、更新されたドキュメントは、リリース日に[リリースノート](release-notes.md)で公開されます。

## 2024 年 5 月先行リリースノート {#e-2024}

**リリース日**:2024 年 5 月 21～22 日

### 新機能 {#e-features}

このリリースでは、以下に示す新機能が導入されています。


<table>
<thead>
<tr>
<th><strong>エクスペリエンス決定 – 限定提供</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Experience Decisioning は、「決定項目」と呼ばれるマーケティングオファーの一元カタログと、高度な決定エンジンを提供することで、パーソナライゼーションを簡素化します。このエンジンは、ルールとランキング条件を活用して、各個人に最も関連性の高い決定項目を選択し、提示します。</p>
<p>これらの決定項目は、新しいコードベースのエクスペリエンスチャネルを通じて様々なインバウンドサーフェスにシームレスに統合され、Journey Optimizer キャンペーン内でアクセスできるようになりました。 エクスペリエンス決定決定ポリシーは、コードベースのエクスペリエンスキャンペーンでのみ使用できます。</p>
<p>エクスペリエンス決定は、現在一連の組織でのみ利用可能です（限定提供）。アクセスするには、アドビ担当者にお問い合わせください。</p>
<img src="assets/do-not-localize/gif-exd.gif"/>
<p>詳しくは、<a href="../experience-decisioning/gs-experience-decisioning.md">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr>
<th><strong>IP ウォームアップワークフロー</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>新しい IP アドレスでメールを送信している場合に、ユーザーインターフェイスから直接 IP ウォームアップワークフローを簡単に実行できるようになりました。 Adobe Journey Optimizerは、最適な配信品質を得るためのベストプラクティスに従って IP アドレスをウォームアップする、標準化された効率的な方法を提供します。</p>
<p>詳しくは、<a href="../configuration/ip-warmup-gs.md">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>ビジネスルール – ベータ版</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>詳細なフリークエンシーキャッピングルールを作成し、ルールセットを使用して様々なタイプのマーケティングコミュニケーションに適用できるようになりました。 </p>
</td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr>
<th><strong>ローカルルックアップのためのマルチエンティティのサポート – ベータ版</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>未定</p>
</td>
</tr>
</tbody>
</table>


<!--table>
<thead>
<tr>
<th><strong>Email Surface Personalization - Private beta </strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>You can now define dynamic subdomains and personalized header parameters when creating email channel surfaces, for increased flexibility and control over your email settings.</p>
</td>
</tr>
</tbody>
</table-->

### 機能強化 {#e-improvements}

このリリースでは、以下に示す機能強化が含まれています。

**Experience Decisioning**

ベータ版から LA まで、次の改善が追加されました。

* **Experience Decisioning + コードベースエクスペリエンス（LA）**:Experience Decisioning 機能を活用して、コードベースのキャンペーンで決定項目を使用できるようになりました。 メモ：Adobeの Healthcare Shield およびプライバシーとセキュリティシールド アドオン機能を購入した組織では、コードベースのエクスペリエンスチャネルとエクスペリエンス決定は使用できません。 [詳細情報](../code-based/get-started-code-based.md)
* 決定ルールとランキング式で、Adobe Experience Platformのコンテキストデータを活用できるようになりました。 [詳細情報](../experience-decisioning/context-data.md)
* 意思決定管理リソースで、新しい「エクスペリエンス決定の管理」権限を利用できるようになりました。Experience Decisioning に関連する権限を管理できます。 [詳細情報](../experience-decisioning/gs-experience-decisioning.md)
* エクスペリエンス決定で特定の決定項目に対して、複数のキャッピングルールを追加できるようになりました。これにより、オファーの送信方法に対する制御レベルを高めることができます。 [詳細情報](../experience-decisioning/items.md#capping)
* を使用して、Experience Decisioning キャンペーンのカスタムレポートダッシュボードを作成できるようになりました [!DNL Customer Journey Analytics]. [詳細情報](../experience-decisioning/cja-reporting.md)


**Offer Decisioning**

* **複数ルールのサポート**  – 意思決定管理で、特定のオファーに対して最大 10 個のキャッピングルールを追加できるようになりました。 これにより、オファーの送信方法に対する制御レベルを高めることができます。
* **監査**  – が **変更ログ** タブを使用すると、オファーまたは決定に加えられたすべての変更が表示されます。 オファーと決定に関連する変更は、**監査**&#x200B;メニューで確認できるようになりました。


**リスト – 登録解除**

* 一括送信者向けの最近の Gmail および Yahoo のお知らせに続いて、Journey Optimizerでは、「投稿/1 クリック」のリスト購読解除オプションをサポートしています。

**オーディエンス**

* オーディエンスコンポジションとカスタムアップロード（CSV ファイル）のオーディエンスと属性を、Healthcare Shield またはプライバシーとセキュリティシールドで使用できるようになりました。

**パーソナライゼーション**

* **参照テーブル** - オブジェクトの配列内で属性を使用して関係が定義された場合、ルックアップデータセットのデータを活用できるようになりました。 ジャーニー（条件、カスタムアクションなど）でルックアップ値を使用できるようになります メッセージのパーソナライゼーションでは、参照値は使用できません。
* **式フラグメント** - アプリ内チャネルで式フラグメントを使用できるようになりました。

**ジャーニー**

* **結合ポリシー**  – 結合ポリシーを設定し、ジャーニーで使用できるようになりました。
* **mTLS サポート** - mTLS プロトコルがJourney Optimizer API とカスタムアクションでサポートされるようになりました。
