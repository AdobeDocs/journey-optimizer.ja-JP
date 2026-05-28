---
title: リクエストのレビューと承認
description: ジャーニーとキャンペーンを公開するリクエストをレビューして承認する方法について説明します。
role: User
level: Beginner
feature: Approval
exl-id: 8f4260b5-98df-4350-bd9b-680c3986ffe6
TQID: https://experienceleague.adobe.com/I7beoyvv-vzc39XjLlPl8iIpxtxOmSkD5AtxW0bCCwA
product_v2: id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2: []
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2: id: c1579802-ddd4-4214-8a91-97b2066abe11
subfeature_v2: id: bf7a266e-e483-42c6-b5bc-09ca6e49900c
source-git-commit: 0ee10a0689d38c22b1180b197796b08a10c286cf
workflow-type: tm+mt
source-wordcount: 362
ht-degree: 60%

---

# リクエストのレビューと承認 {#approve-requests}

承認ポリシーがジャーニーまたはキャンペーンに適用される場合、公開するには承認用に送信する必要があります。 これを行うには、ジャーニー/キャンペーン作成者は承認ポリシーで定義された承認者にリクエストを送信し、ジャーニー/キャンペーンは&#x200B;**[!UICONTROL レビュー中]**&#x200B;のステータスを取得します。

承認者として選択した場合は、メールと Journey Optimizer アラートによって通知されます。これには、画面右上の「**[!UICONTROL リクエスト]**」タブのベルアイコンをクリックするとアクセスできます。

![承認リクエスト通知](assets/request-notification.png)

ジャーニー/キャンペーンを確認するには、メールまたはアラートからジャーニーを開き、オーディエンス、コンテンツ、設定などの設定を確認します。
完了したら、[ジャーニー／キャンペーンを承認して公開する](#approve)か、[アクティブ化する前に変更をリクエストする](#changes)ことができます。

>[!NOTE]
>
>キャンペーンのレビューは読み取り専用の手順です。すべての設定を視覚化できますが、アクションを実行することはできません。
>
>ジャーニーまたはキャンペーンをレビューする前に、必要な権限があることを確認します。

## ジャーニー／キャンペーンの承認と公開 {#approve}

ジャーニーまたはキャンペーンの運用を開始する準備が整ったら、「**[!UICONTROL 承認]**」ボタンをクリックして承認できます。

表示されるウィンドウで、「**[!UICONTROL 承認してアクティブ化]**」をクリックして、ジャーニー／キャンペーンを公開します。

![承認リクエストダイアログ ](assets/approve-request.png)

## ジャーニー／キャンペーンへの変更のリクエスト {#changes}

承認用に送信されたジャーニーまたはキャンペーンに変更が必要な場合は、作成者にリクエストを送信して、必要な変更を加えることができます。

それには、「**[!UICONTROL 変更をリクエスト]**」ボタンをクリックします。 開いたペインで、リクエストの詳細を示すメッセージを入力し、**[!UICONTROL 送信]**&#x200B;をクリックしてリクエストを送信します。

![変更を依頼ダイアログ ](assets/request-changes.png)

リクエストを送信すると、メールと Journey Optimizer アラートでジャーニー／キャンペーン作成者に通知されます。 キャンペーンは「ドラフト」ステータスに戻ります。 変更を統合したら、ジャーニー/キャンペーン作成者は、承認のために変更を再送信できます。

>[!NOTE]
>
> メールで承認通知を受け取っていない場合は、Experience Cloud プロファイルのサブスクリプション設定を更新する必要があります。 [詳細情報](https://experienceleague.adobe.com/ja/docs/core-services/interface/features/account-preferences)
