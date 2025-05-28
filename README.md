# WOFF Delivery QR App Demo

LINE WORKS の WOFF SDK と QRCode.js を使った「納品書作成→QR生成→QR読み取り→納品明細表示」デモアプリです。  
GitHub Pages でホストし、複数のスマホで連携動作を確認できます。

---

## 🔖 特徴

- **納品書作成**（`delivery-form.html`）  
  - WOFF SDK (`woff.init`／`woff.getProfile`) で作成者情報を取得・表示  
  - 納品ID・納品先・納品日の入力（フォーム＋自動生成）  
  - 品目・数量をプルダウンで複数行入力  
  - 入力データを Base64 化し、QR と詳細ページリンクを生成  

- **QR 読取**（`qr-reader.html`）  
  - WOFF SDK の `woff.scanQR()` で QR スキャン  
  - Base64 → JSON → 画面表示  
  - 「納品明細ページ」へのリンクを生成  
  - 「受領」ボタンでバックエンドに POST（コールバック URL は要設定）  

- **納品明細表示**（`delivery-details.html`）  
  - `?data=` パラメータから Base64 データを受け取りデコード  
  - WOFF SDK (`woff.init`／`woff.getProfile`) で閲覧者情報を取得・表示  
  - 品目内容をテーブル出力  
  - 「閉じる」は `woff.closeWindow()` で WOFF ブラウザを終了  

---

## 🚀 動かし方

1. **クローン**  
   ```bash
   git clone https://github.com/<あなたのユーザー名>/woff-delivery-qr-app.git
   cd woff-delivery-qr-app
