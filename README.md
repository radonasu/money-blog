# おかねの教科書 — money-blog

お金の知識をわかりやすく解説するJekyllブログサイト。GitHub Pagesで自動デプロイ。

## セットアップ手順（社長のアクション: 3コマンドのみ）

```bash
# 1. このフォルダに移動
cd "C:\Users\ccffd_000\Desktop\Claude生成\money-blog"

# 2. Gitリポジトリを初期化してコミット
git init
git add .
git commit -m "Initial commit: おかねの教科書 Jekyll site"

# 3. GitHubに新規リポジトリ作成後、pushする
git remote add origin https://github.com/radonasu/money-blog.git
git branch -M main
git push -u origin main
```

## GitHub Pages有効化

GitHubリポジトリの Settings → Pages → Source を **"GitHub Actions"** に設定するだけで自動デプロイ開始。

## 記事の追加方法

`_posts/` フォルダに `YYYY-MM-DD-title.md` 形式でMarkdownファイルを追加してpushするだけ。

## サイト構成

```
money-blog/
├── _config.yml          # サイト設定
├── _posts/              # 記事（Markdown）
│   ├── 2026-03-10-salaryman-setsuzei-8sen.md
│   ├── 2026-03-12-furusato-nozei-yarikata-2026.md
│   ├── 2026-03-14-ideco-setsuzei-simulation.md
│   └── 2026-03-18-nisa-kanzen-guide-2026.md
├── .github/workflows/   # GitHub Actions自動デプロイ
├── index.md             # トップページ
├── about.md             # サイト概要
├── privacy-policy.md    # プライバシーポリシー（AdSense申請必須）
├── contact.md           # お問い合わせ（AdSense申請必須）
└── Gemfile              # Ruby依存関係
```
