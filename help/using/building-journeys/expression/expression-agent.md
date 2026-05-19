---
solution: Journey Optimizer
product: journey optimizer
title: 式アシスタントを使用した式の生成
description: Adobe Journey Optimizerの式アシスタントを使用して、自然言語プロンプトを使用してジャーニーの高度な式エディターで式を直接生成する方法を説明します。
feature: Journeys
topic: Content Management, Artificial Intelligence
role: User
level: Intermediate
badge: label="公開ベータ版" type="Informative"
mini-toc-levels: 2
hide: true
source-git-commit: 21019d3981891b2ea17857dfc15278641bbcb740
workflow-type: tm+mt
source-wordcount: '660'
ht-degree: 2%

---


# 式アシスタントを使用した式の生成 {#expression-agent}

>[!CONTEXTUALHELP]
>id="journeyExpAI"
>title="式アシスタントを使用した式の生成"
>abstract="式アシスタントは、生成AIを使用して、ジャーニーの高度な式エディターで式を直接作成および生成するのに役立ちます。 例えば、条件では、**Optimize** アクティビティ、カスタム日付を使用する&#x200B;**Wait** アクティビティなどです。 必要なものを平易な言葉で説明すると、アシスタントがそれに応じた式を生成します。"

>[!AVAILABILITY]
>
>この機能は現在&#x200B;**公開ベータ版**&#x200B;です。 リリースサイクルと可用性フェーズについて詳しくは、[Journey Optimizer リリースサイクル](../../rn/releases.md)を参照してください。
>
>式アシスタントを使用する前に、Journey Optimizerの生成AI機能に適用される関連する[ ガードレールと制限事項](../../content-management/gs-generative.md#generative-guardrails)をお読みください。

式アシスタントは、ジャーニーの高度な式エディターに組み込まれたAIを活用した機能です。 平易な言語プロンプトから有効な式を生成できます。

ジャーニー **[!UICONTROL 詳細式エディター]**&#x200B;が開いている場所で使用できます。 例えば、**[Optimize アクティビティ](../optimize.md)**&#x200B;内で条件とルーティングを設定する場合、またはカスタム日付を使用し、`dateTimeOnly`式が必要な[**[!UICONTROL Wait ]**アクティビティ ](../wait-activity.md)を設定する場合などです。

## 式の生成 {#generate}

式アシスタントを使用して式を生成するには：

1. ジャーニーで&#x200B;**[!UICONTROL 詳細式エディター]**&#x200B;を開きます。例えば、分岐条件、**[!UICONTROL 最適化]** アクティビティ、カスタム日付を持つ&#x200B;**[!UICONTROL 待機]** アクティビティなどから開きます。

   ![](../assets/expression-assistant-pane.png)

1. テキストフィールドに、生成する式を平易な言語で記述します。 例：

   * *「米国からのユーザーで18歳以上のユーザー」*
   * *「過去30日間に購入した顧客」*

   アイデアについては、このページの最後にある[例のプロンプト ](#example-prompts)を参照してください。

1. 「**[!UICONTROL 生成]**」をクリックしてプロンプトを送信します。

   アシスタントは、対応する式の生成を開始し、生成中に進行状況ステータスメッセージを表示します。

   >[!NOTE]
   >
   >アシスタントが有効な式を生成できない場合（たとえば、プロンプトが使用可能なデータソースに存在しないフィールドを参照している場合）、エラーメッセージが表示されます。 この場合は、ジャーニー設定で使用可能なフィールド名とデータソースを使用するようにプロンプトを修正してから、再度生成します。

1. 式の準備ができたら、パネルで結果を確認します。

   ![](../assets/expression-assistant-result.png)

   * 申し込む前に![ プレビューアイコン ](../assets/do-not-localize/generation-preview.svg) アイコンをクリックして、リクエストしたシナリオのアシスタント出力を確認します。

   * **[!UICONTROL 適用]**&#x200B;をクリックして、生成された式を高度な式エディター（手動で貼り付けるのと同じプレースメント）に直接挿入します。
   * コピーコントロールを使用して、推奨されるエクスプレッションテキストを取得し、必要に応じて別の場所にペーストします。

## プロンプト例 {#example-prompts}

以下のリストは、プロンプトのアイデアのみです。 生成された式の構文は表示されません。正確な出力は、ジャーニーで定義されたフィールドとアクティビティによって異なります。

### ジャーニーイベントとカスタムアクション {#example-prompts-event-action}

* *&quot;注文価格の合計が100を超えるイベント&quot;*
* *&quot;過去7日間に注文が作成されたイベント&quot;*
* *&quot;イベントタイプがコマース購入であるイベント&quot;*
* *「過去1時間に注文が作成されたイベント」*
* *&quot;注文価格の合計が200を超え、アクション応答にステータス コードがあるイベント&quot;*

### アクティビティ式を待つ {#example-prompts-datetime}

**[!UICONTROL 待機]** アクティビティでカスタム日付を使用する場合、**[!UICONTROL 詳細式エディター]**&#x200B;で`dateTimeOnly`式を作成して、プロファイルを続行するタイミングを定義します。 例えば、プロファイル属性、イベントタイムスタンプ、セグメントの選定データ、または現在の時間からの計算されたオフセットなどです。 カスタム待機と適用可能な制限の設定方法については、[ カスタム待機](../wait-activity.md#custom)を参照してください。

* *「顧客の最終注文日を日時としてのみ使用」*
* *&quot;同意メール時間を日時としてのみ使用&quot;*
* *&quot;セグメント メンバーシップの最終選定時刻を日時に変換する&quot;*
* *&quot;待機ノード：2024年クリスマス後1週間を日付時間としてのみ&quot;*
* *「待機ノード：現在から30日後の午後10時（日付時間のみ）」*
* *「UTC タイムゾーンで今日の午前9時まで待ちます。日付の時刻としてのみ返します」*

## 関連リソース {#related}

* [高度な式エディターの操作](expressionadvanced.md) – 式エディターのインターフェイスとサポートされている構文の概要。
* [Journey OptimizerのAI アシスタントの基本を学ぶ](../../content-management/gs-generative.md) – 生成AI機能の一般的なガードレール、アクセス、設定。
