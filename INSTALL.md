---
source-git-commit: 08eaa7ae974c134ea2e920a1fa854dcf6a971e18
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 2%

---
# 🚀 カーソルエージェントのインストール

カーソルエージェントは、ドキュメントをより効率的に作成および管理するのに役立つ共有ツールです。

## 初回設定

これは、リポジトリごとに **1 回** 実行するだけで済みます。

### オプション 1：カーソルの使用（推奨 ⭐）

1. Open Cursor Chat （`Cmd+L` or `Ctrl+L`）
2. タイプ：

   ```
   @setup-agents
   ```

3. エージェントは自動的に以下を行います。
   - SSH および HTTPS アクセスのテスト
   - 作業方法を使用
   - 必要に応じて設定の手順を説明します
4. 完了！✨

**注意：**`git.corp.adobe.com` への SSH または HTTPS アクセス権があるかどうかをエージェントが自動的に検出し、適切なメソッドを使用します。 どちらも機能しない場合は、ガイド付きの設定が提供されます。

### オプション 2：端子を使用する

1. リポジトリルートのターミナルを開きます。
2. 実行：

   ```bash
   ./setup-agents.sh
   ```

   スクリプトは自動的に以下を行います。
   - SSH および HTTPS アクセスのテスト
   - 作業方法を使用
   - 必要に応じてセットアップ手順を表示する

   または手動（Git が設定されていることがわかっている場合）:

   ```bash
   git submodule update --init --recursive
   ```

3. 完了！✨

## 検証

セットアップ後、インストールを確認します。

```bash
ls .cursor-agents/agents/
```

以下が表示されます。
- `draft-page-generator.md`
- `fix-grammar.md`
- その他。

## 用途

インストールが完了すると、Cursor でエージェントを使用できるようになります。

```
@draft-page      # Generate a new documentation page
@fix-grammar     # Fix grammar in current file
```

使用可能なエージェントの完全なリストについては、[AGENTS.md](AGENTS.md) を参照してください。

## エージェントの更新

すべてのエージェントの最新バージョンを取得するには：

### オプション 1：カーソルの使用

```
@update-agents
```

### オプション 2：端子を使用する

```bash
git submodule update --remote
```

## トラブルシューティング

### 「エージェントが見つかりません」エラー

このエラーが表示された場合は、エージェントがまだインストールされていません。 実行：

```
@setup-agents
```

### サブモジュールが空です

`.cursor-agents/` が存在するが空の場合：

```bash
git submodule update --init --recursive --remote
```

### 権限が拒否されました

セットアップスクリプトが実行可能であることを確認します。

```bash
chmod +x setup-agents.sh
```

### ネットワーク/VPN の問題

- Adobe VPN に接続していることを確認します
- ネットワーク接続の確認
- Git アクセスを確認します。

  ```bash
  git ls-remote https://git.corp.adobe.com/AdobeDocs/CursorAgents
  ```

## 仕組み

カーソルエージェントは、**git サブモジュール** として配布されます。

```
your-repo/
  ├── .cursor-agents/          ← Git submodule
  │   ├── agents/
  │   │   ├── draft-page-generator.md
  │   │   └── fix-grammar.md
  │   └── AGENTS.md
  ├── setup-agents.sh          ← Setup script
  └── your-content/
```

サブモジュールはを指します。
**https://git.corp.adobe.com/AdobeDocs/CursorAgents**

これにより、すべてのユーザーが同じ最新のエージェントを使用できるようになります。

## メンテナー向け

### 新しいリポジトリへの追加

1. サブモジュールを追加します。

   ```bash
   git submodule add https://git.corp.adobe.com/AdobeDocs/CursorAgents.git .cursor-agents
   ```

2. 設定ファイルをコピーします。
   - `setup-agents.sh`
   - `setup-agent.md` （サブモジュールではなくルートに配置）
   - `INSTALL.md`

3. コミット :

   ```bash
   git add .gitmodules .cursor-agents setup-agents.sh
   git commit -m "Add Cursor Agents submodule"
   ```

### 中央リポジトリの更新

エージェントに対する変更は、次の場所で行う必要があります。
**https://git.corp.adobe.com/AdobeDocs/CursorAgents**

すべてのリポジトリは、`git submodule update --remote` を介して更新を受け取ります。

---

**サポートが必要な場合** ドキュメントチームのリーダーに問い合わせるか、内部 Wiki を確認します。
