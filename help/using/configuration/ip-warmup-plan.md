---
solution: Journey Optimizer
product: journey optimizer
title: IP ウォームアッププランを作成する
description: IP ウォームアッププランの作成方法を学ぶ
feature: Application Settings
topic: Administration
role: Admin
level: Experienced
keywords: IP、プール、グループ、サブドメイン、配信品質
hide: true
hidefromtoc: true
source-git-commit: dc1eeb3c199e7db2fc152b682404a547e2ae56c7
workflow-type: tm+mt
source-wordcount: '541'
ht-degree: 5%

---

# IP ウォームアッププランを作成する {#ip-warmup}

>[!BEGINSHADEBOX]

このドキュメントガイドの内容は次のとおりです。

* [IP ウォームアップの概要](ip-warmup-gs.md)
* [IP ウォームアップキャンペーンを作成](ip-warmup-campaign.md)
* **[IP ウォームアッププランを作成する](ip-warmup-plan.md)**
* [IP ウォームアッププランを実行する](ip-warmup-running.md)

>[!ENDSHADEBOX]

## IP ウォームアッププランへのアクセスと管理 {#manage-ip-warmup-plans}

1. 次にアクセス： **[!UICONTROL 管理]** > **[!UICONTROL チャネル]** > **[!UICONTROL IP 暖機プラン]** メニュー。 これまでに作成した IP ウォームアップ計画がすべて表示されます。

   ![](assets/ip-warmup-filter-list.png)

1. ステータスに基づいてフィルタリングできます。 様々なステータスを次に示します。

   * **未開始**：実行が発生しませんでした
   * **処理中**:1 回の実行が開始したらすぐに <!--or is done?-->
   * **一時停止**
   * **完了**：プラン内のすべての実行が完了している

1. IP ウォームアッププランを削除するには、 **[!UICONTROL 削除]** リスト項目の横にあるアイコンをクリックし、削除を確定します。

   ![](assets/ip-warmup-delete-plan.png)

   >[!CAUTION]
   >
   >選択した IP ウォームアッププランは完全に削除されます。

## IP ウォームアッププランを作成する {#create-ip-warmup-plan}

>[!CONTEXTUALHELP]
>id="ajo_admin_ip_warmup_upload"
>title="IP ウォームアッププランを指定"
>abstract="CSV テンプレートをダウンロードし、IP ウォームアップフェーズのデータと、ターゲットプロファイル数を入力します。"

>[!CONTEXTUALHELP]
>id="ajo_admin_ip_warmup_surface"
>title="マーケティングサーフェスを選択"
>abstract="IP ウォームアッププランに関連付けるキャンペーンで選択したサーフェスと同じサーフェスを選択する必要があります。"
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/configuration/channel-surfaces.html?lang=ja" text="チャネルサーフェスの設定"
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/configuration/channel-surfaces.html?lang=ja" text="IP ウォームアップキャンペーンを作成"

>[!CAUTION]
>
>IP ウォームアッププランを作成、編集、削除するには、 **[!UICONTROL 配信品質コンサルタント]** 権限。
<!--Learn more on managing [!DNL Journey Optimizer] users' access rights in [this section](../administration/permissions-overview.md).-->

1 つ以上のライブキャンペーンで **[!UICONTROL IP ウォームアッププランの有効化]** オプションが有効になっている場合は、IP ウォームアッププランに関連付けることができます。

>[!CAUTION]
>
>配信品質コンサルタントと協力して、IP ウォームアッププランテンプレートが正しく設定されていることを確認します。 <!--TBC-->

1. 次にアクセス： **[!UICONTROL 管理]** > **[!UICONTROL チャネル]** > **[!UICONTROL IP 暖機プラン]** メニュー、次に「 **[!UICONTROL IP ウォームアッププランを作成]**.

   ![](assets/ip-warmup-create-plan.png)

1. IP ウォームアッププランの詳細を入力し、名前と説明を入力します。

   ![](assets/ip-warmup-plan-details.png)

1. を選択します。 [表面](channel-surfaces.md). 選択できるのはマーケティングサーフェスのみです。 [電子メールのタイプの詳細を説明します](../email/email-settings.md#email-type)

   >[!CAUTION]
   >
   >IP ウォームアッププランに関連付けるキャンペーンで選択したサーフェスと同じサーフェスを選択する必要があります。 [IP ウォームアップキャンペーンの作成方法を説明します](#create-ip-warmup-campaign)

1. IP ウォームアッププランを含む Excel ファイルをアップロードします<!--which formats are allowed?-->. 配信品質チームが提供するテンプレートを使用できます。<!--TBC?--> [詳細情報](#upload-plan)
   <!--
    You can also download the Excel template from the [!DNL Journey Optimizer] user interface and upload it after filling it with the IP warmup details.-->

   ![](assets/ip-warmup-upload-success.png)

1. 「**[!UICONTROL 作成]**」をクリックします。アップロードしたファイルで定義されたフェーズの数が自動的に表示され、各フェーズのすべての実行が表示されます。 [詳細情報](#upload-plan)

   ![](assets/ip-warmup-plan-phases.png)

### IP ウォームアッププランを再度アップロード {#re-upload-plan}

対応するボタンを使用して、別の IP ウォームアッププランを再度アップロードできます。

![](assets/ip-warmup-re-upload-plan.png)

>[!NOTE]
>
>IP ウォームアッププランの詳細は、新しくアップロードされたファイルに従って変更されます。 実行の完了とアクティブ化された実行は影響を受けません。

### プランを含むファイルをアップロードします {#upload-plan}

以下は、IP ウォームアップ計画を含むファイルの例です。

![](assets/ip-warmup-sample-file.png)

各フェーズは、1 つのキャンペーンを割り当てる、複数の実行で構成される期間に対応します。

実行ごとに、一定数の受信者が存在し、この実行が実行される日付を定義します。

配信先のドメインに対して、必要な数の列を設定できます。 この例では、Gmail、Adobe、その他の 3 つの列があります。つまり、

最初の段階で実行を増やし、実行数を減らしながら、ターゲットアドレスの数を徐々に増やすことをお勧めします。
