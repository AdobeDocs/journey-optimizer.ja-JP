---
solution: Journey Optimizer
product: journey optimizer
title: ' [!DNL Journey Optimizer] のデータの基本を学ぶ'
description: ' [!DNL Journey Optimizer] のデータを操作する方法を学ぶ'
feature: Journeys
topic: Content Management
role: User
level: Intermediate
hide: true
hidefromtoc: true
exl-id: 25519acb-a017-446a-992b-653d3a8a3d96
source-git-commit: 2dcfcc8d7006c92e046152db5ac1288bdde8b063
workflow-type: tm+mt
source-wordcount: '891'
ht-degree: 100%

---

# [!DNL Journey Optimizer] のデータ管理の基本を学ぶ {#about-data}

カスタマーエクスペリエンスソリューションの強みと成功は、エンドカスタマーデータの充実さとカバレッジによって定義されます。また、このデータは特定の顧客のためのものであり、最高の価値があります。データ管理機能の評価が厳しくなり、テクノロジーの選択が本質的に組み込まれるようになりました。

Adobe Journey Optimizer を使用すると、このデータを簡単に管理、保持し、テクノロジースタックの一部であるプラットフォームやシステムに書き出すことができます。

**マイデータ、マイルール** - Journey Optimizer は、その操作に固有のすべてのジャーニーデータとオファーデータに加えて、顧客プロファイルデータの豊富なセットを継続的に（リアルタイムで）作成します。データベースから取り込んだユーザーデータの Strawman バージョンは、エンリッチメントされ、カバレッジと深度を備えた高価値のデータに変換されます。IT エコシステム全体でその価値を活用できるように、このデータは安全であると同時にあらゆる場所に存在する必要があります。

広範囲で、データに必要な柔軟性は次の 3 つです。


<table style="table-layout:fixed">
<tr style="border: 0;">
  <td>
    <div><img alt="宛先" src="assets/do-not-localize/dest.png" /><br>他の宛先で利用可能 - Journey Optimizer は、高度にパーソナライズされたカスタマーエクスペリエンスのためにデータを相乗的に統合しますが、データを活用する他の方法を探す一方で、テクノロジー環境全体における他のシステムでも、このデータが必要だと考えていることでしょう。
    <div>
     <a href="../start/ajo-integrations.md">詳細情報</a></div>
    </div>
    <br>
  </td>
</tr>
  <td>
    <div><img alt="保持" src="assets/do-not-localize/retention.png" /><br>規定された期間保持 - 業界または地域の規制（GDPR、CCPA など）または内部データガバナンスポリシーにより、Adobe Experience Platform データレイクでデータを維持またはアーカイブする必要がある期間が規定されています。<a href="../privacy/get-started-privacy.md">詳細情報</a></div>
  </td>
</tr>
<tr style="border: 0;">
  <td>
    <div><img alt="ポリシー" src="assets/do-not-localize/policy.png" /><br>合意したタイムラインまたはポリシーに基づいて削除 - データ削除は、データ保護の重要な側面であり、すべてのデータガバナンスプロセスにおける重要なステップです。Journey Optimizer は、必要以上のデータを生成する場合があります。また、データセットに必要な期間が経過した後の動作について、（ユーティリティまたは規制のために）細心の注意を払う必要があります。必要な制御は、特定の時点でデータを削除することです。<a href="https://experienceleague.adobe.com/docs/experience-platform/hygiene/ui/overview.html?lang=ja">データハイジーンについて詳しくは、Adobe Experience Platform のドキュメントを参照してください</a></div>
  </td>
</tr>
</table>

Journey Optimizer が構築されている Adobe Experience Platform は、エンゲージメント中もエンゲージメント終了時も、最高レベルのデータ制御を提供します。Journey Optimizer 内では、データ（Journey Optimizer に取り込まれるか、Journey Optimizer によって生成される）、そのデータにオーバーレイされるガバナンス、そのデータが送信される宛先を完全に制御できます。

すべてのデータは、顧客のプロパティと見なされ、顧客のリクエストに応じてのみ維持、暗号化、配布または破棄できます。アドビは、顧客の受託者としての役割を果たし、顧客のデータに対する権限は一切ありません。

Journey Optimizer のデータの柔軟性を使用して、データの保持、アーカイブ、削除に関連する特定の要件に対処できます。

* **データの抽出／エクスポート**：ソースデータの抽出は、データアクセス API を使用して、ペナルティや時間の遅延なしでいつでも開始できます。[Data Access API](https://experienceleague.adobe.com/docs/experience-platform/data-access/api.html?lang=ja){target=&quot;_blank&quot;} は、Experience Platform 内に取り込んだデータセットの検出可能性とアクセシビリティに重点を置いた RESTful インターフェイスをユーザーに提供します。<!--In the future (on roadmap), you can use file-based destinations to export and migrate log data from Adobe Journey Optimizer. -->

   ジャーニーやキャンペーンで使用されるコンテンツは、上記の API または宛先メソッドを介して抽出できません。

* **プロファイルサービスデータ保持**：プロファイルに追加された行動および時系列データの場合、プロファイルに追加された日から最大 30 日間、またはユーザーが選択した別の期間まで、このデータを保持するという Journey Optimizer のデフォルト設定を使用することを選択できます。アドビがこのデータを保持する時間は契約ごとに異なります。詳しくは、組織のデータ保持ポリシーを参照してください。

   エクスペリエンスイベントの有効期限について詳しくは、[Adobe Experience Platform のドキュメント](https://experienceleague.adobe.com/docs/experience-platform/profile/event-expirations.html?lang=ja){target=&quot;_blank&quot;}を参照してください。

* **パージとアーカイブのメカニズム**：データのパージとアーカイブは、Journey Optimizer で自由に定義および自動化して、データ保持ポリシーを自動化できます。異なるデータエンティティに対して様々なエージング戦略を定義できます。また、古いデータをパージまたはアーカイブする前に自動的にエクスポートするように、エクスポートメカニズムを定義することもできます。

   Adobe Experience Platform UI のデータハイジーンワークスペースを使用すると、様々なデータハイジーンタスク（消費者 ID の削除やデータセット有効期限のスケジュール設定など）を作成および監視できます。このワークスペースは、セキュリティとプライバシーのシールドとヘルスケアのシールドで利用できます。詳しくは、[Adobe Experience Platform のドキュメント](https://experienceleague.adobe.com/docs/experience-platform/hygiene/ui/overview.html?lang=ja){target=&quot;_blank&quot;}を参照してください。

* **データレイクと削除**：データレイクに保存された顧客データは、Journey Optimizer で保持できます。

   * 顧客データをプロファイルサービスにオンボーディングしやすくするための 7 日間。この期間を過ぎると、永久に削除されるか、
   * 選択することで削除されます


* **エンゲージメント終了時のデータ抽出**：契約が終了すると、データはアドビのストレージスペースから完全に削除されます。また、契約を終了する前に、完全なプロファイル抽出を取り込むこともできます。この機能に追加コストはかかりません。これは、終了時だけでなく、いつでも実行できます。

上記の方法は契約上定義されており、契約の開始時にアドビが相互に同意するデータ処理契約（DPA）に詳細に記載されています。Journey Optimizer を含むアドビのアプリケーションは、各クライアントのデータをそのクライアント独自のデータアセットとして扱うという原則に基づいてエンジニアリングされています。
