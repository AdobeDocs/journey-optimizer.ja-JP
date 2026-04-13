---
solution: Journey Optimizer
product: journey optimizer
title: 分岐アクティビティの使用
description: 調整されたキャンペーンでの分岐アクティビティの使用方法について説明します。
exl-id: 52e8057b-dac1-45f5-9dd0-1b28a59adde9
version: Campaign Orchestration
source-git-commit: 07ec28f7d64296bdc2020a77f50c49fa92074a83
workflow-type: tm+mt
source-wordcount: '139'
ht-degree: 100%

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

1. 各アウトバウンドトランジションにラベルを割り当てます。デフォルトでは、2 つのトランジションが指定されています。

1. トランジションを削除するには、「![](../assets/do-not-localize/Smock_Delete_18_N.svg)」アイコンをクリックします。

1. 必要に応じて、「**[!UICONTROL トランジションを追加]**」をクリックして、さらにアウトバウンドトランジションを追加します。
