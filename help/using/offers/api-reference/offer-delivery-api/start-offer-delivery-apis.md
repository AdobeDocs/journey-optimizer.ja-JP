---
title: オファー配信 Api について学習します。
description: パーソナライズされた機能を提供するために使用できる Api について詳しく説明しています。
feature: Offers
topic: Integrations
role: Data Engineer
level: Experienced
exl-id: 7bc1a4ec-113c-4af7-b549-ee17b843b818
source-git-commit: bf738ebac09d5c852872a8ea85f6532ad9d4222d
workflow-type: tm+mt
source-wordcount: '442'
ht-degree: 0%

---

# オファー配信 Api について学習します。 {#about-decisioning-apis}

Decisioning **また** は Edge Decisioning **API を使用して** 、オファーを配信することができます。さらに、Batch Decisioning **API を使用すると、特定のセグメントに含まれるすべてのプロファイルに対して** 、1回の呼び出しでオファーを配信できます。セグメント内の各プロファイルのオファーコンテンツは、Adobe エクスペリエンスプラットフォームデータセットに配置されます。カスタムバッチワークフローで使用できます。

このページには、Decisioning **および** Edge Decisioning **api で** 使用可能な特定の機能に関する情報が記載されています。どちらの方法でも、顧客に製品を提供することができます。また、Decisioning **API を使用することをお勧めします。これを使用すると、受信時にはエッジを使用し、プラットフォーム上では** レーテンシーとスループットが向上します。

|  | 要求数/秒 | 期間 |
|---|---|---|
| Decisioning API | 2000 | &lt;500ms |
| Edge Decisioning API | 5000 | &lt;250ms |

Api の操作方法について詳しくは、次の項を参照してください。
* [Decisioning API](decisioning-api.md)
* [Edge Decisioning API](edge-decisioning-api.md)
* [Batch Decisioning API](batch-decisioning-api.md)

## Edge Decisioning API の機能 {#edge}

**経験イベントと decisioning 要求に対する一意の要求**

Edge Decisioning API を使用して、2つの異なる要求を使用するのではなく、エクスペリエンスイベント自体を Decisioning 要求と共に1つの要求で送信することができます。

例えば、ユーザーが web サイトを訪問した場合、その要求には、ユーザーによるページへのアクセスが含まれています。また、訪問したページにデータを入力するためのキャンペーンが表示されます。

**Adobe エクスペリエンスプラットフォームへのコンテキストデータの保存**

Context データは、オファーが必要なときにのみわかっているデータのことを意味します。 例えば、購入した記事の色や購入時の気象などを設定できます。

Edge Decisioning API 要求でコンテキストデータを渡すと、データは Adobe エクスペリエンスプラットフォームプロファイルに格納され、将来の再利用が可能になります。

>[!NOTE]
>
>Context データが格納されるようにするには、専用の XDM スキーマが設定されている必要があります。

## Decisioning API の機能 {#decisioning}

以下に示す機能は、Decisioning API を使用した場合にのみ使用できます。 必要に応じて、それらのいずれかを利用する必要がある場合は、Decisioning API を使用してください。 それ以外の場合は、Edge Decisioning Api を使用することをお勧めします。

* ****&#x200B;エクスペリエンスイベント: エクスペリエンスイベントを利用して、decisioning ルールを作成します。
* **コンテンツと特性** の提供: 専用のオプションを使用して、コンテンツや特性を返すことはできません。
* **「メタデータ** を提供する」: オファーのメタデータを返すオプションを有効にします。
* **マージポリシー** : サンドボックスに関連付けられたものとは異なるマージポリシーを要求したときに使用します。
* **Decisioning イベントと周波数上限** : Decisioning イベントのブロックは、発生する頻度によってカウントされません。
* **命題** が重複している場合: 「deduplicate」というオプションは使用できません。
