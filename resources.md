# 资源总览

仓库里的 `resources/` 目录主要存放：

- logo
- icon
- favicon
- 设计系统说明
- 快速使用说明
- 供文档引用的配套资源索引

如果你要把这个中文 fork 发布成独立仓库，也可以在保留来源说明的前提下替换这些资源。

## 2026 年 6 月需要关注的新能力

这轮同步后，中文读者如果只看资源索引，至少要知道这些新入口：

| 能力 | 说明 | 入口 |
|------|------|------|
| `/usage-credits` | 配置额外用量额度；`/extra-usage` 仍可作为 alias（别名） | [Slash Commands](01-slash-commands/) |
| `/run` / `/verify` | bundled skills，用于启动项目并确认改动真实可用 | [Skills Guide](03-skills/) |
| `/run-skill-generator` | 为项目生成专属 run / verify skill | [Skills Guide](03-skills/) |
| `claude agents --json` | 输出机器可读的 Agent View 列表 | [CLI Guide](10-cli/) |
| `/code-review [effort]` | 内置正确性缺陷审查命令，可传入 `/code-review high` | [Skills Guide](03-skills/) |
| `/simplify` | 清理型审查命令，关注复用、简化、效率和抽象层级 | [Skills Guide](03-skills/) |
| `/reload-skills` | 重新扫描 skill 目录，不需要重启当前 session | [Skills Guide](03-skills/) |
| `/workflows` | 查看 dynamic workflows 的运行记录 | [Advanced Features](09-advanced-features/) |
| `claude plugin init <name>` | 在 `.claude/skills` 中脚手架本地 plugin；该目录下的 plugin 会自动加载 | [Plugins Guide](07-plugins/) |
| `CLAUDE_CODE_ENABLE_AUTO_MODE=1` | 在 Bedrock / Vertex / Foundry 上对 Opus 4.7 / 4.8 显式启用 Auto Mode | [CLI Guide](10-cli/) |
| `EnterWorktree` | 在同一 session 中切换 Claude 管理的 worktree | [Advanced Features](09-advanced-features/) |
| `claude agents` 里的 `Ctrl+T` | 固定后台 session，空闲时优先保留 | [CLI Guide](10-cli/) |
| `allowAllClaudeAiMcps` | 组织级允许加载 claude.ai 云端 MCP connectors 的托管设置 | [MCP Guide](05-mcp/) |

这些名称都是可执行标识或协议字段，不要翻译成中文 key。
