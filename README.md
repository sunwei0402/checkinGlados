# Glados自动签到

## 使用方式：

### 使用本仓库

1. 复制该仓库到自己的 GitHub 账号中，或直接使用当前仓库。
2. 在仓库 `Settings` -> `Secrets and variables` -> `Actions` 中添加 secret。
3. 配置 `GLADOS_COOKIES`，内容为 GLaDOS 账号的 cookie 值有效部分。
4. 可选配置 `GLADOS_EXCHANGE_PLAN`、`PUSHPLUS_TOKEN`、`PUSHDEER_SENDKEY` 等。

### 配置 secret

- `GLADOS_COOKIES`：cookie值，多个账号用 `&` 连接。
- `GLADOS_EXCHANGE_PLAN`：可选值 `plan100` / `plan200` / `plan500`。
- `PUSHPLUS_TOKEN`：PushPlus 的 token。
- `PUSHDEER_SENDKEY`：PushDeer 的 key。
- `GLADOS_VERBOSE`：`true` 或 `false`，控制是否输出详细日志。

## 运行方式

工作流会在 `github actions` 中按小时执行：
- cron: `0 * * * *`
- timezone: `Asia/Shanghai`

也可手动通过 `workflow_dispatch` 运行。

## 代码说明

- `checkin.py`：签到脚本
- `logging_config.py`：日志配置
- `.github/workflows/gladosCheck.yml`：GitHub Actions 定时任务

## 声明

本项目不保证稳定运行与更新, 因GitHub相关规定可能会删库, 请注意备份
