---
source-git-commit: d7bb3424bc6dfb837b47d15c448a2d46bf4b6c3c
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 4%

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

3. プロンプトに従います
4. 完了！✨

### オプション 2：端子を使用する

1. リポジトリルートのターミナルを開きます。
2. 実行：

   ```bash
   ./setup-agents.sh
   ```

   または手動で：

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

使用可能なエージェントの完全なリストについては、`.cursor-agents/AGENTS.md` を参照してください。

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
journey-optimizer.en/
  ├── .cursor-agents/          ← Git submodule
  │   ├── agents/
  │   │   ├── draft-page-generator.md
  │   │   └── fix-grammar.md
  │   └── AGENTS.md
  ├── setup-agents.sh          ← Setup script
  ├── setup-agent.md           ← Bootstrap agent
  └── help/                    ← Your documentation
```

サブモジュールはを指します。
**https://git.corp.adobe.com/AdobeDocs/CursorAgents**

これにより、すべてのユーザーが同じ最新のエージェントを使用できるようになります。

&#x200B;---

**サポートが必要な場合** ドキュメントチームのリーダーに問い合わせるか、内部 Wiki を確認します。

