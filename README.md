# Skill Harness

> 不是写一个文件，是设计一条有人工把关的流水线。

**Skill Harness 是一个 Skill 设计方法论框架。** 教你如何把一个复杂工作拆解成多个步骤，每步设人工检查点，经验自动沉淀到知识库。

## 这解决什么问题

你用 AI Agent 做事时，是不是经常遇到：

- AI 一口气做完，中间跳步出错
- 产出太简略，拿到手不能用
- 做完不沉淀，下次从零开始
- 没有方法论，skill 设计全凭感觉

Skill Harness 用 **PDC（多步拆解+人工检查）+ A（经验沉淀）** 解决这些问题。

## 核心模型：PDC + A

```
P（规划）→ 把工作拆成步骤，定义每步的输入/产出/检查标准
    ↓
D（执行）→ 按步骤执行，每步产出具体结果
    ↓
C（检查）→ 每步结束，人工介入检查 ✅/❌，通过才进下一步
    ↓
A（沉淀）→ 收集经验（系统自动 + 人工反馈），写入知识库
```

**最核心的设计**：每步都有人工检查点。AI 跑得快但会出错，人在关键节点把关。

### 示例：开发一个项目

```
步骤1：搜集资料（竞品调研 + 资料搜集）
  → 产出：调研报告
  → 人工检查 ✅/❌
  → 通过才进入下一步

步骤2：根据资料产出文档（需求文档、开发文档）
  → 产出：文档
  → 人工检查 ✅/❌
  → 通过才进入下一步

步骤3：执行编码
  → 产出：代码
  → 人工检查 ✅/❌

A 阶段：收集经验（系统自动 + 人工反馈）→ 写入知识库
```

## 与其他项目的区别

| 项目 | 解决什么 | 方法 |
|------|---------|------|
| [Anthropic skill-creator](https://github.com/anthropics/skills) | 怎么写 SKILL.md | 模板 + 指导 |
| [nuwa-skill](https://github.com/alchaincyf/nuwa-skill)（女娲） | 蒸馏人的思维 | 6路采集 + 3重验证 |
| [darwin-skill](https://github.com/alchaincyf/darwin-skill)（达尔文） | 让 skill 进化 | 自主实验循环 |
| **Skill Harness** | **如何设计多步骤+检查点的 skill** | **PDC拆解 + 人工检查点 + A经验沉淀** |

**一句话：女娲蒸馏人，Skill Harness 设计流水线。**

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
> 帮我为开发项目设计一个 skill
> 帮我做视频设计一个 skill
> 为投资决策设计一个 skill
```

AI 会带你走设计流程：
1. 理解场景（产出什么、有哪些环节、哪里容易出错）
2. 拆步骤（3-7步，每步定义输入/动作/产出/检查标准）
3. 定义检查点（每步人工检查清单）
4. 设计经验沉淀（系统自动+人工反馈→知识库）
5. 读取历史经验（避免重复踩坑）
6. 产出完整 SKILL.md

## 五大设计约束

1. **多步拆解** — 工作必须拆成 3-7 个步骤，禁止一步到位
2. **人工检查点** — 每步结束必须有人工检查，通过才进下一步
3. **明确产出** — 每步必须有明确的产出物
4. **经验沉淀** — 必须设计 A 阶段，收集系统+人工经验入知识库
5. **历史复用** — 设计时必须读取历史经验，避免重复踩坑

## 项目结构

```
skill-harness/
├── README.md                          # 你在看的这个
├── LICENSE                            # MIT
├── SKILL.md                           # Skill Harness 本体（方法论框架）
├── spec.md                            # 完整规范文档
├── CONTRIBUTING.md                    # 贡献规则
├── templates/                         # Skill 模板
│   ├── basic-skill.md                 # 基础型（3-7步+检查点+经验沉淀）
│   ├── workflow-harness-skill.md      # Workflow 型（完整PDC+A+三层知识库）
│   └── knowledge-driven-skill.md      # 知识库驱动型
├── examples/                          # 完整示例
│   ├── content-ops/                   # 视频制作示例（4步）
│   │   ├── SKILL.md
│   │   └── README.md
│   ├── dev-coding/                    # 开发项目示例（3步）
│   │   ├── SKILL.md
│   │   └── README.md
│   └── conversation-closer/           # 对话收尾示例（通用C+A引擎模式）
│       ├── SKILL.md
│       └── README.md
└── references/                        # 参考文档
    ├── skill-format.md                # Skill 格式规范
    └── pdca-guide.md                  # PDC+A 适配指南
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

---

> **Skill Harness** — 不是写一个文件，是设计一条有人工把关的流水线。
