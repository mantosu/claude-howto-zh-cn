# Claude Code 概念总览

这个文件用于把仓库里最容易混淆的几个核心概念放在一起解释。

## 1. Slash Commands（快捷命令）

用户主动输入的快捷命令，适合显式触发某个动作。

## 2. Memory（记忆）

长期自动加载的上下文，适合放项目规则和个人偏好。

## 3. Skills（技能）

可复用、可自动触发的能力，适合沉淀稳定工作流。

`v2.1.150` 这轮同步后，特别值得关注这些 bundled skills 变化：

- `/run`：启动当前项目，确认改动能真实运行
- `/verify`：构建、运行并观察应用，确认修复不是只停留在测试通过
- `/run-skill-generator`：为项目生成专属 run / verify skill
- `/code-review [effort]`：审查当前 diff 的正确性缺陷；它是 `/simplify` 在 `v2.1.146` 后的新名称，旧名不再作为 alias（别名）

## 4. Subagents（子代理）

用于复杂任务拆分和专业分工的子代理。

## 5. MCP（外部工具协议）

让 Claude 连接外部工具和实时数据的协议。

## 6. Hooks（钩子）

在特定事件上自动执行动作的机制。

这轮同步移除了上一版里关于 `Stop` / `SubagentStop` 可读取 `background_tasks`、`session_crons` 的说明；当前官方 hooks reference 没有列出这两个字段，写 hook 时不要依赖它们。

## 7. Plugins（插件）

把 commands、skills、MCP、hooks、subagents 打包成整套方案。

## 8. Checkpoints（检查点）

用于安全试错和回退。

## 9. CLI（命令行）

Claude Code 的核心使用入口，也是自动化、脚本化和 CI/CD 的关键接口。

`claude agents --json` 可以把 Agent View 列表输出为机器可读 JSON，适合接状态栏、脚本巡检或自定义 session picker。

在 `claude agents` 视图里，`Ctrl+T` 可以固定后台 session。已固定的 session 空闲时会被优先保留，升级 Claude Code 时也会在原位重启，只有内存压力较大时才会在未固定 session 之后被清理。

`/usage` 的成本页现在会按 skills、subagents、plugins、MCP server 等类别拆分，排查“钱花在哪里”会更直观。
