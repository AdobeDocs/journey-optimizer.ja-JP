---
solution: Journey Optimizer
product: journey optimizer
title: 独自のメールコンテンツをコーディングする
description: 独自のメールコンテンツのコーディング方法を学ぶ
feature: Email Design
topic: Content Management
role: User
level: Intermediate, Experienced
keywords: コード, HTML, エディター
exl-id: 5fb79300-08c6-4c06-a77c-d0420aafca31
source-git-commit: 48b3ef3d2e041ea49d1b0c91cc72ea04237a5e33
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 50%

---

# コンテンツを独自にコーディング {#code-content}

**[!UICONTROL 独自にコーディング]**&#x200B;モードを使用すると、Raw HTML をインポートしたり、メールコンテンツをコーディングしたりできます。この方法を使用するには、HTML に関するスキルが必要です。

➡️ [この機能について詳しくは、ビデオを参照してください。](#video)

>[!CAUTION]
>
> [Adobe Experience Manager Assets](../integrations/assets.md) の画像は、このメソッドを使用する場合は参照できません。HTML コードで参照される画像は、公開場所に保存する必要があります。

1. E メールデザイナーのホームページで、「**[!UICONTROL 独自にコーディング]**」を選択します。

   ![](assets/code-your-own.png)

1. Raw HTML コードを入力または貼り付けます。

1. 左側のペインを使用して、[!DNL Journey Optimizer] パーソナライゼーション機能を利用します。
[詳細情報](../personalization/personalize.md)

   ![](assets/code-editor.png)

   >[!NOTE]
   >
   >メールDesignerのパーソナライゼーションエディターには、ジャーニー式と比較して、いくつかの関数制限があります。 [&#x200B; 日付/時間関数の制限について詳しくはこちらを参照 &#x200B;](#date-time-limitations)

1. メールの内容をクリアして新しいデザインからメールを開始する場合は、オプション メニューから「**[!UICONTROL デザインを変更]**」を選択します。

   ![](assets/code-editor-change-design.png)

   >[!NOTE]
   >
   >このアクションにより、E メールデザイナーで選択したテンプレートが開きます。ここから、メールのデザインを完成させるか、「**[!UICONTROL コードエディターに切り替え]**」オプションを使用してコードエディターに戻ることができます。

1. 「**[!UICONTROL プレビュー]**」ボタンをクリックし、テストプロファイルを使用したメッセージデザインとパーソナライゼーションを確認します。[詳細情報](../content-management/preview-test.md)

   ![](assets/code-editor-preview.png)

1. コードの準備が整ったら、「**[!UICONTROL 保存]**」をクリックし、メッセージ作成画面に戻ってメッセージを完成させます。

   ![](assets/code-editor-save.png)

## 日時関数の制限 {#date-time-limitations}

電子メールDesignerのコードエディターでパーソナライゼーションを使用する場合、`now()` 関数は動的日付計算に使用できません。

>[!IMPORTANT]
>
>`now()` 関数は、メールビルダーの式言語では **サポートされていません**。 `now()` はジャーニー条件で使用できますが、メールコンテンツやコードエディター内では使用できません。

**代替手段：**

次の関数を使用して、メールのパーソナライゼーションで現在の日時を操作します。

* **`getCurrentZonedDateTime()`** – 現在の日付と時刻をタイムゾーン情報と共に返します。 `now()` の代わりに、この方法を使用することをお勧めします。

  例：`{%= getCurrentZonedDateTime() %}` は `2024-12-06T17:22:02.281067+05:30[Asia/Kolkata]` を返します

* **`currentTimeInMillis()`** – 現在の時刻をエポックミリ秒単位で返します。

  例：`{%= currentTimeInMillis() %}`

**推奨される回避策：**

メールコンテンツで日付計算を実行する必要がある場合：

* **事前計算日付フィールド** - メールを送信する前に、データパイプラインまたはプロファイル属性で必要な日付値を計算し、パーソナライゼーションでこれらの事前計算値を参照します。

  例：`{%= profile.timeSeriesEvents._mobile.hotelBookingDetails.bookingDate %}`

* **日付操作関数の使用** - [&#x200B; や &#x200B;](../personalization/functions/dates.md) などの `dayOfYear()` 日付/時間関数 `diffInDays()` プロファイル属性の日付値と共に使用します。

  例：`{%= formatDate(profile.timeSeriesEvents._mobile.hotelBookingDetails.bookingDate, "MM/dd/YY") %}`

* **計算属性の使用** – 複雑な日付計算を実行する [&#x200B; 計算属性 &#x200B;](../audience/computed-attributes.md) を作成し、結果をプロファイル属性として使用できるようにします。

詳しくは、[&#x200B; パーソナライゼーションの日時関数 &#x200B;](../personalization/functions/dates.md) を参照してください。
