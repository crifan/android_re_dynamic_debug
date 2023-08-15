# 初始化Frida开发环境

## 电脑端安装Frida

* 概述
  * Mac
    * 安装`frida`（和`frida-tools`）
      ```bash
      pip3 install frida
      pip3 install frida-tools
      ```
    * 或：已有frida，去升级到最新版
      ```bash
      pip install --upgrade frida
      pip install --upgrade frida-tools
      ```
* 详解
  * [安装Frida · 逆向调试利器：Frida](https://book.crifan.org/books/reverse_debug_frida/website/install_upgrade/install_frida.html)

此处已安装的（最新）Frida版本是：`16.1.3`

```bash
➜  ~ frida --version
16.1.3
```

## 安卓手机中安装frida-server

由于之前手动从下载frida-server并放到安卓手机Pixel3中，结果后续会报错`Failed to enumerate processes connection closed`，而无法使用

最后解决办法是：安装Magisk的插件：

[ViRb3/magisk-frida: 🔐 Run frida-server on boot with Magisk, always up-to-date](https://github.com/ViRb3/magisk-frida)

具体步骤：

下载到此处最新版的：

https://github.com/ViRb3/magisk-frida/releases/download/16.1.3-1/MagiskFrida-16.1.3-1.zip

得到：`MagiskFrida-16.1.3-1.zip`

（用adb push）传输到安卓手机中（的下载目录）

然后去：

`Magisk`->`模块`->`从本地安装`->找到并点击`MagiskFrida-16.1.3-1.zip`->开始自动安装->重启

（以后）每次重启安卓手机后：

* 可以看到Magisk中的插件：`MagiskFrida`
  * ![magisk_installed_magiskfrida](../assets/img/magisk_installed_magiskfrida.png)
* 都会自动运行frida-server
```bash
blueline:/ # ps -A | grep frida
root           4408   1321 10877092  3696 do_sys_poll         0 S frida-server
```

后续即可正常使用`Frida`：

## Mac中用确认frida工具可用

* 可用的
  * frida-ps
    ```bash
    frida-ps -U
    frida-ps -Uai
    ```
  * frida
    ```bash
    frida -U -F com.example.displaydemo
    ```
  * frida-trace
    ```bash
    frida-trace -U -F com.example.displaydemo -i open
    ```
* 不可用
  * frida-ls
    ```bash
    ➜  frida frida-ls -U
    Failed to retrieve listing: Error: Invalid mode: 0x0
        at I (agent.ts:274)
        at L (agent.ts:274)
        at ls (agent.ts:274)
        at apply (native)
        at <anonymous> (frida/runtime/message-dispatcher.js:13)
        at c (frida/runtime/message-dispatcher.js:23)
    ```
    * 暂时无法解决
