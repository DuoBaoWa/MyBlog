如果你能在端口 443 上通过 SSH 连接到 `git@ssh.github.com`，则可覆盖你的 SSH 设置来强制与 GitHub.com 的任何连接均通过该服务器和端口运行。

要在 SSH 配置文件中设置此行为，请在 `~/.ssh/config` 编辑该文件，并添加以下部分：

```text
Host github.com
    Hostname ssh.github.com
    Port 443
    User git
```

你可以通过再次连接到 GitHub.com 来测试这是否有效：

```bash
$ ssh -T git@github.com
# Hi USERNAME! You've successfully authenticated, but GitHub does not
# provide shell access.
```