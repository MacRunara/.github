<div align="center">

# Macrunara

**Cloud macOS CI/CD runners for GitHub Actions — on real Apple Silicon**

One task. One runner. One clean VM. Flat-rate monthly and annual plans with included build minutes.

[Website](https://macrunara.com) · [Docs](https://docs.macrunara.com/) · [Quickstart](https://github.com/MacRunara/quickstart) · [Install the GitHub App](https://github.com/apps/macrunara-app)

</div>

---

## ⚡ 3-minute setup

1. **Install** the Macrunara GitHub App on your account or organization — [one-click install](https://github.com/apps/macrunara-app).
2. **Point your job at the fleet** and push. No secrets, no extra configuration:

```yaml
jobs:
  build:
    runs-on: [macos, arm64, macrunara]
    steps:
      - uses: actions/checkout@v5
      - run: xcodebuild -scheme MyApp -destination 'platform=iOS Simulator,name=iPhone 17'
```

Preinstalled on every runner: Xcode, Flutter, Android SDK, Node.js, CocoaPods and the usual mobile toolchains — copy a template and build.

## Why Macrunara

| | **Macrunara** | GitHub-hosted macOS |
|---|---|---|
| Hardware | Mac mini with Apple Silicon (M4 / M6 class) | 3-core M1 |
| Billing | **Flat rate: $99/mo or $990/yr (M4)** | $0.08–0.12/min |
| Environment | Fresh ephemeral VM per job, ready in ~30s | Fresh VM per job |
| Preinstalled | Full mobile toolchains out of the box | Base image only |

> 📊 **Break-even:** if your team builds more than ~25–30 hours a month, a flat Macrunara plan costs less than per-minute runners — and the bill never moves.

## 💰 Plans

| Plan | Price | Build minutes / month | Concurrency |
|---|---|---|---|
| Free | $0 | 100 | 1 |
| M4 Runner | $99/mo · $990/yr | 3,000 (200-min grace) | 3 |
| M6 Runner | $119/mo · $1,190/yr | 3,000 (200-min grace) | 3 |

All paid plans bill exclusively through GitHub Marketplace.

## 🔒 Security by design

- **One task = one runner = one VM** — the VM is destroyed right after your job. Zero cross-job contamination.
- **Outbound-only networking** — no inbound ports, ever.
- **Signing assets injected at runtime**, destroyed with the VM.
- **JIT runner registration** via GitHub App — no long-lived personal access tokens on build machines.

## 📦 Repositories

| Repo | What it is |
|---|---|
| [quickstart](https://github.com/MacRunara/quickstart) | One-click workflow templates for iOS / Android / Flutter / React Native |
| [ios-swift-example](https://github.com/MacRunara/ios-swift-example) | Fork-and-run iOS (Swift) example |
| [android-example](https://github.com/MacRunara/android-example) | Fork-and-run Android example |
| [flutter-example](https://github.com/MacRunara/flutter-example) | Fork-and-run Flutter example (IPA + APK) |
| [react-native-example](https://github.com/MacRunara/react-native-example) | Fork-and-run React Native example |
| [xcode-matrix-example](https://github.com/MacRunara/xcode-matrix-example) | Multi-version Xcode matrix builds |
| [benchmarks](https://github.com/MacRunara/benchmarks) | Build-time benchmarks on real hardware |
| [awesome-macos-ci](https://github.com/MacRunara/awesome-macos-ci) | Curated macOS CI resources |
| [blog](https://github.com/MacRunara/blog) | Engineering blog — macOS CI deep dives |

## 💬 Support

- Email: **team@macrunara.com**
- Questions & template requests: [quickstart Issues](https://github.com/MacRunara/quickstart/issues)

---

<details>
<summary>🇨🇳 中文简介</summary>

<br>

**Macrunara 是基于真机 Apple Silicon 的 macOS CI/CD 托管平台，深度集成 GitHub Actions。**

- 安装 GitHub App 即可使用，约 3 分钟接入，无需配置任何 Secret
- 一任务一 Runner 一 VM，用完即毁，任务间零污染
- 固定订阅：M4 $99/月或 $990/年、M6 $119/月或 $1,190/年，均含 3,000 分钟/月额度、单账户 3 并发、额度用尽后 200 分钟宽限（不额外收费）；Free 100 分钟/月、1 并发
- Runner 镜像预热 + 写时复制克隆，约 30 秒就绪
- 节点预装 Xcode / Flutter / Android SDK / Node.js / CocoaPods，模板复制即用

快速开始 → [quickstart 模板库](https://github.com/MacRunara/quickstart)

</details>

<details>
<summary>🇯🇵 日本語の概要</summary>

<br>

**Macrunara は、実機 Apple Silicon 上で動作する GitHub Actions 向け macOS CI/CD プラットフォームです。**

- GitHub App をインストールするだけで約 3 分で開始、Secret の設定は不要
- 1 ジョブ = 1 ランナー = 1 VM、ジョブ終了後すぐに廃棄、ジョブ間の状態共有はゼロ
- 定額制：M4 $99/月または $990/年、M6 $119/月または $1,190/年。いずれも月 3,000 分・同時実行 3・200 分のグレイス付き。Free は月 100 分・同時実行 1
- ランナーはプリワーム済みイメージから約 30 秒で起動
- Xcode / Flutter / Android SDK / Node.js / CocoaPods プリインストール

クイックスタート → [quickstart テンプレート](https://github.com/MacRunara/quickstart)

</details>
