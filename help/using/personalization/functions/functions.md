---
title: ヘルパー関数の使用について学習します。
description: 旅オプティマイザーヘルパー関数ライブラリ
feature: Personalization
topic: Personalization
role: Data Engineer
level: Experienced
exl-id: 9b0b0d8e-a819-4d2e-a241-f3c4d104eab9
source-git-commit: 315c3e8c04b2e3944d0d5b2befb205acbe0ef7c9
workflow-type: tm+mt
source-wordcount: '1744'
ht-degree: 0%

---

# ヘルパー関数の使用について学習します。{#functions}

テンプレート言語を使用 [!DNL Journey Optimizer] して、計算、データフォーマットまたは変換、条件などのデータに対する操作を実行し、カスタマイズのコンテキストでそれらを操作します。 このページ ](../personalization-syntax.md) のパーソナル化のシンタックスガイドラインに [ ついて説明します。

➡️ [ このビデオでヘルパー関数の使用方法について説明しています。](#video)

テンプレート言語は、次に示すように、エクスプレッションエディターの「パーソナライズ」ドロップダウンリストで使用可能なヘルパー関数で活用できます。

![](../assets/access-helper-functions.png)

式エディターは、関数、ヘルパー、演算子 ](#operators-helper) と [ いう3つのカテゴリ [ にグループ化されて [!DNL Journey Optimizer] います。 ](#helper-helper) [ ](#functions-helper)

カテゴリと関数にアクセスするには、カテゴリーを選択します。

アイコンをクリックすると、 `>` サブカテゴリにアクセスできます。 アイコンをクリック `+` して関数を選択します。この関数は、パーソナル化スクリーンに非常に新しく追加されています。

`...`このアイコンをクリックすると、関数の説明が表示され、お気に入りに追加できます。[詳細情報](../personalize.md#fav)

## 業務{#functions-helper}

### 集計関数と配列関数

<table>
    <tr>
        <td><a href="aggregation.md#average">所要</a></td><td>この関数は、配列内の選択されたすべての値の算術平均を返します。</td>
    </tr>
    <tr>
        <td><a href="aggregation.md#count">ティック</a></td><td>この関数は、指定された配列内のエレメントの数を返します。</td>
    </tr>
    <tr>
        <td><a href="aggregation.md#count-only-null">Count Null のみ</a></td><td>この関数は、リスト内の null 値の数を数えます。</td>
    </tr>
    <tr>
        <td><a href="aggregation.md#count-with-null">数が Null の場合</a></td><td>この関数は、null 値を含むリストのすべてのエレメントを数えます。</td>
    </tr>
    <tr>
        <td><a href="arrays-list.md#distinct">異なっ</a></td><td>この関数は、配列または重複する値が削除されたリストから値を取得します。</td>
    </tr>
    <tr>
        <td><a href="arrays-list.md#distinct-count-with-null">Null 値を持つ個別カウント</a></td><td>この関数は、null 値を含む異なる値の数を表示します。</td>
    </tr>
    <tr>
        <td><a href="arrays-list.md#head">最初の項目</a></td><td>この関数は、配列またはリストの最初のアイテムを返します。</td>
    </tr>
    <tr>
        <td><a href="arrays-list.md#first-n">配列の最初の n</a></td><td>この関数は、指定された数値式に基づいて昇順にソートした場合、配列内の最初の「N」項目を返します。</td>
    </tr>
    <tr>
        <td><a href="arrays-list.md#in">単位</a></td><td>この関数は、項目が配列またはリストに属しているかどうかを判別するために使用されます。</td>
    </tr>
    <tr>
        <td><a href="arrays-list.md#includes">あり</a></td><td>この関数は、配列またはリストに特定の項目が含まれているかどうかを判別します。</td>
    </tr>
    <tr>
        <td><a href="arrays-list.md#intersects">交わる</a></td><td>この関数は、2つの配列またはリストに共通のメンバーが少なくとも1つあるかどうかを判定します。</td>
    </tr>
    <tr>
        <td><a href="arrays-list.md#last-n">配列の最後の n</a></td><td>この関数は、指定された数値式に基づいて昇順にソートした場合に、配列内の最後の「N」アイテムを返します。</td>
    </tr>
    <tr>
        <td><a href="aggregation.md#max">値</a></td><td>この関数は、配列内の選択されたすべての値のうち、最も大きな値を返します。</td>
    </tr>
    <tr>
        <td><a href="aggregation.md#min">最小</a></td><td>この関数は、配列内の選択されたすべての値のうち、最小の値を返します。</td>
    </tr>
    <tr>
        <td><a href="arrays-list.md#notin">ではありません</a></td><td>この関数は、項目が配列またはリストのメンバーでないかどうかを判別します。</td>
    </tr>
    <tr>
        <td><a href="arrays-list.md#subset">サブセット</a></td><td>この関数は、特定の配列 (array A) が別の配列のサブセットである (配列 a) かどうかを判別します。つまり、配列 A のすべてのエレメントが配列 B のエレメントであるとします。</td>
    </tr>
    <tr>
        <td><a href="aggregation.md#sum">総額</a></td><td>この関数は、配列内の選択されたすべての値の合計を返します。</td>
    </tr>
    <tr>
    <td><a href="arrays-list.md#superset">のスーパーセット</a></td><td>この関数は、特定の配列 (array A) が別の配列のスーパーセット (array B) かどうかを判別します。つまり、配列 A に配列 B のすべての要素が含まれている場合などです。</td>
    </tr>
</table>

### 日付時刻関数{#date-functions}

<table>
    <tr>
        <td><a href="dates.md#age">寿命</a></td><td>この関数は、指定した日付から経過時間を取得します。</td>
    </tr>
    <tr>
        <td><a href="dates.md#current">現在の時間 (ミリ秒)</a></td><td>この関数は、紀元ミリ秒単位で現在の時刻を取得します。</td>
    </tr>
    <tr>
        <td><a href="dates.md#date-diff">日付の違い</a></td><td>この関数は、2つの日付間の差を日数で取得します。</td>
    </tr>
    <tr>
        <td><a href="dates.md#day-week">曜日</a></td><td>この関数は、曜日を取得します。</td>
    </tr>
    <tr>
        <td><a href="dates.md#day-year">年通算日付</a></td><td>この関数は、年の通算日を取得します。</td>
    </tr>
    <tr>
        <td><a href="dates.md#format-date">日付の形式</a></td><td>この関数は、日付と時刻の値をフォーマットします。</td>
    </tr>
    <tr>
        <td><a href="dates.md#set-days">日の設定</a></td><td>この関数は、指定された日時の月の日付を設定します。</td>
    </tr>
    <tr>
        <td><a href="dates.md#set-hours">時間の設定</a></td><td>この関数は、日付と時刻の間の時間を設定します。</td>
    </tr>
    <tr>
        <td><a href="dates.md#to-utc">UTC へ</a></td><td>この関数では、datetime が UTC に変換されます。</td>
    </tr>
    <tr>
        <td><a href="dates.md#week-of-year">年の通算週</a></td><td>この関数は、年の通算週を返します。</td>
    </tr>
</table>
</table>

### マップ関数 {#map-functions}

<table>
    <tr>
        <td><a href="maps.md#get">取得</a></td><td>この関数は、指定されたキーのマップの値を取得するために使用されます。</td>
    </tr>
    <tr>
        <td><a href="maps.md#keys">キー</a></td><td>この関数は、指定されたマップのすべてのキーを取得するために使用されます。</td>
    </tr>
    <tr>
        <td><a href="maps.md#values">指定</a></td><td>この関数は、指定されたマップのすべての値を取得します。</td>
    </tr>
</table>

### 数学関数 {#math-functions}

<table>
    <tr>
        <td><a href="objects.md#absolute">固定</a></td><td>この関数は、数値の絶対値を返します。</td>
    </tr>
    <tr>
        <td><a href="objects.md#random">無作為</a></td><td>この関数は、0 ~ 1 の範囲のランダムな値を返します。</td>
    </tr>
    <tr>
        <td><a href="objects.md#round-down">切り捨て</a></td><td>この関数は、数値の切り捨てを行います。</td>
    </tr>
    <tr>
        <td><a href="objects.md#round-up">切り上げ</a></td><td>この関数は、数値を切り上げます。</td>
    </tr>
    <tr>
        <td><a href="objects.md#to-percentage">比率にする</a></td><td>この関数は、数値をパーセント単位で指定します。</td>
    </tr>
    <tr>
        <td><a href="objects.md#to-precision">精度</a></td><td>この関数は、数値を必要な精度に変換します。</td>
    </tr>
</table>

### オブジェクト関数 {#object-functions}

<table>
    <tr>
        <td><a href="objects.md#isNotNull">は null ではありません。</a></td><td>この関数は、オブジェクト参照が存在するかどうかを調べるために使用されます。</td>
    </tr>
    <tr>
        <td><a href="objects.md#isNull">は null</a></td><td>この関数は、オブジェクト参照が存在しないかどうかを調べるために使用されます。</td>
    </tr>
</table>

### ストリング関数 {#string-functions}

<table>
    <tr>
        <td><a href="string.md#camelCase">Camel ケース</a></td><td>この関数は、ストリングの各単語の最初の文字を大文字にするために使用されます。</td>
    </tr>
    <tr>
        <td><a href="string.md#concat">連結</a></td><td>この関数は、2つのストリングを1つに結合するために使用されます。</td>
    </tr>
    <tr>
        <td><a href="string.md#contains">さ</a></td><td>この関数は、ストリングに指定された部分文字列が含まれているかどうかを調べるために使用します。</td>
    </tr>
    <tr>
        <td><a href="string.md#doesNotContain">がありません</a></td><td>この関数は、ストリングに指定されたサブストリングが含まれていないかどうかを判別するために使用されます。</td>
    </tr>
    <tr>
        <td><a href="string.md#doesNotEndWith">で終わらない</a></td><td>この関数は、ストリングの末尾に指定された部分文字列が含まれていないかどうかを判別するために使用されます。</td>
    </tr>
    <tr>
        <td><a href="string.md#doesNotStartWith">で始まらない</a></td><td>この関数は、ストリングが特定の部分文字列と共に始まらないかどうかを判別するために使用されます。</td>
    </tr>
    <tr>
        <td><a href="string.md#encode64">エンコード64</a></td><td>この関数は、ストリングのエンコードまたはデコードに使用されます。</td>
    </tr>
    <tr>
        <td><a href="string.md#endsWith">で終わる</a></td><td>この関数は、ストリングの末尾に指定された部分文字列が含まれるかどうかを調べるために使用されます。</td>
    </tr>
        </tr>
    <tr>
        <td><a href="string.md#equals">Str</a></td><td>この関数を使用して、文字列が特定の部分文字列と共に開始されないかどうかを判別します。大文字と小文字が区別されます。</td>
    </tr>
    <tr>
        <td><a href="string.md#equalsIgnoreCase">大文字と小文字を区別</a></td><td>この関数を使用して、文字の大文字と小文字を区別せずに、文字列が特定の部分文字列と共に始まらないかどうかを判断します。</td>
    </tr>
    <tr>
        <td><a href="string.md#extractEmailDomain">電子メールドメインの抽出</a></td><td>この関数は、電子メールアドレスのドメインを抽出するために使用されます。</td>
    </tr>
    <tr>
        <td><a href="string.md#get-url-host">Url ホストの取得</a></td><td>この関数は、url ホストを取得するために使用されます。</td>
    </tr>
    <tr>
        <td><a href="string.md#get-url-path">Url パスを取得します。</a></td><td>この関数は、url パスを取得するために使用されます。</td>
    </tr>
    <tr>
        <td><a href="string.md#get-url-protocol">Get url protocol</a></td><td>この関数は、url プロトコルを取得するために使用されます。</td>
    </tr>
    <tr>
        <td><a href="string.md#index-of">インデックスの作成</a></td><td>この関数は、2番目のパラメーターが最初に出現した位置 (最初の引数) を返します。 一致するアイテムがない場合は-1 を返します。</td>
    </tr>
    <tr>
        <td><a href="string.md#isEmpty">IsEmpty</a></td><td>この関数は、文字列または式が空であるかどうかをチェックするために使用されます。</td>
    </tr>
    <tr>
        <td><a href="string.md#is-not-empty">は空白ではありません。</a></td><td>この関数は、パラメーターのストリングが空でない場合は、true を返します。</td>
    </tr>
    <tr>
        <td><a href="string.md#last-index-of">最後のインデックス</a></td><td>この関数は、2番目のパラメーターが最後に出現する位置の位置 (最初の引数) を返します。 一致するアイテムがない場合は、-1 を返します。</td>
    </tr>
    <tr>
        <td><a href="string.md#leftTrim">左トリム</a></td><td>この関数は、ストリングの先頭から空白文字を削除します。</td>
    </tr>
    <tr>
        <td><a href="string.md#length">長さ</a></td><td>この関数は、ストリングまたは式の文字数を取得するために使用されます。</td>
    </tr>
    <tr>
        <td><a href="string.md#like">という感じで</a></td><td>この関数は、指定したパターンにストリングが一致するかどうかを調べるために使用されます。</td>
    </tr>
    <tr>
        <td><a href="string.md#lower">小文字</a></td><td>この関数は、ストリングを小文字に変換します。</td>
    </tr>
    <tr>
        <td><a href="string.md#mask">隠す</a></td><td>この関数は、ストリングの一部 (「X」文字) を置き換えるために使用されます。</td>
    </tr>
    <tr>
        <td><a href="string.md#matches">該当</a></td><td>この関数は、ストリングが特定の正規表現に一致するかどうかを調べるために使用されます。</td>
    </tr>
    <tr>
        <td><a href="string.md#md5">ハッシュ</a></td><td>この関数は、入力ストリングの md5 ハッシュ値を返します。</td>
    </tr>
    <tr>
        <td><a href="string.md#notEqualTo">が不等号</a></td><td>この関数を使用して、指定したストリングと一致するストリングがないかどうかを判別します。</td>
    </tr>
    <tr>
        <td><a href="string.md#not-equal-with-ignore-case">は無視されます。等しくない</a></td><td>大文字と小文字を区別して比較します。</td>
    </tr>
    <tr>
        <td><a href="string.md#regexGroup">正規表現グループ</a></td><td>この関数は、指定された正規表現に基づいて特定の情報を抽出するために使用されます。</td>
    </tr>
    <tr>
        <td><a href="string.md#replace">置き</a></td><td>この関数は、ストリング内の指定された部分を別の部分文字列に置き換えます。</td>
    </tr>
    <tr>
        <td><a href="string.md#replaceAll">すべて置換</a></td><td>この関数は、指定されたリテラルの「置換」ストリングを使用して、「ターゲット」に一致するテキストのすべての部分文字列を置換します。</td>
    </tr>
    <tr>
        <td><a href="string.md#rightTrim">右トリム</a></td><td>この関数は、ストリングの末尾から空白文字を削除します。 </td>
    </tr>
    <tr>
        <td><a href="string.md#split">分割</a></td><td>この関数は、指定された文字でストリングを分割するために使用されます。</td>
    </tr>
    <tr>
        <td><a href="string.md#startsWith">開始点</a></td><td>この関数は、ストリングの先頭に指定された部分文字列が含まれるかどうかを調べるために使用されます。</td>
    </tr>
    <tr>
        <td><a href="string.md#string-to-date">文字列を日付に</a></td><td>この関数は、ストリングを日付に変換するために使用されます。 無効な入力については、紀元日付が出力されます。</td>
    </tr>
    <tr>
        <td><a href="string.md#string-to-integer">ストリングを整数に</a></td><td>この関数は、ストリング値を整数値に変換します。</td>
    </tr>
    <tr>
        <td><a href="string.md#string-to-number">文字列を数値に</a></td><td>この関数は、ストリングを数値に変換するために使用されます。 無効な入力については、出力と同じストリングが返されます。</td>
    </tr>
    <tr>
        <td><a href="string.md#sub-string">サブストリング</a></td><td>この関数は、開始インデックスと終了インデックスの間にあるストリング式のサブストリングを返します。</td>
    </tr>
    <tr>
        <td><a href="string.md#titleCase">タイトルの大文字/小文字</a></td><td>この関数は、ストリングの各単語の最初の文字を大文字にするために使用されます。</td>
    </tr>
    <tr>
        <td><a href="string.md#to-bool">ブールに</a></td><td>この関数は、引数の値をブール値に変換します。その型によって異なります。</td>
    </tr>
    <tr>
        <td><a href="string.md#to-date-time">日付/時刻</a></td><td>この関数は、ストリングを日付に変換するために使用されます。 無効な入力については、紀元日付が出力されます。</td>
    </tr>
    <tr>
        <td><a href="string.md#to-date-time-only">日付時刻のみ</a></td><td>この関数は、引数の値を日付時刻のみの値に変換します。. 無効な入力については、紀元日付が出力されます。</td>
    </tr>
    <tr>
        <td><a href="string.md#trim">裁断</a></td><td>この関数は、ストリングの先頭および末尾のホワイトスペースを削除します。</td>
    </tr>
    <tr>
        <td><a href="string.md#upper">大文字</a></td><td>この関数は、ストリングを大文字に変換します。</td>
    </tr>
    <tr>
        <td><a href="string.md#url-decode">Url デコード</a></td><td>この関数を使用して、url にエンコードされたストリングをデコードします。</td>
    </tr>
    <tr>
        <td><a href="string.md#url-encode">Url エンコード</a></td><td>この関数は、ストリングを url エンコードするために使用されます。</td>
    </tr>
</table>


## ヘルパー{#helper-helper}

ヘルパーについては、このページ ](helpers.md) で [ 詳しく説明しています。


<table>
    <tr>
        <td><a href="helpers.md#default">デフォルトのフォールバック値</a></td><td>この関数では、デフォルトの変数をレンダリングできます。</td>
    </tr>
    <tr>
        <td><a href="helpers.md#each">相互</a></td><td>この関数は、配列の繰り返し処理に使用されます。</td>
    </tr>
    <tr>
        <td><a href="helpers.md#if-function">もし</a></td><td>この関数は、条件ブロックを定義するために使用されます。式の評価が true を返した場合、そのブロックはレンダリングされます。</td>
    </tr>
    <tr>
        <td><a href="helpers.md#let">Let</a></td><td>この関数を使用して、式を変数として保存して、後で使用することができます。</td>
    </tr>
   <tr>
        <td><a href="helpers.md#unless">ない限り</a></td><td>この関数は、条件ブロックを定義するために使用されます。式の評価が false を返すと、そのブロックはレンダリングされます。</td>
    </tr>
    <tr>
        <td><a href="helpers.md#with">With</a></td><td>この関数は、テンプレートパーツの評価トークンを変更するために使用されます。</td>
    </tr>
</table>

## Operators{#operators-helper}

### 算術関数 {#arithmetic-helper}

算術関数は、値に基づいて基本的な計算を実行するために使用されます。

<table>
    <tr>
        <td><a href="arithmetic-functions.md#add">他</a></td><td>この演算子は、2つの引数式の合計を検索するために使用されます。</td>
    </tr>
    <tr>
        <td><a href="arithmetic-functions.md#divide">分割</a></td><td>この演算子は、2つの引数式の商を求めるために使用されます。</td>
    </tr>
    <tr>
        <td><a href="arithmetic-functions.md#multiply">掛け算</a></td><td>この演算子は、2つの引数式の積を検索するために使用されます。</td>
    </tr>
    <tr>
        <td><a href="arithmetic-functions.md#remainder">割り算</a> </td><td>この演算子は、2つの引数式を割った余りを求めるために使用されます。</td>
    </tr>
    <tr>
        <td><a href="arithmetic-functions.md#substract">加減</a> </td><td>この演算子は、2つの式の違いを返します。</td>
    </tr>
</table>


### ブール関数 {#boolean-functions}

ブール関数は、様々なエレメントに対してブールロジックを実行するために使用されます。

<table>
    <tr>
        <td><a href="operators.md#and">そして</a></td><td>この演算子は、論理積を作成します。</td>
    </tr>
    <tr>
        <td><a href="operators.md#or">か</a></td><td>この演算子は、論理和を作成します。</td>
    </tr>
</table>


### 比較関数 {#comparison-functions}

比較関数は、異なる式と値を比較するために使用され、true または false を返します。

<table>
    <tr>
        <td><a href="operators.md#equals">Str</a></td><td>この操作により、値が等しいかどうかがチェックされます。</td>
    </tr>
    <tr>
        <td><a href="operators.md#greaterthan">より大きい</a></td><td>この演算子は、最初の値が2番目の値より大きいかどうかをチェックします。</td>
    </tr>
    <tr>
        <td><a href="operators.md#greaterthanorequal">「より大きい」または「等しい」</a></td><td>この演算子は、最初の値が2番目の値以上かどうかをチェックします。</td>
    </tr>
    <tr>
        <td><a href="operators.md#lessthanorequal">以下</a> </td><td>この演算子は、最初の値が2番目の値以下かどうかをチェックします。</td>
    </tr>
    <tr>
        <td><a href="operators.md#notequal">が不等号</a></td><td>この演算子は、指定された式が値が指定されていないかどうかを調べます。</td>
    </tr>
</table>

## 操作方法のビデオ{#video}

パーソナル化ヘルパー関数を使用してパーソナル化の値を変換し、ヘルパー関数について別の用途について理解する方法について説明します。

>[!VIDEO](https://video.tv.adobe.com/v/334244?quality=12)
