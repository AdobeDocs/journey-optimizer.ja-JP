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
TQID: https://experienceleague.adobe.com/8CR92GEP0qQqj2h-JqzUdu9oq07Ahedcs1xh8rINvkY
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2:
  - id: dc22c819-3f29-4e91-8b7d-5c6719831141
  - id: fe338112-e2ce-4876-8989-fc4d497613f1
subfeature_v2:
  - id: d595a60b-bcf5-4a63-a189-66a0be755cc7
  - id: ee5bb250-0884-4d71-86eb-d8489e8bcadd
  - id: fb9a80eb-bebc-492f-a0e9-584595621ebb
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2:
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: bc98cb2b61c7c5c8dac78b494fe293a4106a88c4
workflow-type: tm+mt
source-wordcount: 529
ht-degree: 62%

---

# コンテンツを独自にコーディング {#code-content}

>[!BEGINSHADEBOX]

**このページでは、**&#x200B;生のHTMLを電子メールDesigner コードエディターに書き込んだり貼り付けたりして、電子メールコンテンツを作成する方法（パーソナライゼーションの追加方法や使用可能な日時の関数など）について説明します。

>[!ENDSHADEBOX]

**[!UICONTROL 独自のコードを作成]**&#x200B;すると、生のHTMLを書き込んだり貼り付けたりして、[!DNL Journey Optimizer] メール Designerで直接メールコンテンツを作成できます。 このモードは、マークアップを完全に制御する必要がある場合や、既存のHTMLを読み込む場合に使用します。

HTMLのスキルが必要です。このモードを選択すると、コードエディターに留まり、ビジュアルエディターに切り替えることはできません。

➡️ [ビデオでこの機能を確認する](#video)

>[!NOTE]
>
>**[!UICONTROL 独自の]**&#x200B;のコードは、電子メール Designerの高度なHTML エディターと同じではありません。 高度なHTML エディターを使用すると、コードエディターではなく、いつでもHTML ビューとビジュアル（デスクトップ）ビューを切り替えることができます。 [高度なHTML エディターの詳細](email-expert-mode.md)。

## コードエディターの使用 {#use-code-editor}

コードエディターを使用してメールコンテンツを作成または編集するには、次の手順に従います。

1. [&#x200B; メール Designer](get-started-email-design.md)のホームページから、**[!UICONTROL 自分のコード]**&#x200B;を選択します。

   ![](assets/code-your-own.png)

1. Raw HTML コードを入力または貼り付けます。

1. 左側のペインを使用して、[!DNL Journey Optimizer] パーソナライゼーション機能を利用します。 [詳細情報](../personalization/personalize.md)

   ![](assets/code-editor.png)

   >[!NOTE]
   >
   >E メールデザイナーのパーソナライゼーションエディターには、ジャーニー式と比較して、いくつかの関数制限があります。 [日時関数の制限の詳細情報](#date-time-limitations)

1. メールの内容をクリアして新しいデザインからメールを開始する場合は、オプション メニューから「**[!UICONTROL デザインを変更]**」を選択します。

   ![](assets/code-editor-change-design.png)

   >[!NOTE]
   >
   >このアクションにより、E メールデザイナーで選択したテンプレートが開きます。 ここから、メールのデザインを完成させるか、「**[!UICONTROL コードエディターに切り替え]**」オプションを使用してコードエディターに戻ることができます。

1. 「**[!UICONTROL プレビュー]**」ボタンをクリックし、テストプロファイルを使用したメッセージデザインとパーソナライゼーションを確認します。 [詳細情報](../content-management/preview-test.md)

   ![](assets/code-editor-preview.png)

1. コードの準備が整ったら、「**[!UICONTROL 保存]**」をクリックし、メッセージ作成画面に戻ってメッセージを完成させます。

   ![](assets/code-editor-save.png)

>[!CAUTION]
>
>独自のメソッドをコードで使用する場合、[Adobe Experience Manager Assets](../integrations/assets.md)の画像を参照できません。 HTML コードで参照されている画像を公開場所に保存します。

## 日時関数の制限 {#date-time-limitations}

E メールデザイナーのコードエディターでパーソナライゼーションを使用する際、`now()` 関数は動的な日付計算には使用できません。

>[!IMPORTANT]
>
>`now()` 関数は、メールビルダーの式言語では&#x200B;**サポートされていません**。 `now()` はジャーニー条件で使用できますが、メールコンテンツやコードエディター内では使用できません。

**使用可能な代替手段：**

メールのパーソナライゼーションで現在の日時を操作するには、以下の関数を使用します。

* **`getCurrentZonedDateTime()`** - タイムゾーン情報を含む現在の日時を返します。 `now()` の代わりに使用することをお勧めします。

  例：`{%= getCurrentZonedDateTime() %}` は、`2024-12-06T17:22:02.281067+05:30[Asia/Kolkata]` を返します

* **`currentTimeInMillis()`** - 現在の時刻をエポックミリ秒単位で返します。

  例：`{%= currentTimeInMillis() %}`

**推奨される回避策：**

メールコンテンツで日付計算を実行する必要がある場合：

* **日付フィールドを事前計算** - メールを送信する前に、データパイプラインまたはプロファイル属性で必要な日付値を計算し、パーソナライゼーションでこれらの事前計算値を参照します。

  例：`{%= profile.timeSeriesEvents._mobile.hotelBookingDetails.bookingDate %}`

* **日付操作関数を使用** - プロファイル属性の日付値に対して、`dayOfYear()` や `diffInDays()` などの[日時関数](../personalization/functions/dates.md)を使用します。

  例：`{%= formatDate(profile.timeSeriesEvents._mobile.hotelBookingDetails.bookingDate, "MM/dd/YY") %}`

* **計算属性を使用** - 複雑な日付計算を実行する[計算属性](../audience/computed-attributes.md)を作成し、その結果をプロファイル属性として使用できるようにします。

サポートされている関数の完全なリストについては、[日付と時刻の関数](../personalization/functions/dates.md)を参照してください。
