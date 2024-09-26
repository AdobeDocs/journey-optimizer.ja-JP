---
solution: Journey Optimizer
product: journey optimizer
title: 別のサンドボックスへジャーニーをコピー
description: ジャーニーを別のサンドボックスにコピーする方法を説明します
feature: Journeys, Sandboxes
topic: Content Management
role: User, Developer, Data Engineer
level: Experienced
keywords: サンドボックス, ジャーニー, コピー, 環境
exl-id: 8c63f2f2-5cec-4cb2-b3bf-2387eefb5002
source-git-commit: 62b5cfd480414c898ab6f123de8c6b9f99667b7d
workflow-type: tm+mt
source-wordcount: '119'
ht-degree: 32%

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

Journey Optimizerでは、ジャーニー自体に加えて、ジャーニーに必要なオブジェクトのほとんど（オーディエンス、スキーマ、イベントおよびアクション）もコピーされます。

コピープロセスは、ソースサンドボックスとターゲットサンドボックスの間で **パッケージのエクスポートとインポート** を介して実行されます。 オブジェクトを書き出してターゲットサンドボックスに読み込む方法について詳しくは、この節を参照してください。[ 別のサンドボックスにオブジェクトをコピーする ](../configuration/copy-objects-to-sandbox.md)
