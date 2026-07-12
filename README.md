# 🚀 Zive Browser

HTML/CSS/TypeScriptとElectron（Node.js）の[Wexond](https://github.com/wexond/browser-base)で構築された、Chromiumベースの自分専用カスタムWebブラウザです。
ミニマルで高速なタブ機能を備え、不要な機能を極限まで排除して軽量化しています。

## ✨ 特徴

- 🛡️ **広告ブロックなし**: 通信フィルターを排除し、コンテンツをそのまま、ありのまま高速表示
- 🎨 **自作ホームページ**: 起動時や新規タブを開いた際、内蔵された独自のオリジナルHTML（ライト/ダークモード対応）を表示
- 🔒 **最新のChromiumベース**: Electronのアップデートにより、最新のWebセキュリティと規格に対応
- 📂 **独自ブランド化**: コード内のすべての表記を刷新した完全スタンドアロンなブラウザ

## 🛠️ 開発環境のセットアップ

プロジェクトをローカル環境で動かすための手順です。

### 1. 依存関係のインストール
Node.js環境（npm）が必要です。古いプラグインの競合を回避するため、以下のオプションを付けてインストールを完了させています。

```bash
npm install --legacy-peer-deps
```

### 2. 開発モードでの起動
コードの変更をリアルタイムで反映しながら、ブラウザをテスト起動します。

```bash
npm run start
```

## 📦 アプリケーションのビルドとデプロイ

各OS向けにインストーラーや実行ファイルを書き出す方法です。

### Windows向けビルド（.exe）
Windows環境のターミナルで実行します。

```bash
npm run build
npx electron-builder --windows
```
生成されたファイルは `dist/` フォルダに出力されます。

### Mac / Linux向け自動ビルド（GitHub Actions）
Windows環境からMac用（.dmg）やLinux用（.deb）を生成するため、CI/CD環境が構築されています。
バージョンタグを付けてGitHubにプッシュするだけで、クラウド上のMac環境が自動的にビルドを行い、GitHubの「Releases」に成果物を公開します。

```bash
git tag v1.0.0
git push origin v1.0.0
```

## 📂 フォルダ構成（主要な変更箇所）

- `src/main/services/adblock.ts` - 広告ブロックを完全に無効化（コメントアウト済）
- `src/main/view.ts` - 起動時の初期ページ（ホームページ）をローカルHTMLに指定
- `src/extra/index.html` - 自作のホームページファイル
- `icon/logo/` - ライト/ダークモード別のブラウザロゴ画像配置場所
- `package.json` - アプリ名、バージョン、ビルド設定の管理

## 📝 ライセンス

This project is opened under the [MIT License](LICENSE).
