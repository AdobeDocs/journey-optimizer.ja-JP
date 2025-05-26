---
title: イベントトリガージャーニーの追加の識別子
description: イベントトリガージャーニーで補足的な識別子を使用する方法を説明します。
badge: label="限定提供" type="Informative"
exl-id: f6ebd706-4402-448a-a538-e9a4c2cf0f8b
source-git-commit: 3ed75f1193b1a580183d8ee148792ec136d281cd
workflow-type: tm+mt
source-wordcount: '844'
ht-degree: 7%

---

# イベントトリガージャーニーの追加の識別子 {#supplemental-id}

>[!CONTEXTUALHELP]
>id="ajo_journey_parameters_supplemental_identifier"
>title="補足識別子の使用"
>abstract="補足識別子は、ジャーニーの実行に関する追加のコンテキストを指定するセカンダリ識別子です。定義するには、補足識別子として使用するフィールドを選択し、関連付ける名前空間を選択します。"

>[!AVAILABILITY]
>
>この機能は、一連の組織でのみ使用できます（限定提供）。アクセスするには、アドビ担当者にお問い合わせください。

デフォルトでは、イベントトリガージャーニーは **プロファイル ID** のコンテキストで実行されます。 つまり、プロファイルが特定のジャーニーでアクティブになっている限り、別のジャーニーに再度エントリすることはできません。 これを防ぐために、Journey Optimizerでは、プロファイル ID に加えて、注文 ID、サブスクリプション ID、処方箋 ID など、イベントに **追加の ID** を取り込むことができます。
この例では、追加の識別子として予約 ID を追加しました。

![](assets/event-supplemental-id.png){width=40% zoomable}

これにより、イベントによってトリガーされるジャーニーは、追加の識別子（ここでは予約 ID）に関連付けられたプロファイル ID のコンテキストで実行されます。 追加識別子の反復ごとに、ジャーニーのインスタンスが 1 つ実行されます。 これにより、異なる予約をした場合、ジャーニーで同じプロファイル ID の複数のエントリが可能になります。

さらに、Journey Optimizerでは、補足的な識別情報の属性（予約番号、処方箋更新日、商品タイプなど）をメッセージのカスタマイズに活用し、関連性の高いコミュニケーションを確保できます。<!--Example: A healthcare provider can send renewal reminders for each prescription in a patient's profile.-->

## ガードレールと制限

* **同時インスタンス制限**：プロファイルは、10 を超える同時ジャーニーインスタンスを持つことはできません。

<!--* **Array depth**: Supplemental identifier objects can have a maximum depth of 3 levels (2 levels of nesting).

    +++Example

    ```
    [
    (level 1) "Atorvastatin" : {
    "description" : "used to lower cholesterol",
    "renewal_date" : "11/20/25",
    "dosage" : "10mg"
    (level 2) "ingredients" : [
    (level 3) "Atorvastatin calcium",
    "lactose monohydrate",
    "microcrystalline cellulose",
    "other" ]
    }
    ]
    ```

    +++
-->
* **終了条件**：終了条件がトリガーされると、その時点でジャーニーにライブになっているプロファイルのすべてのインスタンスが終了します。 プロファイル ID と追加の識別子の組み合わせには影響しません。

* **頻度ルール**：追加の識別子の使用状況から作成された各ジャーニーインスタンスは、1 つのイベントで複数のジャーニーインスタンスが生成された場合でも、フリークエンシーキャップにカウントされます。

* **データタイプとスキーマ構造**：追加の識別子は、`string` タイプである必要があります。 独立した文字列属性、またはオブジェクトの配列内の文字列属性を指定できます。 独立した文字列属性は、単一のジャーニーインスタンスを生成します。一方、オブジェクトの配列内の文字列属性は、オブジェクト配列の反復ごとに一意のジャーニーインスタンスを生成します。 文字列配列およびマップはサポートされていません。

## 追加の識別子を追加し、ジャーニーで活用する

ジャーニーで追加の識別子を使用するには、次の手順に従います。

1. **属性をイベントスキーマ内の識別子としてマークする**

   1. イベントスキーマにアクセスし、追加の識別子として使用する属性（予約 ID、サブスクリプション ID など）を見つけて、ID としてマークします。 [ スキーマの操作方法については、こちらを参照してください ](../data/get-started-schemas.md)

   1. 識別子を **[!UICONTROL ID]** としてマークします。

      ![](assets/supplemental-ID-schema.png)

      >[!IMPORTANT]
      >
      >属性を **プライマリ ID** としてマークしないでください。

   1. 追加の ID に関連付ける名前空間を選択します。 これは、人物以外の識別子の名前空間にする必要があります。

1. **イベントへの追加の ID の追加**

   1. 目的のイベントを作成または編集します。 [ 単一イベントの設定方法を学ぶ ](../event/about-creating.md)

   1. イベント設定画面で、「**[!UICONTROL 追加の識別子を使用]**」オプションをオンにします。

      ![](assets/supplemental-ID-event.png)

   1. 式エディターを使用して、追加の ID としてマークした属性を選択します。

   1. 追加の ID を選択すると、関連する名前空間がイベント設定画面に読み取り専用として表示されます。

1. **ジャーニーへのイベントの追加**

   設定済みのイベントをジャーニーキャンバスにドラッグします。 プロファイル ID と追加の ID の両方に基づいてジャーニーエントリのトリガーが設定されます。

   ![](assets/supplemental-ID-journey.png)

1. **追加の ID 属性の活用**

   式エディターとパーソナライゼーションエディターを使用して、パーソナライゼーションまたは条件付きロジック用の追加の識別子の属性を参照します。 属性は、**[!UICONTROL コンテキスト属性]** メニューからアクセスできます。

   ![](assets/supplemental-ID-perso.png)

   >[!NOTE]
   >
   >複数の処方箋やポリシーなどの配列を扱う場合は、数式を使用して特定の要素を抽出します。

+++ 例を参照

   追加の ID を `bookingNum`、同じレベルで属性を `bookingCountry` と呼ぶ、オブジェクト配列で、ジャーニーは bookingNum に基づいて配列オブジェクトを反復処理し、各オブジェクトのジャーニーインスタンスを作成します。

   * 条件アクティビティの次の式は、オブジェクト配列を反復処理し、`bookingCountry` の値が「FR」に等しいかどうかを確認します。

     ```
     @event{<event_name>.<object_path>.<object_array_name>.all(currentEventField.<attribute_path>.bookingNum==${supplementalId}).at(0).<attribute_path>.bookingCountry}=="FR"
     ```

   * メールパーソナライゼーションエディターの次の式は、オブジェクト配列を反復処理し、現在のジャーニーインスタンスに適用される `bookingCountry` を取り出して、コンテンツに表示します。

     ```
     {{#each context.journey.events.<event_ID>.<object_path>.<object_array_name> as |l|}} 
     
     {%#if l.<attribute_path>.bookingNum = context.journey.technicalProperties.supplementalId%} {{l.<attribute_path>.bookingCountry}}  {%/if%}
     
     {{/each}}
     ```

   * ジャーニーのトリガーとして使用するイベントの例：

     ```
     "bookingList": [
           {
               "bookingInfo": {
                   "bookingNum": "x1",
                         "bookingCountry": "US"
               }
           },
           {
               "bookingInfo": {
                   "bookingNum": "x2",
                   "bookingCountry": "FR"
               }
           }
       ]
     ```

+++

1. **ジャーニーの公開**

   設定が完了したら、ジャーニーを公開し、追加の識別子に基づいて複数の同時エントリを使用し始めます。

## 使用例

### **ポリシー更新の通知**

* **シナリオ**：保険プロバイダーは、顧客が保持するアクティブなポリシーごとに更新リマインダーを送信します。
* **実行**:
   * プロファイル：「John」。
   * 追加の ID: `"AutoPolicy123", "HomePolicy456"`。
   * ジャーニーは、パーソナライズされた更新日、カバレッジの詳細、プレミアム情報と共に、ポリシーごとに個別に実行されます。

### **購読の管理**

* **シナリオ**：購読サービスは、顧客プロファイルに関連付けられた各購読に対してカスタマイズされたメッセージを送信します。
* **実行**:
   * プロファイル：「Jane」。
   * 追加の ID: `"Luma Yoga Program ", "Luma Fitness PlPrograman"`。
   * ジャーニーは、パーソナライズされた更新オファーを使用して、サブスクリプションごとに個別に実行されます。

### **製品レコメンデーション**

* **シナリオ**:e コマースプラットフォームは、顧客が購入した特定の製品に基づいてレコメンデーションを送信します。
* **実行**:
   * プロファイル：「Alex」。
   * 追加の ID: `"productID1234", "productID5678"`。
   * ジャーニーは商品ごとに個別に実行され、パーソナライズされたアップセルのチャンスがあります。
