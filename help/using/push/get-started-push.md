---
solution: Journey Optimizer
product: journey optimizer
title: プッシュ通知の基本を学ぶ
description: Journey Optimizer でプッシュ通知を作成する方法を説明します
feature: Overview, Push
topic: Content Management
role: User
level: Beginner
exl-id: c1f16edd-efdf-41c2-a0ad-5f55009008f5
TQID: https://experienceleague.adobe.com/S-3ZtTNfgZGEFChfjaXPihxGWpdkWacrWF9AWc-AyZY
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2:
  - id: d998adac-2f81-400b-a669-d07bb196e4eb
  - id: dc22c819-3f29-4e91-8b7d-5c6719831141
  - id: df64005d-8f9a-422e-ba4d-c6f6dc3454b4
  - id: fe338112-e2ce-4876-8989-fc4d497613f1
subfeature_v2:
  - id: fb9a80eb-bebc-492f-a0e9-584595621ebb
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2:
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: f9b8e1590f14cdcd00432295c653769f753b9b40
workflow-type: tm+mt
source-wordcount: 367
ht-degree: 100%

---

# プッシュ通知の基本を学ぶ {#gs-push-notification}

>[!IMPORTANT]
>
>プッシュ通知を初めて作成する場合は、プッシュチャネルが設定されていることを確認してください。 [詳細情報](push-gs.md)

プッシュ通知は、モバイルアプリのユーザーや web 訪問者、特にアプリをアクティブに使用していないユーザーや web サイトを閲覧していないユーザーにいつでもリーチするのに役立ちます。 プッシュ通知は、サービスに関するアップデートのお知らせ、ユーザーに対するアクション実行の依頼、新しい取引に対するユーザーへの警告など、様々なユースケースの実現に役立ちます。デバイスプラットフォームでは、エンドユーザーが通知を受信または表示する前に、オプトイン（同意）が必要となります。 ユーザーのオプトインは、インストール後にアプリを初めて起動した後の早い段階で受け取ることも、必要に応じて後続のセッションやワークフローで受け取ることもできます。

[!DNL Journey Optimizer] はプッシュ通知をサポートし、関連性の高い通知を業界最高のスループット率で送信できます。 Adobe Experience Cloud でのブランドのデータインサイトを活用するために、プッシュ通知には、パーソナライゼーションとジャーニーベースのコンテキストを含めることができます。

プッシュ通知は次の場所で作成できます。

* **ジャーニー**&#x200B;の場合：ジャーニーにプッシュアクティビティを追加し、基本設定を定義したら、右側の&#x200B;**[!UICONTROL アクション : プッシュ]**&#x200B;パネルを使用して、プッシュ通知のコンテンツを作成します。 [詳しくは、ジャーニーの作成方法を参照してください。](../building-journeys/journey-gs.md)

* **キャンペーン**&#x200B;の場合：キャンペーンを作成したら、アクションとして「プッシュ通知」を選択し、基本設定を定義します。 詳しくは、[アクションキャンペーン](../campaigns/campaign-action.md#action-campaign-action) | [API トリガーキャンペーン](../campaigns/api-triggered-campaigns.md) | [オーケストレーションキャンペーン](../orchestrated/create-orchestrated-campaign.md#create)の作成方法を参照してください。

専用のタブを使用して、**iOS**、**Android**、**web** プラットフォームのプッシュ通知設定を定義します。

>[!NOTE]
>
>**[!DNL Journey Optimizer]** には、メールや SMS メッセージのオプトアウトを管理する方法が用意されていますが、プッシュ通知の場合は、受信者が自分のデバイスを介して登録解除できるので、ユーザー側でのアクションは不要です。 例えば、アプリのダウンロード時や使用時に、通知の停止を選択できます。 同様に、モバイルオペレーティングシステムや web ブラウザー設定を通じて通知設定を変更することもできます。 AEP プロファイルビューアーでプロファイルのプッシュ同意ステータスを確認するには、[プッシュオプトアウトステータスの確認](../privacy/opt-out.md#push-opt-out-status)を参照してください。

<table style="table-layout:fixed"><tr style="border: 0;">
<td>
<a href="create-push.md">
<img alt="リード" src="../assets/do-not-localize/push-create.jpg">
</a>
<div><a href="create-push.md"><strong>プッシュ通知の作成</strong>
</div>
<p>
</td>
<td>
<a href="design-push.md">
<img alt="低頻度" src="../assets/do-not-localize/push-design.jpg">
</a>
<div>
<a href="design-push.md"><strong>プッシュ通知のデザイン</strong></a>
</div>
<p></td>
<td>
<a href="send-push.md">
<img alt="検証" src="../assets/do-not-localize/push-sending.jpg">
</a>
<div>
<a href="send-push.md"><strong>プッシュ通知の送信</strong></a>
</div>
<p>
</td>
<td>
<a href="push-gs.md">
<img alt="検証" src="../assets/do-not-localize/push-config.jpg">
</a>
<div>
<a href="push-gs.md"><strong>プッシュ通知の設定</strong></a>
</div>
<p>
</td>
</tr></table>
