---
solution: Journey Optimizer
product: journey optimizer
title: コンポジション canvas の操作
description: コンポジションキャンバスの操作方法について学習します。
feature: Journeys
topic: Content Management
role: User
level: Intermediate
hide: true
hidefromtoc: true
exl-id: 3eb9466e-9d88-4470-a22f-5e24a29923ae
source-git-commit: 8d56e3060e78422b028ced17f415497789908ff9
workflow-type: tm+mt
source-wordcount: '1002'
ht-degree: 0%

---

# コンポジション canvas の操作 {#composition-canvas}

コンポジション canvas は、視聴ユーザーおよび操作を利用してコンポジションを作成するためのビジュアル canvas です (split、exclude、exclude など)。

コンポジションキャンバスでコンポジションを設定するには、次の手順を実行します。

1. [最初の視聴者の定義](#starting-audience)
1. [1つまたは複数のアクティビティーの追加](#action-activities)
1. [新規ユーザーに結果を保存します。](#save)

## 最初の参加者を選択します。 {#starting-audience}

コンポジションを作成するには、まず、1つまたは複数の対象ユーザーをコンポジションの基準として選択します。

1. **[!UICONTROL Audience]**&#x200B;アクティビティーを選択して、アクティビティーのラベルを指定します。

1. 対象となる対象ユーザーを選択します。

   * ボタンをクリックして **[!UICONTROL Add audience]** 、既存の対象ユーザーを1つまたは複数選択します。
   * **[!UICONTROL Build rule]**&#x200B;ボタンをクリックすると、セグメンテーションサービス ](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html) を使用して [ 新しいセグメント定義が作成されます。

   ![](assets/audiences-choose-audience.png)

1. 複数の対象ユーザーが選択されている場合は、これらの対象ユーザーのプロファイルをマージする方法を指定します。

* **[!UICONTROL Union]**: 選択した対象ユーザーのすべてのプロファイルを含めます。
* **[!UICONTROL Intersection]**: 選択した対象ユーザーすべてに共通のプロファイルを含めます。
* **[!UICONTROL Exclude overlap]**: いずれかの対象ユーザーのみに属しているプロファイルを含めます。 複数の視聴者に属しているプロファイルは含まれません。

この例では、ゴールドおよびシルバーの対象者に属するすべてのプロファイルを対象としています。

![](assets/audiences-starting-audience.png)

対象ユーザーが選択されると、アクティビティの下部に表示されるプロファイルの数が見積もり数として表示されます。

## アクティビティの追加 {#action-activities}

参加者を選択して、選択範囲を絞り込むことによって、アクティビティーを追加することができます。

これを行うには、コンポジションパスの「+」ボタンをクリックし、目的の操作を選択します。 右側のペインが表示され、アクティビティを設定することができます。

![](assets/audiences-select-activity.png)

>[!NOTE]
>
>コンポジションには、 **[!UICONTROL Exclude]** 必要なだけ数 **[!UICONTROL Audience]** 個の操作を追加することができます。ただし、and **[!UICONTROL Split]** activity の後 **[!UICONTROL Rank]** にアクティビティを追加することはできません。

いつでも、右ウィンドウの「削除」ボタンをクリックして、カンバスからアクティビティを削除することができます。 このアクティビティーの後に追加されたすべてのアクティビティーもカンバスから削除されます。

使用可能なアクティビティーは、次のとおりです。

* [対象読者 ](#audience) : 1 つまたは複数の対象ユーザーに属する追加のプロファイルを指定します。
* [Exclude ](#exclude) : 既存の対象ユーザーに属するプロファイルを除外します。特定の属性に基づいてプロファイルを除外します。
* [ランク ](#rank) : 特定の属性に基づいてプロファイルをランク付け保存するプロフィールの数を指定して、コンポジションに追加します。
* [分割 ](#split) : ランダムなパーセントまたは属性に基づいて、コンポジションを複数のパスに分割します。

### 対象ユーザーの操作 {#audience}

>[!CONTEXTUALHELP]
>id="ajo_ao_audience"
>title="対象ユーザーの操作"
>abstract="参加者アクティビティを使用すると、既存の参加者に属する追加のプロファイルをコンポジションに含めることができます。"

>[!CONTEXTUALHELP]
>id="ajo_ao_merge_types"
>title="マージの種類"
>abstract="選択された対象ユーザーのプロファイルをマージする方法を指定します。"

アクティビティを使用すると、 **[!UICONTROL Audience]** 既存のユーザーに属する追加のプロファイルをコンポジションに組み込むことができます。

このアクティビティの設定は、受講者が開始 [ するアクティビティ ](#starting-audience) と同じです。

### アクティビティを除外 {#exclude}

>[!CONTEXTUALHELP]
>id="ajo_ao_exclude_type"
>title="除外タイプ"
>abstract="既存の対象ユーザーに属するプロファイルを除外するには、「対象ユーザーを除外」を使用します。 「Using 属性タイプを除外」を使用すると、特定の属性に基づいてプロファイルを除外することができます。"

>[!CONTEXTUALHELP]
>id="ajo_ao_exclude"
>title="アクティビティを除外"
>abstract="エクスクルードアクティビティーを使用すると、既存の対象ユーザーを選択するか、または、条件を使用して、コンポジションからプロファイルを除外できます。"

**[!UICONTROL Exclude]**&#x200B;アクティビティを使用すると、コンポジションからプロファイルを除外できます。次の2種類の除外を使用できます。

* **[!UICONTROL Exclude Audience]**: 既存の対象ユーザーに属するプロファイルを除外します。

   ボタンを **[!UICONTROL Add audience]** クリックしてから、除外する対象ユーザーを選択します。

   ![](assets/audiences-exclude-audience.png)

* **[!UICONTROL Exclude using attribute]**: 特定の属性に基づいてプロファイルを除外します。

   検索する属性を選択してから、除外する値を指定します。 この例では、home 住所が日本にあるコンポジションプロファイルは除外されています。

   ![](assets/audiences-exclude-attribute.png)

### ランク付けアクティビティ {#rank}

>[!CONTEXTUALHELP]
>id="ajo_ao_ranking"
>title="ランク付けアクティビティ"
>abstract="Rank アクティビティを使用すると、特定の属性に基づいてプロファイルをランク付けし、コンポジションに含めることができます。 たとえば、最も多くのロイヤルティポイントを含む50プロファイルを含めます。"

>[!CONTEXTUALHELP]
>id="ajo_ao_rank_profilelimit_text"
>title="プロファイル制限の追加"
>abstract="このオプションをオンにして、コンポジションに含めるプロファイルの最大数を指定します。"

**[!UICONTROL Rank]**&#x200B;アクティビティを使用すると、特定の属性に基づいてプロファイルをランク付けして、コンポジションに含めることができます。たとえば、最も多くのロイヤルティポイントを含む50プロファイルを取り込むことができます。

1. 検索する属性を選択し、ランキングの順序 (昇順または降順) を指定します。

   >[!NOTE]
   >
   >次のデータ型を使用して属性を選択できます。整数、数値、短い <!--(other?)-->

1. **[!UICONTROL Add profile limit]**&#x200B;オプションをオンにして、コンポジションに含めるプロファイルの最大数を指定します。

   ![](assets/audiences-rank.png)

### 分割アクティビティ {#split}

>[!CONTEXTUALHELP]
>id="ajo_ao_control_group_text"
>title="コントロールグループ"
>abstract="コントロールグループを使用して、プロファイルの一部を分離します。 これにより、マーケティング活動の影響を測定し、その他の人口の動作との比較を行うことができます。"

>[!CONTEXTUALHELP]
>id="ajo_ao_split"
>title="分割アクティビティ"
>abstract="分割アクティビティーを使用すると、コンポジションを複数のパスに分けることができます。 コンポジションをパブリッシュすると、1人の参加者が各パスについて Adobe エクスペリエンスプラットフォームに保存されます。"

>[!CONTEXTUALHELP]
>id="ajo_ao_split_type"
>title="分割タイプ"
>abstract="「%」スプリットタイプを使用して、プロファイルをランダムに複数のパスに分割します。 属性分割タイプを使用すると、特定の属性に基づいてプロファイルを分割することができます。"

>[!CONTEXTUALHELP]
>id="ajo_ao_split_otherprofiles_text"
>title="その他のプロファイル"
>abstract="このオプションをオンにすると、他のパスに指定されているいずれかの条件に一致しない残りのプロファイルを含む追加のパスが作成されます。"

**[!UICONTROL Split]**&#x200B;アクティビティを使用すると、コンポジションを複数のパスに分割できます。

この操作により、各パスの最後に自動的にアクティビティーが **[!UICONTROL Save]** 追加されます。 コンポジションをパブリッシュすると、1人の参加者が各パスについて Adobe エクスペリエンスプラットフォームに保存されます。

分割操作には、次の2つのタイプがあります。

* **[!UICONTROL Percent split]**: 複数のパスにプロファイルをランダムに分割します。 例えば、プロファイルを45% という2種類のパスに分割し、制御グループに追加のパスを追加することができます。

   ![](assets/audiences-split-percentage.png)

* **[!UICONTROL Attribute split]**: 特定の属性に基づいてプロファイルを分割します。 この例では、部屋の種類の環境設定に基づいてプロファイルを分割しています。

   ![](assets/audiences-split.png)

   >[!NOTE]
   >
   >**[!UICONTROL Other profiles]**&#x200B;このオプションを使用すると、他のパスに指定されているいずれかの条件に一致しない残りのプロファイルを含む追加のパスを作成することができます。

## 視聴者の保存 {#save}

Adobe エクスペリエンスプラットフォームに保存される対象ユーザーを設定します。

これを行うには、各パスの最後にあるアクティビティを選択 **[!UICONTROL Save audience]** し、作成する新しい視聴者の名前を指定します。

![](assets/audiences-publish.png)

コンポジションが準備できたら、パブリッシュすることができます。 [コンポジションを作成する方法を学習します。](create-compositions.md)

詳細情報：

* [対象ユーザー向けコンポジションの使用を開始する](get-started-audience-orchestration.md)
* [コンポジションワークフローの作成](create-compositions.md)
* [対象ユーザーへのアクセスと管理](access-audiences.md)
