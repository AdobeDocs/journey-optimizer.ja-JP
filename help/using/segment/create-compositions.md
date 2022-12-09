---
solution: Journey Optimizer
product: journey optimizer
title: コンポジションワークフローの作成
description: コンポジションワークフローを作成して、既存の対象ユーザーを結合または配置する方法を説明します。
feature: Journeys
topic: Content Management
role: User
level: Intermediate
hide: true
hidefromtoc: true
exl-id: 8b978900-fcef-46f2-bc19-70776e4f3d43
source-git-commit: 8d56e3060e78422b028ced17f415497789908ff9
workflow-type: tm+mt
source-wordcount: '344'
ht-degree: 0%

---

# コンポジションワークフローの作成 {#create-compositions}

コンポジションワークフローを使用すると、既存の対象ユーザーを組み合わせて配置することによって、新規ユーザーを作成することができます。

## コンポジションワークフローの作成 {#create}

1. メニューに **[!UICONTROL Segments]** アクセスし、を選択 **[!UICONTROL Create Audience]** します。

1. を選択 **[!UICONTROL Compose Audience]** します。

   >[!NOTE]
   >
   >**[!UICONTROL Build rule]**&#x200B;作成方法では、セグメンテーションサービス ](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html) を使用して [ 新しいセグメント定義を作成することができます。

   ![](assets/audiences-create.png)

1. コンポジション canvas には、次の2つのデフォルトのアクティビティーが表示されます。

   * **[!UICONTROL Audience]**: コンポジションの開始点。 この方法では、ワークフローのベースとして、1つまたは複数の対象ユーザーを選択できます。

   * **[!UICONTROL Save]**: コンポジションの最後のステップです。 この操作を行うと、ワークフローの結果を新規ユーザーに保存することができます。
   コンポジションワークフロー canvas でアクティビティを設定する方法について詳しくは、「コンポジションキャンバス ](composition-canvas.md) の操作」を参照してください [ 。

1. コンポジションプロパティを開き、タイトルと説明を指定します。

   プロパティにタイトルが定義されていない場合は、コンポジションラベルが開始 **[!UICONTROL Audience]** アクティビティーの1つになります。

   ![](assets/audiences-properties.png)

1. And **[!UICONTROL Save]** アクティビティー間に必要な数の **[!UICONTROL Audience]** アクティビティーを追加することで、コンポジションを設定します。[コンポジションキャンバスの操作方法について学習します。](composition-canvas.md)

   ![](assets/audiences-publish.png)

1. コンポジションの準備ができたら、ボタンをクリック **[!UICONTROL Publish]** してコンポジションをパブリッシュし、結果のユーザーを Adobe エクスペリエンスプラットフォームに保存します。

   発行中に何らかのエラーが発生した場合は、その問題の解決方法についての情報がアラートに表示されます。

   ![](assets/audiences-alerts.png)

1. コンポジションがパブリッシュされます。 結果の対象ユーザーは Adobe エクスペリエンスプラットフォームに保存され、旅オプティマイザーのキャンペーンをターゲットとして使用できるようになりました。 [キャンペーンの操作方法について説明します。](../campaigns/get-started-with-campaigns.md)

## コンポジションへのアクセス {#access}

>[!CONTEXTUALHELP]
>id="ajo_ao_publish"
>title="参加者のパブリッシュ"
>abstract="コンポジションをパブリッシュして、結果のユーザーを Adobe エクスペリエンスプラットフォームに保存します。"

作成したすべてのコンポジションに **[!UICONTROL Compositions]** はタブからアクセスできます。 次のように複数の状態を持つことができます。

* **[!UICONTROL Draft]**: コンポジションが進行中で、パブリッシュされていません。
* **[!UICONTROL Published]**: コンポジションがパブリッシュされました。その結果、対象ユーザーは保存され、使用可能になります。
* **[!UICONTROL Archived]**: コンポジションがアーカイブされています。

![](assets/audiences-compositions.png)

>[!NOTE]
>
>リスト内の楕円ボタンを使用して、コンポジションをいつでも複製または削除することができます。

詳細情報：

* [対象ユーザー向けコンポジションの使用を開始する](get-started-audience-orchestration.md)
* [コンポジション canvas の操作](composition-canvas.md)
* [対象ユーザーへのアクセスと管理](access-audiences.md)
