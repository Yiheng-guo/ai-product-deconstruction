# AI 产品拆解工作流（Skill）

> 把"拆解一个 AI 产品 / Multi-Agent 平台"沉淀为可复用、可验证的标准工作流。
> 技术每 3 个月就大变样，**唯有拆解与还原的底层思考框架是永恒的。**

## 这是什么

一个用于**深度拆解 AI 产品 / Agent 平台**的开源 Skill。它把"看清一个产品本质"的方法论封装成 6 层框架：

```text
市场层 → 商业层 → 用户层 → 技术层 → 模型层 → 基础层
```

每一层回答固定的核心问题，并产出固定产物：

| 层级 | 要解决的核心问题 | 产出物 |
|---|---|---|
| 0. 产品速览 | 它到底是什么？ | 一句话定位、产品构成、场景清单 |
| 1. 市场层 | 赛道是否值得进入，什么时候进入？ | 竞品分析报告、是否立项决策 |
| 2. 商业层 | 这是一个什么样的生意/机会？ | 一句话定位、商业模式、护城河 |
| 3. 用户层 | 用户真正完成的任务是什么？ | 用户旅程图、能力评测表与分数 |
| 4. 技术层 | 团队分工如何映射为 Agent？ | 技术流程图、逐 Agent 四件套 |
| 5. 模型层 | 哪些环节靠强模型？ | 模型路由逻辑、选择理由 |
| 6. 基础层 | 靠什么数据与知识变强？ | 数据内容、数据来源、知识库结构 |

## 目录结构

```text
ai-product-deconstruction/
├── SKILL.md                                  # Skill 主文件（完整工作流 + 质量门）
├── README.md
├── references/
│   ├── deconstruction-framework.md           # 六层框架详解、每层问题清单
│   └── evaluation-method.md                  # 效果评测权重、维度表、评级标准
├── examples/
│   └── oiioii-deconstruction.md              # 完整示例：OiiOii Multi-Agent 平台拆解
└── templates/
    └── deconstruction-template.md            # 可复用的空白拆解模板
```

## 怎么用

1. 读取 `SKILL.md`，按六层框架逐步执行。
2. 每一层先回答"核心问题"，再产出对应产物，最后过质量门。
3. 拆解 AI/Agent 平台时，重点走"人类团队分工 → Agent 映射"主线（技术层）。
4. 使用 `examples/oiioii-deconstruction.md` 作为参考范本，用 `templates/deconstruction-template.md` 作为新任务起点。

## 示例：OiiOii

`examples/oiioii-deconstruction.md` 以 **OiiOii（全球首个动画创作 Agent）** 为例完整演示了本工作流，涵盖：

- 六层拆解：市场 / 商业 / 用户 / 技术 / 模型 / 基础层
- 逐 Agent 四件套：艺术总监、编剧、角色设计师、场景设计师、分镜师、音乐总监、产品设计师（逻辑梳理 / 构成推导 / 工具推导 / 提示词推导）
- 全局上下文一致性协议、模型路由表、评测打分、架构总结

## 许可证

[MIT](./LICENSE)
