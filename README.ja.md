<div align="center">

<img src="voicebox-icon.png" width="128" height="128" alt="voiceBox" />

# voiceBox

**どんな声もクローン。どんな文章も読み上げ。すべてあなたの Mac で。**

ローカル音声クローン · 長文読み上げ · クラウド不要 · Apple Silicon ネイティブ

[English](README.md) · [中文](README.zh-Hans.md) · **日本語**

[![Download](https://img.shields.io/github/v/release/caspianchan31/voiceBox?style=for-the-badge&logo=apple&label=Download&color=2563eb)](https://github.com/caspianchan31/voiceBox/releases/latest)
[![Platform](https://img.shields.io/badge/macOS-15%2B-lightgrey?style=for-the-badge&logo=apple)](https://www.apple.com/macos/)
[![Chip](https://img.shields.io/badge/Apple%20Silicon-M1%20%7C%20M2%20%7C%20M3%20%7C%20M4-orange?style=for-the-badge)](https://en.wikipedia.org/wiki/Apple_silicon)

</div>

---

## TL;DR

> 5 秒の参考音声を用意するだけ。中国語・英語の音声をローカルでクローンし、どんな長さの原稿でも読み上げ可能 — 一バイトもクラウドに送らずに。

---

## ✨ できること

- 🎙 **音声クローン** — 5〜15 秒のサンプルから、自動文字起こし付きで音声を複製
- 📝 **長文読み上げ** — 自動分割とストリーミング再生で長い原稿にも対応
- 🎧 **エクスポート** — WAV / M4A / MP3 形式に ⌘S で書き出し
- 📚 **音声ライブラリ** — 作成した音声を起動をまたいで保存・管理
- 🕘 **生成履歴** — すべての読み上げ結果を保存、いつでも再生・再エクスポート
- 🛡 **完全ローカル** — オンデバイス処理、ネットワーク通信一切なし

---

## 📦 ダウンロード

**[⬇️ 最新バージョンをダウンロード](https://github.com/caspianchan31/voiceBox/releases/latest)**

過去バージョンは [Releases ページ](https://github.com/caspianchan31/voiceBox/releases) からどうぞ。

---

## 🚀 インストール

1. `voiceBox-X.Y.Z.dmg` をダウンロードしてダブルクリックでマウント
2. `voiceBox.app` を `Applications` フォルダにドラッグ
3. **初回起動時：** Applications 内の `voiceBox.app` を右クリック（または Control + クリック）→ **「開く」** を選択 → ダイアログで **「開く」** をクリック
4. 2 回目以降はダブルクリックで起動できます

> アプリは公証を受けていません（Apple の年間 $99 の費用を避けています）。右クリック → 開く の手順は一度だけ必要な macOS の仕様であり、voiceBox 自体の問題ではありません。
> 「破損しています」という警告が表示された場合は、ターミナルで次のコマンドを実行してください： `xattr -dr com.apple.quarantine /Applications/voiceBox.app`

---

## 🎬 使い方

```
   ┌──────────────┐      ┌──────────────┐      ┌──────────────┐
   │ Reference    │      │  Your        │      │  Cloned      │
   │  Audio (5s)  │  +   │   Script     │  →   │   Speech     │
   │  + ASR text  │      │  (any len)   │      │  WAV/M4A/MP3 │
   └──────────────┘      └──────────────┘      └──────────────┘
       (one click ✨)         (paste / drop)         (⌘S export)
```

**3 ステップ：**

1. **Studio** タブ → 音声チップをクリック → **「音声を追加」** → 参考音声をドロップ → ✨ をクリックして自動文字起こし → 保存
2. **Studio** メイン入力欄 → 原稿を貼り付け（または `.txt` をドロップ）→ 音声を選択
3. ⌘↩ で生成 · 試聴 · ⌘S でエクスポート

---

## 🧠 内部の仕組み

| 機能 | エンジン | 提供元 |
|---|---|---|
| 音声合成（TTS） | Qwen3 音声エンジン | Alibaba Qwen |
| 音声認識（ASR） | Qwen3 音声認識 | Alibaba Qwen |
| オンデバイス処理 | Apple Silicon（GPU / Neural Engine） | Apple |

初回起動時に音声モデル（合計約 4 GB）をダウンロードします — 安定した接続環境で行ってください。それ以降は完全オフラインで動作します。

---

## ❓ よくある質問

<details>
<summary><b>voiceBox はオープンソースですか？</b></summary>

バイナリリリースは個人利用に限り無償で提供しています。ソースコードは公開していません。voiceBox はオープンソースのモデルやフレームワーク（下記クレジット参照）の恩恵を受けています — オープンソースの巨人たちがいてこそ存在するアプリです。このリポジトリはあくまで配布チャンネルです。

</details>

<details>
<summary><b>音声やテキストはアップロードされますか？</b></summary>

されません。すべての音声処理は Mac の GPU / Neural Engine 上でローカルに実行され、完全オフラインです。唯一の通信は初回起動時の音声モデルのダウンロードのみ。それ以降はネット接続なしで使い続けられます。

</details>

<details>
<summary><b>対応言語は何ですか？</b></summary>

中国語（普通話）と英語が最も高品質です。Qwen3 音声エンジンはスペイン語、フランス語、ドイツ語、日本語、ポルトガル語、イタリア語など、公式対応 10 言語をサポートしています。

</details>

<details>
<summary><b>Mac App Store には対応しないのですか？</b></summary>

App Store のサンドボックス制限により、参考音声やエクスポートに必要なローカルファイルシステムへのアクセスができなくなります。直接配布の方が快適に使えるため、この形式を選んでいます。

</details>

<details>
<summary><b>商用利用はできますか？</b></summary>

アプリ自体は無料ですが、使用している Qwen3 モデルの商用ライセンスは各モデルのライセンス条項に従います。voiceBox は生成物の利用コンプライアンスについて責任を負いません。

</details>

---

## 📋 動作要件

- macOS 15 以降（Sequoia 以降）
- Apple Silicon（M1 / M2 / M3 / M4）
- 空きディスク容量 5 GB 以上（モデルデータ用）
- インターネット接続（初回モデルダウンロード時のみ）

---

## 🗺 今後の予定

- [ ] アプリ公証 + 自動アップデート（Sparkle）
- [ ] 複数音声での一括生成
- [ ] 字幕（SRT）の同期エクスポート
- [ ] カスタム間隔 / 強調マーカー
- [ ] iOS 版

---

## 🙏 謝辞

voiceBox wouldn't exist without these projects:

- [**MLX**](https://github.com/ml-explore/mlx) by Apple — the framework
- [**mlx-audio-swift**](https://github.com/Blaizzy/mlx-audio-swift) by Prince Canuma — the Swift TTS/STT layer
- [**mlx-audio**](https://github.com/Blaizzy/mlx-audio) by Prince Canuma — the Python research playground
- [**Qwen**](https://github.com/QwenLM) by Alibaba — TTS & ASR models
- [**Hugging Face**](https://huggingface.co/) — model distribution

---

## 📮 フィードバック

バグ報告・機能要望は [Issue](https://github.com/caspianchan31/voiceBox/issues) からどうぞ。

---

<div align="center">

Made with ☕ on Apple Silicon.

</div>
