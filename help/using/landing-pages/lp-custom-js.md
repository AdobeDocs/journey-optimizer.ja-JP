---
solution: Journey Optimizer
product: journey optimizer
title: ランディングページでのカスタム JavaScript の使用
description: このページでは、旅オプティマイザーのランディングページのコンテンツをデザインする方法について学習します。
feature: Landing Pages
topic: Content Management
role: User
level: Beginner
exl-id: 2a7ebead-5f09-4ea5-8f00-8b5625963290
source-git-commit: 020c4fb18cbd0c10a6eb92865f7f0457e5db8bc0
workflow-type: tm+mt
source-wordcount: '562'
ht-degree: 0%

---

# ランディングページでのカスタム JavaScript の使用 {#lp-custom-js}

カスタム JavaScript を使用して、ランディングページのコンテンツを定義することができます。 例えば、高度なスタイルを実行する必要がある場合、またはランディングページにカスタムビヘイビアーを追加する必要がある場合は、独自のコントロールを作成して、その [!DNL Journey Optimizer] コントロールを実行することができます。

## JavaScript コードのランディングページへの挿入

カスタム JavaScript をランディングページのコンテンツに挿入するには、次のいずれかの操作を行います。

* コンテンツの作成を開始するときに既存の HTML コンテンツを読み込み、カスタム JavaScript コードを含むファイルを選択します。 このセクション ](../email/existing-content.md) の内容 [ を読み込む方法について説明します。

* ランディングページは、最初に作成することも、保存したテンプレートからデザインすることもできます。 コンテンツコンポーネントをカンバスにドラッグ &amp; ドロップ **[!UICONTROL HTML]** し、ソースコードを表示して JavaSCript をコンポーネントに追加します。 ここで [ ](../email/content-components.md#HTML) は、HTML コンポーネントを使用する方法について説明します。 <!--You can also simply switch the whole landing page content to code view and enter or paste your JavaScript code.-->

   ![](assets/lp_designer-html-component.png)

* JavaScript コードをコンテンツデザイナーに直接入力するか、または貼り付けます。 ここでは ](../email/code-content.md) 、独自のコンテンツ [ をコーディングする方法について説明します。

>[!NOTE]
>
>現在のところ、ランディングページ ](create-lp.md#test-landing-page) のプレビュー時に JavaScript が表示される [ ようにすることはできません。

ランディングページが正しく表示されるようにするには、次のシンタックスを使用してください。

## コードの初期化

JavaScript コードを初期化するには、イベントを使用 `lpRuntimeReady` する必要があります。 このイベントは、ライブラリの初期化が正常に完了したときに開始されます。 コールバックは、ライブラリのメソッドとフックを公開するために、オブジェクトを使用して `lpRuntime` 実行されます。

`LpRuntime` 「ランディングページランタイム」を意味します。 このオブジェクトは、メインライブラリ識別子です。 フック、フォーム送信メソッド、およびカスタム JavaScript で使用可能なその他のユーティリティメソッドが公開されています。

**一**

```
if(window.lpRuntime){
    init(window.lpRuntime);
}else{
    window.addEventListener('lpRuntimeReady',function(e){
        init(e.detail);
    });
}
 
function init(lpRuntime){
    // Enter custom JavaScript here using methods from lpRuntime.
}
```

## フック

フックを使用すると、フォーム送信のライフサイクル中にメソッドを関連付けることができます。 例えば、フォームが実際に送信される前に、フックを使用して、何らかのフォーム検証を実行することができます。

使用できるフックは以下のとおりです。

| 氏名 | つい |
|--- |--- |
| addBeforeSubmitHook | フォームを送信する前に呼び出すカスタムフックです。 送信を継続する場合は true、送信をブロックする場合は false を返します。 |
| addOnFailureHook | フォーム送信に失敗したときに呼び出されるカスタムフックです。 |
| addOnSuccessHook | フォーム送信が成功したときに呼び出されるカスタムフックです。 |

**一**

```
//LpRuntime hooks
lpRuntime.hooks.addBeforeSubmitHook(function(){
    // Add your validation logic here.
});
```

## カスタムフォーム送信

以下のメソッドを使用して、カスタムフォームの送信を実行します。

>[!NOTE]
>
>フォームの送信はカスタム JavaScript によって処理されるため、デフォルトの送信は、グローバル変数 `disableDefaultFormSubmission` をに `true` 設定することによって明示的に無効化する必要があります。

| 氏名 | つい |
|--- |--- |
| submitForm | このメソッドでは、フォームが送信され、送信後フローが処理されます。 |
| submitFormPartial | このメソッドでは、フォームが送信されますが、送信された送信フローはスキップされます。 例えば、「成功ページを後に post」を設定した場合、部分的なフォームの送信によってリダイレクトが実行されることはありません。 |

**例**

```
//LpRuntime methods
window.disableDefaultFormSubmission = true        // Flag to disable the default submission flow.
 
lpRuntime.submitForm(formSubmissionData);         // This will trigger the default form submission handling like redirecting to error or success page.
  
lpRuntime.submitFormPartial(formSubmissionData,{   // This will not trigger the default submission handling.
    beforeSubmit : callback,
    onFailure : failureCallback,                   // Custom onFailureCallback - will be used in partial submission of form.
    onSuccess : successCallback                    // Custom onSuccessCallback - will be used in partial submission of form.
})
```

## ユーティリティ関数

| 氏名 | つい |
|--- |--- |
| getFormData | このメソッドを使用して、 `formData` JSON オブジェクトの形式でを取得することができます。 このオブジェクトは、フォームの送信のために `submitForm` 渡すことができます。 |

**一**

```
let formData = lpRuntime.getFormData();                           // Method to generate formdata
 
lpRuntime.submitForm(formData);
```

## 使用例

### 「ユースケース1」: フォームを送信する前に検証を追加します。

```
<html>
<body>
// Enter HTML body here.
  
<script>
        if(window.lpRuntime){
          console.log('got runtime',lpRuntime);
          init(window.lpRuntime);
        }else{
          window.addEventListener('lpRuntimeReady',function(e){
            init(window.lpRuntime);
          });
        }
        
  
      // Here validate the function is checking if the checkbox is selected. This method should return true if you want form submission.
      function validateForm(){
        return document.querySelector('.spectrum-Checkbox-input').checked;
      }    
  
      function init(lpRuntime){
          lpRuntime.hooks.addBeforeSubmitHook(function(){
              return validateForm(); // This method should return true if you want to proceed with submission.
          })
      }
  
</script>  
  
</body>
</html>
```

### 使用例 2: 部分フォームの送信

例えば、1つのフォームに複数のチェックボックスが表示されているとします。 チェックボックスをオンにすると、ユーザーが「送信」ボタンをクリックするのを待たずに、このデータをバックエンドに保存しておくことができます。

```
<html>
<body>
    <form>
        <input type='checkbox' value="1" name="name1"/>
        <input type='checkbox' value="2" name="name2"/>
        <input type='checkbox' value="3" name="name3"/>
        <input type='checkbox' value="4" name="name4"/>
    </form>
  
<script>
      window.disableDefaultFormSubmission=true;
 
      window.addEventListener('lpRuntimeReady',function(e){        
        init(e.detail)
      }
 
     function init(lpRuntime){
        window.getElementByTagName('input').addEventListener('change',function(e){
            let formData = lpRuntime.getFormData();
            lpRuntime.submitFormPartial(formData);
        })
      }
    </script>
  
</body>
</html>
```

### ユースケース 3: カスタム分析タグ

JavaScript を使用して、入力フィールドのリスナーを追加し、カスタムの分析呼び出しトリガーを関連付けることができます。

```
<html>
<body>
    <form>
        <input type='checkbox' value="1" name="name1"/>
        <input type='checkbox' value="2" name="name2"/>
        <input type='checkbox' value="3" name="name3"/>
        <input type='checkbox' value="4" name="name4"/>
    </form>
  
<script>
      window.disableDefaultFormSubmission=false;  
 
      window.addEventListener('lpRuntimeReady',function(e){        
        init(e.detail)
      }
 
     function init(lpRuntime){
         window.getElementByTagName('input').addEventListener('change',function(e){
            //trigger analytics events
        })
      }
        
    </script>
  
</body>
</html>
```

### Use case 4: Dynamic form

```
<html>
<body>
    <form>
        <input type='checkbox' value="1" name="name1"/>
        <div class="hiddenInput hidden">
            <input type='text' name="name2"/>
        </div>
    </form>
  
<script>
      window.disableDefaultFormSubmission=false;     
 
      window.addEventListener('lpRuntimeReady',function(e){        
        init(e.detail)
      }
 
      function init(lpRuntime){
        window.getElementByTagName('input').addEventListener('change',function(e){
            document.querySelector('.hiddenInput').toggleClass('hidden');
        })
      }
        
    </script>
  
</body>
</html>
```
