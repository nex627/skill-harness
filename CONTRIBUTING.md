# 贡献指南

感谢你对 Skill Harness 的兴趣！以下是如何参与贡献。

## 贡献方式

### 1. 报告问题

发现 bug 或有改进建议？请 [开一个 issue](https://github.com/nex627/skill-harness/issues/new)，描述：

- 你遇到的问题
- 期望的行为
- 复现步骤（如适用）

### 2. 贡献模板

欢迎贡献新的 skill 模板！请确保：

- 模板遵循 [spec.md](spec.md) 中的规范
- 包含完整的 YAML frontmatter
- 包含所有必需模块（定位、触发规则、执行逻辑、检查项、禁忌）
- 使用 `{占位符}` 标记需要用户填充的部分

### 3. 贡献示例

欢迎分享你用 Skill Harness 创建的 skill 示例！请确保：

- 示例是完整可用的 SKILL.md
- 附带 README.md 说明创建过程
- 不包含敏感信息（API key、内部数据等）

### 4. 改进文档

文档永远可以更好。欢迎改进措辞、补充说明、添加示例。

## 核心资产规则

| 资产 | PR 政策 |
|------|---------|
| `SKILL.md` | **不接受外部 PR**。发现问题请开 issue 讨论，被采纳的想法由维护者实现并在 commit 中致谢 |
| `spec.md` | 开 issue 讨论，重大变更由维护者决策 |
| `templates/` | 欢迎 PR，需符合规范 |
| `examples/` | 欢迎 PR，需附 README |
| `references/` | 欢迎 PR |
| `README.md` / `CONTRIBUTING.md` | 欢迎 PR |

## PR 流程

1. Fork 仓库
2. 创建分支：`git checkout -b feature/your-feature`
3. 提交更改：`git commit -m 'feat: 添加 XXX 模板'`
4. 推送：`git push origin feature/your-feature`
5. 开 PR，描述变更内容

### Commit 规范

| 前缀 | 用途 | 示例 |
|------|------|------|
| `feat:` | 新功能/新模板 | `feat: 添加电商运营 skill 模板` |
| `fix:` | 修复问题 | `fix: 修复模板缺少禁忌模块` |
| `docs:` | 文档改进 | `docs: 补充安装说明` |
| `refactor:` | 重构 | `refactor: 简化 PDCA 阻断规则描述` |
| `chore:` | 杂项 | `chore: 更新版本号` |

## 社区 Skill 收录

如果你用 Skill Harness 创建了一个好用的 skill，欢迎收录到社区索引：

1. 在你自己的仓库发布 skill（star 归你）
2. 用 Skill Harness 的 C 阶段自检评分 ≥ 80 分
3. 提一行 PR 添加到社区索引（后续开通）

## 行为准则

- 尊重所有贡献者
- 聚焦技术讨论，不搞人身攻击
- 欢迎新手提问
- 好想法比头衔重要

## 许可证

所有贡献内容遵循 MIT 协议。
