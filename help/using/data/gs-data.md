---
solution: Journey Optimizer
product: journey optimizer
title: でのデータの基本を学ぶ [!DNL Journey Optimizer]
description: でデータを使用する方法を学ぶ [!DNL Journey Optimizer]
feature: Journeys
topic: Content Management
role: User
level: Intermediate
hide: true
hidefromtoc: true
exl-id: 25519acb-a017-446a-992b-653d3a8a3d96
source-git-commit: f418570a82d7b56dfb4c83df22b8109f506ec73a
workflow-type: tm+mt
source-wordcount: '877'
ht-degree: 4%

---

# でのデータ管理の概要 [!DNL Journey Optimizer] {#about-data}

エンドカスタマーエクスペリエンスソリューションの強みと成功は、エンドカスタマーデータの充実と範囲によって定義されます。また、このデータは、特定のお客様にとって最高の価値を持つ神聖なものです。 データ管理機能の評価が厳しくなり、テクノロジーの選択が本質的に組み込まれるようになりました。

Adobe Journey Optimizerを使用すると、このデータを容易に管理、保持、およびテクノロジースタックの一部であるプラットフォームやシステムに書き出すことができます。

**マイデータ、マイルール** - Journey Optimizerは継続的に（リアルタイムで）、操作に固有のすべてのジャーニーデータやオファーデータに加えて、豊富な顧客プロファイルデータのセットを作成します。 データベースから取り込んだユーザーデータの Stromman バージョンは、有効範囲と深さを含む高価値のデータにエンリッチメントされ、変換されます。 このデータを安全で、同時にあらゆる場所に分散させ、IT エコシステム全体にわたってその価値を活用したいと考えています。

大まかに、データから求められる柔軟性は次の 3 倍です。


<table style="table-layout:fixed">
<tr style="border: 0;">
  <td>
    <div><img alt="宛先" src="assets/do-not-localize/dest.png" /> 
    <br>他の宛先で利用可能 — Journey Optimizerは、高度にパーソナライズされた顧客体験のためにデータを相乗的に統合しますが、このデータをテクノロジーの全体的な状況にある他のシステムで利用し、他の方法で利用する場合に注意が必要です。
    <div>
     <a href="../start/ajo-integrations.md">詳細情報</a></div>
    </div>
    <br>
  </td>
</tr>
  <td>
    <div><img alt="保持" src="assets/do-not-localize/retention.png" />  
    <br>規定された期間 ( 業界や地域の規制（GDPR、CCPA など）や内部データガバナンスポリシーでは、Adobe Experience Platform Data Lake でデータを維持またはアーカイブする必要がある期間や期間の短さを規定しています。 <a href="../privacy/get-started-privacy.md">詳細情報</a></div>
  </td>
</tr>
<tr style="border: 0;">
  <td>
    <div><img alt="ポリシー" src="assets/do-not-localize/policy.png" /> 
    <br>合意したタイムラインまたはポリシーに基づいて削除 — データ削除は、データ保護の重要な側面であり、すべてのデータガバナンスプロセスの重要なステップです。 Journey Optimizerでは、必要以上のデータを生成できる場合があります。 また、データセットに必要な期間が経過した後の動作（ユーティリティや規制のためである）にも、最大限の注意を払う必要があります。 必要なコントロールは、任意の時点でデータを削除することです。 <a href="https://experienceleague.adobe.com/docs/experience-platform/hygiene/ui/overview.html">データの衛生状態について詳しくは、 Adobe Experience Platformのドキュメントを参照してください</a></div>
  </td>
</tr>
</table>

Journey Optimizerが構築されるAdobe Experience Platformは、エンゲージメント中およびエンゲージメントの終了時に、最高レベルのデータ制御を提供します。 Journey Optimizer内では、データ (Journey Optimizerに取り込まれる、またはによって生成される )、そのデータにオーバーレイされたガバナンス、およびそのデータの送信先を制御できます。

すべてのデータはお客様の所有物と見なされ、お客様のリクエストに応じてのみ、維持、暗号化、配布または破棄できます。 Adobeは、データに対する権限をまったく持たず、受託者としての役割を果たします。

Journey Optimizerのデータは柔軟に取り扱え、データの保持、アーカイブ、削除に関する特定の要件に対応できます。

* **データの抽出/書き出し**:ソースデータの抽出は、データアクセス API を使用して、罰則や時間の遅延なしでいつでも開始できます。 この [データアクセス API](https://experienceleague.adobe.com/docs/experience-platform/data-access/api.html){target=&quot;_blank&quot;} は、Experience Platform内に取り込んだデータセットの検出性とアクセシビリティに重点を置いた RESTful インターフェイスをユーザーに提供します。 <!--In the future (on roadmap), you can use file-based destinations to export and migrate log data from Adobe Journey Optimizer. -->

   ジャーニーやキャンペーンで使用されるコンテンツは、前述の API または宛先メソッドを使用して抽出することはできません。

* **プロファイルサービスデータ保持**:行動と時系列のデータを任意のプロファイルに追加する場合、Journey Optimizerのデフォルト設定を使用して、プロファイルに追加した日から最大 30 日間、または選択した別の期間まで、このデータを保持するように選択できます。 Adobeがこのデータを保持する時間は契約によって異なります。詳しくは、組織のデータ保持ポリシーを参照してください。

   Experience Event の有効期限について詳しくは、 [Adobe Experience Platformドキュメント](https://experienceleague.adobe.com/docs/experience-platform/profile/event-expirations.html){target=&quot;_blank&quot;}。

* **パージとアーカイブのメカニズム**:データのパージとアーカイブは、Journey Optimizerで自由に定義および自動化して、データ保持ポリシーを自動化できます。 異なるデータエンティティに対して異なるエージング戦略を定義できます。 また、古いデータをパージまたはアーカイブする前に自動的にエクスポートするように、エクスポートメカニズムを定義することもできます。

   Adobe Experience Platform UI のデータハイジーンワークスペースを使用すると、様々なデータハイジーンタスク（消費者 ID の削除やデータセット有効期限のスケジュール設定など）を作成および監視できます。詳しくは、[Adobe Experience Platform のドキュメント](https://experienceleague.adobe.com/docs/experience-platform/hygiene/ui/overview.html){target=&quot;_blank&quot;}を参照してください。

* **データレイクと削除**:データレイクに保存された顧客データは、Journey Optimizerで保持できます。

   * 顧客データをプロファイルサービスにオンボーディングしやすくするために 7 日間。この期間を過ぎると、完全に削除される場合もあります。
   * あなたが削除することを選択するまで


* **エンゲージメント終了時/終了時のデータ抽出**:契約が終了すると、データはAdobeのストレージ領域から完全に削除されます。 また、契約を終了する前に、完全なプロファイル抽出を取り込むこともできます。 この機能に追加費用はかかりません。 これは、終了時だけでなく、いつでも実行できます。

上記の方法は契約上定義され、契約の開始時にAdobeがお客様と相互に合意するデータ処理契約 (DPA) に詳細にレイアウトされます。 Journey Optimizerを含むAdobeアプリケーションは、各クライアントのデータをそのクライアントの独自のデータアセットとして扱うという原則に基づいてエンジニアリングされます。
