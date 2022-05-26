---
title: ランディングページでのカスタム JavaScript の使用
description: Journey Optimizerでランディングページのコンテンツを作成する方法を説明します。
feature: Landing Pages
topic: Content Management
role: User
level: Beginner
source-git-commit: f4b3a9de47e724f7b23df8a02b8106c131cf1b12
workflow-type: tm+mt
source-wordcount: '559'
ht-degree: 7%

---

# ランディングページでのカスタム JavaScript の使用 {#lp-custom-js}

カスタム JavaScript を使用してランディングページのコンテンツを定義できます。 例えば、高度なスタイル設定を実行する必要がある場合や、ランディングページにカスタムビヘイビアーを追加する場合は、独自のコントロールを作成し、 [!DNL Journey Optimizer].

## ランディングページへの JavaScript コードの挿入

ランディングページコンテンツにカスタム JavaScript を挿入するには、次のいずれかを実行します。

* コンテンツの作成を開始する際に既存のHTMLコンテンツを読み込み、カスタム JavaScript コードを含むファイルを選択します。 コンテンツの読み込み方法については、[この節](../design/existing-content.md)を参照してください。

* ランディングページを最初から、または保存済みのテンプレートからデザインします。 次をドラッグ&amp;ドロップ： **[!UICONTROL HTML]** コンテンツコンポーネントをキャンバスに挿入し、JavaSCript をコンポーネントに追加するためのソースコードを表示します。 でのHTMLコンポーネントの使用方法を説明します。 [この節](../design/content-components.md#HTML). <!--You can also simply switch the whole landing page content to code view and enter or paste your JavaScript code.-->

   ![](assets/lp_designer-html-component.png)

* JavaScript コードをコンテンツデザイナーに直接入力または貼り付けます。 独自のコンテンツの作成方法については、[iこの節](../design/code-content.md)を参照してください。

>[!NOTE]
>
>現在、JavaScript を実行中に [ランディングページのプレビュー](create-lp.md#test-landing-page).

ランディングページを正しく表示するには、以下の節で説明するように、次の構文を使用します。

## コードの初期化

JavaScript コードを初期化するには、 `lpRuntimeReady` イベント。 このイベントは、ライブラリの初期化が成功した後にトリガーされます。 コールバックは、 `lpRuntime` オブジェクトを使用して、ライブラリのメソッドとフックを公開します。

`LpRuntime` は、「ランディングページランタイム」を意味します。 このオブジェクトは、メインライブラリ識別子です。 カスタム JavaScript で使用できるフック、フォーム送信メソッド、その他のユーティリティメソッドが公開されます。

**例：**

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

フックを使用すると、フォーム送信のライフサイクル中にメソッドを添付できます。 例えば、フックを使用して、フォームが実際に送信される前に、フォームの検証を実行できます。

次に、使用できるフックを示します。

| 名前 | 説明 |
|--- |--- |
| addBeforeSubmitHook | フォーム送信前に呼び出されるカスタムフック。 送信を続行する場合は true を返し、送信をブロックする場合は false を返します。 |
| addBeforeSubmitHook | 失敗したフォーム送信時に呼び出されるカスタムフック。 |
| addOnSuccessHook | フォーム送信が成功したときに呼び出されるカスタムフック。 |

**例：**

```
//LpRuntime hooks
lpRuntime.hooks.addBeforeSubmitHook(function(){
    // Add your validation logic here.
});
```

## カスタムフォームの送信

以下に示す方法は、カスタムフォーム送信の実行に使用されます。

>[!NOTE]
>
>フォームの送信はカスタム JavaScript で処理されるので、デフォルトの送信をグローバル変数を設定して明示的に無効にする必要があります `disableDefaultFormSubmission` から `true`.

| 名前 | 説明 |
|--- |--- |
| submitForm | このメソッドは、フォームを送信し、送信後のフローを処理します。 |
| submitFormPartial | このメソッドはまた、フォームを送信しますが、送信後のフローはスキップします。 例えば、送信が成功した後に成功ページへのリダイレクトを設定した場合、部分的なフォーム送信の場合はリダイレクトは発生しません。 |

**例：**

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

| 名前 | 説明 |
|--- |--- |
| getFormData | このメソッドを使用して、 `formData` を JSON オブジェクトの形式で指定します。 このオブジェクトはに渡すことができます。 `submitForm` フォーム送信用 |

**例：**

```
let formData = lpRuntime.getFormData();                           // Method to generate formdata
 
lpRuntime.submitForm(formData);
```

## ユースケース

### 使用例 1:フォーム送信前の検証の追加

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

### 使用例 2:部分的なフォーム送信

例えば、ページ上に複数のチェックボックスがあるフォームがあるとします。 任意のチェックボックスをオンにすると、ユーザーが送信ボタンをクリックするのを待たずに、このデータをバックエンドに保存する必要があります。

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

### 使用例 3:カスタム分析タグ

JavaScript を使用して、入力フィールドのリスナーを追加し、カスタムの Analytics 呼び出しトリガーをアタッチできます。

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

### 使用例 4:ダイナミックフォーム

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
