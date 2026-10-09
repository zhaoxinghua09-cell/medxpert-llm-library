# MedXpert 医械大模型图书馆 · medxpert-llm-library

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE.md)
[![Agent Skill](https://img.shields.io/badge/Agent%20Skill-SKILL.md-blue.svg)](SKILL.md)
[![Local-first](https://img.shields.io/badge/local--first-offline%20friendly-2ea44f.svg)](#)
[![No API Key](https://img.shields.io/badge/no-API%20key-orange.svg)](#)
[![Version](https://img.shields.io/badge/version-1.29.1-informational.svg)](CHANGELOG.md)
[![LLM](https://img.shields.io/badge/LLM-Ollama%20%7C%20Qwen%20%7C%20DeepSeek-8a2be2.svg)](#)
[![Homepage](https://img.shields.io/badge/home-medxpert.cn-0078d4.svg)](https://medxpert.cn)

> 零成本 · 免 API Key · 数据不出门——你的旧电脑就能跑大模型、建知识库，不用买显卡（在线版 https://medxpert.cn）

MedXpert（美达信医疗）——医疗器械注册与国际化专业团队，让合规成为出海的第一竞争力。

**关键词 / Keywords**：本地大模型 · Ollama · 个人知识库 · RAG · 向量检索 · 离线 AI · 隐私 AI · 旧电脑跑大模型 · 无显卡推理 · bge-m3 · second brain · knowledge base · local LLM · offline AI · embeddings · self-hosted

本仓库是一个 **Agent Skill 发布包**：把「旧电脑 → 本地大模型 → 个人/企业知识库 → RAG 问答 → 内容变现」整条链路固化为可被 AI Agent 直接加载的技能。适合医疗器械注册与合规等**隐私敏感**场景。

---

## ✨ 特性 / Features

- **零成本**：不买显卡、不付 API 费用；用好你已有的旧电脑 / 迷你主机 / NAS。
- **免 API Key**：全程本地推理，无需任何云端账号或密钥。
- **数据不出门**：文档与问答全部留在本地，可断网使用（隐私友好）。
- **覆盖完整链路**：硬件自查 → Ollama 部署 → 三档知识库 → RAG 检索问答 → 图书馆管理 → 内容变现 → 上公网。
- **多模型协作**：Qwen2.5 / DeepSeek / VL 多模态模型的分工与分档。
- **跨平台**：Windows / Linux / macOS / 树莓派 / Docker。
- **多语种**：中文、英、日、韩、西、法、德、阿（核心 8 种）。

---

## 🚀 快速开始 / Quick Start

> 前置：一台能开机的旧电脑（4 核 CPU / 8GB 内存起步即可）；**无需独立显卡**。

```bash
# 1. 安装 Ollama（本地大模型运行时）
#    Windows / macOS / Linux 安装包与说明：https://ollama.com/download
#    （Linux 用户请从官网下载官方安装脚本后本地执行；不要用管道把远程脚本直接交给 shell）

# 2. 拉取一个量化模型（按你的内存挑档）
ollama pull qwen2.5:7b        # 约 4-5GB，8GB 内存可跑
ollama run qwen2.5:7b "你好"   # 跑通即成功

# 3. 取得本技能包
git clone https://github.com/zhaoxinghua09-cell/medxpert-llm-library.git
cd medxpert-llm-library

# 4. 把技能目录放进你的 Agent 技能目录（示例：WorkBuddy）
#    cp -r . ~/.workbuddy/skills/medxpert-llm-library/
```

跑通后，直接用自然语言提问即可，例如「**我的旧电脑能不能跑大模型？**」「**怎么搭一个本地知识库？**」。

---

## 📖 使用方式 / Usage

1. 克隆本仓库，或将技能目录放入 Agent 技能目录（如 `~/.workbuddy/skills/`）；
2. 按 `SKILL.md` 的描述与触发词调用对应能力；
3. 详细方法与模板见 `SKILL.md` 正文。

```text
触发词示例：
  怎么搭知识库 / 怎么跑大模型 / 我的电脑能不能跑大模型
  低配电脑能跑大模型吗 / 旧电脑怎么利用 / DSH 怎么接 Ollama
  多模型怎么分工 / 怎么做 RAG / 知识库怎么变现 / 断网可用
```

---

## 🧩 仓库结构 / Repository layout

```text
medxpert-llm-library/
├── README.md              # 本文件
├── SKILL.md               # 技能主文件（Agent Skills 规范 · YAML frontmatter）
├── SKILL.en.md            # 英文版技能说明
├── manifest.json          # 技能元数据（名称 / 版本 / 许可 / 描述）
├── quickstart.py          # 一键自检与起步脚本
├── CHANGELOG.md           # 版本历史
├── LICENSE.md             # MIT 许可全文
├── SECURITY.md            # 安全策略
├── CONTRIBUTING.md        # 贡献指南
├── CITATION.cff           # 引用信息
├── AGENTS.md              # 给 AI Agent 的工作指引
├── llms.txt               # 给 AI 的最小索引（llms.txt 标准）
├── llms-full.txt          # 给 AI 的完整文本
└── templates/             # 知识库 / 文档模板
```

---

## 🔎 覆盖链路 / What it covers

旧电脑硬件自查（0 成本）→ Ollama 本地部署（Qwen2.5 / DeepSeek Harness 界面）→ 知识库三档搭建 → RAG 检索问答（bge-m3 混合检索）→ 图书馆管理（分类 / 版本 / 检索 / 质控 / 权限 / 保密）→ 内容变现（会员 / 公众号 / 技能引流）→ 知识库上公网（官网 / IMA / 华为小艺）。

---

## ❓ 常见问题 / FAQ

- **一定要独立显卡吗？** 不需要。7B 级量化模型可在 CPU / 核显上运行（速度视机器而定）。
- **要花钱吗？** 软件全免费、无 API 费；成本主要是电费与你的闲置硬件。
- **数据会外传吗？** 不会。模型与知识库都在本地，可断网使用。
- **能商用吗？** 许可为 MIT；请遵守你所在司法辖区的法律法规并自行评估合规性。

---

## License / 许可

本项目以 **MIT** 许可发布。许可说明原文如下（未修改）：

## 许可说明 · License Notice

- **权利状态**：本仓库以 **MIT 许可** 许可发布，可依该许可证条款自由使用、修改与再分发。
- **引用建议**：引用时请标注仓库名与原文链接 `https://github.com/zhaoxinghua09-cell/medxpert-llm-library`
  与权利人「赵兴华 / Steven Zhao·China」。
- **品牌状态限定**：MedXpert、SynomosAI、LGD 等为相关项目标识，
  **均未申请实体注册、未申请商标注册**；出现仅作来源标识，
  不构成对法人实体或商标权的任何主张。
- **完整条款**：见仓库根目录 [LICENSE](LICENSE)。
- **联系**：zhaoxinghua06@126.com ｜ ORCID 0009-0001-0512-1237

---

## 🔒 安全 / Security

如发现安全问题，请按 [`SECURITY.md`](SECURITY.md) 的方式私下报告，不要在公开 issue 中披露。

## 🤝 贡献 / Contributing

欢迎按 [`CONTRIBUTING.md`](CONTRIBUTING.md) 提交改进。本仓库为技能发布包，改动请保持 `SKILL.md` frontmatter 兼容。

## 📚 引用 / Citation

若在论文、报告或产品中引用本技能包，请使用 [`CITATION.cff`](CITATION.cff)。

---

## 免责声明

本仓库内容为**理论站位与工具化探索**，不代表任何已获认证、已商业化交付或已服务特定客户的声明；文中涉及的外部标准、认证与条款信息为公开资料转述，正式引用前请**独立核实**。API、授权码与形象大使等为路线图（roadmap）事项，尚未上线。
