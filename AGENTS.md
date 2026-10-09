# AGENTS.md — 给 AI Agent 的工作指引

本文件面向自动化 AI Agent（编码助手、技能加载器、知识库机器人）。人类读者请看 [README.md](README.md)。

## 这个仓库是什么

`medxpert-llm-library` 是一个 **Agent Skill 发布包**，不是可运行的 SDK。核心资产是 `SKILL.md`（遵循 Agent Skills 规范，带 YAML frontmatter）。把本目录放入 Agent 的技能目录即可让它获得「本地大模型 / 知识库搭建」能力。

## 可用的工作命令

```bash
# 查看技能元数据（名称 / 版本 / 许可 / 描述）
cat manifest.json

# 运行环境自检与起步脚本
python quickstart.py

# 查看技能全文（触发词、方法、边界）
cat SKILL.md
```

前置依赖：本机已安装 Python 3.8+；若要真正跑本地大模型，还需安装 [Ollama](https://ollama.com/download)。

## 约定（Do）

- 修改前先读 `SKILL.md` 的 YAML frontmatter，**保持字段兼容**（`name` / `slug` / `version` / `license` 等）。
- 新增能力写进 `SKILL.md` 正文，并同步更新 `CHANGELOG.md`。
- 交付前跑 `python quickstart.py` 自检。

## 禁止（Don't）

- 不要改动 `SKILL.md` 的 `copyright` / `author` 字段，也不要改 `LICENSE.md` 的版权主体——**权属字段只由维护者变更**。
- 不要在仓库内提交任何密钥、令牌或真实客户数据。
- 不要声称本包「已认证 / 已商用交付 / 已服务特定客户」。

## 边界

本技能专注**本地**大模型与知识库；不覆盖云端 API 部署、编程开发教学等场景。
