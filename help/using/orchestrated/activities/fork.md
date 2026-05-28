---
solution: Journey Optimizer
product: journey optimizer
title: 分岐アクティビティの使用
description: 調整されたキャンペーンでの分岐アクティビティの使用方法について説明します。
exl-id: 52e8057b-dac1-45f5-9dd0-1b28a59adde9
version: Campaign Orchestration
TQID: https://experienceleague.adobe.com/b0FyVaM0LcSz1DLGd-UEhHqBqXMWcb0rbimJA6E7WOM
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2:
  - id: b3538224-471e-4c63-a444-9b19d89ae29c
  - id: b423a773-0a58-4a77-b65d-3dd4ae6ef841
subfeature_v2:
  - id: b5e335a9-0e5f-4dda-8845-c4ac5dca2be4
source-git-commit: 0ee10a0689d38c22b1180b197796b08a10c286cf
workflow-type: tm+mt
source-wordcount: 256
ht-degree: 54%

---

# 分岐 {#fork}

>[!CONTEXTUALHELP]
>id="ajo_orchestration_fork"
>title="「分岐」アクティビティ"
>abstract="**分岐**&#x200B;アクティビティを使用すると、アウトバウンドトランジションを作成して、複数のアクティビティを同時に開始できます。"

>[!CONTEXTUALHELP]
>id="ajo_orchestration_fork_transitions"
>title="分岐アクティビティのトランジション"
>abstract="デフォルトでは、**分岐**&#x200B;アクティビティで 2 つのトランジションが作成されます。 「**トランジションを追加**」ボタンをクリックして追加のアウトバウンドトランジションを定義し、そのラベルを入力します。"

**[!UICONTROL 分岐]**&#x200B;アクティビティは、複数のアウトバウンドトランジションを作成し、複数のアクティビティを並行して実行できる&#x200B;**[!UICONTROL フロー制御]**&#x200B;コンポーネントです。

## 分岐アクティビティの設定{#fork-configuration}

次の手順に従って、**[!UICONTROL 分岐]**&#x200B;アクティビティを設定します。

![](../assets/workflow-fork.png)

1. **[!UICONTROL 分岐]**&#x200B;アクティビティを調整されたキャンペーンに追加します。

1. **[!UICONTROL ラベル]**&#x200B;を定義します。

1. 各アウトバウンドトランジションにラベルを割り当てます。 デフォルトでは、2 つのトランジションが指定されています。

1. トランジションを削除するには、「![](../assets/do-not-localize/Smock_Delete_18_N.svg)」アイコンをクリックします。

1. 必要に応じて、「**[!UICONTROL トランジションを追加]**」をクリックして、さらにアウトバウンドトランジションを追加します。

## 例 {#fork-examples}

ここでは、**[!UICONTROL Fork]** アクティビティの一般的な使用例を示します。同じオーディエンスを2つの異なるメールチャネル（1つのマーケティングチャネルと1つのトランザクションチャネル）でターゲットにして、配信行動を比較します。

**[!UICONTROL オーディエンスを作成]** アクティビティがターゲット母集団を選択すると、**[!UICONTROL フォーク]**&#x200B;は2つの並列ブランチを作成します。

* **分岐1**&#x200B;は、マーケティングメールチャネルアクティビティに接続します。 メッセージは標準的なビジネスルールに従い、オプトインしたプロファイルにのみ送信されます。
* **分岐2**&#x200B;は、トランザクションメール チャネルアクティビティに接続します。 メッセージはビジネスルールを回避し、オプトインステータスに関係なくすべてのプロファイルに配信されます。

![](../assets/workflow-fork.png)

このパターンは、チャネルカテゴリの設定が配信動作に与える影響を理解したり、1回のキャンペーン実行で同じオーディエンスに異なるメッセージタイプを送信したりするのに役立ちます。
