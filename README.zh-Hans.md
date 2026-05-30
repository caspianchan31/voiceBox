<div align="center">

<img src="voicebox-icon.png" width="128" height="128" alt="voiceBox" />

# voiceBox

**克隆任意声音 · 朗读任何文字 · 全程在你的 Mac 上**

本地声音克隆 · 长文朗读 · 零云端 · Apple Silicon 原生

[English](README.md) · **中文** · [日本語](README.ja.md)

[![Download](https://img.shields.io/github/v/release/caspianchan31/voiceBox?style=for-the-badge&logo=apple&label=Download&color=2563eb)](https://github.com/caspianchan31/voiceBox/releases/latest)
[![Platform](https://img.shields.io/badge/macOS-15%2B-lightgrey?style=for-the-badge&logo=apple)](https://www.apple.com/macos/)
[![Chip](https://img.shields.io/badge/Apple%20Silicon-M1%20%7C%20M2%20%7C%20M3%20%7C%20M4-orange?style=for-the-badge)](https://en.wikipedia.org/wiki/Apple_silicon)

</div>

---

## 一句话

> 用 5 秒参考音,本地克隆任意中英声音,把整篇长稿合成成自然的语音 —— 全程不上传一个字节。

---

## ✨ 它能做什么

- 🎙 **声音克隆** · 拖一段 5–15 秒人声,自动转录,生成新的克隆音色
- 📝 **长文朗读** · 上千字脚本自动分段,流式播放
- 🎧 **多格式导出** · WAV / M4A / MP3,一键 ⌘S
- 📚 **声音库** · 多音色保存,跨次启动持续
- 🕘 **生成历史** · 自动归档每次合成,随时回听 / 重导出
- 🛡 **完全本地** · 推理在 Apple Silicon 本地完成,无网络请求

---

## 📦 下载

**[⬇️ 下载最新版](https://github.com/caspianchan31/voiceBox/releases/latest)**

或打开 [Releases 页面](https://github.com/caspianchan31/voiceBox/releases) 选择历史版本。

---

## 🚀 安装

1. 下载 `voiceBox-X.Y.Z.dmg` 并双击挂载
2. 把 `voiceBox.app` 拖入 `Applications` 文件夹
3. **首次打开** · 在「应用程序」里**右键**(或 Control 点击)`voiceBox.app` → 选**打开** → 弹窗里再点**打开**
4. 之后双击即可启动

> 应用未付费购买 Apple 公证,首次需绕过 Gatekeeper —— 这是 macOS 对非公证软件的统一处理,不是 voiceBox 的问题。
> 如果出现「已损坏」提示,终端执行:`xattr -dr com.apple.quarantine /Applications/voiceBox.app`

---

## 🎬 工作流

```
   ┌──────────────┐      ┌──────────────┐      ┌──────────────┐
   │ Reference    │      │  Your        │      │  Cloned      │
   │  Audio (5s)  │  +   │   Script     │  →   │   Speech     │
   │  + ASR text  │      │  (any len)   │      │  WAV/M4A/MP3 │
   └──────────────┘      └──────────────┘      └──────────────┘
       (one click ✨)         (paste / drop)         (⌘S export)
```

**3 步上手:**

1. **Studio** 标签页 → 点声音胶囊 → **添加声音** → 拖入参考音频 → 点 ✨ 自动转录 → 保存
2. **Studio** 主输入框 → 粘贴脚本(或拖入 `.txt`)→ 选音色
3. ⌘↩ 生成 · 听完 · ⌘S 导出

---

## 🧠 技术

| 用途 | 引擎 | 来源 |
|---|---|---|
| 语音合成 TTS | Qwen3 语音引擎 | Alibaba Qwen |
| 语音识别 ASR | Qwen3 语音识别 | Alibaba Qwen |
| 端侧加速 | Apple Silicon(GPU / 神经引擎) | Apple |

首次启动会下载语音模型(共 ~4 GB),建议接稳定网络;之后全部离线运行。

---

## ❓ 常见问题

<details>
<summary><b>voiceBox 开源吗?</b></summary>

二进制版本可免费个人使用,源码**不公开**。voiceBox 站在开源模型和框架(见下方致谢)的肩膀上 —— 那些才是开源巨人。本仓库是分发渠道。

</details>

<details>
<summary><b>会不会上传我的声音或文本?</b></summary>

不会。所有语音计算都在你 Mac 本地的 GPU / 神经引擎上跑,完全离线。唯一的网络请求只在首次启动:下载语音模型。下载完成后可以断网使用。

</details>

<details>
<summary><b>支持哪些语言?</b></summary>

中文(普通话)和英文表现最好。Qwen3 语音引擎官方还支持西语、法语、德语、日语、葡萄牙语、意大利语等十种语言。

</details>

<details>
<summary><b>为什么不上 Mac App Store?</b></summary>

App Store 沙盒会破坏我们需要的本地文件访问(参考音频、导出)。直接分发体验更干净。

</details>

<details>
<summary><b>可以商用吗?</b></summary>

应用本身免费,但底层 Qwen3 模型的商用授权请遵循各自模型 license。voiceBox 不为模型输出承担合规责任。

</details>

---

## 📋 系统要求

- macOS 15+(Sequoia 或更新)
- Apple Silicon(M1 / M2 / M3 / M4)
- 至少 5 GB 可用磁盘空间
- 网络(仅首次下载模型)

---

## 🗺 路线图

- [ ] 应用公证 + 自动更新(Sparkle)
- [ ] 多音色批量生成
- [ ] 字幕(SRT)同步导出
- [ ] 自定义停顿 / 强调标记
- [ ] iOS 版本

---

## 🙏 致谢

没有这些项目,就没有 voiceBox:

- [**MLX**](https://github.com/ml-explore/mlx) by Apple — the framework
- [**mlx-audio-swift**](https://github.com/Blaizzy/mlx-audio-swift) by Prince Canuma — the Swift TTS/STT layer
- [**mlx-audio**](https://github.com/Blaizzy/mlx-audio) by Prince Canuma — the Python research playground
- [**Qwen**](https://github.com/QwenLM) by Alibaba — TTS & ASR models
- [**Hugging Face**](https://huggingface.co/) — model distribution

---

## 📮 反馈

发现 bug / 想加功能?开个 [Issue](https://github.com/caspianchan31/voiceBox/issues)。

---

<div align="center">

Made with ☕ on Apple Silicon.

</div>
