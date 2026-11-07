# qtfounder

量潮创始人平台的 Hermes worker——以 profile 分发的形式存放。

- 仓库：[quanttide/qtfounder](https://github.com/quanttide/qtfounder)，位于父仓 `quanttide-founder` 的 `apps/qtfounder`
- 模型：小米 MiMo（provider `xiaomi`，`mimo-v2.6-flash`）

## 结构

| 文件 | 说明 |
|:--|:--|
| `distribution.yaml` | profile 分发清单：名称、版本、密钥要求 |
| `config.yaml` | 运行时配置：模型、审批、轮次 |
| `SOUL.md` | 身份与工作口径 |
| `README.md` | 本文件 |

## 安装

```bash
hermes profile install ~/repos/quanttide/adapters/quanttide-hermes/data/profile/qtfounder
hermes -p qtfounder config env-path            # 把 XIAOMI_API_KEY 写进该 .env
hermes -p qtfounder doctor
```

安装不会创建 `qtfounder` 命令别名（`--alias` 才会），避免顶掉同名的 `qtfounder` CLI；统一用 `hermes -p qtfounder`。

## 模块与验证

| 模块 | 技术 | 验证 |
|:--|:--|:--|
| `src/cli` | Rust | `cargo build && cargo test` |
| `src/studio` | Flutter | `flutter analyze && flutter test` |
| `src/site` | React + Vite | `npm run build` |
| `src/lite` | Taro + React + TS | `npm run build` |
| `src/provider` | Go（待删除） | `go build ./... && go vet ./... && go test ./...` |
