---
solution: Journey Optimizer
product: journey optimizer
title: 別のサンドボックスへジャーニーをコピー
description: ジャーニーを別のサンドボックスにコピーする方法を説明します
feature: Journeys, Sandboxes
topic: Content Management
role: User, Developer
level: Experienced
keywords: サンドボックス, ジャーニー, コピー, 環境
exl-id: 8c63f2f2-5cec-4cb2-b3bf-2387eefb5002
version: Journey Orchestration
source-git-commit: 6f7b9bfb65617ee1ace3a2faaebdb24fa068d74f
workflow-type: tm+mt
source-wordcount: '120'
ht-degree: 100%

---

# 別のサンドボックスへジャーニーをコピー {#copy-to-sandbox}

<!--
>[!CONTEXTUALHELP]
>id="ajo_journey_copy_main"
>title="Copy a journey to another sandbox"
>abstract="Journey Optimizer allows you to copy an entire journey from one sandbox to another. For example, you can copy a journey from the Stage sandbox environment to your Production sandbox. In addition to the Journey itself, Journey Optimizer also copies most of the objects the journey depends on."

>[!CONTEXTUALHELP]
>id="ajo_journey_copy_sandbox_details"
>title="Sandbox details"
>abstract="Select the destination sandbox you want to copy the journey to. Only sandboxes within your organization are available."

>[!CONTEXTUALHELP]
>id="ajo_journey_copy_object_details"
>title="Object details"
>abstract="This is the journey you are going to copy."

>[!CONTEXTUALHELP]
>id="ajo_journey_copy_dependent_objects"
>title="Dependent objects"
>abstract="This is the list of associated objects used in the journey. This list displays the name, the object type, as well as the internal Journey Optimizer ID."
-->

Journey Optimizer では、1 つのサンドボックスから別のサンドボックスにジャーニー全体をコピーできます。例えば、ステージサンドボックス環境から実稼動サンドボックスにジャーニーをコピーできます。

Journey Optimizer では、ジャーニー自体に加えて、ジャーニーに必要なほとんどのオブジェクト（オーディエンス、スキーマ、イベントおよびアクション）もコピーします。

コピープロセスは、ソースサンドボックスとターゲットサンドボックス間の&#x200B;**パッケージの書き出しおよび読み込み**&#x200B;を介して実行されます。オブジェクトを書き出してターゲットサンドボックスに読み込む方法について詳しくは、[別のサンドボックスへのオブジェクトのコピー](../configuration/copy-objects-to-sandbox.md)の節を参照してください。
