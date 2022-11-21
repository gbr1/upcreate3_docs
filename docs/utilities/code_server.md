# Code server

You can use vscode directly on your robot without installing anything on your remote.

```bash
curl -fsSL https://code-server.dev/install.sh | sh
```

Then you need to edit di config file at `~/.config/code-server/config.yaml` to setup access:

```yaml
bind-addr: 0.0.0.0:8081
auth: password
password: <your password>
cert: false
```

This allows to access your robot from another device connected on the same local netowork (computer, smartphone, tablet, etc) via:

`<your ip>:8081`

Learn more at: [https://coder.com/docs/code-server/latest](https://coder.com/docs/code-server/latest)

You can also install the ROS pluging in vscode, using the vsix file available on the Microsoft Website: [https://marketplace.visualstudio.com/items?itemName=ms-iot.vscode-ros](https://marketplace.visualstudio.com/items?itemName=ms-iot.vscode-ros)

>Copyrights © 2022 G. Bruno gbr1.github.io under MIT License