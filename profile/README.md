# HK 1121

日常工作中攒下来的 AI 助手能力：让助手看得懂工作系统里的数据，也能把重复的 SIT 操作按固定流程跑一遍。

## 组成

| 仓库 | 说明 |
| --- | --- |
| [`ado-work-item-skill`](https://github.com/HK-1121/ado-work-item-skill) | 在 Codex / Claude Code 里读 Azure DevOps 工作项：本体、评论、关联链接、附件截图四块一起看，再给结论和证据。取数走官方 `@azure-devops/mcp`，PAT 各人一份 |
| [`analyze-azure-devops-bug-skill`](https://github.com/HK-1121/analyze-azure-devops-bug-skill) | 对着一个已经打开的 ADO Bug 做根因分析：描述与复现步骤、评论与内嵌截图、完整历史、父子与提交/PR/build 链接、附件、本地源码与部署身份一起核，产出一段可以直接贴进 DevOps 的结论（不会自动发出去） |
| [`eccms-sit-flows`](https://github.com/HK-1121/eccms-sit-flows) | ECCMS SIT 里可重复执行的流程脚本（Playwright）：登录与选 post、CP01 / CP10 建案与查询、Enquiry 23 个页面查询。默认有头可视化，一条流程一个文件，配置集中在一处 |

## 约定

- 各仓库独立维护，装哪个、怎么装、兼容什么版本，看各仓库自己的 README。
- 取数和判断分开：数据从官方 MCP 或页面本身拿，skill 只固化「看什么、怎么看、怎么下结论」。
- 默认只读。改状态、加评论、建链接这类写操作，都要先经人工确认。
- 流程脚本的账号、密码、环境地址和选择器集中在 `config.json`，不入库；仓库里只放 `config.example.json`。

这些是个人整理的工具，不是任何系统的官方项目。
