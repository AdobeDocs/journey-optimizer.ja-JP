---
solution: Journey Optimizer
product: journey optimizer
title: ライセンス使用状況ダッシュボード
description: Journey Optimizer ライセンス使用状況ダッシュボードについて説明します
feature: Audiences, Profiles
topic: Content Management
role: User
level: Beginner
exl-id: 7e91face-c8f4-4e70-9123-9e36bae7e67e
source-git-commit: db1e4ee5b2b4bb3a3d7d9e86aded14ad3c613765
workflow-type: tm+mt
source-wordcount: '795'
ht-degree: 17%

---

# ライセンス使用状況ダッシュボード {#license-usage}

[!DNL Adobe Journey Optimizer] [ユーザーインターフェイス](../start/user-interface.md)は、毎日のスナップショットでキャプチャされた、組織のライセンス使用状況に関する重要な情報を表示するダッシュボードを提供します。

このダッシュボードにアクセスするには、**[!UICONTROL 管理]**／**[!UICONTROL ライセンスの使用状況]**&#x200B;に移動します。これにより、ダッシュボードに表示される「**[!UICONTROL 概要]**」タブが開きます。

![ライセンス使用状況ダッシュボードの概要](assets/license-usage-dashboard.png)

>[!NOTE]
>
>* ダッシュボードを表示するには、[ライセンス使用状況ダッシュボードを表示](https://experienceleague.adobe.com/docs/experience-platform/dashboards/permissions.html?lang=ja#available-permissions){target="_blank"}権限を付与されている必要があります。
>
>* 開発サンドボックスの場合、割り当て量列に `N/A` と示されるので、特定の指標（例：計算時間、メールなど）は表示されません。ダッシュボードには、null 以外の値のみが表示されます。指標がゼロまたはゼロに近い場合、これらの値は入力されません。


[!DNL Adobe Journey Optimizer] えば、ダッシュボードでは、**エンゲージメント可能なプロファイル** の数を確認できます。

## エンゲージメントプロファイルとは {#what-is-engageable-profile}

**エンゲージメント可能なプロファイル** は、プロファイルサービスに保存され、ジャーニーやキャンペーンによってエンゲージメントされた個人を表す情報のレコードです。

エンゲージメント可能なプロファイルの主な特徴：

* **12 か月のローリングウィンドウ**：エンゲージメント可能なプロファイルは、過去 12 か月のエンゲージメントに基づいてカウントされます。 この指標は、Journey Optimizerのオーサリング、意思決定、配信、実験またはオーケストレーションの機能を使用してエンゲージしようとした一意のプロファイルの数を示します。

* **サンドボックスあたりのユニーク数**：プロファイルが 1 つのサンドボックス内に複数のジャーニーまたはキャンペーンにエントリする場合、そのサンドボックスの単一のエンゲージメント可能なプロファイルとして 1 回だけカウントされます。

* **アドレス可能なオーディエンスに基づく**：エンゲージメント可能なプロファイルは、アドレス可能なオーディエンスから計算されます。 このカウントは、アドレス可能なオーディエンスの合計のうち、任意のJourney Optimizer機能を使用して過去 12 か月にエンゲージしたオーディエンスを表します。

* **指標動作**：エンゲージメント可能なプロファイル数：
   * ジャーニーやキャンペーンを通じて新しいプロファイルが関与する際に増加する可能性があります
   * 12 か月以上、特定のプロファイルとのエンゲージメントがない限り、減らすことはできません
   * 偽名プロファイルが既知のプロファイルにステッチされると、減少する可能性があります

>[!NOTE]
>
>エンゲージメント可能なプロファイル数が突然急増した場合は、以下の [ トラブルシューティングの節 ](#troubleshooting-engageable-profiles) で、問題の理解と解決に関する詳細なガイダンスを参照してください。

## トラブルシューティング：エンゲージメントプロファイル数の大幅な増加 {#troubleshooting-engageable-profiles}

エンゲージメント可能なプロファイル数が突然スパイクされた場合（例えば、プロファイルの数が 1 日で数十万から数百万に増えた場合）、この節では、問題を理解し対処するためのガイダンスを提供します。

### 増加について

「エンゲージメント可能なプロファイル」指標は、過去 12 か月間にジャーニーまたはキャンペーンによってエンゲージメントされた一意のプロファイルの数を反映します。 突然の増加は、以下の原因で起こる可能性があります。

* 新しいジャーニーまたはキャンペーンのターゲットとなる大きなオーディエンス
* プロファイルサービスに対して有効なデータセットの変更
* 最近エンゲージしていないオーディエンスのバッチ処理

### 解決手順

この問題に対処するには、次の手順に従います。

1. **プロファイルカウントロジックについて：**

   * エンゲージメント可能なプロファイルは、過去 12 か月間にジャーニーまたはキャンペーンによってエンゲージメントされた一意のプロファイルに基づいて計算されます。
   * プロファイルが複数のジャーニーにエントリすると、そのサンドボックスに対する 1 つのエンゲージメント可能なプロファイルとしてカウントされます。
   * 指標を減らすには、特定のプロファイルとのエンゲージメントが 12 か月以上存在しない場合や、偽名プロファイルが既知のプロファイルにステッチされている場合を除きます。
   * エンゲージメント可能なプロファイルは、顧客のアドレス可能なオーディエンスを使用して計算されます。
   * アドレス可能なオーディエンスの合計のうち、過去 12 か月にJourney Optimizerの機能のいずれかを使用してエンゲージメントしたオーディエンスが、エンゲージメント可能なプロファイルの数を決定します。

2. **大規模なオーディエンスをターゲットにしたジャーニー、キャンペーンおよび決定を調査します。**

   * [ エンゲージメントプロファイルクエリ ](../reports/query-examples.md#engageable-profiles-queries) または [ クエリサービス ](https://experienceleague.adobe.com/ja/docs/experience-platform/query/home){target="_blank"} を使用して、多数のプロファイルをターゲットにした最近のジャーニーやキャンペーンをレビューします。
   * プロファイル数の急増に貢献した特定のジャーニーバージョンを識別します。
   * 新しいプロファイルを含むジャーニー、キャンペーン、決定は、ジャーニーデータセットのイベント数の増加を招き、エンゲージメント可能なプロファイル数の増加の一因となる可能性があります。

3. **ジャーニーレベルとキャンペーンレベルでのオーディエンスのフィルタリング：**

   * ジャーニーやキャンペーンを開始する前にオーディエンスレベルでフィルターを適用して、エンゲージメント可能なプロファイルの不要な増加を防ぎます。
   * エンゲージメント中に、関連するオーディエンスのみをターゲットにします。

4. **アドレス可能なオーディエンスサイズの削減：**

   * 必要に応じて、偽名プロファイルを削除します。 この操作は、Journey OptimizerとReal-Time Customer Data Platformの両方に影響することに注意してください。
   * [ 偽名プロファイルデータの有効期限 ](https://experienceleague.adobe.com/ja/docs/experience-platform/profile/pseudonymous-profiles){target="_blank"} について詳しくは、リアルタイム顧客プロファイルガイドを参照してください。
   * **メモ：** 偽名プロファイルデータの有効期限は、Platform UI または API を使用して設定することはできません。 この機能を有効にするには、サポートに連絡する必要があります。

5. **データセットの変更の監視：**

   * プロファイルが有効になっているデータセットを検証し、過剰な ECID （Experience Cloud ID）が含まれていないことを確認します。
   * 必要に応じて、ECID 数の多いデータセットを削除し、削減されたレコードで再作成します。

6. **長期的な削減戦略の策定：**

   * 特定のプロファイルが 12 か月以上エンゲージメントされていない状態が続くと、エンゲージメント可能なプロファイルの数が自然に減ります。

**関連トピック：**

* [ エンゲージメントプロファイルクエリの例 ](../reports/query-examples.md#engageable-profiles-queries) - エンゲージメント可能なプロファイルを監視および分析するサンプルクエリ
* [Adobe Experience Platform クエリサービスの概要 ](https://experienceleague.adobe.com/ja/docs/experience-platform/query/home){target="_blank"}

## 関連ドキュメント {#related-documentation}

詳しくは、Adobe Experience Platform ドキュメントを参照してください。

* [ライセンス使用状況ダッシュボードの概要](https://experienceleague.adobe.com/docs/experience-platform/dashboards/guides/license-usage.html?lang=ja){target="_blank"}
* [ライセンス使用状況ダッシュボードの確認](https://experienceleague.adobe.com/docs/experience-platform/dashboards/guides/license-usage.html?lang=ja#exploring-the-license-usage-dashboard){target="_blank"}
* [使用可能な指標](https://experienceleague.adobe.com/docs/experience-platform/dashboards/guides/license-usage.html?lang=ja#available-metrics){target="_blank"}
* [ 偽名プロファイルデータの有効期限 ](https://experienceleague.adobe.com/docs/experience-platform/profile/pseudonymous-profiles.html?lang=ja){target="_blank"}
