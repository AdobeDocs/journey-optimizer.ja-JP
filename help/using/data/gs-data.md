---
solution: Journey Optimizer
product: journey optimizer
title: でのデータの使用を開始する [!DNL Journey Optimizer]
description: でのデータの操作方法について説明します。 [!DNL Journey Optimizer]
feature: Journeys
topic: Content Management
role: User
level: Intermediate
hide: true
hidefromtoc: true
exl-id: 25519acb-a017-446a-992b-653d3a8a3d96
source-git-commit: 2dcfcc8d7006c92e046152db5ac1288bdde8b063
workflow-type: tm+mt
source-wordcount: '871'
ht-degree: 0%

---

# でのデータ管理の開始について [!DNL Journey Optimizer] {#about-data}

エンドユーザー向けに豊富なデータを提供することは、カスタマーエクスペリエンスソリューションの強みと成功度を定義することです。そして、このデータは、あらゆるユーザーにとって優れた優れた価値を提供します。 テクノロジーの選択は、データ管理機能の評価を厳格に行うようになりました。

Adobe の旅オプティマイザーを使用すると、このデータを、テクノロジスタックの一部となっているプラットフォームやシステムに簡単に管理、保存、およびエクスポートすることができます。

**私のデータは、ルール** によって継続的に (そして、リアルタイムに) 作成されているので、すべてのデータに加えて、その業務に固有のデータを提供します。 Strawman-データベースのユーザーデータ ingested の機能強化と変換により、カバレッジや深度が高い価値あるデータに追加されています。 このデータは安全なものにし、同時に広く普及しているので、IT システム全体にわたってその価値を活かすことができます。

データに必要な柔軟性は、次の3つに大別されます。


<table style="table-layout:fixed">
<tr style="border: 0;">
  <td>
    <div><img alt="宛先" src="assets/do-not-localize/dest.png" /> 
    <br>他のターゲットでも利用可能ですが、旅のオプティマイザーは synergizes して、データをハイパースレッディングユーザー向けの操作に合わせて統合します。このデータは、リサーチの他のシステムでは検索することができます。これにより、このデータを活用するためのその他の方法が必要になります。
    <div>
     <a href="../start/ajo-integrations.md">詳細情報</a></div>
    </div>
    <br>
  </td>
</tr>
  <td>
    <div><img alt="保留" src="assets/do-not-localize/retention.png" />  
    <br>規定された期間 (GDPR または CCPA など) または内部データガバナンスポリシーによって保持されるのは、Adobe Experience Platform Data Lake でのデータの管理またはアーカイブにおいて、データを維持または縮小する必要があることを示します。 <a href="../privacy/get-started-privacy.md">詳細情報</a></div>
  </td>
</tr>
<tr style="border: 0;">
  <td>
    <div><img alt="ポリシー" src="assets/do-not-localize/policy.png" /> 
    <br>承諾されたタイムラインまたはポリシーが削除されたことにより、データが削除されると、すべてのデータガバナンスプロセスにおいて重要なステップとなります。 また、必要な数より多くのデータが出力オプティマイザーによって生成されます。 また、必要に応じて、データセットに必要な期間が経過した場合の動作を、ユーティリティや規制により十分に考慮してください。 必要な制御は、任意の時点のデータを削除することです。 <a href="https://experienceleague.adobe.com/docs/experience-platform/hygiene/ui/overview.html">Adobe エクスペリエンスプラットフォームマニュアルに記載されるデータの検疫について詳しくは、</a></div>
  </td>
</tr>
</table>

Adobe エクスペリエンスプラットフォームは、旅オプティマイザーが構築される際に、ユーザーに最高レベルのデータを管理できるようにします。また、それに加えて、取り組みの終わりにもなります。 このような旅において、データに対して完全な制御 (旅オプティマイザーによって作成または生成されたもの)、そのデータに対して発生したガバナンス、データが送信先に移動したことを示しています。

すべてのデータはお客様のプロパティと見なされ、お客様の要求によってのみ管理、暗号化、配信、破棄することができます。 Adobe では、fiduciary として機能します。これは、データに対する権限がまったくありません。

次のように、データの保存、アーカイブ、削除に関する特定の要件に対応するために、旅オプティマイザーのデータの柔軟性を利用できます。

* **データの抽出/書き出し** : データアクセス API を使用すると、いつでもソースデータを抽出して実行することができます。 [データアクセス API ](https://experienceleague.adobe.com/docs/experience-platform/data-access/api.html) {target = &quot;_blank&quot;} は、エクスペリエンスプラットフォーム内の ingested データセットの発見性とアクセシビリティに焦点を絞った RESTful インターフェイスをユーザーに提供します。<!--In the future (on roadmap), you can use file-based destinations to export and migrate log data from Adobe Journey Optimizer. -->

   Journeys またはキャンペーンで使用されるコンテンツは、上記の API または目的のメソッドを使用して抽出することはできません。

* **プロファイルサービスデータの保持: プロファイルに機能** およびタイムシリーズのデータが追加されるようにするには、プロファイルに追加された日付から、または、ユーザーによって選択された期間が経過するまでの間は、旅のオプティマイザーの初期設定を使用して、そのデータを最大30日間保持することができます。 アドビシステムズ社がこのデータを保持するのは、契約によって異なります。また、組織のデータ保存ポリシーにも盛り込まれています。

   Adobe エクスペリエンスプラットフォームのマニュアル ](https://experienceleague.adobe.com/docs/experience-platform/profile/event-expirations.html) でのイベントの有効期限について詳しくは、「target = &quot;_blank&quot;}」を [ 参照してください。

* **パージおよびアーカイブメカニズム** : データおよびアーカイブの削除を自由に定義し、旅のオプティマイザーを自動化することによって、データ保存ポリシーを自動化することができます。 データエンティティごとに異なるエージング方法を定義することができます。 また、書き出しメカニズムを定義してから、保存する前にエイジングデータを自動的に書き出すこともできます。

   Adobe エクスペリエンスプラットフォーム UI の「データの予防」ワークスペースを使用すると、コンシューマー id の削除、データセットの有効期限切れなど、様々なデータ検疫タスクを作成して監視することができます。 このワークスペースは、セキュリティ &amp; プライバシー保護およびヘルスケアシールドで利用できます。 Adobe エクスペリエンスプラットフォームのマニュアル ](https://experienceleague.adobe.com/docs/experience-platform/hygiene/ui/overview.html) について詳しくは、「target = &quot;_blank&quot;}」を [ 参照してください。

* **Data Lake and 欠落** : Data lake に保存された顧客データは、次のように、旅オプティマイザーによって保持されます。

   * お客様のデータをプロファイルサービスに簡単に適用できるようにするための7日間、その後は完全に削除されます。
   * あなたが削除することを選択しない限り、


* **本契約の終了** 時にデータ Extract: 契約が終了すると、データは Adobe の記憶領域から完全に削除されます。 また、アグリーメントの作成を終了する前に、すべてのプロファイルを取得することもできます。 この機能に追加料金はありません。 これは、終了時に行うだけではなく、いつでも行うことができます。

上記の方法は、contractually によって定義されています。また、DPA (データ処理契約) について詳しく説明しています。これは、アドビにおいて契約の開始時に同意されるということです。 Adobe アプリケーションは、旅オプティマイザーも含まれており、各クライアントデータは、クライアント独自のデータアセットとして処理されるという原則に基づいてエンジニアリングされています。
