---
solution: Journey Optimizer
product: journey optimizer
title: 他のソリューションとの統合
description: Journey Optimizer を他のソリューションと統合する方法を学ぶ
feature: Integrations
role: User
level: Intermediate
exl-id: 700dc66e-ae2d-418f-b75e-ece15af57ab3
source-git-commit: 25eba9f5e738f669edbef8725328dba958b555b6
workflow-type: tm+mt
source-wordcount: '960'
ht-degree: 100%

---

# 他のソリューションとの統合 {#integration}

Adobe Journey Optimizer を使用すると、このデータを簡単に管理、保持し、テクノロジースタックの一部であるプラットフォームやシステムに書き出すことができます。これらの統合は、特定の使用例に対処し、Adobe Journey Optimizer の機能範囲を拡張するのに役立ちます。

>[!NOTE]
>
> Adobe Experience Platform 上に構築された Adobe Journey Optimizer は、[Adobe リアルタイム顧客プロファイル](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=ja){target="_blank"}にネイティブに接続されています。この組み込みのデータソースは事前に設定されており、リアルタイム顧客プロファイルからデータを取得して使用するように設計されています（例えば、ジャーニーにエントリしたユーザーがクライアントであるかどうかを確認します）。プロファイルデータとエクスペリエンスイベントデータを使用できます。[詳細情報](../datasource/adobe-experience-platform-data-source.md)。


## Adobe Customer Journey Analytics {#integration-cja}

Customer Journey Analytics を使用すると、Journey Optimizer で生成されたデータに対してアドバンス分析を実行できます。

Journey Optimizer は、Adobe Experience Platform にデータを保存し、Customer Journey Analytics を使用して、自動レポート配信とデータのカスタムビジュアライゼーションにより、すべてのジャーニー、キャンペーン、オファーの総合的なビューを提供します。

Journey Optimizer でジャーニーを作成した後、Customer Journey Analytics は、プラットフォームからデータを取り込み、レポートを開始して、顧客がジャーニーで行ったすべてのインタラクションの影響を理解できます。

詳しくは、[Journey Optimizer + Customer Journey Analytics](../reports/cja-ajo.md) を参照してください。

## Adobe Analytics {#integration-aa}

リアルタイムのジャーニーをトリガーし、顧客のエクスペリエンスを自動化するために、既にキャプチャして Adobe Experience Platform にストリーミングしている Adobe Analytics のあらゆる行動イベントデータを活用できます。このデータは、Journey Optimizer を使用してエンゲージ可能なオーディエンスの作成にも使用できます。

詳しくは、[Journey Optimizer + Analytics](../event/about-analytics.md) を参照してください。

## Adobe Experience Manager {#integration-aem}

Adobe Experience Manager ユーザーは、ワークフローを Adobe Journey Optimizer と組み合わせることができます。使用可能なユースケースは以下のとおりです。


>[!BEGINTABS]

>[!TAB AEM Assets]

**[!DNL Adobe Experience Manager Assets]** を使用してマーケティングワークフローとクリエイティブワークフローを統合します。**[!DNL Adobe Journey Optimizer]** とネイティブに統合され、**[!DNL Assets Essentials]** または **[!DNL Assets as a Cloud Service]** へアクセスして、デジタルアセットの保存、管理、検出、配布を行います。メッセージの入力に使用できる、アセットの一元的なリポジトリを提供します。

[![詳細情報](../assets/do-not-localize/learn-more-button.svg)](../integrations/assets.md)

<!--
>[!TAB AEM Templates]

With Adobe Journey Optimizer, you can create custom-tailored messages through Adobe Experience Manager sites. Start by designing your templates using Adobe Experience Manager's content sources, then send them to Adobe Journey Optimizer. Once shared, these templates can be accessed in Adobe Journey Optimizer's email designer, simplifying the process of crafting and sending messages to your desired audience.

[![learn more](../assets/do-not-localize/learn-more-button.svg)](../integrations/aem-templates.md)

-->

>[!TAB AEM フラグメント]

Adobe Experience Manager を Adobe Journey Optimizer と統合することで、AEM コンテンツフラグメントを Journey Optimizer のメールコンテンツにシームレスに組み込めるようになりました。この合理化された接続により、AEM コンテンツへのアクセスと活用のプロセスが簡略化され、パーソナライズされた動的なキャンペーンやジャーニーの作成が可能になります。

[![詳細情報](../assets/do-not-localize/learn-more-button.svg)](../integrations/aem-fragments.md)

>[!TAB Dynamic Media]

Journey Optimizer アセットセレクターを使用して、Journey Optimizer 内で承認済み Dynamic Media レンディションを選択して使用します。Adobe Experience Manager のアセットに行った変更は Journey Optimizer コンテンツに即座に反映されるので、手動での更新が必要なく、常に最新バージョンが使用されます。

[![詳細情報](../assets/do-not-localize/learn-more-button.svg)](../integrations/aem-dynamic.md)


>[!ENDTABS]



## Adobe Stock {#integration-stock}

[!DNL Adobe Stock] と [!DNL Adobe Journey Optimizer] E メールデザイナーの統合プラグインを使用すると、メッセージオーサリングで使用する画像のナビゲーション、ライセンス取得および保存を簡単に行うことができます。

詳しくは、[Journey Optimizer + Stock](../integrations/stock.md) を参照してください。

## Adobe Express {#express}

Adobe Journey Optimizer の Adobe Express 統合により、コンテンツの作成中に Adobe Express の強力な編集ツールに簡単にアクセスできます。この統合により、ソリューションを切り替えることなく、画像のサイズ変更、背景の削除、ビジュアルの切り抜き、アセットの JPEG または PNG への変換が可能になります。

詳しくは、[Journey Optimizer + Adobe Express](../integrations/express.md) を参照してください。

## GenStudio for Performance Marketing

Adobe GenStudio for Performance Marketing は、マーケティングチームが独自の広告やメールを作成し、ブランド標準および企業ポリシーに準拠した、効果的でパーソナライズされたマーケティングキャンペーンを推進できるようにする生成 AI 中心のアプリケーションです。アドビの AI テクノロジーを活用することで、コンテンツの作成と管理の複雑さを軽減し、クリエイターが革新性に焦点を当てることができるようにする包括的なツールスイートを提供します。

詳しくは、[Journey Optimizer + GenStudio for Performance Marketing](../integrations/genstudio.md) を参照してください。


## Adobe インテリジェントサービス {#integration-intelligent-service}

リアルタイム顧客データプラットフォームにネイティブな Adobe インテリジェントサービスを使用すると、カスタマーエクスペリエンスのユースケースで人工知能と機械学習の機能を活用できます。これにより、マーケティングアナリストは、データサイエンスの専門知識がなくても、ビジネスレベルの設定を使用して、会社のニーズに特化した予測を設定できます。

顧客 AI を使用すると、ブランドは、Adobe Experience Platform でプロファイル属性として使用でき、ジャーニーをパーソナライズするために使用できるチャーンまたはコンバージョンの機械学習ベースのスコアを作成できます。

詳しくは、[Journey Optimizer + Adobe インテリジェントサービス](../building-journeys/ai-services-overview.md)を参照してください。


## Adobe Campaign {#integration-ac}

統合は、Adobe Campaign v7 または v8 のユーザーが使用できます。この統合により、Adobe Campaign のトランザクションメッセージ機能を使用して、メール、プッシュ通知、SMS を送信できるようになります。

詳しくは、[Journey Optimizer + Campaign](../building-journeys/ajo-ac.md) を参照してください。

また、Adobe Campaign Standard との統合を設定して、ジャーニーでメッセージを送信することもできます。

詳しくは、[Journey Optimizer + Campaign Standard](../building-journeys/using-adobe-campaign-standard.md) を参照してください。


## Adobe Workfront {#integration-workfront}

Adobe Workfront の Adobe Journey Optimizer モジュールを使用すると、レコードの作成、読み取り、更新、削除を行ったり、Adobe Journey Optimizer API に対するカスタム API 呼び出しを実行したりできます。

この統合の主な手順の概要については、[このブログ投稿](https://experienceleaguecommunities.adobe.com/t5/journey-optimizer-blogs/accelerating-go-to-market-how-workfront-workfront-fusion-aep-and/ba-p/653685){target="_blank"}を参照してください。

Journey Optimizer と Adobe Workfront について詳しくは、[Adobe Workfront ドキュメント](https://experienceleague.adobe.com/docs/workfront/using/adobe-workfront-fusion/fusion-apps-and-modules/adobe-journey-optimizer-modules.html?lang=ja){target="_blank"}を参照してください。

## カスタムチャネル {#integration-custom}

サードパーティ製システムを使用してメッセージを送信する場合、またはジャーニーがサードパーティ製システムに API 呼び出しを送信する場合は、カスタムアクションを使用してジャーニーに接続します。例えば、カスタムアクションを使用して Epsilon、Slack、[Adobe Developer](https://developer.adobe.com){target="_blank"}、Firebase などのシステムに接続できます。

カスタムアクションは、技術ユーザーが定義し、マーケターが使用できる追加のアクションです。設定が完了すると、**[!UICONTROL アクション]**&#x200B;カテゴリの、ジャーニーの左側のパレットに表示されます。詳しくは、[このページ](../building-journeys/about-journey-activities.md#action-activities)を参照してください。

詳しくは、[カスタムアクション](../action/about-custom-action-configuration.md)を参照してください。

## 外部データソース {#integration-external-systems}

Journey Optimizer では、カスタムデータソースとカスタムアクションを使用して、外部システムへの接続を設定できます。 これにより、例えば、外部の予約システムからのデータでジャーニーをエンリッチメントできます。

外部データ ソースを使用して、サードパーティ製システムへの接続を定義する方法については、[この節](../datasource/external-data-sources.md)を参照してください。
