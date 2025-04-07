---
solution: Journey Optimizer
product: journey optimizer
title: Journey Optimizer におけるデータ管理の基本を学ぶ
description: Journey Optimizer でデータを操作する方法を学ぶ
feature: Journeys
topic: Content Management
role: User
level: Intermediate
keywords: データ, 管理, プラットフォーム
exl-id: 25519acb-a017-446a-992b-653d3a8a3d96
source-git-commit: 47185cdcfb243d7cb3becd861fec87abcef1f929
workflow-type: tm+mt
source-wordcount: '655'
ht-degree: 99%

---

# データ管理の基本を学ぶ {#about-data}

カスタマーエクスペリエンスソリューションの強みと成功は、エンドカスタマーデータの充実度とカバレッジによって定義されます。また、このデータは貴重であり、特定の顧客にとって最高の価値があります。データ管理機能の評価が厳しくなり、テクノロジーの選択が本質的に組み込まれるようになりました。

[!DNL Adobe Journey Optimizer] を使用すると、このデータを簡単に管理、保持し、テクノロジースタックの一部であるプラットフォームやシステムに書き出すことができます。

**マイデータ、マイルール** - [!DNL Adobe Journey Optimizer] は、その操作に固有のすべてのジャーニーデータとオファーデータに加えて、顧客プロファイルデータの豊富なセットを継続的に（リアルタイムで）作成します。データベースから取り込んだユーザーデータの Strawman バージョンは、エンリッチメントされ、カバレッジと深度を備えた高価値のデータに変換されます。IT エコシステム全体でその価値を活用できるように、このデータは安全であると同時にあらゆる場所に存在する必要があります。

大まかに言えば、データに必要な柔軟性は次のとおりです。


<table style="table-layout:fixed">
<tr style="border: 0;">
  <td>
    <div><img alt="宛先" src="assets/do-not-localize/dest.png" /> 
    <br>他の宛先で利用可能 -  [!DNL Adobe Journey Optimizer] は、高度にパーソナライズされたカスタマーエクスペリエンスのためにデータを相乗的に統合しますが、データを活用する他の方法を探す一方で、テクノロジー環境全体における他のシステムでも、このデータを使用する必要があります。
    <div>
     <a href="../integrations/ajo-integrations.md">詳細情報</a></div>
    </div>
    <br>
  </td>
</tr>
</table>

<!--td>
    <div><img alt="retention" src="assets/do-not-localize/retention.png" />  
    <br>Retained for a stipulated duration – Industry or regional regulations (such as GDPR or CCPA) or internal data governance policies stipulate how long or how short a duration, data needs to be maintained or archived in Adobe Experience Platform Data Lake. <a href="../privacy/get-started-privacy.md">Learn more</a></div>
  </td>
</tr>
<tr style="border: 0;"-->
<table style="table-layout:fixed">
<tr style="border: 0;">
  <td>
    <div><img alt="ポリシー" src="assets/do-not-localize/policy.png" />
 <br>合意したタイムラインまたはポリシーに基づいて削除 - データ削除は、データ保護の重要な側面であり、すべてのデータガバナンスプロセスにおける重要なステップです。[!DNL Adobe Journey Optimizer] では、必要以上のデータを生成することがあります。また、データセットに必要な期間が経過した後の動作について、（ユーティリティまたは規制のために）細心の注意を払う必要があります。必要な制御は、特定の時点でデータを削除することです。 
    </div>
      <div>
     <a href="../privacy/data-hygiene.md">詳細情報</a></div>
    </div>
  </td>
</tr>
</table>

[!DNL Adobe Journey Optimizer] が構築されている [!DNL Adobe Experience Platform] は、エンゲージメント中もエンゲージメント終了時も、最高レベルのデータ制御を提供します。[!DNL Journey Optimizer] 内では、データ（[!DNL Journey Optimizer] に取り込まれるか、Journey Optimizer によって生成される）、そのデータにオーバーレイされるガバナンス、そのデータが送信される宛先を完全に制御できます。

すべてのデータは、顧客のプロパティと見なされ、顧客のリクエストに応じてのみ維持、暗号化、配布または破棄できます。アドビは、顧客の受託者としての役割を果たし、顧客のデータに対する権限は一切ありません。

[!DNL Journey Optimizer] のデータの柔軟性を使用して、データの保持、アーカイブ、削除に関連する特定の要件に対処できます。

* **データの抽出／書き出し**：ソースデータの抽出は、データアクセス API を使用して、ペナルティや時間の遅延なしでいつでも開始できます。[Data Access API](https://experienceleague.adobe.com/docs/experience-platform/data-access/api.html?lang=ja){target="_blank"} は、[!DNL Adobe Experience Platform] 内に取り込んだデータセットの検出可能性とアクセシビリティに重点を置いた RESTful インターフェイスをユーザーに提供します。<!--In the future (on roadmap), you can use file-based destinations to export and migrate log data from Adobe Journey Optimizer. -->

  ジャーニーやキャンペーンで使用されるコンテンツは、上記の API または宛先メソッドを介して抽出できません。

<!--
* **Profile Service Data Retention**: For Behavioral and Time series data appended to any Profile, you may choose to use Journey Optimizer's default setting of retaining this data for up to 91 days from the date of its addition to a Profile, or until an alternative time-period selected by the you. The time that Adobe keeps this data varies from contract to contract, and is outlined in an organization's data retention policy.

  Learn more about Experience Event expirations in [Adobe Experience Platform documentation](https://experienceleague.adobe.com/docs/experience-platform/profile/event-expirations.html){target="_blank"}.
-->

* **パージとアーカイブのメカニズム**：データのパージとアーカイブは、[!DNL Adobe Journey Optimizer] で自由に定義および自動化して、データ保持ポリシーを自動化できます。異なるデータエンティティに対して様々なエージング戦略を定義できます。また、古いデータをパージまたはアーカイブする前に自動的にエクスポートするように、エクスポートメカニズムを定義することもできます。

  データライフサイクルワークスペースを使用すると、様々なデータライフサイクルタスク（消費者 ID の削除やデータセット有効期限のスケジュール設定など）を作成および監視できます。このワークスペースは、セキュリティとプライバシーのシールドとヘルスケアのシールドで利用できます。詳しくは、[ このページ ](../privacy/data-hygiene.md) を参照してください。

<!--
* **Data Lake and Deletions**: Customer Data stored in the Data Lake can be retained by Journey Optimizer:
    
    * for 7 days to facilitate the onboarding of Customer Data into the Profile Services, after which it may be permanently deleted, or
    * until chosen to be deleted by you

-->

* **エンゲージメント終了時のデータ抽出**：契約が終了すると、データはアドビのストレージスペースから完全に削除されます。また、契約を終了する前に、完全なプロファイル抽出を取り込むこともできます。この機能に追加コストはかかりません。これは、終了時だけでなく、いつでも実行できます。

上記の方法は契約上定義されており、契約の開始時にアドビが相互に同意するデータ処理契約（DPA）に詳細に記載されています。[!DNL Journey Optimizer] を含むアドビのアプリケーションは、各クライアントのデータをそのクライアント独自のデータアセットとして扱うという原則に基づいてエンジニアリングされています。
