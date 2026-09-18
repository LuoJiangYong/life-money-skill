# Life Money Skill（人生搞钱）

把「7 提示词职业变现法」产品化的 Hermes 诊断 Skill：**访谈建档 → 7 轮分析 → 单文件 HTML 诊断报告**（设计语言）。

> 状态：**开发中**（Phase 0-3 已完成，Phase 4 收口）｜私有仓库

## 这是什么

- **输入**：个人档案与职业经历（简历 / 项目报告 / 作品集 + 访谈补全）
- **处理**：Agent 执行 7 轮结构化分析 —— 隐藏技能 → 收入机会 → 变现路径 → 最大杠杆 → 高薪方向 → AI 副业 → 90 天计划
- **输出**：`report.html` —— 单文件、离线可开、含 4 组可视化（机会矩阵 / 薪酬阶梯 / 时间预算 / 90 天时间线）与 7 个原始提示词附录

## 快速开始（仓库内跑演示）

```bash
python scripts/render_report.py examples/demo/analysis.json --profile examples/demo/profile.json
# → examples/demo/report.html
```

仓库自检（契约校验 + 渲染冒烟 + 结构核对，零依赖）：

```bash
python scripts/verify_repo.py
```

## 目录

| 路径 | 内容 |
|---|---|
| `CONSTITUTION.md` | 设计宪法（5 原则 / 7 维度 / 禁止模式 / 元数据治理） |
| `SKILL.md` | 路由中枢（4 阶段 + 3 道用户门禁） |
| `references/` | 访谈指南 · 分析规格 · 报告设计 · 数据校准 · 7 提示词 canonical · 案例库 |
| `assets/schemas/` | 两个公共契约（career_profile / career_analysis） |
| `assets/templates/report.css` | 报告设计系统样式（tokens + 组件 + 打印） |
| `scripts/render_report.py` | `analysis.json → report.html`（含契约校验，纯本地、无依赖） |
| `scripts/verify_repo.py` | 仓库自检：契约 + 渲染冒烟 + 结构核对（零依赖，可用于 CI） |
| `examples/demo/` | 虚构人设完整示例（profile + analysis + 成品报告） |
| `projects/` | 运行产物（gitignored；含用户敏感数据） |

## 三道用户门禁（不可跳过）

| 门禁 | 触发点 | 内容 | 默认值 |
|---|---|---|---|
| 1 | L1 建档 | 收集材料（简历/项目报告/作品集）+ 访谈补全 + 用户确认 | — |
| 2 | 隐藏技能后、收入机会前 | 用户选每月额外赚取目标 | 1000-3000 元/月 |
| 3 | AI 副业服务前 | 用户填每周启动可投入时间 | 6 小时 |

## 开发状态

| Phase | 内容 | 状态 |
|---|---|---|
| 0 | 宪法 + 双契约 + 仓库上线 | 完成 |
| 1 | SKILL.md + 7 提示词 canonical + 案例库骨架 | 完成 |
| 2 | references 领域文档（访谈/分析/设计/校准） | 完成 |
| 3 | 渲染管线 + 设计系统 + 可视化图示 | 完成 |
| 4 | 示例 + 端到端验证 + 文档 | 收口中（安装待定） |

## 硬约束

- 7 个分析维度不可增删、改名、合并（忠实源方法论）
- 不调用外部 LLM API；渲染纯本地、离线可用
- 用户数据禁止进入 git（`projects/` 全程 gitignored）
- 报告不写「保证收入」类承诺；附录保留免责声明
