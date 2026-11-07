# workers

Hermes Worker 配置：一个项目仓库一份，文件名取仓库名。

Worker 是 Hermes 里绑定到一个项目仓库的 profile（worker lane）；本目录的 YAML 是它的声明式清单，字段对齐 Hermes 既有契约：

| 字段 | 对应 | 用途 |
|:--|:--|:--|
| `name` `version` `description` `hermes_requires` `author` `license` `env_requires` | `distribution.yaml` | profile 分发清单；`description` 供 kanban 编排按角色路由 |
| `project` | `hermes project` | 命名多仓工作区：slug、主目录、绑定 board |
| `workspace` | kanban workspace | `dir` 常驻（完成后保留）、`worktree`、`scratch` |
| `config` | `~/.hermes/profiles/<name>/config.yaml` | 运行时配置子集 |
| `conventions` | 各仓 `AGENTS.md` / `CONTRIBUTING` | 提交、验证、边界 |

| 文件 | 仓库 | 角色 |
|:--|:--|:--|
| `quanttide-founder.yml` | [quanttide-founder](https://github.com/quanttide/quanttide-founder) | 上级文件夹（子模块伞仓） |
| `qtfounder.yml` | [qtfounder](https://github.com/quanttide/qtfounder) | 下级平台（`apps/qtfounder`） |

装载顺序：`hermes profile create <name>` → 写 `config.yaml` → `hermes project create`（按 `project`）→ `hermes kanban boards create` 与 `bind-board`。
