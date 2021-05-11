---
title: タイムゾーン管理
description: タイムゾーン管理について説明します。
translation-type: tm+mt
source-git-commit: 55b9e5d8ed259ec6ed7746e835691d7d6261a8a4
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 2%

---

# タイムゾーン管理 {#timezone_management}

![](../assets/do-not-localize/badge.png)

タイムゾーンは、ジャーニーの[プロパティ](../building-journeys/journey-gs.md#change-properties)で定義できます。

「プロパティ」にアクセスするには、画面の右上にある鉛筆アイコンをクリックします。

このタイムゾーンは、次のような時間要素を含むジャーニーのすべてのアクティビティで使用されます。

* [時間条件](../building-journeys/condition-activity.md#time_condition)
* [日付条件](../building-journeys/condition-activity.md#date_condition)
* [カスタムの待機](../building-journeys/wait-activity.md#custom)
* [固定日の待機](../building-journeys/wait-activity.md#fixed_date)

タイムゾーンを選択するか、ユーザープロファイルで定義されたタイムゾーンを使用するかを選択できます。

## 固定タイムゾーンの定義{#fixed-timezone}

タイムゾーンも修正できます。 定義済みのタイムゾーンをクリアし、ドロップダウンリストからタイムゾーンを選択します。 固定タイムゾーンを使用する場合、ジャーニーに入る個人のタイムゾーンは同じになります。

これを行うには、**[!UICONTROL プロパティ]**&#x200B;でタイムゾーンを選択します。

![](../assets/journey73.png)

## プロファイルを使用したジャーニータイムゾーンの定義{#timezone-from-profiles}

ジャーニーの入口イベントが名前空間を持つ場合、ジャーニーがAdobe Experience Platformのリアルタイム顧客プロファイルサービスに到達できる場合、ジャーニーを流れる個人のプロファイルに指定されたタイムゾーンでタイムゾーンを事前定義する。

タイムゾーンがAdobe Experience Platformプロファイルで定義されている場合は、ジャーニーで取得できます。

個々のプロファイルにタイムゾーンが含まれていない場合、取得されるタイムゾーンはtimezoneフィールドに定義されているタイムゾーンになります。

これを行うには、**[!UICONTROL プロパティ]**&#x200B;で、**[!UICONTROL タイマーと条件でプロファイルタイムゾーンを使用する]**&#x200B;をチェックします。

![](../assets/journey72.png)

## 式{#timezone-in-expressions}でのタイムゾーンの使用

ジャーニーの開始日と終了日を特定のタイムゾーンにリンクすることはできません。 これらは、インスタンスのタイムゾーンに自動的に関連付けられます。
