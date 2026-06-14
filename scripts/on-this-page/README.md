---
source-git-commit: f59dc265b0de732b52e9d26b6ee510733d0d760e
workflow-type: tm+mt
source-wordcount: '188'
ht-degree: 0%

---
# 「このページ上」ボックスツール

標準の追加と検証を行うためのツール **&quot;このページ上&quot;**&#x200B;の上部にある陰影ボックス
AJOのドキュメントページ。`.cursor/rules/on-this-page-box.mdc`の仕様を参照してください。
ロールアウトは、エピック **DOCAC-14936** （最上位フォルダーごとに1つのタスク）で追跡されます。

## 箱の見た目

```text
# Page Title {#anchor}

>[!BEGINSHADEBOX]

**On this page:** <one clear sentence describing the page's purpose>

>[!ENDSHADEBOX]
```

## 推奨されるワークフロー（フォルダーごと / Jira タスク）

リポジトリ ルート （`journey-optimizer.en/`）から実行します。

1. **ボックスを挿入** （各ページの前部から最初のドラフト文をシードする）
   `description`). 機械的な、idempotent、決して前部の問題に触れない：

   ```bash
   python scripts/on-this-page/add_on_this_page.py help/using/reports --seed-from-description
   ```

   `--dry-run`で最初にプレビューします。

2. **文言を調整します。** シードは出発点です。各文を編集して
目的のステートメントとして読み取ります（一文、プレーンテキスト、アメリカ英語）。 **リード
why**：読者の結果/メリットを述べます（&quot;...可能です &lt;outcome>&quot;）、なし
それぞれの要素のリストを表示するだけです。 ハウススタイルの機能名を一致させる（例：
&quot;Orchestrated campaign&quot;, &quot;アプリ内&quot;）。 `.cursor/rules/on-this-page-box.mdc`を参照してください。 自分が
`--seed-from-description`をスキップすると、`{{TODO...}}` プレースホルダーが代わりに挿入され、
バリデーターは残った部分にフラグを付けます。

3. PRを開く前に&#x200B;**検証**:

   ```bash
   python scripts/on-this-page/validate_on_this_page.py help/using/reports --require
   ```

   終了コードは任意のエラーに対してゼロではないので、CIをゲートできます。

## 範囲/除外事項

参照ページと構文ページはデフォルトで除外されます（パス部分`api-reference`,
`expression`, `functions`). 必要に応じて`--exclude ...`で上書きします。

## リポジトリ全体の進捗状況チェック

```bash
python scripts/on-this-page/validate_on_this_page.py help
```

`--require`がない場合、ボックスが見つからないページは`pending`として報告されます（
failure）を呼び出すと、ガイド全体のロールアウトの進行状況を追跡できます。
