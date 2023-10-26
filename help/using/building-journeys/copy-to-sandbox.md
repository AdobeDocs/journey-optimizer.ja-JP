---
solution: Journey Optimizer
product: journey optimizer
title: 別のサンドボックスへのジャーニーのコピー
description: ジャーニーを別のサンドボックスにコピーする方法を説明します
feature: Journeys, Sandboxes
topic: Content Management
role: User, Developer, Data Engineer
level: Experienced
keywords: サンドボックス, ジャーニー, コピー, 環境
exl-id: 8c63f2f2-5cec-4cb2-b3bf-2387eefb5002
source-git-commit: a6b2c1585867719a48f9abc4bf0eb81558855d85
workflow-type: tm+mt
source-wordcount: '612'
ht-degree: 39%

---

# 別のサンドボックスへのジャーニーのコピー {#copy-to-sandbox}

<!--
>[!CONTEXTUALHELP]
>id="ajo_journey_copy_main"
>title="Copy a journey to another sandbox"
>abstract="Journey Optimizer allows you to copy an entire journey from one sandbox to another. For example, you can copy a journey from the Stage sandbox environment to your Production sandbox. In addition to the Journey itself, Journey Optimizer also copies most of the objects the journey depends on."

>[!CONTEXTUALHELP]
>id="ajo_journey_copy_sandbox_details"
>title="Sandbox details"
>abstract="Select the destination sandbox you want to copy the journey to. Only sandboxes within your organization are available."

>[!CONTEXTUALHELP]
>id="ajo_journey_copy_object_details"
>title="Object details"
>abstract="This is the journey you are going to copy."

>[!CONTEXTUALHELP]
>id="ajo_journey_copy_dependent_objects"
>title="Dependent objects"
>abstract="This is the list of associated objects used in the journey. This list displays the name, the object type, as well as the internal Journey Optimizer ID."
-->

サンドボックスツールを使用すると、パッケージのエクスポートとインポートを活用して、複数のサンドボックスにまたがってオブジェクトをコピーできます。 パッケージは、1 つのオブジェクトまたは複数のオブジェクトで構成できます。 パッケージに含まれるオブジェクトは、同じサンドボックスからのものである必要があります。

このページでは、Journey Optimizerのコンテキストでのサンドボックスツールの使用例について説明します。 機能自体について詳しくは、 [Experience Platform文書](https://experienceleague.corp.adobe.com/docs/experience-platform/sandbox/ui/sandbox-tooling.html).

## サンドボックスツールの概要{#sandbox-gs}

Journey Optimizer では、1 つのサンドボックスから別のサンドボックスにジャーニー全体をコピーできます。例えば、ステージサンドボックス環境から実稼動サンドボックスにジャーニーをコピーできます。ジャーニー自体に加えて、Journey Optimizerでは、ジャーニーが依存するオブジェクト（オーディエンス、スキーマ、イベント、アクション）のほとんどがコピーされます。 コピーされたオブジェクトについて詳しくは、この[節](https://experienceleague.adobe.com/docs/experience-platform/sandbox/ui/sandbox-tooling.html#abobe-journey-optimizer-objects)を参照してください。

>[!CAUTION]
>
>リンクされたすべての要素が宛先サンドボックスにコピーされるとは限りません。ジャーニーを公開する前に、徹底的に確認することを強くお勧めします。これにより、見つからない可能性のあるオブジェクトを識別できます。

ターゲットサンドボックスにコピーされたオブジェクトは一意で、既存の要素が上書きされるリスクはありません。ジャーニーとジャーニー内のあらゆるメッセージは、両方ともドラフトモードで引き継がれます。これにより、ターゲットサンドボックスで公開する前に、徹底的な検証を実行できます。コピープロセスでは、ジャーニーとそのジャーニー内のオブジェクトに関するメタデータのみをコピーします。プロファイルまたはデータセットのデータは、このプロセスの一環としてコピーされません。

## ジャーニーを書き出す {#export}

ジャーニーを別のサンドボックスにコピーするには、次の手順に従います。

1. 「ジャーニー管理」メニューセクションで、「**[!UICONTROL ジャーニー]**」をクリックします。ジャーニーのリストが表示されます。

1. コピーするジャーニーを検索し、 **その他のアクション** アイコン（ジャーニー名の横の 3 つのドット）をクリックし、 **パッケージに追加**.

![](assets/journey-sandbox1.png)

The **パッケージに追加** ウィンドウが表示されます。

![](assets/journey-sandbox2.png)

1. 既存のパッケージにジャーニーを追加するか、新しいパッケージを作成するかを選択します。

   * **既存のパッケージ**：ドロップダウンメニューからパッケージを選択します。
   * **新しいパッケージを作成**：パッケージ名を入力します。 説明を追加することもできます。

1. [ 管理 ] メニューセクションで、 **[!UICONTROL サンドボックス]**&#x200B;を選択し、 **パッケージ** 」タブをクリックし、エクスポートするパッケージをクリックします。

   ![](assets/journey-sandbox3.png)

1. 書き出すオブジェクトを選択し、 **公開**

   ![](assets/journey-sandbox4.png)

   公開が失敗した場合は、ログを確認して失敗の理由を特定できます。 パッケージを開き、「 **失敗したジョブを参照**、インポートジョブを選択して、 **インポートの詳細を表示**.

   ![](assets/journey-sandbox9.png)

## ジャーニーをインポート {#export}

1. パッケージリストで、パッケージ名の横にある「+」アイコンをクリックします。

   ![](assets/journey-sandbox5.png)

1. を選択します。 **ターゲットサンドボックス** ドロップダウンフィールドから、「 」を選択し、 **次へ**. 組織内のサンドボックスのみ使用できます。

   ![](assets/journey-sandbox6.png)

1. パッケージオブジェクトと依存関係を確認します。 これは、ジャーニーで使用される関連オブジェクトのリストです。このリストには、名前とオブジェクトタイプが表示されます。 各オブジェクトに対して、新しいオブジェクトを作成するか、ターゲットサンドボックス内の既存のオブジェクトを使用するかを選択できます。

   ![](assets/journey-sandbox7.png)

1. 次をクリック： **完了** ボタン（右上隅）を使用して、パッケージのターゲットサンドボックスへのコピーを開始します。 コピー処理は、ジャーニーの複雑さや、コピーする必要のあるオブジェクトの数によって異なります。

1. インポートジョブをクリックして、コピー結果を確認します。

   * クリック **インポートしたオブジェクトの表示** コピーした個々のオブジェクトを表示します。
   * クリック **インポートの詳細を表示** をクリックして、各オブジェクトのインポート結果を確認します。

   ![](assets/journey-sandbox8.png)

1. ターゲットサンドボックスにアクセスし、コピーしたすべてのオブジェクトを徹底的に確認します。
