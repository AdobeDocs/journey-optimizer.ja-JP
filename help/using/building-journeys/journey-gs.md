---
solution: Journey Optimizer
product: journey optimizer
title: 初めてのジャーニーの作成
description: Adobe Journey Optimizer で最初のジャーニーを作成するための主な手順
feature: Journeys, Get Started
topic: Content Management
role: User
level: Intermediate
keywords: ジャーニー, 最初, 開始, クイックスタート, オーディエンス, イベント, アクション
exl-id: d940191e-8f37-4956-8482-d2df0c4274aa
source-git-commit: fa46397b87ae3a81cd016d95afd3e09bb002cfaa
workflow-type: tm+mt
source-wordcount: '768'
ht-degree: 63%

---

# 初めてのジャーニーの作成 {#jo-quick-start}

>[!CONTEXTUALHELP]
>id="ajo_homepage_card2"
>title="ジャーニーを作成"
>abstract="**Adobe Journey Optimizer** を利用すると、イベントやデータソースに格納されているコンテキストデータを使用して、リアルタイムオーケストレーションのユースケースを構築できます。"

>[!CONTEXTUALHELP]
>id="ajo_journey_create"
>title="ジャーニー"
>abstract="カスタマージャーニーを設計して、状況に即したパーソナライズされたエクスペリエンスを提供します。Journey Optimizer を利用すると、イベントやデータソースに格納されているコンテキストデータを使用して、リアルタイムオーケストレーションのユースケースを構築できます。「**概要**」タブには、ジャーニーに関連する主要指標を含むダッシュボードが表示されます。「**参照**」タブには、既存のジャーニーのリストが表示されます。"

Adobe Journey Optimizer には、マーケターがマーケティングアウトリーチを 1 対 1 の顧客エンゲージメントと調和させるためのオムニチャネルオーケストレーションキャンバスが含まれています。ユーザーインターフェイスを使用すると、パレットからキャンバスにアクティビティを簡単にドラッグ＆ドロップして、ジャーニーを作成できます。ジャーニーのユーザーインターフェイスについて詳しくは、[このページ](journey-ui.md)を参照してください。

![ジャーニーキャンバスのサンプル](assets/journey38.png)


ジャーニーを作成する主な手順について詳しくは、このページを参照してください。次のように効率化されています。

![ジャーニーの作成手順：作成、デザイン、テスト、公開](assets/journey-creation-process.png)


複数のステップから成るカスタマージャーニーを作成し、チャネルをまたいで、インタラクション、オファーおよびメッセージのシーケンスをリアルタイムで開始します。 このアプローチにより、お客様の行動と関連するビジネスシグナルに基づいて、最適なタイミングで顧客と関与できるようになります。ターゲットオーディエンスは、行動、コンテキストデータおよびビジネスイベントに基づいて定義されます。 前提条件は、ユースケースと、構築している [ ジャーニーのタイプ ](entry-management.md#types-of-journeys) によって異なります。

ジャーニーの構築を開始する前に、関連する設定手順が完了していることを確認します。

* イベントを受信したときにジャーニーを個別にトリガーする場合は、**イベントを設定** します。 想定される情報とその処理方法を定義します。 [詳細情報](../event/about-events.md)。

<!--   ![](assets/jo-event7bis.png)  -->

* ジャーニーでは、Adobe Experience Platform オーディエンスをリッスンして、指定した一連のプロファイルにメッセージを一括で送信することもできます。 これには、**オーディエンスを作成** を使用します。 [詳細情報](../audience/about-audiences.md)。

<!--   ![](assets/segment2.png)  -->

* ジャーニーで使用する追加情報（条件など）を取得するために、システムへの接続を定義します。 この接続は、**データソース**&#x200B;に基づいています。[詳細情報](../datasource/about-data-sources.md)。

<!--   ![](assets/jo-datasource.png)  -->

* Journey Optimizer には、[組み込みのメッセージ](../building-journeys/journeys-message.md)機能が含まれています。サードパーティシステムを使用してメッセージを送信する場合は、**カスタムアクションを作成**&#x200B;できます。詳しくは、[この節](../action/action.md)を参照してください。

<!--    ![](assets/custom2.png)  -->


データエンジニアとして、データソース、イベント、アクションを含むジャーニーを設定する手順について詳しくは、[この節](../configuration/about-data-sources-events-actions.md)を参照してください。


>[!NOTE]
>
>ジャーニーのガードレールと制限について詳しくは、[このページ](../start/guardrails.md)を参照してください

## ジャーニーの作成 {#jo-build}

複数の手順から成るジャーニーを作成するには、次の手順に従います。

1. 「ジャーニー管理」メニューセクションで、「**[!UICONTROL ジャーニー]**」をクリックします。

1. 「**[!UICONTROL ジャーニーを作成]**」ボタンをクリックして、新しいジャーニーを作成します。

1. ジャーニーの設定パネルを編集して、ジャーニーの名前を定義し、そのプロパティを設定します。ジャーニーのプロパティを設定する方法について詳しくは、[このページ](journey-properties.md)を参照してください。

   ![](assets/jo-properties.png)

その後、ジャーニーのデザインを開始できます。

## ジャーニーのデザイン {#jo-design}

オムニチャネルジャーニーデザイナーは、直感的なドラッグ＆ドロップインターフェイスを用いて、ターゲットオーディエンス、リアルタイムの顧客やビジネスインタラクションに基づく最新情報、およびオムニチャネルメッセージを使用した、複数手順のジャーニーの作成を支援します。

![](assets/journey38.png)

1. まず、イベントまたは&#x200B;**オーディエンスを読み取り**&#x200B;アクティビティを、パレットからキャンバスにドラッグ＆ドロップします。ジャーニーのデザインの詳細については、[この節](using-the-journey-designer.md)を参照してください。

   ![](assets/read-segment.png)

1. まず、イベントまたは **オーディエンスを読み取り** アクティビティを、パレットからキャンバスにドラッグ&amp;ドロップします。 ジャーニーのデザインの詳細については、[この節](using-the-journey-designer.md)を参照してください。

## ジャーニーのテスト {#jo-test}

ジャーニーを作成したら、公開する前にテストします。 Journey Optimizerは、ジャーニーに沿って進む際にテストプロファイルを確認し、アクティブ化の前に潜在的なエラーを検出する方法として、**テストモード** を提供しています。 クイックテストを実行すると、ジャーニーが正しく動作し、自信を持って公開できるようになります。 ジャーニーのテスト方法を学ぶ [ この節 ](testing-the-journey.md)

また、**ドライラン** でジャーニーを実行することもできます。 ジャーニーのドライランは、Adobe Journey Optimizer の特別なジャーニー公開モードで、ジャーニー実務担当者は実際の顧客に連絡したり、プロファイル情報を更新したりすることなく、実際の実稼動データを使用してジャーニーをテストできます。この機能により、ジャーニー実務担当者は、ジャーニーをライブで公開する前に、ジャーニーのデザインとオーディエンスのターゲティングに自信を持つことができます。 ドライランモードでジャーニーを公開する方法を学びます [ この節 ](journey-dry-run.md)。

## ジャーニーの公開 {#jo-pub}

ジャーニーをアクティブ化し、新しいプロファイルが入力できるようにするには、ジャーニーを公開する必要があります。ジャーニーを公開する前に、そのジャーニーが有効であり、エラーがないことを確認します。 エラーのあるジャーニーは公開できません。ジャーニーの公開について詳しくは、この [ 節 ](publishing-the-journey.md) を参照してください。

![](assets/jo-journeyuc2_32bis.png)

公開したら、専用のレポートツールを使用してジャーニーを監視し、ジャーニーの有効性を測定できます。

![](assets/jo-dynamic_report_journey_12.png)

ジャーニーレポートについて詳しくは、[この節](../reports/live-report.md)を参照してください。

>[!NOTE]
>
>**ライブ** ジャーニーを変更する必要がある場合は、ジャーニーの [ 新しいバージョンを作成 ](journey-ui.md#journey-versions) します。
