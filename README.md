<div align="center">

<img src="voicebox-icon.png" width="128" height="128" alt="voiceBox" />

# voiceBox

**Clone any voice. Read anything. All on your Mac.**

本地声音克隆 · 长文朗读 · 零云端 · Apple Silicon 原生

[![Download](https://img.shields.io/github/v/release/caspianchan31/voiceBox?style=for-the-badge&logo=apple&label=Download&color=2563eb)](https://github.com/caspianchan31/voiceBox/releases/latest)
[![Platform](https://img.shields.io/badge/macOS-15%2B-lightgrey?style=for-the-badge&logo=apple)](https://www.apple.com/macos/)
[![Chip](https://img.shields.io/badge/Apple%20Silicon-M1%20%7C%20M2%20%7C%20M3%20%7C%20M4-orange?style=for-the-badge)](https://en.wikipedia.org/wiki/Apple_silicon)

</div>

---

## 一句话 · TL;DR

> 用 5 秒参考音,本地克隆任意中英声音,把整篇长稿合成成自然的语音 —— 全程不上传一个字节。
>
> Drop in 5 seconds of reference audio, clone any Mandarin or English voice locally, and read your entire script aloud — without sending a single byte to the cloud.

---

## ✨ 它能做什么 · What it does

| 中文 | English |
|---|---|
| 🎙 **声音克隆** · 拖一段 5-15 秒人声,自动转录,生成新的克隆音色 | **Voice clone** from a 5-15 sec sample, auto-transcribed |
| 📝 **长文朗读** · 上千字脚本自动分段,流式播放,12 分钟音频约 12 分钟出 | **Long-form synthesis** with auto-chunking and streaming playback |
| 🎧 **多格式导出** · WAV / M4A / MP3,一键 ⌘S | **Export** to WAV / M4A / MP3 with ⌘S |
| 📚 **声音库** · 多音色保存,跨次启动持续 | **Persistent voice library** across launches |
| 🕘 **生成历史** · 自动归档每次合成,随时回听 / 重导出 | **Generation history** — every synthesis saved, replay & re-export |
| 🛡 **完全本地** · 推理跑在 Metal/MLX 上,无网络请求 | **100% local** inference via Apple's MLX framework |

---

## 📦 下载 · Download

**[⬇️ 下载最新版 / Download Latest Release](https://github.com/caspianchan31/voiceBox/releases/latest)**

或者直接打开 [Releases 页面](https://github.com/caspianchan31/voiceBox/releases) 选择历史版本。

---

## 🚀 安装 · Install

<details>
<summary><b>中文步骤</b></summary>

1. 下载 `voiceBox-X.Y.Z.dmg` 并双击挂载
2. 把 `voiceBox.app` 拖入左侧的 `Applications` 文件夹
3. **首次打开** · 在 `应用程序` 里**右键**(或 Control 点击)`voiceBox.app` → 选**打开** → 弹窗里再点**打开**
4. 之后双击即可启动

> 因为应用未付费购买 Apple 公证,首次需要绕过 Gatekeeper。这是 macOS 对非公证软件的统一处理,不是 voiceBox 的问题。
> 如果出现"已损坏"提示,终端执行 `xattr -dr com.apple.quarantine /Applications/voiceBox.app`。

</details>

<details>
<summary><b>English</b></summary>

1. Download `voiceBox-X.Y.Z.dmg` and double-click to mount
2. Drag `voiceBox.app` to your `Applications` folder
3. **First launch:** right-click (or Control-click) `voiceBox.app` in Applications → choose **Open** → click **Open** again in the dialog
4. Subsequent launches: just double-click

> The app isn't notarized (we'd rather not pay Apple's $99/yr). The right-click → Open dance is a one-time macOS quirk.
> If you see "damaged" warning: `xattr -dr com.apple.quarantine /Applications/voiceBox.app`

</details>

---

## 🎬 工作流 · Workflow

```
   ┌──────────────┐      ┌──────────────┐      ┌──────────────┐
   │ Reference    │      │  Your        │      │  Cloned      │
   │  Audio (5s)  │  +   │   Script     │  →   │   Speech     │
   │  + ASR text  │      │  (any len)   │      │  WAV/M4A/MP3 │
   └──────────────┘      └──────────────┘      └──────────────┘
       (one click ✨)         (paste / drop)         (⌘S export)
```

**3 步上手 · 3 steps:**

1. **Studio** Tab → 点声音胶囊 → **添加声音** → 拖入参考音频 → 点 ✨ 自动转录 → 保存
2. **Studio** 主输入框 → 粘贴脚本 (或拖 .txt) → 选音色
3. ⌘↩ 生成 · 听完 · ⌘S 导出

---

## 🧠 模型 · Under the Hood

| 用途 | 模型 | 来源 |
|---|---|---|
| TTS | `Qwen3-TTS-12Hz-1.7B-Base-bf16` | Alibaba Qwen |
| ASR | `Qwen3-ASR-0.6B-4bit` | Alibaba Qwen |
| 推理框架 | [MLX](https://github.com/ml-explore/mlx) | Apple |
| Swift 封装 | [mlx-audio-swift](https://github.com/Blaizzy/mlx-audio-swift) | Blaizzy |

首次启动会从 Hugging Face 拉模型(共 ~4 GB),建议接稳定网络;之后全部离线运行。

---

## ❓ FAQ

<details>
<summary><b>Is voiceBox open source?</b></summary>

The binary releases are free for personal use. The source code is **not** publicly available. voiceBox stands on the shoulders of open-source models and the [mlx-audio-swift](https://github.com/Blaizzy/mlx-audio-swift) library — those are the open-source giants. This repo is the distribution channel.

</details>

<details>
<summary><b>会不会上传我的声音或文本?</b></summary>

不会。所有 TTS/ASR 计算都在你 Mac 上的 GPU/ANE 跑,完全离线。唯一的网络请求只在首次启动:从 Hugging Face 下载模型权重。下载完成后可以断网使用。

</details>

<details>
<summary><b>支持哪些语言?</b></summary>

中文(普通话)和英文表现最好。Qwen3-TTS 官方还支持西语、法语、德语、日语、葡萄牙语、意大利语等十种语言。

</details>

<details>
<summary><b>Why isn't it on the Mac App Store?</b></summary>

App Store sandboxing breaks the local file system access we need for ref audio and exports. Direct distribution gives a cleaner experience.

</details>

<details>
<summary><b>我可以商用吗?</b></summary>

应用本身免费,但底层模型(Qwen3-TTS / Qwen3-ASR)的商用授权请遵循各自模型 license。voiceBox 不为模型输出承担合规责任。

</details>

---

## 📋 系统要求 · Requirements

- macOS 15+ (Sequoia 或更新)
- Apple Silicon (M1 / M2 / M3 / M4)
- 至少 5 GB 可用磁盘空间(模型权重)
- 网络(仅首次下载模型)

---

## 🗺 Roadmap

- [ ] 应用公证 + 自动更新 (Sparkle)
- [ ] 多音色 batch generation
- [ ] 字幕(SRT)同步导出
- [ ] 自定义停顿 / 强调标记
- [ ] iOS 版本

---

## 🙏 致谢 · Acknowledgements

voiceBox 不存在,如果没有这些项目:

- [**MLX**](https://github.com/ml-explore/mlx) by Apple — the framework
- [**mlx-audio-swift**](https://github.com/Blaizzy/mlx-audio-swift) by Prince Canuma — the Swift TTS/STT layer
- [**mlx-audio**](https://github.com/Blaizzy/mlx-audio) by Prince Canuma — the Python research playground
- [**Qwen**](https://github.com/QwenLM) by Alibaba — TTS & ASR models
- [**Hugging Face**](https://huggingface.co/) — model distribution

---

## 📮 反馈 · Feedback

发现 bug / 想加功能? 开个 [Issue](https://github.com/caspianchan31/voiceBox/issues)。

---

<div align="center">

Made with ☕ + MLX on Apple Silicon.

</div>
