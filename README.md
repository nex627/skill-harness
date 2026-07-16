# Skill Harness

> 为每一个业务场景，创建不可跳步、不可简化的工程级 skill。

**Skill Harness 是一个工程约束型 skill 创建器。** 它不是给你一个模板让你填空，而是带你走一遍 PDCA 流程，确保产出的 skill 有流程管控、有知识库支撑、有质量校验。

## 这解决什么问题

你用 AI Agent 做事时，是不是经常遇到：

- AI 跳步，该做的调研没做就开始产出
- 产出太简略，拿到手不能用
- 草稿直接上线，出了问题才发现
- 做完不沉淀，下次又从零开始
- skill 越来越多，越来越乱

Skill Harness 用 **PDCA 闭环 + 三层知识库 + 五大工程约束** 解决这些问题。

## 与其他项目的区别

| 项目 | 解决什么 | 方法 |
|------|---------|------|
| [Anthropic skill-creator](https://github.com/anthropics/skills) | 怎么写 SKILL.md | 模板 + 指导 |
| [nuwa-skill](https://github.com/alchaincyf/nuwa-skill)（女娲） | 蒸馏人的思维 | 6路采集 + 3重验证 |
| [darwin-skill](https://github.com/alchaincyf/darwin-skill)（达尔文） | 让 skill 进化 | 自主实验循环 |
| **Skill Harness** | **为业务场景创建工程化 skill** | **PDCA + 三层知识库 + 五大约束** |

**一句话：女娲蒸馏人，Skill Harness 装配业务。**

## 安装

### 方式一：一行命令（推荐）

```
帮我安装这个 skill：https://github.com/nex627/skill-harness
```

或使用通用安装器：

```
npx skills add nex627/skill-harness
```

### 方式二：手动安装

| Runtime | 安装路径 |
|---------|---------|
| Claude Code | `~/.claude/skills/skill-harness/` |
| Codex CLI | `~/.codex/skills/skill-harness/` |
| Cursor | `~/.cursor/skills/skill-harness/` |
| TRAE | 项目 `.skills/` 目录 |
| 其他 | clone 到对应 runtime 的 `skills/` 目录 |

### 方式三：直接使用

把 `SKILL.md` 内容粘贴进对话，它本质就是 markdown + YAML frontmatter。

## 使用

装好后，告诉 AI：

```
> 帮我为抖音内容运营创建一个 skill
> 为开发团队做一个 code review 的 skill
> 我想给投资决策创建一个 skill
```

AI 会启动 PDCA 流水线，带你走完四步：

```
P（计划）→ 读取历史经验 + 搜索行业对标 + 确定方案
D（执行）→ 三段式结构化产出 skill 草稿
C（检查）→ AI 自检评分 + 人工复核
A（沉淀）→ 经验入库 + 版本号
```

## 三种 Skill 类型

| 类型 | 适用场景 | 模板 |
|------|---------|------|
| **基础型** | 简单工具调用、格式转换 | `templates/basic-skill.md` |
| **Workflow Harness 型** | 内容运营、开发编码、产品需求 | `templates/workflow-harness-skill.md` |
| **知识库驱动型** | 投资、学习、关系决策 | `templates/knowledge-driven-skill.md` |

## 五大工程约束

1. **流程硬阻断** — PDCA 阶段强依赖，不通过不可进入下一步
2. **三层知识库** — 公共库 + 行业库 + 私有库，不重复造轮子
3. **禁止简略输出** — 必须分段结构化交付
4. **人机双校验** — AI 自检 + 人工复核，草稿不可直接生效
5. **版本可迭代** — 语义化版本号，可回溯可复用

## 项目结构

```
skill-harness/
├── README.md                          # 你在看的这个
├── LICENSE                            # MIT
├── SKILL.md                           # Skill Harness 本体（元技能）
├── spec.md                            # 完整规范文档
├── CONTRIBUTING.md                    # 贡献规则
├── templates/                         # Skill 模板
│   ├── basic-skill.md                 # 基础型模板
│   ├── workflow-harness-skill.md      # Workflow Harness 型模板
│   └── knowledge-driven-skill.md      # 知识库驱动型模板
├── examples/                          # 完整示例
│   ├── content-ops/                   # 抖音内容运营示例
│   │   ├── SKILL.md
│   │   └── README.md
│   └── dev-coding/                    # AI 辅助开发示例
│       ├── SKILL.md
│       └── README.md
└── references/                        # 参考文档
    ├── skill-format.md                # Skill 格式规范
    └── pdca-guide.md                  # PDCA 适配指南
```

## 兼容性

- 兼容 [Agent Skills 协议](https://agentskills.io/)
- 可在 Claude Code、Codex、Cursor、TRAE、OpenClaw、Hermes 等 50+ runtime 中运行
- 本质是 markdown + YAML frontmatter，不依赖特定平台

## 贡献

欢迎贡献！请阅读 [CONTRIBUTING.md](CONTRIBUTING.md) 了解贡献规则。

核心规则：
- `SKILL.md` 是核心资产，不接受外部 PR（开 issue 讨论）
- 模板和示例欢迎 PR
- 社区创建的 skill 走索引收录

## 许可证

MIT — 随便用，随便改，随便造。

## 关于作者

**NEX** — 超级个体布道师，独立开发者。代表作：NEX 决策系统（AI 驱动的个人决策操作系统）、mgmt-skill（管理方法论蒸馏知识库）。

---

> **Skill Harness** — 不是写一个文件，是装配一条流水线。
