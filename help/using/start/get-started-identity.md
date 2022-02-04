---
title: Journey Optimizer における ID の基本を学ぶ
description: Adobe Journey Optimizer で ID を管理する方法を説明します
feature: Profiles
role: User
level: Beginner
exl-id: 90e892e9-33c2-4da5-be1d-496b42572897
source-git-commit: 2088b5ba2ec77e56644683e118e734acfe6707fc
workflow-type: tm+mt
source-wordcount: '348'
ht-degree: 100%

---

# ID の基本を学ぶ {#identities-gs}

ID とは、エンティティ（通常は個人）に固有のデータです。ログイン ID、ECID、ロイヤルティ ID などの ID は、既知の ID と呼ばれます。


メールアドレスや電話番号などの個人を特定できる情報（PII）は、顧客を直接識別する役割を果たします。その結果、PII は、システム間で顧客の複数の ID を照合するために使用されます。

 [!DNL Adobe Journey Optimizer] では、**ID** はデバイスやチャネルをまたいで消費者をリンクします。その結果が [ID グラフ](#id-graph)になります。 リンクされた ID グラフは、すべてのビジネスタッチポイントにわたるインタラクションに基づいてエクスペリエンスをパーソナライズするために使用します。

![](../assets/identities-home.png)

**ID サービス**&#x200B;について詳しくは、[このドキュメント](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=ja){target=&quot;_blank&quot;}を参照してください。

## ID 名前空間 {#identity-namespaces}

**ID 名前空間** は、ID の関連先コンテキストのインジケーターとして機能する ID サービスのコンポーネントです。例えば、`name@email.com` の値をメールアドレスとして、または `443522` を数値 CRM ID として区別します。ID 名前空間を使用するには、関連する様々な Adobe Experience Platform サービスについて理解している必要があります。名前空間の使用を開始する前に、次のサービスのドキュメントを確認してください。

**ID 名前空間**&#x200B;について詳しくは、[このドキュメント](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html?lang=ja){target=&quot;_blank&quot;}を参照してください。

## ID グラフ{#id-graph}

**ID グラフ**&#x200B;は、特定の顧客の異なる ID 間の関係のマップで、顧客が様々なチャネルでブランドとどのようにやり取りするかを視覚的に表現します。 すべての顧客 ID グラフは、顧客のアクティビティに応じて、Adobe Experience Platform ID サービスによってほぼリアルタイムで一括管理および更新されます。

[!DNL Adobe Journey Optimizer] ユーザーインターフェイスの ID グラフビューアを使用すると、スティッチされる顧客 ID とその方法を視覚化し、より深く理解できます。 このビューアを使用すると、グラフの様々な部分をドラッグおよび操作でき、ID 間の複雑な関係を調べたり、デバッグをより効率的に実行したり、情報の利用方法に関する透明性を高めたりできます。

**ID グラフ**&#x200B;について詳しくは、[このドキュメント](https://experienceleague.adobe.com/docs/experience-platform/identity/ui/identity-graph-viewer.html?lang=ja){target=&quot;_blank&quot;}を参照してください。
