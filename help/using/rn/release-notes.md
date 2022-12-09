---
solution: Journey Optimizer
product: journey optimizer
title: リリースノート
description: 旅のオプティマイザーリリースノート
exl-id: 06fa956a-b500-416e-9d42-b683c328e837
source-git-commit: 3a932747de33ced59d68835a96386b7ac560e4fe
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 0%

---

# リリースノート {#release-notes}

このページには、の [!DNL Journey Optimizer] すべての新機能と機能強化が記載されています。 その他の変更点については、最新のドキュメントの更新 ](documentation-updates.md) ページを参照して [ ください。

[!DNL Adobe Journey Optimizer] ネイティブに構築され、最新の革新的機能と機能強化に [!DNL Adobe Experience Platform] よって継承されます。 Adobe エクスペリエンス Platform リリースノート ](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html) でのこれらの変更点について詳しくは、{target = &quot;_blank 「}」を [ 参照してください。

![](../assets/do-not-localize/nl-icon.png)Adobe 旅オプティマイザー向けにサインアップすることが [ できます。年4月 ](https://www.adobe.com/subscription/Adobe_Journey_Optimizer_NL.html) {target = &quot;_blank&quot;} 今日、最新の製品アップデート、魅力的な記事、使用例、ヒント、その他の情報は、各四半期に受信トレイに直接配信されます。


## 2022 10 月リリース {#oct-2022-release}

<!--

### New capability{#oct-2022-features}

<table>
<thead>
<tr>
<th><strong>Direct Mail Channel (Limited Availability)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>You can now add direct mail messages in your campaigns and journeys. Direct mail is an offline channel that allows you to personalize and generate the files required by direct mail providers to send mail to your customers.</p>
<p>When you prepare a direct mail delivery, Journey Optimizer generates a file including all the targeted profiles and the chosen contact information (postal address for example). You will then be able to send this file to your direct mail provider who will take care of the actual sending.</p>
</td>
</tr>
</tbody>
</table>

-->

### 実現 {#oct-2022-improvements}

**Journeys**

* **定期的に行う「定期的なアイテム** の再開始」オプションが追加されました。このオプションを使用すると、次の実行時にすべてのプロファイルが自動的に終了するように、その旅に残っているすべてのプロファイルを自動的に終了させることができます。 このオプションをオフにすると、プロファイルは、別の開催時に再入力されるようになる前に、旅を終了する必要があります。 [詳細情報](../building-journeys/read-segment.md#configuring-segment-trigger-activity)

**管理**

* サブドメインについて警告するメッセージがユーザーインターフェイスに追加されました。これは、すべてのサンドボックスについて、このような構成に変更を加えると、これらの設定に変更を加えた場合もプロダクションサンドボックスに影響を与えることになります。
* ユーザーインターフェイスを使用して、抑制リストを CSV ファイルとしてアップロードする手順が修正されました。 [詳細情報](../configuration/manage-suppression-list.md#download-suppression-list)

**キャンペーン**

* 完成したキャンペーンおよび停止したキャンペーンをアーカイブできるようになりました。 [詳細情報](../campaigns/modify-stop-campaign.md#archive)
