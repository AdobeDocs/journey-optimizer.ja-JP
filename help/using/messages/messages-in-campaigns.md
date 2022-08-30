---
title: キャンペーンにメッセージを追加
description: キャンペーンにメッセージを追加する方法を説明します
feature: Overview
topic: Content Management
role: User
level: Beginner
source-git-commit: 87f9a4661b64cf24a8cd62bb9c70d5f1c9fcaddf
workflow-type: tm+mt
source-wordcount: '459'
ht-degree: 81%

---


# キャンペーンにメッセージを追加{#messages-in- campaigns}

キャンペーンで、オーディエンスに送信するメッセージをデザインおよびパーソナライズするチャネルを選択します。 E メール、SMS、プッシュをキャンペーンに追加する際に、即座に送信したり、メッセージのスケジュールを設定したりできます。

>[!NOTE]
>また、トリガーメッセージを送信するジャーニーを作成することもできます。 詳しくは、[この節](messages-in-journeys.md)を参照してください。

キャンペーンでメッセージを追加して設定する方法を説明します [この節](../campaigns/create-campaign.md)

メッセージコンテンツを作成する詳細な手順については、次のページを参照してください。

* [E メールの作成](create-email.md)
* [プッシュ通知の作成](create-push.md)
* [SMS メッセージの作成](create-sms.md)

## 送信時間の最適化を有効にする{#sto-in-journeys}

メールおよびプッシュ通知の場合、**[!UICONTROL 送信時間の最適化]**&#x200B;を有効にできます。

**[!UICONTROL 送信時間の最適化]**&#x200B;を使用して、ユーザーごとにパーソナライズされた送信時間をスケジュールし、メッセージの開封率やクリック率を高めます。[詳細情報](../messages/send-time-optimization.md)。

## 詳細設定パラメーター{#adv-settings}

詳細設定パラメーターは読み取り専用で、デフォルトでは非表示になっています。

詳細設定パラメーターにアクセスするには、メッセージペインの上部にある「**[!UICONTROL 読み取り専用フィールドを表示]**」アイコンをクリックします。

![](assets/show-read-only.png)

詳細設定パラメーターがメッセージペインの下部に表示されます。 これらのパラメーターは、メッセージに関連付けられた[チャネルサーフェス](../configuration/channel-surfaces.md)（メッセージプリセットなど）で [システム管理者](../start/path/administrator.md)によって定義されます。

プッシュ通知の場合、次のパラメーター（トークン、AppID、AppPlatform）を表示できます。

![](assets/push-adv-parameters.png)

メールの場合は、プライマリメールアドレスを表示できます。

特定の用途では、特定のコンテキストでこれらの値を上書きできます。 値を強制的に指定するには、フィールドの右側にある「**パラメーターの上書きを有効にする**」アイコンをクリックします。このオプションは、例えば次のような目的に役立つ可能性があります。

* メールをテストし、メールアドレスを追加する。 ジャーニーの公開後にメールが届きます。
* リストの購読者のメールアドレスを参照する。詳しくは、[このユースケース](../building-journeys/message-to-subscribers-uc.md)を参照してください。

同じアイコンをクリックして、詳細設定を非表示にします。

## メッセージの参照{#browse-message}

1 つのジャーニーで複数のメッセージを使用する場合は、**コンテンツを編集**&#x200B;画面からメッセージを切り替えることができます。

![](assets/inline-messages-multi-content.png)

[アラートをチェック](alerts.md)し、単一のビューから各コンテンツを[シミュレート](../design/preview.md)できます。

## メッセージの複製 {#duplicate-message}

ジャーニーキャンバスから既存のメッセージをコピーできます。

手順は次のとおりです。

1. コピーするメッセージを選択します。

1. **[!UICONTROL アクション]**&#x200B;パネルの&#x200B;**[!UICONTROL コピー]**&#x200B;ボタンを使用します。

   ![](assets/message-duplicate.png)

1. **Ctrl l+ V** キーを押して、メッセージをペーストします。

   メッセージがジャーニーキャンバスに追加されます。すべての設定が新しいメッセージにコピーされます。

   ![](assets/message-duplicated.png)

1. メッセージの編集時などに、最初のメッセージとコピーを区別できるように、次のようにメッセージの名前を変更します。

   ![](assets/multi-message.png)


>[!NOTE]
>
>メールの場合、既存のメッセージをテンプレートに変換することもできます。 [詳細情報](../design/email-templates.md)。

## メッセージの削除{#delete-message}

メッセージを削除するには、チャネルアクションアクティビティパネル上部にあるごみ箱アイコンを使用します。

![](assets/delete-message.png)

**[!UICONTROL 確認]**&#x200B;ボタンを使用して検証します。
