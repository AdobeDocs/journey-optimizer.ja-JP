---
title: ジャーニーでの補足的な識別子の使用
description: ジャーニーで追加の識別子を使用する方法を説明します。
exl-id: f6ebd706-4402-448a-a538-e9a4c2cf0f8b
source-git-commit: dcb2be7fef47e0d62fdd5a423799823ba4ef586c
workflow-type: tm+mt
source-wordcount: '1157'
ht-degree: 72%

---

# ジャーニーでの補足的な識別子の使用 {#supplemental-id}

>[!CONTEXTUALHELP]
>id="ajo_journey_parameters_supplemental_identifier"
>title="補足識別子の使用"
>abstract="補足識別子は、ジャーニーの実行に関する追加のコンテキストを指定するセカンダリ識別子です。定義するには、補足識別子として使用するフィールドを選択し、関連付ける名前空間を選択します。"

デフォルトでは、ジャーニーは **プロファイル ID** のコンテキストで実行されます。 つまり、特定のジャーニーでプロファイルがアクティブである限り、別のジャーニーに再エントリできません。これを防ぐ [!DNL Journey Optimizer] めに、プロファイル ID に加えて、注文 ID、サブスクリプション ID、処方箋 ID などの **追加の識別子** を取得できます。
この例では、予約 ID を補足識別子として追加しています。

![](assets/event-supplemental-id.png){width=40% zoomable}

これにより、ジャーニーは、追加の識別子（ここでは予約 ID）に関連付けられたプロファイル ID のコンテキストで実行されます。 補助識別子の反復ごとに、ジャーニーのインスタンスが 1 つ実行されます。これにより、異なる予約を行った場合、ジャーニーで同じプロファイル ID の複数のエントリが可能になります。

さらに、Journey Optimizer を使用すると、補足識別子の属性（予約番号、処方箋の更新日、製品タイプなど）を活用してメッセージをカスタマイズできるので、関連性の高いコミュニケーションを確保できます。<!--Example: A healthcare provider can send renewal reminders for each prescription in a patient's profile.-->

➡️ [この機能について詳しくは、ビデオを参照してください](#video)。

## ガードレールと制限 {#guardrails}

* **サポートされているジャーニー**：現時点では、**イベントトリガー** ジャーニーと **オーディエンスを読み取り** ジャーニーで追加の識別子を使用できます。 オーディエンスの選定ジャーニーでは使用できません。

* **同時インスタンス制限**：プロファイルには、10 を超えるジャーニーインスタンスを同時に含めることはできません。

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
* **終了条件**：終了条件がトリガーされると、その時点でジャーニーでライブになっているプロファイルのすべてのインスタンスが終了します。これは、プロファイル ID と補足識別子の組み合わせとは関係ありません。

* **頻度ルール**：補足的な識別子の使用から作成された各ジャーニーインスタンスは、補足的な識別子の使用によって複数のジャーニーインスタンスが作成された場合でも、フリークエンシーキャップに対してカウントされます。

* **データタイプとスキーマ構造**：補足識別子は、`string` タイプにする必要があります。独立した文字列属性や、オブジェクト配列内の文字列属性にすることができます。独立した文字列属性では、単一のジャーニーインスタンスが生成されますが、オブジェクト配列内の文字列属性では、オブジェクト配列の反復ごとに一意のジャーニーインスタンスが生成されます。文字列配列およびマップはサポートされていません。

* **ジャーニーの再エントリ**

  補助識別子を使用したジャーニーの再エントリ動作は、既存の再エントリポリシーに従います。

   * ジャーニーが再エントリ不可の場合、同じプロファイル ID + 補助 ID の組み合わせでジャーニーに再エントリすることはできません。
   * 時間枠でジャーニーが再エントリ可能な場合、定義した時間枠の後に同じプロファイル ID + 補助 ID の組み合わせで再エントリできます。

* **ダウンストリームイベントの設定**

  ジャーニーのダウンストリームで別のイベントを使用している場合は、同じ補足 ID を使用し、同じ ID 名前空間を持つ必要があります。

* **オーディエンスジャーニーの読み取り**

   * ビジネスイベントを使用する場合、追加の ID は無効になります。

   * 追加の ID は、プロファイルのフィールド （イベント/コンテキストフィールドではない）にする必要があります。

## 補足識別子の追加とジャーニーでの活用 {#add}

>[!BEGINTABS]

>[!TAB  イベントトリガージャーニー ]

イベントトリガージャーニーで追加の識別子を使用するには、次の手順に従います。

1. **属性をイベントスキーマの識別子としてマーク**

   1. イベントスキーマにアクセスし、補足識別子として使用する属性（予約 ID、サブスクリプション ID など）を見つけて、ID としてマークします。[スキーマの操作方法の詳細情報](../data/get-started-schemas.md)

   1. 識別子を **[!UICONTROL ID]** としてマークします。

      ![](assets/supplemental-ID-schema.png)

      >[!IMPORTANT]
      >
      >属性を&#x200B;**プライマリ ID** としてマークしないでください。

   1. 補足 ID に関連付ける名前空間を選択します。これは、ユーザー以外の識別子の名前空間にする必要があります。

1. **イベントに補足 ID を追加**

   1. 目的のイベントを作成または編集します。[単一イベントの設定方法の詳細情報](../event/about-creating.md)

   1. イベント設定画面で、「**[!UICONTROL 補助識別子を使用]**」オプションをオンにします。

      ![](assets/supplemental-ID-event.png)

   1. 式エディターを使用して、補足 ID としてマークした属性を選択します。

      >[!NOTE]
      >
      >式エディターを&#x200B;**[!UICONTROL 詳細設定モード]**&#x200B;で使用して、属性を選択していることを確認します。

   1. 補足 ID を選択すると、関連付けられた名前空間がイベント設定画面に読み取り専用として表示されます。

1. **ジャーニーにイベントを追加**

   設定したイベントをジャーニーキャンバスにドラッグします。プロファイル ID と補足 ID の両方に基づいてジャーニーエントリがトリガーされます。

   ![](assets/supplemental-ID-journey.png)

>[!TAB  オーディエンスジャーニーを読み取る ]

オーディエンスを読み取りジャーニーで補足的な識別子を使用するには、次の手順に従います。

1. **属性を和集合/プロファイルスキーマの識別子としてマークする**

   1. 和集合/プロファイルスキーマにアクセスし、補助識別子として使用する属性（予約 ID、購読 ID など）を見つけて、ID としてマークします。 [スキーマの操作方法の詳細情報](../data/get-started-schemas.md)

   1. 識別子を **[!UICONTROL ID]** としてマークします。

      ![](assets/supplemental-ID-schema-profile.png)

      >[!IMPORTANT]
      >
      >属性を&#x200B;**プライマリ ID** としてマークしないでください。

   1. 補足 ID に関連付ける名前空間を選択します。これは、ユーザー以外の識別子の名前空間にする必要があります。

<!--1. **Add the supplemental ID field to the data source**

    1. Navigate to the **[!UICONTROL Configuration]** / **[!UICONTROL Data Sources]** menu, then locate the "ExperiencePlatformDataSource" data source.

        ![](assets/supplemental-ID-data-source.png)

    1. Open the field selector then select the attribute you want to use as a supplemental identifier (e.g., booking ID, subscription ID).-->

1. **ジャーニーでのオーディエンスを読み取りアクティビティの追加と設定**

   1. **[!UICONTROL オーディエンスを読み取り]** アクティビティをジャーニーにドラッグします。

   1. アクティビティプロパティペインで、「**[!UICONTROL 追加の識別子を使用]** オプションをオンにします。

      ![](assets/supplemental-ID-read-audience.png)

   1. 「**[!UICONTROL 補足識別子]**」フィールドで、式エディターを使用して、追加 ID としてマークした属性を選択します。

      >[!NOTE]
      >
      >式エディターを&#x200B;**[!UICONTROL 詳細設定モード]**&#x200B;で使用して、属性を選択していることを確認します。

   1. 追加の ID を選択すると、関連する名前空間が「**[!UICONTROL 追加の名前空間]**」フィールドに読み取り専用で表示されます。

>[!ENDTABS]

## 追加の ID 属性の活用

式エディターとパーソナライゼーションエディターを使用して、パーソナライゼーションまたは条件付きロジックの補足識別子の属性を参照します。属性は、**[!UICONTROL コンテキスト属性]**&#x200B;メニューからアクセスできます。

![](assets/supplemental-ID-perso.png)

配列（複数の処方箋やポリシーなど）を使用する場合、イベントトリガージャーニーでは、式を使用して特定の要素を抽出します。

+++ 例を参照

補足 ID が `bookingNum` で、同じレベルの属性が `bookingCountry` であるオブジェクト配列では、ジャーニーは bookingNum に基づいて配列オブジェクトを反復し、各オブジェクトのジャーニーインスタンスを作成します。

* 条件アクティビティの次の式は、オブジェクト配列を反復し、`bookingCountry` の値が「FR」と等しいかどうかを確認します。

  ```
  @event{<event_name>.<object_path>.<object_array_name>.all(currentEventField.<attribute_path>.bookingNum==${supplementalId}).at(0).<attribute_path>.bookingCountry}=="FR"
  ```

* メールパーソナライゼーションエディターの次の式は、オブジェクト配列を反復し、現在のジャーニーインスタンスに適用可能な `bookingCountry` を取得して、コンテンツに表示します。

  ```
  {{#each context.journey.events.<event_ID>.<object_path>.<object_array_name> as |l|}} 
  
  {%#if l.<attribute_path>.bookingNum = context.journey.technicalProperties.supplementalId%} {{l.<attribute_path>.bookingCountry}}  {%/if%}
  
  {{/each}}
  ```

* ジャーニーをトリガーするために使用されるイベントの例：

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

## ユースケースの例

### **ポリシー更新通知**

* **シナリオ**：保険プロバイダーは、お客様が保持するアクティブなポリシーごとに更新リマインダーを送信します。
* **実行**：
   * プロファイル：「John」。
   * 補足 ID：`"AutoPolicy123", "HomePolicy456"`。
   * ジャーニーは、パーソナライズされた更新日、カバレッジの詳細、プレミアム情報と共に、各ポリシーに対して個別に実行されます。

### **購読管理**

* **シナリオ**：購読サービスは、この購読のイベントをトリガーする際に、各購読に対して調整されたメッセージを送信します。
* **実行**：
   * プロファイル：「Jane」。
   * 補足 ID：`"Luma Yoga Program ", "Luma Fitness Program"`。
   * 各イベントには、購読 ID およびこの購読に関する詳細が含まれます。ジャーニーは、各イベント／購読に対して個別に実行されるので、購読ごとにパーソナライズされた更新オファーが可能になります。

### **製品レコメンデーション**

* **シナリオ**：e コマースプラットフォームは、お客様が購入した特定の製品に基づいてレコメンデーションを送信します。
* **実行**：
   * プロファイル：「Alex」。
   * 補足 ID：`"productID1234", "productID5678"`。
   * ジャーニーは、パーソナライズされたアップセルの商談と共に、各製品に対して個別に実行されます。

## チュートリアルビデオ {#video}

[!DNL Adobe Journey Optimizer] で補足識別子を有効にして適用する方法について説明します。

>[!VIDEO](https://video.tv.adobe.com/v/3464793?quality=12&captions=jpn)
