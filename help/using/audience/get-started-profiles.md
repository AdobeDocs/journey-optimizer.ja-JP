---
solution: Journey Optimizer
product: journey optimizer
title: Journey Optimizer におけるプロファイルの基本を学ぶ
description: Adobe Journey Optimizer でのプロファイルの作成および管理方法について説明します
feature: Profiles
role: User
level: Beginner
exl-id: be3936e4-8185-4031-9daf-95eea58077d0
source-git-commit: 1ad534b7877f0ac6c1f50e29f41af708e83b34c9
workflow-type: tm+mt
source-wordcount: '428'
ht-degree: 69%

---

# プロファイルの基本を学ぶ {#profiles-gs}

## プロファイルについて

[!DNL Adobe Journey Optimizer] のリアルタイム顧客プロファイルを活用すると、オンライン、オフライン、CRM、サードパーティデータなど、複数のチャネルのデータを組み合わせて、個々の顧客の全体像を確認できます。**プロファイル**&#x200B;を使用すると、顧客データを統合ビューにまとめて、顧客インタラクションごとにアクションにつながるタイムスタンプ付きアカウントを提供できます。

➡️ [ビデオでこの機能を確認する](#video)

**リアルタイム顧客プロファイル&#x200B;** – 顧客属性とイベントを、オンライン、オフライン、偽名のソースから統合した単一の統合プロファイルに統合します。&#x200B;プロファイルを使用して、複数のタッチポイントでパーソナライズされたリアルタイムのエクスペリエンスを顧客にエンゲージできます。

**データ取り込み** - 様々なデータソースに接続して、行動、トランザクション、財務、運用に関するデータを取り込みます。リアルタイムまたはバッチアップロードでデータを取り込んで、プロファイルを常に最新の状態に保ちます。

**ID グラフ** - ロイヤルティ ID や CRM システム ID などの顧客 ID を使用して、様々なソースからのデータを組み合わせます。ブランドのデータセット内の異なる ID 間の関係をマッピングすることで、顧客の包括的なビューを作成します。&#x200B;

**顧客エンゲージメント** - リアルタイム顧客プロファイルを使用して、ターゲットオファーやメッセージなど、コンテキストに応じてパーソナライズされたエクスペリエンスを提供します。マーケティングキャンペーン、カスタマーサポート、トランザクションの更新など、様々なチャネルで顧客をエンゲージします。

**データ共有** - Amazon Web Services、Microsoft Azure、Google Cloud などの大手クラウドストレージプロバイダーと顧客プロファイルを共有します。共有プロファイルを使用して、ビジネスインテリジェンスツールによるレポート、データのアーカイブ、詳細な分析を行います。

>[!MORELIKETHIS]
>
>* [リアルタイム顧客プロファイルのドキュメント](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=ja){target="_blank"}
>* [ リアルタイム顧客プロファイルデータとセグメント化のデフォルトガードレール ](https://experienceleague.adobe.com/ja/docs/experience-platform/profile/guardrails){target="_blank"}
>* &#x200B;[ データ取り込みドキュメント ](https://experienceleague.adobe.com/ja/docs/experience-platform/ingestion/home){target="_blank"}

## プロファイルダッシュボード

プロファイルにアクセスするには、左側のナビゲーションパネルにある&#x200B;**[!UICONTROL 顧客]**／**[!UICONTROL プロファイル]**&#x200B;メニューに移動します。

>[!NOTE]
>
>[!DNL Adobe Journey Optimizer] を初めて使用する組織で、アクティブなプロファイルデータセットや結合ポリシーが作成されていない場合は、**プロファイル**&#x200B;ダッシュボードは表示されません。代わりに、「**概要**」タブに、リアルタイム顧客プロファイルを初めて使用する際に役立つ Adobe Experience Platform ドキュメントへのリンクが表示されます。**プロファイルダッシュボード** の操作方法と、ダッシュボードに表示される指標の詳細については、[ この節 ](https://experienceleague.adobe.com/docs/experience-platform/profile/ui/user-guide.html?lang=ja){target="_blank"} を参照してください。

複数のソースのデータフラグメントを統合および組み合わせて、個々の顧客の全体像を把握できます。 結合ポリシーとは、データを統合する場合のデータの優先順位付け方法と、統合されたビューを作成するためにどのデータを組み合わせるかを決定するために使用されるルールです。 **結合ポリシー** について詳しくは、この [ ドキュメント ](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/ui-guide.html?lang=ja){target="_blank"} を参照してください。

![](assets/profiles-home.png)

## チュートリアルビデオ {#video}

Adobe Experience Platform がリアルタイム顧客プロファイルをアセンブルおよび更新する方法、これらのプロファイルにアクセスして使用する方法について説明します。

>[!VIDEO](https://video.tv.adobe.com/v/31660?quality=12&captions=jpn)
