---
title: タイムゾーン管理
description: タイムゾーン管理について説明します。
feature: ジャーニー
topic: コンテンツ管理
role: User
level: Intermediate
source-git-commit: d76eee0efa6735d6d81d7d7c752ed253b4cbebb5
workflow-type: tm+mt
source-wordcount: '290'
ht-degree: 85%

---

# タイムゾーン管理 {#timezone_management}

タイムゾーンは、ジャーニーの[プロパティ](../building-journeys/journey-gs.md#change-properties)で定義できます。

「プロパティ」にアクセスするには、画面の右上にある鉛筆アイコンをクリックします。

このタイムゾーンは、次のような時間要素を含むジャーニーのすべてのアクティビティで使用されます。

* [時間条件](../building-journeys/condition-activity.md#time_condition)
* [日付条件](../building-journeys/condition-activity.md#date_condition)
* [カスタム待機](../building-journeys/wait-activity.md#custom)
* [固定日待機](../building-journeys/wait-activity.md#fixed_date)

タイムゾーンを選択するか、ユーザープロファイルで定義されたタイムゾーンを使用するかを選択できます。

>[!NOTE]
>
>プロファイルタイムゾーンは、**Preference Details**&#x200B;フィールドグループに存在する&#x200B;**timeZone**&#x200B;フィールドと連携します。

## 固定タイムゾーンの定義 {#fixed-timezone}

タイムゾーンを固定することもできます。定義済みのタイムゾーンをクリアし、ドロップダウンリストからタイムゾーンを選択します。固定タイムゾーンを使用すると、ジャーニーにエントリするすべての個人のタイムゾーンは同じになります。

それには、**[!UICONTROL ジャーニーのプロパティ]**&#x200B;ウィンドウでタイムゾーンを選択します。

![](../assets/journey72.png)

## プロファイルを使用したジャーニータイムゾーンの定義 {#timezone-from-profiles}

ジャーニーのエントリイベントに名前空間がある（ジャーニーが Adobe Experience Platform のリアルタイム顧客プロファイルサービスにアクセスする）場合、タイムゾーンは、ジャーニーを進む個人のプロファイルで指定されたタイムゾーンを使用してあらかじめ定義されます。

Adobe Experience Platform プロファイルでタイムゾーンが定義されている場合は、ジャーニーでそのタイムゾーンを取得できます。

個人のプロファイルにタイムゾーンが含まれていない場合、取得されるタイムゾーンはタイムゾーンフィールドに定義されているものになります。

これをおこなうには、**[!UICONTROL プロパティ]**&#x200B;で、「**[!UICONTROL 待機と条件でプロファイルタイムゾーンを使用]**」をオンにします。

![](../assets/journey73.png)

## タイムゾーン式の使用 {#timezone-in-expressions}

ジャーニーの開始日と終了日を特定のタイムゾーンにリンクすることはできません。これらはインスタンスのタイムゾーンに自動的に関連付けられます。
