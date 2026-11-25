# Security Policy · 安全政策

**[English](#english) · [中文](#中文)**

---

<a id="english"></a>
## 🇬🇧 English

Macrunara provides ephemeral macOS CI runners for GitHub Actions on real Apple Silicon. Security is a core design property of the platform, and we take every report seriously.

### Reporting a Vulnerability

**Please do NOT open public GitHub Issues for security reports.**

- Email: **team@macrunara.com** (subject line starting with `[security]`)
- Include: affected component, steps to reproduce, potential impact, and whether the issue is already public anywhere
- You may encrypt reports on request — ask for our PGP key in your first email

### Response Commitments

| Stage | Commitment |
|---|---|
| Acknowledgement | Within **48 hours** |
| Initial assessment & severity | Within **5 business days** |
| Fix or mitigation for critical issues | Target **14 days** |
| Public disclosure | Coordinated with you; we credit reporters (with permission) |

### Scope

**In scope:**
- The Macrunara platform: control plane, scheduling, GitHub App integration, runner lifecycle
- Public repositories under the `MacRunara` organization (quickstart templates, example repositories, documentation)
- Isolation boundaries of the ephemeral build VMs

**Out of scope:**
- Vulnerabilities in your own workflow code, dependencies, or third-party Actions you use
- Issues requiring physical access to Apple hardware
- Social engineering of Macrunara staff or customers

### How the Platform Is Built

- **One task = one runner = one VM** — each job runs in a fresh VM cloned from a pre-warmed image, destroyed immediately after the job ends; no state is shared between jobs or customers.
- **Outbound-only networking** — build VMs expose no inbound ports.
- **JIT runner registration** — runners are registered just-in-time via the GitHub App and de-registered when the job finishes; no long-lived tokens on build machines.
- **Signing assets injected at runtime** — code-signing material is injected for the duration of the job and destroyed with the VM.

### Safe Harbor

We will not pursue legal action against researchers who: act in good faith, do not access or modify other customers' data, do not degrade service availability, and give us reasonable time to remediate before public disclosure.

---

<a id="中文"></a>
## 🇨🇳 中文

Macrunara 在真机 Apple Silicon 上为 GitHub Actions 提供一次性 macOS CI Runner。安全是本产品的核心设计属性，我们认真对待每一份报告。

### 报告漏洞

**请勿通过公开的 GitHub Issues 提交安全报告。**

- 邮箱：**team@macrunara.com**（主题以 `[security]` 开头）
- 请包含：受影响的组件、复现步骤、潜在影响、该问题是否已在任何渠道公开
- 如需加密通信，可在首封邮件中索取我们的 PGP 公钥

### 响应承诺

| 阶段 | 承诺 |
|---|---|
| 确认收到 | **48 小时**内 |
| 初步评估与定级 | **5 个工作日**内 |
| 严重问题修复或缓解 | 目标 **14 天** |
| 公开披露 | 与报告者协调；经许可后公开致谢 |

### 范围

**在范围内：** Macrunara 平台（控制平面、调度、GitHub App 集成、Runner 生命周期）；`MacRunara` 组织下公开仓库（quickstart 模板、示例仓库、文档）；一次性构建 VM 的隔离边界。

**不在范围内：** 您自己 workflow 代码、依赖或您使用的第三方 Action 中的漏洞；需要对 Apple 硬件物理接触的问题；针对 Macrunara 员工或客户的社工攻击。

### 平台安全设计

- **一任务一 Runner 一 VM**：每个任务在从预热镜像克隆的全新 VM 中运行，任务结束即刻销毁，任务与客户之间零状态共享。
- **仅出站连接**：构建 VM 不开放任何入站端口。
- **JIT Runner 注册**：Runner 通过 GitHub App 即时注册、任务结束即注销，构建机上不存放长期令牌。
- **签名资产运行时注入**：代码签名材料仅在任务期间注入，随 VM 一并销毁。

### 安全港

对于善意行事、不访问或篡改其他客户数据、不降低服务可用性、并在公开披露前给予我们合理修复时间的研究者，我们不会采取法律行动。
