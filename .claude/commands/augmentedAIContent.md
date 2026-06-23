---
source-git-commit: bf5866b0e7437f93936f573fd83ada8526fe004d
workflow-type: tm+mt
source-wordcount: '381'
ht-degree: 3%

---
# augmentedAIContent

Journey Optimizer ドキュメントリポジトリの1つ以上のマークダウンファイルの最後に、自動生成AI アシスタント アコーディオンを追加します。

## ターゲットリポジトリ

`help/using/` （リポジトリルートに対して相対的）

## アコーディオン構文（Experience League）

```
+++Title of the accordion

Content here — any standard markdown is valid.

+++
```

**ルール：**
- 1行の`+++Title` — タイトルはすぐに`+++`に続きます
- 行の`+++`のみがアコーディオンを閉じます
- 開始`+++`の前と終了`+++`の後の空白行

---

## ワークフロー

### ステップ 1：ターゲットの選定

ユーザーに尋ねる：
> エンリッチメントするファイルまたはフォルダー
> - 単一ファイル：リポジトリルートに対する相対パス （例：`help/using/email/get-started-email.md`）
> - フォルダー：すべての`.md` ファイル （例：`help/using/email`）
> - ファイル/フォルダーのリスト

フォルダーが指定されている場合は、見つかった`.md` ファイルを一覧表示し、処理する前に確認します。

### ステップ 2 – 各ファイルについて：読み取りと生成

1. **ファイル**&#x200B;を完全に読み取ります。
2. **ページトピックを理解する** – どのような機能、概念、タスクをカバーしていますか？
3. **以下のルールを使用して、アコーディオンコンテンツ**&#x200B;を生成します。
4. **AI アコーディオンが既に末尾に存在するかどうかを**&#x200B;確認します（末尾の`+++AI Assistant`を探してください）。 はい場合は、ユーザーに「置換」または「スキップ」を依頼します。

### ステップ 3 - アコーディオンを追加する

ファイルの最後に追加します。 他のコンテンツは変更しないでください。

### ステップ 4：レポート

- 変更されたファイル：✓
- スキップされたファイル +理由（既にアコーディオン/空/インデックスページがあります）

---

## コンテンツ生成ルール

ページを分析し、**の下のセクションをマークダウン箇条書きとして**&#x200B;順番に作成します。 意味のあるコンテンツを抽出できないセクションをスキップします。

### アコーディオンタイトル

`+++AI Assistant — Page context`

### 1. TL;DR

そのページが教えたり可能にすることの一文の要約。

```
- **TL;DR:** [one sentence]
```

### &#x200B;2. 意図

3-6このページを読んだ後に達成できること。

```
**Intents:**
- [action]
- [action]
```

### &#x200B;3. 用語集

短い定義を含むこのページ/機能に固有の主な用語。 製品固有の用語にフラグを付ける：

```
**Glossary:**
- **[Term]**: [definition] *(product-specific)*
```

このページに関連する用語のみを含めます。 一般的なマーケティング用語は使用しないでください。

### &#x200B;4. ガードレール

制限事項、前提条件、権限、またはページに記載されている制約。

```
**Guardrails:**
- [guardrail]
```

### &#x200B;5. 用語

正規の名前、頭字語、使用可能なバリアント、類義語、曖昧さ回避。 主にAI パイプラインの正規化に関するものです。

```
**Terminology:**
- Canonical name: [name] — Acronym: [acronym] — variants: [list]
- Synonyms: "[term A]" = "[term B]"
- Do not confuse: "[term]" ≠ "[other term]"
```

### &#x200B;6. よくある質問

3～6の質問に簡単に回答。

```
**FAQ:**
- **Q: [question]** — [short answer]
```

### 含めないもの

- 本文コンテンツを&#x200B;**not**&#x200B;書き換えまたは要約します（既にページ内にあります）
- **not**&#x200B;に手順ごとの指示を含める
- ページでサポートされていないコンテンツを&#x200B;**not**&#x200B;で作成してください

### 完全テンプレート

```markdown
+++ AI Knowledge Reference

This section contains structured knowledge intended to support interpretation, retrieval, and question answering related to this topic.

For complete understanding, this information should be combined with the documentation on this page. Neither source is intended to stand alone; the page describes the feature, while this section provides additional context that helps disambiguate terminology, intent, applicability, and constraints.

- **TL;DR:** [one sentence]

**Intents:**
- [intent]

**Glossary:**
- **[Term]**: [definition]

**Guardrails:**
- [guardrail]

**Terminology:**
- Canonical name: [name] — Acronym: [acronym] — variants: [variants]
- Synonyms: "[a]" = "[b]"
- Do not confuse: "[x]" ≠ "[y]"

**FAQ:**
- **Q: [question]** — [short answer]

+++
```

---

## メモ

- ファイルを1つずつ処理して品質を確保します。
- 非常に短いページまたはインデックスのみのページにフラグを付け、スキップするかどうかをユーザーに尋ねます。
- 新しいファイルは作成しないでください。既存の`.md` ファイルのみを編集してください。
