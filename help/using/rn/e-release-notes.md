---
solution: Journey Optimizer
product: journey optimizer
title: リリースノート
description: Journey Optimizer 早期リリースノート
hide: true
hidefromtoc: true
source-git-commit: 5edd643f7e93ade8d12515c83dc6321c96fe3c77
workflow-type: tm+mt
source-wordcount: '634'
ht-degree: 21%

---

# 早期リリースノート {#e-release-notes}

[!DNL Adobe Journey Optimizer] は、新機能、既存機能の強化、およびバグ修正を継続的に提供します。[リリースノート](release-notes.md)では、すべての変更が各月の最終週にまとめられます。

以下の早期リリースノートは、リリースの公開日まで予告なく変更される場合があります。リンク、画面、更新されたドキュメントは、リリース日に[リリースノート](release-notes.md)で公開されます。

## 2023 年 9 月の早期リリースノート {#sept-rn-2023}

**リリース日**:2023 年 9 月 26～27 日

### 新機能{#sept-2023-features}

このリリースでは、以下に示す新機能が導入されています。


<table>
<thead>
<tr>
<th><strong>統合されたチャネルレポート</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>チャネルレポート機能を使用すると、チャネルレベルでのトラフィックとエンゲージメント指標の包括的な概要を、アナリストとマーケターに提供できます。 「レポート」メニューにアクセスするには、「チャネルレポートの表示」権限が必要です。</p>
<img src="assets/channel-reports.png"/>
<!--p>For more information, refer to the <a href="../in-app/get-started-in-app.md">detailed documentation</a>.</p-->
</tr>
</tbody>
</table>


<table>
<thead>
<tr>
<th><strong>データセット書き出し先 (GA)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>クラウドストレージの宛先へのJourney Optimizerデータセットの書き出しを、一般に利用できるようになりました。 この機能を使用すると、データセットの内容を書き出すために、クラウドストレージの場所とのライブ接続を確立できます。</p>
<img src="../data/assets/dataset-export-setup.png">
<!--p>For more information, refer to the <a href="../audience/get-started-audience-orchestration.md">detailed documentation</a>.</p-->
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>サンドボックスごとのモバイルアプリケーション資格情報ストレージ</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>この新機能を使用すると、プッシュ資格情報を簡単に管理し、アプリサーフェスの専用サンドボックスに関連付けることができます。</p>
<p>詳しくは、<a href="../in-app/inapp-configuration.md">詳細なドキュメント</a>を参照してください。</p>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>計算済み属性</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>計算済み属性を使用すると、直感的なユーザーインターフェイスでイベントデータを簡単にプロファイル属性に要約し、動作ベースのセグメント化、パーソナライゼーション、アクティベーションを強化できます。 この機能を使用すると、計算済み属性をセルフサービス方式で作成し、管理し、セグメント化、リアルタイム顧客プロファイルの宛先、またはJourney Optimizerで使用できます。 <br/>
さらに、計算済み属性を使用すると、セグメント化とジャーニーワークフローが簡素化され、関連性の高いエクスペリエンスをシームレスに配信できます。 詳しくは、 <a href="https://experienceleague.adobe.com/docs/experience-platform/profile/computed-attributes/overview.html">詳細なドキュメント</a>.</p>
</tr>
</tbody>
</table>


### 機能強化 {#sept-2023-improvements}

このリリースでは、以下に示す機能強化が含まれています。

<!--**Audiences**

* You can now target audiences uploaded from a CSV file into journeys and campaigns.
* You can now target audiences resulting from composition workflows into journeys. -->

**パーソナライゼーション**

* ビジュアルフラグメントに加えて、式エディターを使用して、Journey Optimizerインターフェイスから式フラグメントを作成、保存、再利用できるようになりました。 式フラグメントは、以前に保存した式を置き換えます。

**アラート**

* 新しいタイプのシステムアラートが導入されました。読み取りオーディエンスが失敗した場合に通知を受け取れるようになりました。

**Web チャネル**

* Web デザイナーのビジュアルエディターで単一ページアプリケーション (SPA) を作成できるようになりました。これにより、Web ページの変更を適用する特定のビューを選択できます。 ビューは、サイト全体またはサイト上のビジュアル要素のグループ（ホームページ、製品サイト全体、すべてのチェックアウトページの配信設定フレームなど）として定義できます。 SPAでAdobe Journey Optimizer Web キャンペーンを作成して実行するには、Adobe Experience Platform Web SDK 実装でビューを定義するために、開発者の 1 回限りの設定が必要です。

* Web デザイナーを使用してページを編集する際、 **変更** パネル — コンポーネントを選択して designer インターフェイスから編集する必要はありません。
* Web サブドメインを設定する際、既にAdobeにデリゲートされたサブドメインを使用する以外に、独自のサブドメインを追加するオプションが追加できるようになりました。

**ジャーニー**

* カスタムアクション応答のサポートが GA になりました。 これにより、カスタムアクションで API 呼び出し応答を活用し、これらの応答に基づいてジャーニーを調整できます。 さらに、すべての税関アクションをエンドポイントあたり 5,000 呼び出し/秒に制限する新しいガードレールが追加されました。
* ジャーニーを複製する際に、ジャーニーコピーの名前を定義できるようになりました。

<!--
* The maximum duration that you can define in the Wait activity is now 29 days instead of 30.
-->

**メールチャネル**

E メールのサーフェス設定の新しいオプションにより、E メールアドレスがAdobe Journey Optimizer抑制リストに含まれている場合でも、プロファイルにトランザクションメッセージを送信することを選択できます。

**SMS チャネル**

2 つの新しいフィールド **オプトインメッセージ** および **ヘルプメッセージ**&#x200B;を API 設定画面に追加し、ユーザーがインバウンドキーワードの応答をカスタマイズできるようにしました。 これは、Sinch SMS プロバイダーでのみ使用できます。

**レポート**

Journey Optimizerレポートを CSV ファイルとして書き出せるようになりました。 [詳細情報](../reports/global-report.md#export-reports)

<!--**Decision management**

Enhancements have been made to the audience picker in journeys or campaigns, with the addition of new columns displaying the origin and update frequency of audiences.    -->