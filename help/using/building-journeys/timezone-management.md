---
solution: Journey Optimizer
product: journey optimizer
title: タイムゾーン管理
description: タイムゾーン管理について
feature: Journeys
topic: Content Management
role: User
level: Intermediate
exl-id: 3bcc08d6-1210-4ff9-92f4-edee8285b469
source-git-commit: 021cf48ab4b5ea8975135a20d5cef8846faa5991
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 0%

---

# タイムゾーン管理 {#timezone_management}

このような場合は、 [ フライトのプロパティ ](../building-journeys/journey-gs.md#change-properties) でタイムゾーンを定義することができます。

旅のプロパティにアクセスするには、画面の右上にある鉛筆アイコンをクリックします。

このタイムゾーンは、次のような time エレメントが含まれている場合に、すべての処理に使用されます。

* [時刻条件](../building-journeys/condition-activity.md#time_condition)
* [日付条件](../building-journeys/condition-activity.md#date_condition)
* [カスタム待機](../building-journeys/wait-activity.md#custom)

<!--
* [Fixed date wait](../building-journeys/wait-activity.md#fixed_date)
-->

タイムゾーンを選択するか、またはユーザープロファイルに定義されているタイムゾーンを選択することができます。

>[!NOTE]
>
>プロファイルのタイムゾーンは、「詳細 **設定」フィールドグループにある** 「timeZone **」フィールドと** 同じように動作します。

## 固定タイムゾーンの定義 {#fixed-timezone}

タイムゾーンを修正することもできます。 事前に定義されたタイムゾーンをオフにして、ドロップダウンリストから選択します。 固定されたタイムゾーンを使用している場合は、すべてのユーザーが同じ時間帯に移行することになります。

これを行うには、ウィンドウで **[!UICONTROL Journey Properties]** タイムゾーンを選択します。

![](assets/journey72.png)

## プロファイルを使用して、旅のタイムゾーンを定義します。 {#timezone-from-profiles}

このような旅のエントリイベントに名前空間がある場合は、その名前空間を使用して、その旅が Adobe エクスペリエンスプラットフォームのリアルタイムカスタマープロファイルサービスに到達する可能性があるので、プロファイルレベルで定義されたタイムゾーンを使用することもできます。 そのためには、プロパティ **で** 、待機と状態 **で「プロファイルのタイムゾーンを使用」チェックボックスをオン** にします。デフォルトでは、このオプションは選択されていません。

タイムゾーンがプロファイルに定義されている場合は、その機能が取得され、旅に使用されます。 指定されていない場合は、使用するタイムゾーンは timezone フィールドで定義されているタイムゾーンになります。

![](assets/journey73.png)

## エクスプレッションでのタイムゾーンの使用 {#timezone-in-expressions}

予定の開始日と終了日を特定のタイムゾーンにリンクすることはできません。 それらは、インスタンスのタイムゾーンに自動的に関連付けられます。
