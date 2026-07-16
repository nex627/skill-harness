# Skill 格式规范

## 文件格式

所有 skill 文件使用 Markdown + YAML frontmatter。

## YAML Frontmatter

```yaml
---
name: skill-name          # 必需，小写连字符
version: 1.0.0            # 必需，语义化版本
description: 描述          # 必需，≤300字（防超 loader 1024 上限）
author: 作者名             # 必需
tags: [tag1, tag2]        # 推荐，便于检索
license: MIT              # 可选
skill_type: basic         # 可选：basic / workflow-harness / knowledge-driven
pdca: true                # 可选，Workflow Harness 型必填
knowledge_layers: [L1]    # 可选，使用的知识库层级
knowledge_base: path      # 可选，知识库驱动型必填
---
```

## 字段说明

| 字段 | 必需 | 说明 | 示例 |
|------|:---:|------|------|
| `name` | ✅ | skill 唯一标识，小写连字符 | `douyin-content-ops` |
| `version` | ✅ | 语义化版本号 | `1.0.0` |
| `description` | ✅ | 一句话说清干什么，≤300字 | `抖音内容运营全流程 skill` |
| `author` | ✅ | 作者 | `NEX` |
| `tags` | 推荐 | 标签数组 | `[content, douyin]` |
| `skill_type` | 可选 | skill 类型 | `basic` / `workflow-harness` / `knowledge-driven` |
| `pdca` | 可选 | 是否启用 PDCA 流程 | `true` |
| `knowledge_layers` | 可选 | 知识库层级 | `[L1, L2, L3]` |
| `knowledge_base` | 可选 | 知识库路径 | `path/to/kb.md` |

## Markdown 结构

### 基础结构（所有 skill 必需）

```markdown
# Skill 名称

## 定位
## 触发规则
## 执行逻辑
## 检查项
## 禁忌
## 版本记录
```

### Workflow Harness 型额外结构

```markdown
## 三层知识库
## PDCA 执行流程
### P 阶段 — 计划
### D 阶段 — 执行
### C 阶段 — 检查
### A 阶段 — 沉淀
## 五大工程约束
```

### 知识库驱动型额外结构

```markdown
## 知识库
## 决策流程
## 决策表
## 输出规范
## 关联 wiki
```

## 命名规范

| 对象 | 规范 | 示例 |
|------|------|------|
| 文件名 | `{skill-name}.skill.md` 或 `SKILL.md` | `douyin-content-ops.skill.md` |
| skill name | 小写连字符 | `douyin-content-ops` |
| 标签 | 小写英文 | `[content, short-video]` |
| 版本号 | 语义化 | `1.0.0` |

## description 字段要求

- ≤300字（防止超过 skill loader 的 1024 字符上限）
- 一句话说清这个 skill 干什么
- 包含关键词，便于检索
- 不含 markdown 格式

```yaml
# ✅ 好的 description
description: 抖音内容运营全流程 skill。从选题到发布，PDCA 闭环管理，包含爆款拆解、脚本创作、分镜设计、发布策略。

# ❌ 不好的 description
description: 一个很好的 skill，帮助你做事。
```
