---
solution: Journey Optimizer
product: journey optimizer
title: モバイルメッセージの作成
description: Journey Optimizerでモバイルメッセージを作成する方法を説明します
feature: SMS
topic: Content Management
role: User
level: Beginner
exl-id: 1f88626a-b491-4b36-8e3f-57f2b7567dd0
TQID: https://experienceleague.adobe.com/xgPlWorA3lsIF8ZBPHdg2UAK8cLKUsJO-2ONc7ZG8AU
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2:
  - id: d556b755-390a-43f0-be32-a08cf6236126
  - id: d998adac-2f81-400b-a669-d07bb196e4eb
  - id: dc22c819-3f29-4e91-8b7d-5c6719831141
subfeature_v2:
  - id: e5329d1b-e590-4e24-a3fb-ef3fe0f2c721
  - id: fa683eda-48de-4558-af32-2673edcd44fe
  - id: fb9a80eb-bebc-492f-a0e9-584595621ebb
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 9a68782b0ca1a9a65db621209cf4f39ea5ce911d
workflow-type: tm+mt
source-wordcount: 747
ht-degree: 49%

---

# モバイルメッセージの作成 {#create-sms}

>[!CONTEXTUALHELP]
>id="ajo_message_sms"
>title="テキストメッセージの作成"
>abstract="モバイルメッセージを作成するには、ジャーニーまたはキャンペーンにSMS アクションを追加し、パーソナライゼーションエディターを使用してパーソナライズを開始します。"

>[!AVAILABILITY]
>
>RCS は HIPAA 対応サービスではないので、組織が Journey Optimizer で処理することを許可されている場合がある、許可されたヘルスデータ（個人ヘルス情報など）を含むセンシティブな個人データの収集、保存、処理に使用できません。

Adobe Journey Optimizer を使用して、テキスト（SMS）、リッチ通信（RCS）およびマルチメディア（MMS）メッセージををデザインして送信できます。 最初に、ジャーニーまたはキャンペーンにモバイルメッセージアクションを追加し、次に詳細に説明するように、テキストメッセージのコンテンツを定義する必要があります。 また、Adobe Journey Optimizer には、送信前にテキストメッセージをテストする機能も用意されているので、レンダリング、パーソナライゼーション属性、その他すべての設定を確認できます。

業界標準と規制に従って、すべての SMS／MMS マーケティングメッセージには、受信者が簡単に登録解除できる方法を含める必要があります。 SMS 受信者は、オプトインおよびオプトアウトのキーワードで返信ですることでこれを実行できます。 [オプトアウトの管理方法について学ぶ](../privacy/opt-out.md#opt-out-decision-management)

## テキストメッセージの追加 {#create-sms-journey-campaign}

キャンペーンまたはジャーニーにモバイルメッセージを追加する方法については、以下のタブを参照してください。

>[!BEGINTABS]

>[!TAB ジャーニーへのテキストメッセージの追加]

1. ジャーニーを開き、パレットの「**[!UICONTROL アクション]**」セクションから「**[!UICONTROL アクション]**」アクティビティをドラッグ&amp;ドロップします。 [&#x200B; アクションアクティビティ &#x200B;](../building-journeys/journey-action.md)の詳細をご覧ください。

   >[!IMPORTANT]
   >
   >従来のネイティブチャネルアクティビティ（電子メール、プッシュ、SMS、アプリ内、web、コードベースのエクスペリエンス、コンテンツカード）は、2026年3月のリリースで廃止されました。 これらのアクティビティを使用する既存のジャーニーは、変更なしで引き続き機能します。移行は必要ありません。

1. アクションの種類として&#x200B;**[!UICONTROL モバイルメッセージ]**&#x200B;を選択し、**[!UICONTROL 追加]**&#x200B;をクリックします。

   ![](assets/sms_create_1.png)

1. ジャーニーキャンバスでアクションを識別するには、**[!UICONTROL ラベル]**&#x200B;を入力します。

1. 「**[!UICONTROL 設定アクション]**」ボタンをクリックします。

1. 「**[!UICONTROL アクション]**」タブに移動します。 そこから、使用するモバイルメッセージ設定を選択または作成します。 [詳細情報](mobile-configuration.md)

   ![](assets/sms_create_2.png)

1. さらに、**[!UICONTROL ビジネスルール]** ドロップダウンリストでルールセットを選択して、モバイルメッセージアクションにキャッピングルールを適用できます。 [詳細情報](../conflict-prioritization/channel-capping.md)

1. 「**[!UICONTROL コンテンツを編集]**」ボタンを選択し、必要に応じてコンテンツを作成します。 [詳細情報](design-mobile.md)

1. ジャーニーキャンバスに戻ります。 必要に応じて、追加のアクションまたはイベントをドラッグ＆ドロップして、ジャーニーフローを完了します。 [詳細情報](../building-journeys/about-journey-activities.md)

ジャーニーの作成、設定、公開の方法について詳しくは、[このページ &#x200B;](../building-journeys/journey-gs.md)を参照してください。

>[!TAB キャンペーンへのテキストメッセージの追加]

1. **[!UICONTROL キャンペーン]**&#x200B;メニューにアクセスし、「**[!UICONTROL キャンペーンを作成]**」をクリックします。

1. 実施するキャンペーンのタイプを選択します。

   * **Scheduled - Marketing**：キャンペーンをすぐに実行するか、指定日に実行します。 スケジュール済みキャンペーンは、マーケティングメッセージを送信することを目的としています。 ユーザーインターフェイスから設定および実行します。

   * **API トリガー - マーケティング／トランザクション**：API 呼び出しを使用してキャンペーンを実行します。 API トリガーキャンペーンは、マーケティングメッセージまたはトランザクションメッセージのいずれか、つまり、個人が実行したアクション（パスワードのリセット、買い物かごでの購入など）に続いて送信されるメッセージの送信を目的としています。

1. 「**[!UICONTROL プロパティ]**」セクションで、キャンペーンの「**[!UICONTROL タイトル]**」と「**[!UICONTROL 説明]**」を編集します。

1. 「**[!UICONTROL アクション]**」タブで、**[!UICONTROL アクションを追加]**&#x200B;をクリックし、**[!UICONTROL モバイルメッセージ]**&#x200B;を選択します。 次に、新しい設定を選択または作成します。

   モバイルメッセージの設定について詳しくは、[このページ &#x200B;](mobile-configuration.md)を参照してください。

   ![](assets/sms_create_3.png)

1. 「**[!UICONTROL 実験を作成]**」をクリックしてコンテンツ実験の設定を開始し、パフォーマンスを測定してターゲットオーディエンスに最適なオプションを特定するための処理を作成します。 [詳細情報](../content-management/content-experiment.md)

1. 「**[!UICONTROL アクションの追跡]**」セクションで、モバイルメッセージ内のリンクのクリックを追跡するかどうかを指定します。

1. 「**[!UICONTROL オーディエンス]**」タブで、「**[!UICONTROL オーディエンスを選択]**」ボタンをクリックして、使用可能なAdobe Experience Platform オーディエンスのリストからターゲットにするオーディエンスを定義します。 [詳細情報](../audience/about-audiences.md)。

1. 「**[!UICONTROL ID 名前空間]**」フィールドで、選択したオーディエンスから個人を識別するために使用する名前空間を選択します。 [詳細情報](../event/about-creating.md#select-the-namespace)

1. 「**[!UICONTROL スケジュール]**」タブから、特定の日付または定期的な頻度でキャンペーンを実行するようにキャンペーンを設計できます。 キャンペーンの&#x200B;**[!UICONTROL スケジュール]**&#x200B;を設定する方法については、[この節](../campaigns/campaign-schedule.md#action-campaign-schedule)を参照してください。

1. **[!UICONTROL アクショントリガー]** メニューから、モバイルメッセージの&#x200B;**[!UICONTROL 頻度]**&#x200B;を選択します。

   * 1 回
   * 毎日
   * 毎週
   * 月

これで、以下に説明するように、「**[!UICONTROL コンテンツを編集]**」ボタンからテキストメッセージのコンテンツのデザインを開始できます。 [詳細情報](design-mobile.md)

キャンペーンの作成、設定およびアクティベート方法について詳しくは、[このページ &#x200B;](../campaigns/get-started-with-campaigns.md)を参照してください。

>[!ENDTABS]

**関連トピック**

* [モバイルメッセージのデザイン](design-mobile.md)
* [キャンペーンへのメッセージの追加](../campaigns/create-campaign.md)
* [テキストメッセージのプレビュー、テスト、送信](send-mobile-message.md)
* [モバイルメッセージチャネルの設定](mobile-configuration.md)
* [モバイルメッセージレポート](../reports/journey-global-report-cja-sms.md)

