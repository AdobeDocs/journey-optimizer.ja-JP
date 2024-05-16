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
source-git-commit: c667d04e22ad3addb35b1508366295a89751d8f0
workflow-type: tm+mt
source-wordcount: '844'
ht-degree: 26%

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
<p>詳細なフリークエンシーキャッピングルールを作成し、ルールセットを使用して様々なタイプのマーケティングコミュニケーションに適用できるようになりました。 この新しい機能を使用すると、過剰に配信を受けているプロファイルをメッセージやアクションから自動的に除外するクロスチャネルルールを設定することで、オーディエンスがメッセージを受け取る頻度を制御できます。</p>
<p>ビジネスルール機能は現在、パブリックベータ版として利用できます。</p>
<p>詳しくは、<a href="../configuration/business-rules.md">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr>
<th><strong>拡張されたパーソナライゼーションデータ – ベータ版</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Adobe Experience Platform データセット内のデータ値を検索して取得し、これらの値を使用してAdobe Journey Optimizerで条件を作成できるようになりました。 オブジェクトの配列内で属性を使用して関係が定義されている場合、ルックアップデータセットのデータを活用できます。 プロファイルが有効になっていないデータセットを参照用に指定できます。 有効にすると、指定したデータセットへの結合キーとしてプロファイル属性を使用し、パーソナライゼーション用にさらにデータを取得できます。</p>
<p>この機能は、現在、パブリックベータ版として利用できます。</p>
</td>
</tr>
</tbody>
</table>

### 機能強化 {#e-improvements}

このリリースでは、以下に示す機能強化が含まれています。

**Experience Decisioning**

ベータ版からこのリリースでは、次の改善が追加されました。

* **Experience Decisioning + コードベースエクスペリエンス（LA）** - Experience Decisioning 機能を活用して、コードベースのキャンペーンで決定項目を使用できるようになりました。 メモ：Adobeの Healthcare Shield およびプライバシーとセキュリティシールド アドオン機能を購入した組織では、コードベースのエクスペリエンスチャネルとエクスペリエンス決定は使用できません。 [詳細情報](../code-based/get-started-code-based.md)
* **コンテキストデータ**  – 決定ルールとランキング式で、Adobe Experience Platformのコンテキストデータを活用できるようになりました。 [詳細情報](../experience-decisioning/context-data.md)
* **新しい権限**  – 新しい「エクスペリエンス決定の管理」権限が意思決定管理リソースで使用できるようになりました。 Experience Decisioning に関連する権限を管理できます。 [詳細情報](../experience-decisioning/gs-experience-decisioning.md)
* **キャッピングルール** - Experience Decisioning で特定の決定項目に対して複数のキャッピングルールを追加できるようになりました。 これにより、オファーの送信方法に対する制御レベルを高めることができます。 [詳細情報](../experience-decisioning/items.md#capping)
* **報告書**  – を使用して、エクスペリエンス決定キャンペーンのカスタムレポートダッシュボードを作成できるようになりました [!DNL Customer Journey Analytics]. [詳細情報](../experience-decisioning/cja-reporting.md)


**意思決定管理**

* **複数ルールのサポート**  – 意思決定管理で、特定のオファーに対して最大 10 個のキャッピングルールを追加できるようになりました。 これにより、オファーの送信方法に対する制御レベルを高めることができます。
* **監査**  – が **変更ログ** タブを使用すると、オファーまたは決定に加えられたすべての変更が表示されます。 オファーと決定に関連する変更は、**監査**&#x200B;メニューで確認できるようになりました。


**メールチャネル**

* **リスト – 登録解除**  – 一括送信者向けの最近の Gmail および Yahoo のお知らせに続いて、Journey Optimizerでは、「投稿/1 クリック」のリスト購読解除オプションをサポートしています。
* **スパムのスコアリング** （ベータ版） – コンテンツのスパムのスコアを専用のスパムレポートで確認できるようになりました。 Adobe Journey Optimizerは SpamAssassin を使用してメールコンテンツをテストし、ISP プロバイダーがスパムと見なすかどうかを示すスコアを付与できるようになりました。 [詳細情報](../content-management/spam-report.md)


**オーディエンス**

* オーディエンスコンポジションとカスタムアップロード（CSV ファイル）のオーディエンスと属性を、Healthcare Shield またはプライバシーとセキュリティシールドで使用できるようになりました。

**パーソナライゼーション**

* **式フラグメント**  – 式フラグメントを **アプリ内チャネル**. [詳細情報](../personalization/use-expression-fragments.md)

**ジャーニー**

* **結合ポリシー** （限定提供） – ジャーニーで使用される結合ポリシーがジャーニー全体で表示され、一貫性を持つようになりました。
* **mTLS サポート** - mTLS プロトコルがJourney Optimizer API とカスタムアクションでサポートされるようになりました。
* **イベントのルックアップテーブル** - オブジェクトの配列内で属性を使用して関係が定義された場合、ルックアップデータセットのデータを活用できるようになりました。 ジャーニー（条件、カスタムアクションなど）でルックアップ値を使用できるようになります メッセージのパーソナライゼーションでは、参照値は使用できません。
