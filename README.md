# dotfiles

個人環境の設定ファイル集です。

## 構成

```
claude/                  # Claude Code の設定
├── CLAUDE.md            # グローバル指示（全プロジェクト共通）
├── settings.json        # Claude Code 本体の設定
├── commands/            # カスタムスラッシュコマンド
│   └── save-log.md      # 会話ログを日記として Obsidian に保存
└── roles/               # ロールプレイ用キャラクター設定
    ├── takanashi_yui.md # 後輩エンジニア「小鳥遊ゆい」
    └── ryland_grace.md  # プロジェクト・ヘイル・メアリーのグレース博士
```

## 使い方

`claude/` 以下のファイルを `~/.claude/` に配置してください。

```powershell
Copy-Item -Recurse claude\* ~\.claude\
```

## 注意

`~/.claude/` 配下には認証情報（`.credentials.json`）や会話履歴などの
機密ファイルが自動生成されます。このリポジトリに含めないでください。
