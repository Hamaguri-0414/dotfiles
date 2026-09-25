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

ghostty/                 # Ghostty（ターミナル）の設定
└── config               # フォント・背景透過・画面分割キーバインドなど

zsh/                     # zsh の設定
└── prompt.zsh           # プロンプトの見た目（カレントフォルダ・Gitブランチ・時刻表示など）
```

## 使い方

### Claude Code

`claude/` 以下のファイルを `~/.claude/` に配置してください。

```powershell
Copy-Item -Recurse claude\* ~\.claude\
```

### Ghostty（macOS）

`ghostty/config` を Ghostty の設定パスに配置してください。

```sh
cp ghostty/config ~/Library/Application\ Support/com.mitchellh.ghostty/config
```

配置後は Ghostty 上で Cmd + Shift + , を押すと設定をリロードできます。

### zsh プロンプト

`zsh/prompt.zsh` を `~/.zsh/` に配置し、`~/.zshrc` から読み込んでください。

```sh
mkdir -p ~/.zsh
cp zsh/prompt.zsh ~/.zsh/prompt.zsh
```

`~/.zshrc` に以下の1行を追加します。

```zsh
source "$HOME/.zsh/prompt.zsh"
```

`.zshrc` 本体はマシン固有の設定や機密情報を含むため、このリポジトリでは管理しません。

## 注意

`~/.claude/` 配下には認証情報（`.credentials.json`）や会話履歴などの
機密ファイルが自動生成されます。このリポジトリに含めないでください。
