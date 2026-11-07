# quanttide-founder

量潮创始人第二大脑伞仓的 Hermes worker——以 profile 分发的形式存放。

- 仓库：`quanttide-founder`，位于第二大脑根仓 `quanttide` 的 `defaults/quanttide-founder`
- 模型：小米 MiMo（provider `xiaomi`，`mimo-v2.6-flash`）
- 工作入口：`qtfounder` CLI

## 结构

| 文件 | 说明 |
|:--|:--|
| `distribution.yaml` | profile 分发清单：名称、版本、密钥要求 |
| `config.yaml` | 运行时配置：模型、审批、轮次 |
| `SOUL.md` | 身份与工作口径 |
| `README.md` | 本文件 |

## 安装

在本仓 `data/profile` 下执行：

```bash
hermes profile install ./quanttide-founder
hermes -p quanttide-founder config env-path   # 把 XIAOMI_API_KEY 写进该 .env
hermes -p quanttide-founder doctor
```

安装不加 `--alias`，不创建同名命令别名，统一用 `hermes -p quanttide-founder`。

## 维护对象

| 目录 | 内容 |
|:--|:--|
| `apps/` | 应用子模块（qtfounder） |
| `assets/` | 创作资产（blog / fiction） |
| `data/` | 陈述性记忆（archive / context / journal / profile / roadmap 等） |
| `docs/` | 程序性记忆（bylaw / handbook / specification / tutorial 等） |
| `examples/` | 实验室与一次性脚本 |
| `packages/` | 包子模块 |

结构类变更是破坏性变更：升 major 并在 CHANGELOG 写明迁移映射。
