# 贡献指南 / Contributing

感谢你愿意改进 `medxpert-llm-library`！

## 提交前

1. 先搜一搜 [issues](https://github.com/zhaoxinghua09-cell/medxpert-llm-library/issues)，避免重复。
2. Fork 仓库并从 `main` 拉一个分支：`git checkout -b fix/your-topic`。
3. 改动尽量小而聚焦（一个 PR 一件事）。

## 本仓库的特殊约束

本仓库是 **Agent Skill 发布包**，请遵守：

- **保持 `SKILL.md` frontmatter 兼容**：`name` / `slug` / `version` / `license` 等字段不要随意改动。
- **权属字段只由维护者变更**：`copyright` / `author` / `LICENSE.md` 的版权主体不要在 PR 中修改。
- **同步文档**：改了能力，请更新 `CHANGELOG.md`；改了用法，请更新 `README.md`。
- **不要提交密钥、令牌或真实客户数据。**

## 提交 PR

- 说明「为什么改」与「怎么验证」。
- 若改动了 `quickstart.py`，请附上你本机跑 `python quickstart.py` 的输出。

## 许可

本仓库以 **MIT** 许可发布。你的贡献将以同一许可发布。

---

许可：MIT ｜ 权利人：赵兴华 / Steven Zhao·China
