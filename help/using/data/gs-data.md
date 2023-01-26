---
solution: Journey Optimizer
product: journey optimizer
title: Journey Optimizerでのデータの概要
description: Journey Optimizerでのデータの操作方法を説明します
feature: Journeys
topic: Content Management
role: User
level: Intermediate
keywords: データ、管理、プラットフォーム
exl-id: 25519acb-a017-446a-992b-653d3a8a3d96
source-git-commit: ef34cb0207d3011eca6d76ad6568f3edc00e13a3
workflow-type: tm+mt
source-wordcount: '660'
ht-degree: 64%

---

# [!DNL Journey Optimizer] のデータ管理の基本を学ぶ {#about-data}

エンドカスタマーエクスペリエンスソリューションの強みと成功は、エンドカスタマーデータの充実と範囲によって定義されます。また、このデータは、特定の顧客にとって神聖で最も価値の高いものです。 データ管理機能の評価が厳しくなり、テクノロジーの選択が本質的に組み込まれるようになりました。

を使用 [!DNL Adobe Journey Optimizer]を使用すると、このデータを容易に管理、保持、およびテクノロジースタックの一部であるプラットフォームやシステムに書き出すことができます。

**マイデータ、マイルール** - [!DNL Adobe Journey Optimizer] 継続的に（リアルタイムで）は、操作に固有のすべてのジャーニーデータやオファーデータに加えて、豊富な顧客プロファイルデータのセットを作成します。 データベースから取り込んだユーザーデータの Strawman バージョンは、エンリッチメントされ、カバレッジと深度を備えた高価値のデータに変換されます。IT エコシステム全体でその価値を活用できるように、このデータは安全であると同時にあらゆる場所に存在する必要があります。

大まかに、データから求められる柔軟性は次のとおりです。


<table style="table-layout:fixed">
<tr style="border: 0;">
  <td>
    <div><img alt="宛先" src="assets/do-not-localize/dest.png" /><br>[!DNL Adobe Journey Optimizer]他の宛先で利用可能 -  は、高度にパーソナライズされたカスタマーエクスペリエンスのためにデータを相乗的に統合しますが、データを活用する他の方法を探す一方で、テクノロジー環境全体における他のシステムでも、このデータが必要だと考えていることでしょう。
    <div>
     <a href="../start/ajo-integrations.md">詳細情報</a></div>
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
    <div><img alt="ポリシー" src="assets/do-not-localize/policy.png" /><br>合意したタイムラインまたはポリシーに基づいて削除 - データ削除は、データ保護の重要な側面であり、すべてのデータガバナンスプロセスにおける重要なステップです。[!DNL Adobe Journey Optimizer] は、必要以上のデータを生成する場合があります。 また、データセットに必要な期間が経過した後の動作について、（ユーティリティまたは規制のために）細心の注意を払う必要があります。必要な制御は、特定の時点でデータを削除することです。 
    </div>
      <div>
     (<a href="../privacy/data-hygiene.md">詳細情報</a>)</div>
    </div>
  </td>
</tr>
</table>

[!DNL Adobe Experience Platform] が構築されている は、エンゲージメント中もエンゲージメント終了時も、最高レベルのデータ制御を提供します。[!DNL Adobe Journey Optimizer]内 [!DNL Journey Optimizer]を使用すると、データ（で取り込まれる、または生成される）を完全に制御できます。 [!DNL Journey Optimizer])、そのデータおよびそのデータの送信先にオーバーレイされたガバナンス。

すべてのデータは、顧客のプロパティと見なされ、顧客のリクエストに応じてのみ維持、暗号化、配布または破棄できます。アドビは、顧客の受託者としての役割を果たし、顧客のデータに対する権限は一切ありません。

以下を使用して、 [!DNL Journey Optimizer]のデータは、データの保持、アーカイブ、削除に関する特定の要件に対応する柔軟性を備えています。

* **データの抽出／エクスポート**：ソースデータの抽出は、データアクセス API を使用して、ペナルティや時間の遅延なしでいつでも開始できます。この [データアクセス API](https://experienceleague.adobe.com/docs/experience-platform/data-access/api.html?lang=ja){target="_blank"} は、内で取り込んだデータセットの検出性とアクセシビリティに重点を置いた RESTful インターフェイスをユーザーに提供します。 [!DNL Adobe Experience Platform]. <!--In the future (on roadmap), you can use file-based destinations to export and migrate log data from Adobe Journey Optimizer. -->

   ジャーニーやキャンペーンで使用されるコンテンツは、上記の API または宛先メソッドを介して抽出できません。

<!--
* **Profile Service Data Retention**: For Behavioral and Time series data appended to any Profile, you may choose to use Journey Optimizer’s default setting of retaining this data for up to 30 days from the date of its addition to a Profile, or until an alternative time-period selected by the you. The time that Adobe keeps this data varies from contract to contract, and is outlined in an organization’s data retention policy.

  Learn more about Experience Event expirations in [Adobe Experience Platform documentation](https://experienceleague.adobe.com/docs/experience-platform/profile/event-expirations.html){target="_blank"}.
-->

* **パージとアーカイブのメカニズム**[!DNL Adobe Journey Optimizer]：データのパージとアーカイブは、 で自由に定義および自動化して、データ保持ポリシーを自動化できます。異なるデータエンティティに対して様々なエージング戦略を定義できます。また、古いデータをパージまたはアーカイブする前に自動的にエクスポートするように、エクスポートメカニズムを定義することもできます。

   データ衛生ワークスペースを使用すると、消費者 ID の削除やデータセット有効期限のスケジュール設定など、様々なデータ衛生タスクを作成および監視できます。 このワークスペースは、セキュリティとプライバシーのシールドとヘルスケアのシールドで利用できます。詳しくは、[このページ](../privacy/data-hygiene.md)を参照してください。

<!--
* **Data Lake and Deletions**: Customer Data stored in the Data Lake can be retained by Journey Optimizer:
    
    * for 7 days to facilitate the onboarding of Customer Data into the Profile Services, after which it may be permanently deleted, or
    * until chosen to be deleted by you

-->

* **エンゲージメント終了時のデータ抽出**：契約が終了すると、データはアドビのストレージスペースから完全に削除されます。また、契約を終了する前に、完全なプロファイル抽出を取り込むこともできます。この機能に追加コストはかかりません。これは、終了時だけでなく、いつでも実行できます。

上記の方法は契約上定義されており、契約の開始時にアドビが相互に同意するデータ処理契約（DPA）に詳細に記載されています。Adobe・アプリケーション： [!DNL Journey Optimizer]は、各クライアントのデータをそのクライアントの独自のデータアセットとして扱うという原則に基づいて設計されています。
