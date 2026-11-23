# web-site

World会 の公式 Web サイトのソースコードです。

## デプロイ先

**本番 URL:** https://world-kai.com

ドメインは Squarespace で管理しています。
- Squarespace ドメイン管理画面: https://account.squarespace.com/domains/managed/world-kai.com
- 開けない場合は権限のある人から招待を受ける必要があります。

## ファイル構成

```
web-site/
├── index.html              # メインページ
├── CNAME                   # カスタムドメイン設定
├── assets/
│   ├── css/
│   │   ├── reset.css       # CSS リセット
│   │   └── style.css       # サイト全体のスタイル
│   ├── js/
│   │   └── script.js       # JavaScript
│   ├── img/                # 画像ファイル
│   │   ├── about/
│   │   ├── about-contents/
│   │   ├── background/
│   │   ├── counseling/
│   │   ├── data/
│   │   ├── favicon/
│   │   ├── footer/
│   │   ├── gallery/
│   │   ├── header/
│   │   ├── message-movie/
│   │   ├── news/
│   │   └── top/
│   └── textdata/
│       └── text_data.ai    # テキストデータ（Illustratorファイル）
```

## セットアップ（ローカルで確認する方法）

### 1. リポジトリをクローン

```bash
git clone https://github.com/yukorin1107/web-site.git
cd web-site
```

### 2. ローカルサーバーを起動

このプロジェクトはビルド不要の静的サイトです。以下のいずれかの方法でローカル確認できます。

**VS Code の場合（推奨）:**
- [Live Server 拡張機能](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) をインストール
- `index.html` を右クリック → "Open with Live Server"
- ブラウザで `http://127.0.0.1:5500` が開きます

**Python の場合:**
```bash
# Python 3
python3 -m http.server 8080
```
ブラウザで `http://localhost:8080` を開く

**Node.js の場合:**
```bash
npx serve .
```

## デプロイの仕組み

GitHub にプッシュすると、**GitHub Pages** 経由で自動デプロイされます。

```
git push origin main
```
※ プッシュできない場合は権限がない可能性があります。Githubオーナーから権限をもらう必要があります。

カスタムドメイン `world-kai.com` は Squarespace の DNS 設定で GitHub Pages に向いており、`CNAME` ファイルによってドメインの紐づけが行われています。

### デプロイの流れ

```
コード変更
  ↓
git push origin main
  ↓
GitHub Pages が自動でサイトを公開
  ↓
https://world-kai.com で反映
```

> **注意:** push 後、反映まで数分かかる場合があります。
