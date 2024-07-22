# 初始化Frida开发环境

* 概述
  * 电脑端安装`frida`（和`frida-tools`），移动端安装`frida`（的**server**）
    * Mac中逆向iOS
      * Mac：安装`frida`（`pip3 install frida`）和安装`frida-tools`（`pip3 install frida-tools`）
      * iOS（iPhone）：包管理器（`Sileo`/`Cydia`）中（通过软件源：`https://build.frida.re`）安装`frida`的插件
    * Mac中逆向Android
      * Mac：安装`frida`（`pip3 install frida`）和安装`frida-tools`（`pip3 install frida-tools`）
      * Android：`Magisk`中安装[MagiskFrida](https://github.com/ViRb3/magisk-frida)插件
        * 注：Frida官网的Android版`frida-server`有问题，所以换装第三方可用版本
* 详见
  * [安装和升级 · 逆向调试利器：Frida (crifan.org)](https://book.crifan.org/books/reverse_debug_frida/website/install_upgrade/)
