# AdSense申請チェックリスト（money-blog用）

## 申請前チェック（約1時間で完了）

### ✅ サイト基本要件
- [ ] サイトが公開されている（GitHub Pages URL: `https://radonasu.github.io/money-blog/`）
- [ ] 公開から2〜4週間以上経過している
- [ ] 独自ドメイン（推奨）または無料ドメインでアクセス可能

### ✅ コンテンツ要件
- [ ] 記事10本以上（**現在11本達成済み** ✅）
- [ ] 各記事が1,500字以上のオリジナルコンテンツ（**全記事2,500〜4,500字** ✅）
- [ ] 記事に広告・アフィリエイトリンクが多すぎない（申請時は少なめに）
- [ ] 著作権を侵害するコンテンツがない

### ✅ 必須ページ（全て作成済み ✅）
- [ ] `/about` — サイト紹介ページ
- [ ] `/privacy-policy` — プライバシーポリシー
- [ ] `/contact` — お問い合わせページ

### ✅ Jekyll設定確認
- [ ] `_config.yml` に `title`, `description`, `url` が設定されている
- [ ] `jekyll-sitemap` プラグインが有効（`sitemap.xml` が自動生成される）
- [ ] `jekyll-seo-tag` プラグインが有効（meta descriptionが自動生成される）

---

## 申請手順（当日・約30分）

### STEP 1: Google AdSenseにアクセス（5分）
1. https://www.google.com/adsense/ を開く
2. Googleアカウントでログイン
3. 「今すぐ開始」をクリック

### STEP 2: サイト情報入力（5分）
1. サイトURL: `https://radonasu.github.io/money-blog/`（または独自ドメイン）
2. 支払い先住所・氏名を入力
3. 電話番号認証（SMS）

### STEP 3: AdSenseコード設置（15分）
1. AdSenseから「ads.txt」スニペットとJavaScriptコードが発行される
2. `ads.txt` をリポジトリのルートに配置:
   ```
   google.com, pub-XXXXXXXXXX, DIRECT, f08c47fec0942fa0
   ```
3. `_includes/head.html` または `_layouts/default.html` の `<head>` 内にAdSenseコードを追加:
   ```html
   <script async src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js?client=ca-pub-XXXXXXXXXX"
        crossorigin="anonymous"></script>
   ```
4. git add → git commit → git push

### STEP 4: 審査完了待ち（2〜4週間）
- 審査状況はAdSenseダッシュボードで確認
- メールで合否通知が届く
- 合格後、広告ユニットを作成して記事に配置

---

## 審査通過率を上げる3つのコツ

1. **申請前にアフィリエイトリンクを一時非表示にする**
   - AdSenseと他社広告の共存は審査通過後でOK
   - 申請中は記事末尾のアフィリエイトCTAを一時コメントアウト

2. **Google Search Consoleで事前登録しておく**
   - サイトマップ (`/sitemap.xml`) を送信
   - クロール状況を確認してからAdSense申請

3. **プライバシーポリシーに「Cookieの使用」を明記する**
   - money-blogのprivacy-policy.mdには既に記載済み ✅

---

## A8.net アフィリエイト申請手順（申請優先リスト）

### アカウント作成（未登録の場合・10分）
1. https://www.a8.net/ にアクセス
2. 「無料メンバー登録」
3. サイトURL: `https://radonasu.github.io/money-blog/`
4. サイトのジャンル: 「生活・暮らし」「マネー・投資」を選択
5. メール認証で完了

### 優先申請リスト（申請順）

#### 🥇 最優先①: 楽天証券（NISA・iDeCo口座開設）
- 報酬: 口座開設1件 **¥8,000〜10,000**
- 申請: A8.net → 検索「楽天証券」→ 提携申請
- 対応記事: 第3記事（iDeCo）、第4記事（新NISA）、第10記事

#### 🥇 最優先②: 保険の窓口（保険比較・無料相談）
- 報酬: 来店予約1件 **¥3,000〜8,000**
- 申請: A8.net → 検索「保険の窓口」→ 提携申請
- 対応記事: 第1記事（節税）、第6記事（生命保険）

#### 🥈 優先③: freee（会計ソフト）
- 報酬: 有料プラン登録1件 **¥1,500〜3,000**
- 申請: A8.net → 検索「freee」→ 提携申請
- 対応記事: 第8記事（確定申告）

#### 🥈 優先④: エネチェンジ（電力会社比較）
- 報酬: 切り替え1件 **¥3,000〜5,000**
- 申請: A8.net → 検索「エネチェンジ」→ 提携申請
- 対応記事: 第7記事（電気代節約）

#### 🥈 優先⑤: マネーフォワード ME
- 報酬: プレミアム登録1件 **¥1,000〜2,000**
- 申請: A8.net → 検索「マネーフォワード」→ 提携申請
- 対応記事: 第8記事（確定申告）、第10記事（貯金習慣）

---

## 収益試算（AdSense + アフィリ合算）

| 時期 | 月間PV | AdSense | アフィリ | 合計 |
|------|--------|---------|---------|------|
| git push翌月 | 100〜500 | ¥100〜500 | ¥0〜3,000 | ¥100〜3,500 |
| 3ヶ月後 | 1,000〜3,000 | ¥1,000〜3,000 | ¥3,000〜20,000 | ¥4,000〜23,000 |
| 6ヶ月後 | 5,000〜15,000 | ¥5,000〜15,000 | ¥15,000〜80,000 | ¥20,000〜95,000 |
| 12ヶ月後 | 20,000〜50,000 | ¥20,000〜50,000 | ¥50,000〜200,000 | ¥70,000〜250,000 |

> 💡 **アフィリエイト1件成約（¥5,000）だけで、AdSenseの5,000PV分に相当する。**

---

## Google Search Console 登録手順（git push当日に実施）

1. https://search.google.com/search-console/ にアクセス
2. プロパティ追加 → URL プレフィックス
3. URL: `https://radonasu.github.io/money-blog/`
4. 所有権確認: HTMLタグ（`<meta name="google-site-verification" content="..." />`）
   - Jekyll `_config.yml` に `google_site_verification: "XXXX"` を追加
5. サイトマップ送信: `https://radonasu.github.io/money-blog/sitemap.xml`

---

**結論: git push一回で、このチェックリストが全て動き始める。**
