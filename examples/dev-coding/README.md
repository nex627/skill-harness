# 示例：Vibe Coding Skill

这是一个使用 Skill Harness 创建的 **Workflow Harness 型** skill 示例，面向 AI 辅助开发场景。

## 创建过程

```
用户 ❯ 帮我为开发编码创建一个 skill

Skill Harness ❯ 启动 PDCA 流水线...

【P 阶段】
- 读取历史：无（首次创建，标记放行）
- 行业对标：搜索 AI 辅助开发最佳实践，找到3个对标
- 模板选择：Workflow Harness 型
- 产出：技术调研报告 + 需求规格 + 技术方案

【D 阶段】
- D1 执行摘要：架构决策 + 技术选型理由
- D2 详细定义：完整 SKILL.md（见同目录 SKILL.md）
- D3 偏差记录：无偏差

【C 阶段】
- AI 自检：语法 95 / 边界 88 / 安全 90 / 可维护 85 / 测试 87 → 综合 89.2 ✅
- 人工复核：通过 ✅

【A 阶段】
- 版本号：v1.0.0
- 踩坑记录：首次创建，暂无
- 写入 L3：已沉淀
```

## 使用方式

将 `SKILL.md` 复制到你的 AI Agent 的 skills 目录，然后：

```
> 帮我开发一个用户登录功能
> 技术选型：用 Next.js 还是 Nuxt？
> 修一下这个 bug
> code review 一下这段代码
```

## 文件清单

| 文件 | 说明 |
|------|------|
| `SKILL.md` | Vibe Coding skill 定义 |
| `README.md` | 本文件 |
