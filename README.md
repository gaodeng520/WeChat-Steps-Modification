# WeChat-Steps-Modification

这个项目旨在帮助你定期运行Python脚本，以便在需要时修改特定账号的步数。脚本运行失败时，会通过Telegram向你发送通知，以便你可以及时采取行动。以下是关于如何使用和配置该项目的详细说明。

- 群聊: [HeroCore](https://t.me/HeroCore)
- 频道: [HeroMsg](https://t.me/HeroMsg)

<img width="1045" alt="image" src="https://github.com/user-attachments/assets/29e51606-ba29-4f75-b398-c16550127243">


## 使用方法

### 1. Fork 本仓库

首先，点击本仓库右上角的 "Fork" 按钮，将项目复制到你自己的GitHub账户下。

### 2. 配置 Secrets

在你的GitHub仓库中，点击上方菜单中的 "Settings"，然后选择 "Secrets" 选项卡。你需要添加以下几个Secrets以便项目正常工作：

- `TELEGRAM_API_TOKEN`: 你的Telegram机器人API Token。你可以从 [BotFather](https://core.telegram.org/bots#botfather) 获取它。**（选填）**

- `TELEGRAM_CHAT_ID`: 你希望接收通知的Telegram聊天ID。你可以从 [userinfobot](https://core.telegram.org/bots#usernames-and-telegram-ids) 获取它。**（选填）**

- `ACCOUNTS_AND_PASSWORDS`: 你想要修改步数的账号和密码对，以分号分隔。每个对之间使用逗号分隔。例如，`username1,password1;username2,password2`。请确保保密这个Secrets以保护你的账号信息。**（必填）**

### 3. 自定义脚本

在本仓库中，你可以找到一个名为 `steps.py` 的Python脚本文件。这个脚本用于修改账号的步数。你可以根据自己的需求修改这个脚本，例如更改最小和最大步数，修改API请求的URL等。

### 4. 自定义运行时间

默认情况下，脚本会在UTC时间的上午10点6分运行（每天一次）。如果你想要更改运行时间，可以编辑 `.github/workflows/main.yml` 文件中的 `schedule` 部分。按照 [Cron表达式](https://docs.github.com/en/actions/learn-github-actions/workflow-syntax-for-github-actions#onschedule) 的格式来配置。

### 5. 自定义最小和最大步数

在脚本的 `__main__` 部分，你可以找到 `min_steps` 和 `max_steps` 变量。你可以根据需要更改这些值，以定义修改步数的范围。


## 注意事项

- **Telegram通知**：脚本会在运行失败时向你的Telegram账号发送通知。如果脚本成功运行，不会发送通知。

- **默认设置**：脚本默认使用了最小步数为50000，最大步数为80000的设置，以及在UTC 时间上午10点6分运行的计划。你可以根据需要进行自定义。

- **账号信息**：请务必保护好你的账号信息，特别是 `ACCOUNTS_AND_PASSWORDS` Secret。不要将这些信息公开。

- **定期检查**：定期检查项目是否正常运行，以确保你的账号步数得到及时更新。


## 免责声明

欢迎使用微信步数修改器项目。在使用此项目前，请务必阅读并理解以下免责声明。通过使用本项目，即表示您同意以下条款：

1. **服务性质**

   本项目旨在演示如何与Telegram API集成以及对微信步数进行模拟修改。项目仅供学习和研究之用，不提供任何形式的保证或承诺。使用者需自行承担风险。

2. **法律合规**

   请在使用本项目时严格遵守所在国家/地区的法律法规。未经授权修改微信步数可能违反用户协议，可能导致账号被封禁或其他法律责任。使用者应自行承担因违反法律法规而造成的后果。

3. **责任限制**

   本项目的开发者和贡献者不对任何直接、间接或特殊损失负责，包括但不限于利润损失、数据丢失或因使用本项目造成的任何损害。用户对使用本项目所产生的风险自行承担。

4. **数据隐私**

   本项目不会收集、存储或传输任何敏感用户信息。对于使用者可能在与Telegram API交互过程中泄露的信息，本项目开发者不承担责任。

5. **变更和终止**

   本项目开发者保留随时变更、暂停或终止项目的权利，无需提前通知。对于因此造成的任何损失，开发者不承担责任。

6. **接受条款**

   通过使用本项目，即表示您已阅读、理解并接受本免责声明。如果您不同意本声明中的任何条款，请勿使用本项目。


## 许可证

本项目采用 MIT 许可证。详细信息请参阅 [LICENSE](LICENSE) 文件。

通过遵循以上步骤，你可以轻松使用这个项目来定期修改特定账号的步数并接收通知。如果你有任何问题或需要进一步的帮助，欢迎提出问题或提出建议。
