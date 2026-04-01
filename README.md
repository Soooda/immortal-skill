<div align="center">

# 永生.skill

### 与其等着被别人蒸，不如先蒸自己。

### 不蒸馒头争口气！顺便还能蒸馏下身边的人。

[![License MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Python 3.9+](https://img.shields.io/badge/Python-3.9+-blue.svg)](https://python.org)
[![AgentSkills Standard](https://img.shields.io/badge/AgentSkills-Standard-8A2BE2.svg)](https://agentskills.io/)
[![OpenClaw Compatible](https://img.shields.io/badge/OpenClaw-Compatible-orange.svg)](https://docs.openclaw.ai/)
[![被蒸馏的人数](https://img.shields.io/badge/被蒸馏-∞人-red.svg)](#谁能被蒸馏)

</div>

<div align="center">

**2026 年了，人人都在聊 AI Agent，但还没人认真想过一件事——**

**你自己，值不值得被蒸馏成一个 Skill？**

</div>

---

<div align="center">

你的同事跑路了？蒸馏他。让他的经验还能接着用。

你的导师退休了？蒸馏他。让「这事你得这么想」还能继续响在你耳边。

你奶奶的唠叨快忘了？蒸馏她。让 AI 替她继续念叨你。

你的朋友不联系了？蒸馏他。你们之间最好笑的对话不该消失。

你前任的语气忘不掉？蒸馏 TA。——算了这个你自己决定。

你自己呢？万一哪天你不在了，谁来当你？

<br/>

**别人蒸馏你之前，先把自己蒸明白。**

</div>

<div align="center">

[谁能被蒸馏？](#谁能被蒸馏) · [蒸什么？](#蒸什么四维蒸馏) · [从哪蒸？](#从哪蒸) · [怎么蒸？](#怎么蒸) · [蒸出来长什么样？](#蒸出来长什么样) · [English](#english)

</div>

---

## 谁能被蒸馏？

> 简单来说：你认识的所有人。包括你自己。

| | 蒸谁 | 蒸什么重点 | 伦理底线 |
|:---:|:---:|---------|---------|
| 🪞 | **你自己** | 全蒸。怎么做事、怎么说话、经历过什么、是什么人 | 你的数据你做主 |
| 🏢 | **跑路的同事** | 工作流程 + 沟通风格 | 仅限团队内部用 |
| 🎓 | **退休的导师** | 教学方式 + 人生智慧 | 经本人授权 |
| 👴 | **远去的亲人** | 家族记忆 + 生活智慧 + 唠叨语气 | 家人知情同意 |
| 💔 | **离开的前任** | 关系互动 + 共同记忆 + 说话方式 | 正面回忆，严格脱敏 |
| 🍻 | **失联的朋友** | 友谊互动 + 共同经历 + 社交偏好 | 对方知情同意 |
| 🌍 | **公众人物** | 公开风格 + 方法论 + 公开事迹 | 仅限公开资料 |

每种角色都有独立的[蒸馏模板](personas/)——因为蒸同事和蒸前任，方法肯定不一样。

---

## 蒸什么？四维蒸馏

> 不是把聊天记录塞进向量库就叫蒸馏。那叫腌制。

```
        🔧 怎么做事                    💬 怎么说话
        ┌──────────┐              ┌──────────┐
        │ 程序性知识 │              │ 互动风格  │
        │ procedure │              │interaction│
        └──────────┘              └──────────┘

        📖 经历过什么                  🧠 是什么人
        ┌──────────┐              ┌──────────┐
        │ 记忆经历  │              │性格价值观 │
        │  memory   │              │personality│
        └──────────┘              └──────────┘
```

蒸馏出来的每一条都标注**证据等级**：

- `verbatim` 原话 —— TA 亲口说的
- `artifact` 文档 —— 留下的文字材料
- `impression` 印象 —— 别人觉得 TA 是这样的

矛盾的地方**不强行统一**——人本来就是矛盾的，周一说的话周五自己都能推翻。

---

## 从哪蒸？

> 你和 TA 的对话散落在十几个 App 里。没关系，都能收。

| | 平台 | 怎么收 |
|:---:|------|---------|
| 💬 | **飞书** · **钉钉** · **Slack** · **Discord** · **Telegram** | API 自动拉，配个 token 就行 |
| 📱 | **微信** · **iMessage** | 本地数据库读取 |
| 📦 | **WhatsApp** · **Twitter/X** · **Google Takeout** · **Facebook/Instagram** | 官方归档解析 |
| 📧 | **Email** (Gmail / mbox) | 邮箱归档解析 |
| 📄 | **任意文件** · TXT · JSON · CSV · Markdown | 手动丢进来 |

12+ 个平台，每个都有[保姆级数据获取指南](docs/PLATFORM-GUIDE.md)。

---

## 怎么蒸？

**方式一：对话触发**

在 OpenClaw / Claude Code 里直接说人话：

> "帮我把李工蒸馏成 Skill，他的飞书记录在这儿"
>
> "我想蒸馏我奶奶，微信记录我导出来了"
>
> "蒸馏我自己，微信 + Twitter 全上"

**方式二：CLI 手动挡**

```bash
# 能蒸哪些平台？
python3 kit/immortal_cli.py platforms

# 配置凭证
python3 kit/immortal_cli.py setup feishu

# 开蒸
python3 kit/immortal_cli.py collect --platform feishu --scan
python3 kit/immortal_cli.py collect --platform wechat --db ~/wechat.db --channel "张三"
python3 kit/immortal_cli.py collect --platform imessage --scan

# 手动喂料
python3 kit/immortal_cli.py import ~/chat-export.txt --output corpus/chat.md

# 初始化 → 封包 → 快照
python3 kit/immortal_cli.py init --slug grandma --persona family
python3 kit/immortal_cli.py stamp --slug grandma --sources "wechat:chat,paste:notes"
python3 kit/immortal_cli.py snapshot --slug grandma --note "第一版"
```

---

## 蒸出来长什么样？

一个人 = 一个文件夹 = 一个可以直接用的 AI Skill：

```
grandma/
├── SKILL.md          ← AI 读这个就知道「奶奶是谁」
├── interaction.md    ← 奶奶怎么说话、怎么唠叨、怎么关心人
├── memory.md         ← 奶奶讲过什么故事、经历过什么
├── personality.md    ← 奶奶是什么样的人、在乎什么
├── conflicts.md      ← 不同来源说法不一致的地方
└── manifest.json     ← 元数据（来源、时间、指纹）
```

丢进 OpenClaw 的 skills 目录，AI 就能用奶奶的语气跟你说话了。

不是复制粘贴。是真的理解她怎么说话、怎么想、在乎什么。

### 现成的示例

| 蒸了谁 | 角色 | 蒸了几个维度 | 看看效果 |
|:---:|:---:|:---:|:---:|
| 李工 | 跑路的同事 | 2 维 | [examples/li-gong-demo/](examples/li-gong-demo/) |
| 陈韵 | 自己 | 全 4 维 | [examples/self-demo/](examples/self-demo/) |
| 王老师 | 退休的导师 | 4 维 | [examples/mentor-demo/](examples/mentor-demo/) |

---

## 安装

```bash
# 扔进工作区
cp -r immortal-skill <your-workspace>/skills/immortal-skill

# 或者全局装
cp -r immortal-skill ~/.openclaw/skills/immortal-skill
```

验证一下：
```bash
openclaw skills list | grep immortal-skill
```

---

## 项目结构

```
immortal-skill/
├── SKILL.md            # 蒸馏器入口
├── personas/           # 7 种角色蒸馏模板
├── recipes/            # 蒸馏方法论（怎么提取、怎么合并、怎么处理矛盾）
├── prompts/            # 给 LLM 的 Prompt 模板
├── collectors/         # 12 个平台的数据采集器
├── kit/                # CLI 工具集
├── examples/           # 3 个蒸好的示例
└── docs/               # 调研综述 + 平台数据获取指南
```

---

## 设计哲学

| 原则 | 翻译成人话 |
|------|---------|
| **分路蒸馏** | 四个维度分开提，不搞一锅炖 |
| **证据分级** | 原话 > 文档 > 印象，说清楚谁说的 |
| **伦理先行** | 蒸谁都行，但得有底线 |
| **矛盾保留** | 人本来就前后不一致，不强行洗白 |
| **版本快照** | 蒸歪了？一键回滚重来 |
| **多源融合** | 微信 + 飞书 + Twitter 混着蒸，味道更正 |

---

<div align="center">

## 最后说句正经的。

人会走，记忆会模糊，聊天记录会沉到第 99 页。

但 TA 说话的方式、讲过的故事、在乎的东西——

可以不跟着消失。

<br/>

**⭐ Star 一下，下次轮到你被蒸馏的时候，至少蒸馏器是开源的。**

<br/>

MIT License · [调研综述](docs/RESEARCH.md) · [平台指南](docs/PLATFORM-GUIDE.md)

</div>

---

<a name="english"></a>

<details>
<summary><b>English</b></summary>

## immortal-skill

**Rather than waiting for someone else to distill you, distill yourself first.**

A universal digital immortality framework — distill **anyone's** digital persona from chat logs, social media, and documents across 12+ platforms.

- **7 persona templates**: Self, Colleague, Mentor, Family, Partner/Ex, Friend, Public Figure
- **4 distillation dimensions**: Procedural knowledge · Interaction style · Memories & experiences · Personality & values
- **Evidence grading**: verbatim > artifact > impression, with explicit conflict tracking
- **Role-based ethics**: Different consent and anonymization requirements per relationship type
- **12+ data platforms**: WeChat, Feishu, iMessage, Telegram, Slack, Discord, WhatsApp, Twitter/X, Email, and more
- **Output**: [Agent Skills](https://agentskills.io/) standard, compatible with [OpenClaw](https://docs.openclaw.ai/)

⭐ Star this repo — next time you get distilled, at least the distiller will be open source.

</details>
