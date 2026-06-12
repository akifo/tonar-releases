# Tonariyuki（となりゆき）

## Tonariyuki とは

オンライン雑談中に「会話の横にそっといる」Mac 用の会話サポートアプリです。
会議録アプリではなく、まだよく知らない相手との 1on1 をちょっとだけ楽にするためのツールです。
文字起こしは完全オンデバイスで処理され、音声データが外部に送信されることはありません。
AI による会話サポートはオプトイン制で、有効化した場合でもテキストのみを送信します（音声は送信しません）。

ソースコードは現在非公開です。

---

## 動作要件

| 項目 | 要件 |
|---|---|
| macOS | **macOS 26 (Tahoe) 以降** |
| チップ | **Apple Silicon**（aarch64 ビルドのみ提供） |
| 音声デバイス | **イヤホン / ヘッドホン推奨** |
| 会話の言語 | **日本語のみ**（文字起こしは ja-JP 専用。英語等の音声は文字起こしできません） |

> **イヤホンについて**: v0.1 はイヤホン前提です。スピーカーを使うと相手の声がマイクに回り込み、「自分」レーンに混入することがあります。

---

## インストール

1. [Releases](https://github.com/akifo/tonariyuki-releases/releases) から最新バージョンの `.dmg` ファイルをダウンロードします
2. ダウンロードした `.dmg` を開き、**Tonariyuki.app** を **Applications** フォルダへドラッグします
3. `.dmg` はアンマウントして削除して構いません

---

## 初回起動（重要）

Tonariyuki は Apple Developer Program 未加入のため、Gatekeeper による警告が表示されます。
以下の手順で一度だけ許可してください。次回からは通常どおり起動できます。

1. Applications フォルダの **Tonariyuki.app** をダブルクリックする
2. 「"Tonariyuki" は開発元を確認できないため開けません。」というダイアログが表示される → **「OK」で閉じる**
3. **システム設定** → **プライバシーとセキュリティ** を開く
4. 画面を下にスクロールすると「"Tonariyuki" は開発元を確認できないため、使用がブロックされました。」という表示が出る
5. その隣の **「このまま開く」** ボタンをクリックする
6. Mac のパスワード（または Touch ID）で認証する
7. 確認ダイアログで **「開く」** をクリックする

> macOS 15 以降では「右クリック → 開く」だけでは突破できないケースがあるため、上記の設定経由の手順を正式手順としています。

---

## 権限の許可

初回セッション開始時に、以下の権限を求めるダイアログが表示されます。

| 権限 | 用途 |
|---|---|
| マイク | 自分の声の文字起こし |
| 画面収録とシステムオーディオ録音 | 相手の声（システム音声）の文字起こし |

**どちらも許可しないと相手の音声が文字起こしされません**（アプリ内のバナーでも案内されます）。

後から許可する場合: **システム設定** → **プライバシーとセキュリティ** → **画面収録とシステムオーディオ録音**

---

## 初回の文字起こしモデル

初回セッション開始時に、日本語音声認識モデルのダウンロードが自動的に走ります。
ダウンロードの進捗はレーンの状態表示に出ます。完了するまで文字起こしは始まりません。
ネットワーク環境により数分かかる場合があります。

---

## プライバシー

- **音声・文字起こしは Mac の外に出ません**: 文字起こしはオンデバイス（macOS 26 の SpeechAnalyzer）で行い、音声データは保存・送信しません。文字起こしテキストはローカルの SQLite データベースにのみ保存されます
- **AI 機能はオプトイン**: 会話サポート・ブリーフィングなどの AI 機能は設定で有効化した場合のみ動作します。その場合でも、送信されるのはテキストのみです（音声は送信しません）。送信先は設定で選択した AI プロバイダです
- **録音中は macOS 標準の録音インジケータが表示されます**（迂回しません）

---

## アップデート

アップデートが配信されると、アプリ内に通知バナーが表示されます。
**「更新して再起動」** を押すだけで自動的に最新バージョンになります。

---

## フィードバック

不具合・要望は [Issues](https://github.com/akifo/tonariyuki-releases/issues) へお寄せください。

---

## English Summary

**Tonariyuki** ("sitting quietly beside you") is a Mac app that offers gentle, real-time conversation support during online chats — not a meeting recorder, but a tool to help you connect with people you don't know well yet.

- **Fully on-device transcription**: your voice (mic) and the other person's voice (system audio) are transcribed locally using macOS 26's SpeechAnalyzer. No audio ever leaves your Mac.
- **AI support is opt-in**: when enabled, only text is sent to the AI provider of your choice — never audio.
- **Requirements**: macOS 26 (Tahoe) or later, Apple Silicon. Earphones/headphones strongly recommended.
- **Note**: transcription currently supports **Japanese (ja-JP) only** — English or other languages cannot be transcribed.

### First Launch (Gatekeeper)

Because Tonariyuki is not notarized, you need to allow it once via System Settings:

1. Double-click Tonariyuki.app → dismiss the "can't be opened" dialog
2. Open **System Settings → Privacy & Security**
3. Scroll down to find the Tonariyuki blocked message → click **"Open Anyway"**
4. Authenticate with your Mac password or Touch ID
5. Click **"Open"** in the confirmation dialog

After this one-time step, the app opens normally.
