# AdminTerminal

![Minecraft](https://img.shields.io/badge/Minecraft-1.8.9--1.21.4-green)  
![Java](https://img.shields.io/badge/Java-21%2B-orange)

**AdminTerminal** 是一个 **（十分危险的）** 基于bukkit api Minecraft 服务器插件，允许有权限的玩家通过游戏内命令直接访问服务器操作系统的 Shell 并执行系统命令

---
## 警告： 本插件仅适用于特定场景（如无法通过 SSH 访问服务器时）的服务器维护。滥用此插件可能导致服务器安全风险，请谨慎使用！

---

## 在非必要情况下，请禁用此插件。使用此插件需自行承担风险，开发者不对因滥用插件导致的任何损失负责

---

## 功能概述

- **直接执行系统命令**：通过 `/at execute` 命令执行服务器操作系统的 Shell 命令
- **工作目录切换**：支持通过 `/at cd` 命令切换当前工作目录
- **进程管理**：通过 `/at killall` 命令终止所有由插件创建的进程
- **系统信息查看**：通过 `/at platform` 命令查看服务器的操作系统信息
- **警报系统**：支持开启/关闭命令执行警报，提醒管理员潜在的危险操作
- **权限控制**：仅允许具有特定权限的玩家使用插件功能

---


## 配置文件

插件首次启动时会生成配置文件 `config.yml`，您可以根据需要修改以下配置项：

- **use_alarm（警报系统）**：启用或禁用命令执行警报
- **force_english（强制英文环境）**：强制命令执行时的语言环境为英文
- **remove_ansi_escape_sequences （移除 ANSI 转义序列）**：清理命令输出中的 ANSI 转义字符

---

## 命令列表

### 主命令：`/at`

| 命令                  | 描述                                          |
|-----------------------|-----------------------------------------------|
| `/at help`            | 显示插件帮助信息                             |
| `/at platform`        | 显示服务器的操作系统信息                         |
| `/at cd <目录>`       | 切换当前工作目录                             |
| `/at execute <命令>`  | 执行系统命令（请谨慎使用）                        |
| `/at killall`         | 终止所有由插件创建的进程                         |
| `/at alarm`           | 开启或关闭命令执行警报                          |
| `/at reload`          | 重新加载插件配置文件                           |
| `/at license`         | 查看插件的许可证信息                           |

---

## 权限

| 权限          | 描述             |
|-------------|----------------|
| `at.use`    | 允许玩家使用 /at 命令  |
| `at.alarm`  | 使玩家能获取系统命令执行警报.|

---

## 注意事项

1. 插件允许执行系统命令，存在被恶意利用的风险，请将权限授予可信的人，推荐开启警报并定期检查日志。
2. 执行命令前请三思，务必要清楚自己在做什么，必要时备份服务器数据。
3. 请使用权限管理插件 (如[LuckPerms](https://luckperms.net/)) 而不是允许所有管理员运行系统命令。

---
## 使用示例

### 查看服务器操作系统信息
```bash
/at platform
```
输出示例：
```
[AT] 当前服务器操作系统：Linux (x86_64) - 5.15.0-83-generic
```

### 切换工作目录
```bash
/at cd /home/minecraft
```
输出示例：
```
[AT] 已切换目录到: /home/minecraft
```

### 执行系统命令
```bash
/at execute ls -l
```
输出示例：
```
[AT OUT] drwxr-xr-x 2 minecraft minecraft 4096 Oct 1 12:34 plugins
[AT OUT] drwxr-xr-x 2 minecraft minecraft 4096 Oct 1 12:34 worlds
```

### 终止所有进程
```bash
/at execute ping baidu.com
# ...此处省略输出
/at killall
```
输出示例：
```
[AT] 已终止所有由插件创建的进程（共 1 个）
```
## 闭源说明与致歉
- 我们理解许多用户希望能够查看和修改插件的源代码。由于一些安全和维护方面的考虑，`AdminTerminal` 插件目前为闭源项目。我们对无法提供源代码给广大用户感到抱歉。我们将持续关注社区的反馈，未来会考虑是否公开源码或提供更多功能

- 同时，我们郑重声明：**此插件不包含任何恶意代码**，所有功能均严格按照其预期用途设计，仅限于提供受控的系统命令执行能力。
- (说实话，你要是觉得20kb不到的东西能藏后门，你是这个👍。我要是混淆了哪怕一个方法，我是这个👎)

---

## 问题反馈

欢迎提交问题或提出建议！
- **GitHub Issues**：[提交问题](https://github.com/Ryorin1337/AdminTerminal-release/issues)

---

## 版权声明

- 请移步[LICENSE](https://github.com/Ryorin1337/AdminTerminal-release/blob/main/LICENSE)查看
---