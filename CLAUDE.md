# AutoGen — Claude Code 配置

## gstack 技能集

本项目已集成 [gstack](https://github.com/reinhardliu-cloud/gstack) AI 工程工作流技能集。
所有技能以 `/rs-` 前缀激活，安装路径：`.claude/skills/gstack/`

> **网页浏览**：所有网页浏览操作请使用 `/rs-browse` 技能，不要使用 `mcp__claude-in-chrome__*` 工具。

### 可用的 /rs-* 指令

| 指令 | 说明 |
|------|------|
| `/rs-office-hours` | 产品方向讨论 — YC风格办公时间，在写代码前重新审视想法，确认是否值得构建 |
| `/rs-plan-ceo-review` | CEO视角规划评审 — 从CEO角度找到10分产品，重新定义需求方向 |
| `/rs-plan-eng-review` | 工程规划评审 — 锁定架构、数据流、边界情况和测试方案 |
| `/rs-plan-design-review` | 设计规划评审 — 从0-10分评估设计各维度，解释如何达到10分 |
| `/rs-design-consultation` | 设计系统咨询 — 从零构建完整设计系统，包含颜色、排版、组件规范 |
| `/rs-review` | 代码审查 — 提交前PR审查，检查SQL安全、LLM信任边界等结构性问题 |
| `/rs-ship` | 一键发布 — 运行测试、代码审查、推送代码、创建PR，一键完成发布流程 |
| `/rs-land-and-deploy` | 落地部署 — 合并代码并部署到生产环境，含金丝雀验证 |
| `/rs-canary` | 金丝雀监控 — 部署后持续监控，检测生产环境异常 |
| `/rs-benchmark` | 性能基准测试 — 检测性能回退，对比前后性能变化 |
| `/rs-browse` | 无头浏览器 — 基于Playwright的真实Chrome浏览器，用于网页操作和截图 |
| `/rs-qa` | 质量保证测试 — 打开真实浏览器发现bug，修复后重新验证 |
| `/rs-qa-only` | 仅QA报告 — 与qa相同，但只报告问题，不修改代码 |
| `/rs-design-review` | 设计审查 — 对UI设计进行评审并执行修复循环，提交原子化commits |
| `/rs-setup-browser-cookies` | 浏览器Cookie配置 — 从真实浏览器导入认证Cookie用于测试 |
| `/rs-setup-deploy` | 部署配置 — 一次性部署环境配置 |
| `/rs-retro` | 每周回顾总结 — 按人统计代码量、commits数量和发布记录 |
| `/rs-investigate` | 问题排查 — 系统性根因分析调试，先调查后修复 |
| `/rs-document-release` | 版本文档更新 — 发布后更新所有相关文档，确保文档与代码同步 |
| `/rs-codex` | AI第二意见 — 通过OpenAI Codex CLI获取AI的第二次代码审查意见 |
| `/rs-cso` | 安全审计 — 运行OWASP Top 10 + STRIDE安全扫描，发现安全漏洞 |
| `/rs-autoplan` | 自动规划 — 自动运行CEO→设计→工程评审流水线，一次性完成完整规划 |
| `/rs-careful` | 谨慎操作模式 — 执行危险命令（rm -rf、DROP TABLE、强制推送等）前发出警告 |
| `/rs-freeze` | 目录锁定 — 锁定指定目录，阻止任何文件编辑操作 |
| `/rs-guard` | 全面防护 — 同时激活careful（谨慎操作）和freeze（目录锁定）保护 |
| `/rs-unfreeze` | 解除锁定 — 移除freeze设置的目录编辑限制 |
| `/rs-gstack-upgrade` | 升级gstack — 将gstack更新到最新版本 |

### 如果技能不工作

如果 `/rs-*` 技能无法正常使用，请运行以下命令重新构建并注册：

```bash
cd .claude/skills/gstack && ./setup
```

> **前提条件**：需要安装 [Bun](https://bun.sh/) v1.0+
