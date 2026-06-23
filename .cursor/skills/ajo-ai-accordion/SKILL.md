---
name: ajo-ai-accordion
description: 各マークダウンファイルの最後にAI アシスタントのアコーディオンセクションを追加して、Adobe Journey Optimizer ドキュメントページを強化します。 各ページを読み取り、ページのトピックにもとづいてAI アシスタントの関連コンテンツを自動生成し、折りたたみ可能なアコーディオンとして挿入します。 AJO ドキュメントにAI情報を追加する場合、AI コンテンツを使用してAJOのマークダウンページを充実させる場合、またはAI アコーディオンセクションを使用してマークダウンファイルのファイルまたはフォルダーを処理する場合に使用します。
disable-model-invocation: true
source-git-commit: bf5866b0e7437f93936f573fd83ada8526fe004d
workflow-type: tm+mt
source-wordcount: '565'
ht-degree: 1%

---


# AJO AI Accordion Enrichment

Journey Optimizer ドキュメントリポジトリの1つ以上のマークダウンファイルの最後に、自動生成AI アシスタント アコーディオンを追加します。

## ターゲットリポジトリ

`/Users/sauviat/GitHub/GHEC/journey-optimizer.en/help/using/`

## アコーディオン構文（Experience League）

```markdown
+++Title of the accordion

Content here — any standard markdown is valid.

+++
```

**ルール：**
- 1行の`+++Title` — タイトルはすぐに`+++`に続き、間にスペースがありません
- 行の`+++`のみがアコーディオンを閉じます
- 開始`+++`の前と終了`+++`の後の空白行

&#x200B;---

## ワークフロー

### ステップ 1：ターゲットの選定

ユーザーに尋ねる：

> エンリッチメントするファイルまたはフォルダー
> - 単一ファイル：リポジトリルートに対する相対パス （例：`help/using/email/get-started-email.md`）
> - フォルダー：再帰的に内部のすべての`.md` ファイルを処理します（例：`help/using/email`）。
> - ファイル/フォルダーのリスト

`AskQuestion`を使用してください。使用できない場合は、会話で質問してください。

フォルダーが指定されている場合は、見つかったすべての`.md` ファイルを一覧表示し、処理する前にユーザーに確認します。

### ステップ 2 – 各ファイルについて：読み取りと生成

各ターゲットファイルに対して：

1. **ファイル**&#x200B;を完全に読み取ります。
2. **ページトピックを理解する** – どのような機能、概念、タスクをカバーしていますか？
3. **以下のコンテンツ生成ルールを使用して、アコーディオンコンテンツ**&#x200B;を生成します。
4. **AI アコーディオンが既にファイルの末尾に存在するかどうかを**&#x200B;確認します（末尾の`+++`を探してください）。 機能する場合は、置き換えるかスキップするかをユーザーに尋ねます。

### ステップ 3 - アコーディオンを追加する

ファイルの最後に次の行を追加します。

```markdown
+++[ACCORDION_TITLE]

[GENERATED_CONTENT]

+++
```

ファイル内の他のコンテンツは変更しないでください。

### ステップ 4：レポート

すべてのファイルを処理した後：
- 変更されたファイルを一覧表示✓
- スキップされたファイルと理由のリスト（既にアコーディオン、空のファイル、関連性がないなど）

&#x200B;---

## コンテンツ生成ルール

マークダウンページを分析して、アコーディオンコンテンツを生成します。 次のセクション **を順番**&#x200B;に作成し、マークダウン箇条書きとして書式設定します。 ページから意味のあるコンテンツを抽出できないセクションはスキップします。

&#x200B;---

### アコーディオンタイトル

使用：`+++AI Assistant — Page context`

&#x200B;---

### 生成するセクション （順序）

**1. TL;DR**

一文です。 このページは何を教えるか、有効にするか？

```markdown
- **TL;DR:** [one sentence summary]
```

&#x200B;---

**2. インテント**

ユーザーがこのページを読んだ後に達成できることの箇条書きリスト（3 ～ 6項目）。

```markdown
**Intents:**
- [action the user can perform]
- [action the user can perform]
```

&#x200B;---

**3. 用語集**

このページ/機能に固有の主な用語と短い定義。 製品固有の用語にフラグを付ける：

```markdown
**Glossary:**
- **[Term]**: [definition] *(product-specific)*
- **[Term]**: [definition]
```

このページのトピックに関連する用語のみを含めます。 一般的なマーケティング用語は使用しないでください。

&#x200B;---

**4. ガードレール**

制限事項、前提条件、権限、またはページに記載されている制約。

```markdown
**Guardrails:**
- [guardrail or prerequisite]
- [guardrail or prerequisite]
```

&#x200B;---

**5. 用語**

正規の製品名、略語、受け入れられているバリエーション、類義語、曖昧さ回避のヒント。 このセクションは、主にAI パイプラインの正規化を目的としています。

```markdown
**Terminology:**
- Canonical name: [e.g. Adobe Journey Optimizer]
- Acronym: [e.g. AJO] — variants: [e.g. Journey Optimizer, A-JO]
- Synonyms: [e.g. "brand guidelines" = "brand rules", "branding standards"]
- Do not confuse: [e.g. "AI Assistant" ≠ "Adobe Sensei"]
```

ページに存在するか暗黙的なエントリのみを含めます。

&#x200B;---

**6. FAQ**

3-6の質問ユーザーがこのページのコンテンツについて簡単な回答で尋ねるかもしれません。

```markdown
**FAQ:**
- **Q: [question]** — [short answer]
- **Q: [question]** — [short answer]
```

&#x200B;---

### 含めないもの

- ページの本文コンテンツを&#x200B;**not**&#x200B;書き換えたり、要約したりしてください（既に存在します）。
- **not**&#x200B;には、手順ごとの指示を含めます（これらはページ内にあります）。
- ページでサポートされていないコンテンツを&#x200B;**not**&#x200B;で作成してください。

&#x200B;---

### フルアコーディオンテンプレート

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
- Canonical name: [name]
- Acronym: [acronym] — variants: [variants]

**FAQ:**
- **Q: [question]** — [short answer]

+++
```

&#x200B;---

## メモ

- ファイルを一括ではなく1つずつ処理することで、生成品質を高く保つことができます。
- ページが非常に短い場合や、純粋にリダイレクト/インデックスページの場合は、ページにフラグを付け、スキップするかどうかをユーザーに尋ねます。
- 新しいファイルは作成しないでください。既存の`.md` ファイルのみを編集してください。
