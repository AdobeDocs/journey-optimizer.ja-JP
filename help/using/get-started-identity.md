---
title: Journey OptimizerでのIDの使用の手引き
description: Adobe Journey OptimizerでIDを管理する方法を説明します
feature: プロファイル
role: User
level: Beginner
source-git-commit: b07970ff11f1ba7c4e6db30dc2eca1252a579ca4
workflow-type: tm+mt
source-wordcount: '349'
ht-degree: 28%

---

# IDの概要 {#identities-gs}

ID とは、エンティティ（通常は個人）に固有のデータです。ログイン ID、ECID、ロイヤリティ ID などの ID は、既知の ID と呼ばれます。

電子メールアドレスや電話番号などの個人を特定できる情報(PII)は、顧客を直接特定する役割を果たします。 その結果、PIIは、複数のシステムをまたいで顧客の複数のIDを照合するために使用されます。

[!DNL Adobe Journey Optimizer]、**ID**&#x200B;では、デバイスやチャネルをまたいで消費者をリンクします。結果は、[IDグラフ](#id-graph)になります。 リンクされたIDグラフは、すべてのビジネスタッチポイントにわたるインタラクションに基づいてエクスペリエンスをパーソナライズするために使用します。

![](assets/identities-home.png)

**IDサービス**&#x200B;について詳しくは、[このドキュメント](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=ja){target=&quot;_blank&quot;}を参照してください。

## ID 名前空間

**** ID 名前空間は、ID が関連するコンテキストのインジケーターとして機能する ID サービスのコンポーネントです。例えば、`name@email.com`の値を電子メールアドレスとして、または`443522`を数値CRM IDとして区別します。 ID 名前空間を使用するには、関連する様々な Adobe Experience Platform サービスについて理解している必要があります。名前空間の使用を開始する前に、次のサービスのドキュメントを確認してください。

**ID名前空間**&#x200B;について詳しくは、[このドキュメント](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html?lang=ja){target=&quot;_blank&quot;}を参照してください。

## ID グラフ{#id-graph}

**IDグラフ**&#x200B;は、特定の顧客の異なるID間の関係のマップで、顧客が様々なチャネルをまたいでブランドとどのようにやり取りするかを視覚的に示します。 すべての顧客IDグラフは、顧客の行動に応じて、ほぼリアルタイムでAdobe Experience Platform IDサービスで管理および更新されます。

[!DNL Adobe Journey Optimizer]ユーザーインターフェイスのIDグラフビューアを使用すると、顧客IDが結び付けられる方法と方法を視覚化し、より深く理解できます。 ビューアを使用すると、グラフの様々な部分をドラッグおよび操作でき、複雑なIDの関係を調べたり、デバッグをより効率的に実行したり、情報の利用方法に関する透明性を高めたりできます。

**IDグラフ**&#x200B;について詳しくは、[このドキュメント](https://experienceleague.adobe.com/docs/experience-platform/identity/ui/identity-graph-viewer.html){target=&quot;_blank&quot;}を参照してください。

