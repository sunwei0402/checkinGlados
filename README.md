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

查找cookie

跳转至自己的仓库的Settings->Secrets and variables->Action

添加1个repository secret，命名为GLADOS_COOKIES，其值对应GLaDOS账号的cookie值中的有效部分（获取方式如下）

在GLaDOS的签到页面按F12

切换到Network页面下，刷新

<img width="633" height="386" alt="image" src="https://github.com/user-attachments/assets/555e68e4-0666-49fb-8cf3-68f1395ce153" />

点击第一个选项卡后在Request Headers下找到Cookie，右键复制cookie的值即可

参考格式：koa:sess=eyJ1c2xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxAwMH0=; koa:sess.sig=xJkOxxxxxxxxxxxxxxxtnM;


多账号请在 COOKIES 中 添加多个 cookies 中间使用 &连接即可。（例如： c1&c3&c3...）

也可手动通过 `workflow_dispatch` 运行。

## 代码说明

- `checkin.py`：签到脚本
- `logging_config.py`：日志配置
- `.github/workflows/gladosCheck.yml`：GitHub Actions 定时任务

## 声明

本项目不保证稳定运行与更新, 因GitHub相关规定可能会删库, 请注意备份
