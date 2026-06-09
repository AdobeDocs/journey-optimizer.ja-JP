---
solution: Journey Optimizer
product: journey optimizer
title: コスト最適化の SMS のベストプラクティス
description: Journey Optimizer で文字数制限、エンコーディング、パーソナライゼーションを管理して、SMS メッセージのコストを最適化する方法について説明します
feature: SMS
topic: Content Management
role: User
level: Intermediate
exl-id: c8c156da-8482-4932-9c15-45ab83c173e7
TQID: https://experienceleague.adobe.com/ccUbyMiVNBULBlaYAb-z6-WFGcWURtmelyKUy7v2g2o
product_v2: id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2: id: d0a62d3c-b79e-47e4-929e-40ef3cffa037
subfeature_v2: id: b3b09fe1-10f1-4793-9f6b-1ca0269eebe7id: b3a93754-a8b8-46eb-9421-7eccaeeb3dff
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: cdd65e7e-8839-44a2-bc21-0e03623b5dd1id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: a4e4f5ca5c3eb9dbfb5691cb5de420009ed7e5a5
workflow-type: tm+mt
source-wordcount: 545
ht-degree: 97%

---

# SMS コスト最適化のベストプラクティス {#sms-cost-optimization}

SMS メッセージは通常、メッセージあたり 160 文字の制限に基づいてプロバイダーにより課金されます。 メッセージが複数の部分に分割されている場合、SMS メッセージの送信には追加コストが発生することがあります。

メッセージ戦略を最適化し、費用を削減するには、次のガイドラインに従ってください。

## メッセージを簡潔にする {#keep-messages-short}

Journey Optimizer では、SMS メッセージ本文に最大 1,500 文字まで使用できます。 この制限を超えると警告が表示され、このしきい値を超えるメッセージによりエラーがトリガーされます。

ほとんどの SMS プロバイダーは、GSM 7 ビットエンコーディングをサポートし、1 つの SMS に最大 160 文字を含めることができます。 この長さを超えるメッセージは、自動的に次の複数の SMS 部分に分割されます（連結）。

* **160 文字未満**：1 つの SMS 部分
* **161～306 文字**：2 つの SMS 部分
* **307～459 文字**：3 つの SMS 部分

**コストを最小限に抑えるには**、メッセージを 160 文字未満に保持し、1 つの SMS 部分として課金されるようにします。

例えば、1,600 文字のメッセージは、Journey Optimizer では 1 つのメッセージとして表示されますが、10 個の SMS クレジットを消費する可能性があります。

## 長さを増やす特殊文字を回避 {#avoid-special-characters}

`| ^ &euro; { } [ ] ~ \` などの特定の文字は、GSM エンコーディングでは 2 文字としてカウントされます。 これらの文字を含めると、メッセージが **160 文字の制限**&#x200B;をすぐに超える場合があります。

## UCS-2 エンコーディングを防ぐ {#prevent-ucs2-encoding}

メッセージに中国語やアラビア語のテキスト、商標記号、リッチフォーマットツールからのハード改行など、GSM 以外の文字が含まれている場合、メッセージはプロバイダーにより UCS-2 を使用してエンコードされます。UCS-2 では、SMS あたり 70 文字のみがサポートされます。

UCS-2 エンコーディングを使用すると、文字数が増加し、その結果、サービスプロバイダーへのメッセージ課金に影響する場合があります。

例えば、200 文字の Unicode メッセージは、3 つの SMS 部分で配信されます。

## オーサリングのベストプラクティス {#authoring-best-practices}

最終的な SMS メッセージを Journey Optimizer 内で直接作成するか、プレーンテキストアプリケーションからペーストします。

UCS-2 エンコーディングをトリガーする非表示文字や改行が導入されることにより、SMS 部分の数と関連コストが増加する可能性があるので、リッチテキストアプリケーションの使用を回避します。

## 送信前に文字カウントを確認 {#check-character-count}

プレーンテキストアプリケーションまたは&#x200B;**[!UICONTROL コンテンツをシミュレート]**&#x200B;のいずれかのシミュレーションメソッドを使用して、文字数を検証します。

Journey Optimizer では、コンテンツのシミュレーション中にスペースを含む文字カウントが表示されますが、次の点に注意してください。

* 動的パーソナライゼーションを通じて生成した文字や、特定の特殊文字は含まれ&#x200B;**ません**。

* **x/1500 カウント**&#x200B;は、メッセージごとの制限（例えば、160 文字の GSM 7 ビット制限）ではなく、技術的なペイロード制限の視覚的なインジケーターとして機能します。

* アドビでは、エディターで UTF-8 エンコーディングをサポートしていますが、これは GSM 7 ビットエンコーディングとは異なります。

## レポートについて {#understanding-reporting}

**Journey Optimizer レポート**&#x200B;では、SMS 部分に関係なく、メッセージ全体を 1 回の送信としてカウントします。

**プロバイダーレポート**&#x200B;には、配信に使用される SMS メッセージ部分の実際の数が反映されており、課金と潜在的な超過分を確認するために参照する必要があります。 アドビが Sinch 経由の SMS プロバイダーである場合は、この課金レポートを月単位で個別に受け取ります。

## パーソナライゼーションの考慮事項 {#personalization-considerations}

動的なパーソナライゼーションにより、メッセージの長さが増える場合があります。 例えば、変数の代わりに長い名を使用すると、文字数が追加されることがあります。

## その他のリソース {#additional-resources}

サポートされる文字とエンコーディングルールの確認について詳しくは、[Sinch 文字サポートガイド](https://developers.sinch.com/docs/sms/resources/message-info/character-support/)を参照してください
