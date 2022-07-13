---
title: オファー配信 API の概要
description: パーソナライズされたオファーを配信するために使用できる API について詳しく説明します。
feature: Offers
topic: Integrations
role: Data Engineer
level: Experienced
exl-id: 7bc1a4ec-113c-4af7-b549-ee17b843b818
source-git-commit: bf738ebac09d5c852872a8ea85f6532ad9d4222d
workflow-type: tm+mt
source-wordcount: '442'
ht-degree: 85%

---

# オファー配信 API の概要 {#about-decisioning-apis}

**Decisioning** API または **Edge Decisioning** API のいずれかを使用してオファーを配信できます。また、 **バッチ判定** API を使用すると、特定のセグメント内のすべてのプロファイルに対して、1 回の呼び出しでオファーを配信できます。 セグメント内の各プロファイルに対するオファーコンテンツは、Adobe Experience Platform データセットに配置され、カスタムバッチワークフローで使用できます。

このページでは、 **判定** および **Edge Decisioning** API どちらでも顧客にオファーを配信することができますが、インバウンドのユースケースにはできるだけ **Edge Decisioning** API を使用し、プラットフォームでの待ち時間とスループットを改善することをお勧めします。

|  | 1 秒あたりのリクエスト数 | 待ち時間 |
|---|---|---|
| Decisioning API | 2,000 | &lt;500 ms |
| Edge Decisioning API | 5,000 | &lt;250 ms |

API の使用方法について詳しくは、次の節を参照してください。
* [判定 API](decisioning-api.md)
* [Edge 判定 API](edge-decisioning-api.md)
* [Batch Decisioning API](batch-decisioning-api.md)

## Edge Decisioning API の機能 {#edge}

**エクスペリエンスイベントと決定リクエストについての一意のリクエスト**

Edge Decisioning API を使用すると、エクスペリエンスイベント自体と決定リクエストを、2 つの異なるリクエストではなく、まとめて 1 つのリクエストで送信できます。

例えば、顧客が web サイトを訪問した場合、リクエストにはエクスペリエンスイベント（顧客のページへの訪問）が含まれ、訪問したページに入力するためのオファーが返されます。

**Adobe Experience Platform へのコンテキストデータの格納**

コンテキストデータは、オファーを返す際にしか分からないデータを指します。例えば、購入した商品の色、購入時の天気などです。

Edge Decisioning API リクエストでコンテキストデータを渡す場合、データは Adobe Experience Platform プロファイルに保存され、後で再利用できるようになります。

>[!NOTE]
>
>コンテキストデータを保存するには、専用の XDM スキーマを設定する必要があります。

## Decisioning API の機能 {#decisioning}

以下に示す機能は、Decisioning API でのみ使用できます。要件を満たすためにこれらのいずれかを利用する必要がある場合は、Decisioning API を使用します。それ以外の場合は、Edge Decisioning API を使用することをお勧めします。

* **エクスペリエンスイベント**：エクスペリエンスイベントを利用して決定ルールを作成します。
* **オファーのコンテンツと特性**：専用オプションを使用して、オファーのコンテンツや特性を返さないように選択できます。
* **オファーメタデータ**：オファーのメタデータを返すオプションを有効にします。
* **結合ポリシー**：サンドボックスに関連付けられたものとは異なる結合ポリシーをリクエストで使用します。
* **決定イベントとフリークエンシーキャップ**：発生するフリークエンシーキャップによって決定イベントがカウントされないようにします。
* **提案の重複**：提案の重複を排除しないオプションを有効にします。
