# quanttide

量潮第二大脑根仓的 Hermes worker——以 profile 分发的形式存放。

- 仓库：`quanttide`，量潮知识管理体系的根仓库
- 模型：小米 MiMo（provider `xiaomi`，`mimo-v2.6-flash`）
- 关系：`quanttide-founder`、`qtfounder` 分别是它的主体轴伞仓与下级平台

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
hermes profile install ./quanttide
hermes -p quanttide config env-path   # 把 XIAOMI_API_KEY 写进该 .env
hermes -p quanttide doctor
```

安装不加 `--alias`，不创建同名命令别名，统一用 `hermes -p quanttide`。

## 四轴与目录

| 轴 | 目录 | 语义 |
|:--|:--|:--|
| 范畴轴 | `categories/` | 我如何运行（工程标准、工作档案、平台资源） |
| 领域轴 | `domains/` | 我关心什么（数据工程、认知科学、叙事方法） |
| 主体轴 | `defaults/` | 我是谁（法人主体档案） |
| 适配轴 | `adapters/` | 我如何被接通（feishu / github / hermes / pi） |

平台资源一分为三：`quanttide-platform`（系统发布）、`quanttide-toolkit`（标准库）、`quanttide-laboratory`（实验室）。
