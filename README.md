# ckc-telepush

Simple integration for CheckChan => Telepush. 适用于 Check酱 与 Telepush 的简单集成。

# 注意

- 请支持原作者。如果您使用国内推送，建议购买原作者提供的 Server酱 推送服务。
- 您需要可以访问 Telegram API。
- 您需要知道如何创建 Telegram 机器人，并知道如何获得其 token。
- 您需要知道如何在终端中运行命令，并具备 docker 相关的基础知识。

# 如何部署

- 下载本项目：`git clone https://github.com/JokerQyou/ckc-telepush.git`。以下操作都是在项目目录中进行的。
- 初始化子模块：``
- 编辑 `docker-compose.yml`，替换以下内容：
  - 两个数据卷的路径。您需要确保这两个目录存在。
  - BOT_TOKEN 替换为 Telegram 机器人的 token。
  - 变量 CKC_PASSWD 和 API_KEY 的值您可以视实际情况修改。
- 启动 telepush 服务：`docker-compose up -d telepush`。
- 与 Telegram 机器人对话，输入 `/start` 指令，获得 telepush 推送 token。
- 编辑 `docker-compose.yml` 文件，将 TELEPUSH_TOKEN 替换为刚刚获得的推送 token，并复制此时完整的 WEBHOOK 地址
- 启动所有服务：`docker-compose up -d`。
- 正常使用

# 如何使用
 
- 您可通过浏览器访问其 web 远程桌面端口，输入设置的密码，来确认容器中 Chrome 的运行状态。
- Check酱容器中分为两部分：一部分是 Check酱云端，另一部分是图形界面的 Chrome 浏览器（也就是通过 VNC 或 web 远程桌面访问的界面），两部分互不干扰。
  - 您可以在本机浏览器的 Check酱扩展中设置云端为容器所在机器的 IP 地址，从而将本机的任务同步到容器中的云端运行。
    - 这些任务在容器中图形界面的 Chrome 浏览器中不可见。
    - 任务使用到的 cookie 将从您本机的浏览器同步到容器内，这是 Check酱自身的机制。
  - 您也可以直接将容器中的 Chrome 浏览器当作本地浏览器一样使用，但您需要首先在此浏览器的 Check酱扩展中，设置 webhook 地址为您部署时最后复制的完整 WEBHOOK 地址

# 授权

注意：本项目仅是一个非常基本的对接 webhook 示例，不提供任何担保，也不涉及对 Check酱的修改。使用本项目造成的一切后果都由您自己承担。授权详情请见 LICENSE 文件。
