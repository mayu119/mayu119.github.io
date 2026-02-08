# PawCalm Website (app-ads.txt + Marketing URL)

このフォルダは、以下をまとめて公開するための静的サイトです。

- Marketing URL 用トップページ (`index.html`)
- Support URL (`support.html`)
- Privacy Policy URL (`privacy.html`)
- AdMob 用 `app-ads.txt`

## 1) 公開前に置換する項目

- `support.html` のメールアドレス（現在は `mayumayu110999@gmail.com`）

## 2) 重要: app-ads.txt の公開場所

`app-ads.txt` は**ドメイン直下**で公開する必要があります。

- 正しい例: `https://example-domain.com/app-ads.txt`
- 正しい例: `https://xxxxx.pages.dev/app-ads.txt`

## 3) ドメインを持っていない場合の推奨

Cloudflare Pages か Netlify を使うと、無料でサブドメイン配下のルートに公開できます。

### Cloudflare Pages の場合

1. GitHub にこのプロジェクトを push
2. Cloudflare Pages で新規プロジェクトを作成
3. Build settings:
   - Framework preset: `None`
   - Build command: 空欄
   - Output directory: `website`
4. デプロイ完了後、`https://<project>.pages.dev/app-ads.txt` にアクセスできることを確認

### Netlify の場合

1. GitHub 連携で新規サイトを作成
2. Publish directory を `website` に設定
3. デプロイ後、`https://<site>.netlify.app/app-ads.txt` を確認

## 4) App Store Connect に設定する値

- Marketing URL: `https://<your-domain>/`
- Support URL: `https://<your-domain>/support.html`
- Privacy Policy URL: `https://<your-domain>/privacy.html`

`<your-domain>` は Pages/Netlify の公開ドメイン（または独自ドメイン）に置換してください。

## 5) AdMob 側の確認

1. AdMob で app-ads.txt ステータスを確認
2. 反映まで通常 24 時間以上待つ

## 6) ローカル確認

```bash
cd website
python3 -m http.server 8080
```

ブラウザで以下にアクセス:

- `http://localhost:8080/`
- `http://localhost:8080/app-ads.txt`
