# 子の連れ去り国賠訴訟 — 公式サイト

子の連れ去り・面会交流妨害・交互監護拒否に関する国会の立法不作為を問う、30名の原告による国家賠償請求訴訟（東京地方裁判所・令和8年3月23日提訴）の情報発信サイトです。

[English summary below ↓](#english)

---

## 構成

| ファイル / フォルダ | 役割 |
| --- | --- |
| `index.html` | 公開サイト本体（1ファイル完結・日英バイリンガル） |
| `pdfs/` | 訴状PDF等を置くディレクトリ。中身は `.gitignore` で公開リポジトリには含めない |
| `admin.html` | **ローカル専用**の管理ツール。`.gitignore` で除外。配布・公開しない |
| `.gitignore` | 公開してはいけないファイルの除外設定 |
| `LICENSE` | MITライセンス（コード部分） |

> **注：** サイトの法律的な内容（訴状・記事・原告団の声明等）は MIT ライセンスの対象外です。引用・再利用される場合は事前に原告団・代理人弁護士までお問い合わせください。

---

## 公開（GitHub Pages）

このリポジトリは GitHub Pages にそのまま置けます。

1. リポジトリの **Settings → Pages** を開く
2. **Source** を `Deploy from a branch` にし、Branch を `main` / `(root)` に設定
3. 数分待つと `https://<owner>.github.io/<repo>/` で公開される

カスタムドメインを使う場合は、リポジトリのルートに `CNAME` ファイル（中身はドメイン1行）を追加してください。

---

## 公開サイトの編集方法（`index.html`）

`index.html` の冒頭にある **Configuration** ブロックで主要な値を変更できます：

```js
// 訴状PDFのパス（pdfs/ ディレクトリに配置）
var COMPLAINT_PDF_PATH = ''; // 例: 'pdfs/sojo.pdf'

// Googleフォーム URL
var SIGN_FORM_URL    = 'https://forms.gle/PLACEHOLDER_SIGN_FORM';
var CONTACT_FORM_URL = 'https://forms.gle/PLACEHOLDER_CONTACT_FORM';
```

### 訴状PDFを公開する場合

1. PDFを `pdfs/sojo.pdf`（または任意の名前）として配置
2. `.gitignore` の `pdfs/*.pdf` をコメントアウトするか、対象ファイルだけ `!pdfs/sojo.pdf` で例外指定
3. `COMPLAINT_PDF_PATH = 'pdfs/sojo.pdf'` に書き換え
4. `git add` → `git commit` → `git push`

### Google フォームを設定する場合

1. Google フォームで「賛同署名」「お問い合わせ」フォームを作成
2. 公開URL（`https://forms.gle/...`）をコピー
3. `index.html` の `SIGN_FORM_URL` / `CONTACT_FORM_URL` に貼り付け

### テキスト・i18n

すべての日本語・英語テキストは `index.html` 内の `var I18N = { ja: {...}, en: {...} }` に集約されています。同じキーが両言語にあるので、両方を更新してください。

---

## 訴訟経緯・関連記事の追加

`index.html` 内の以下の配列を直接編集します：

```js
var entries  = [ /* 訴訟経緯の書面・期日 */ ];
var articles = [ /* 関連記事・判例 */ ];
```

### `admin.html` を使った編集（推奨）

ローカル PC で `admin.html` をブラウザで開くと、フォームから書面・記事を追加・編集できます。

1. `admin.html` を直接ブラウザで開く（`file://` でOK）
2. 書面・記事を追加・編集（自動的に `localStorage` に保存）
3. 「📦 Export / Import」タブで **Export JSON** ボタンを押す
4. 出力された `var entries = [...]; var articles = [...];` を `index.html` の対応箇所に貼り付け
5. `git commit && git push`

`admin.html` は `.gitignore` で除外されているため、公開リポジトリには絶対に含まれません。

---

## セキュリティ上の注意

このサイトは **静的サイト** として設計されており、バックエンドを持ちません：

- **管理者パスワードや API キーをコード内に書かない**こと（GitHubの自動スキャナが検出します）
- **個人情報を収集する署名フォーム等は Google Forms 等の外部サービス**に委ねる
- **訴状PDF等の機密情報を含む可能性があるファイル**は、公開してよいか確認してから配置する

---

## ライセンス

コード部分は [MIT License](./LICENSE) です。法律文書・声明・記事等のコンテンツは別途、原告団・代理人弁護士までお問い合わせください。

---

## 連絡先

- **代理人弁護士：** 作花知志（作花法律事務所・岡山市北区本町3番13号）
- **TEL：** 086-206-2331 ／ **FAX：** 086-206-2332

---

<a id="english"></a>

## English

Official information site for the **State Compensation Lawsuit on Child Abduction**, filed at the Tokyo District Court on March 23, 2026, by 30 plaintiffs challenging the Japanese Diet's prolonged legislative inaction on child abduction, obstruction of visitation, and refusal of shared custody.

### Structure

- `index.html` — public bilingual (JA/EN) site, single-file
- `admin.html` — local-only editor, excluded from the public repo via `.gitignore`
- `pdfs/` — directory for the complaint PDF and other documents (binary contents excluded by default)

### Deployment

The repository is ready for **GitHub Pages**: enable Pages in repo Settings → Pages → Source = `main / (root)`.

### License

Code under [MIT License](./LICENSE). Site content (legal documents, statements, articles) requires separate permission — please contact the plaintiff group or their counsel.
