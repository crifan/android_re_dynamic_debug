# Android逆向动态调试概览

关于安卓逆向，之前已通过[安卓应用的安全和破解](https://book.crifan.org/books/android_app_security_crack/website/)进行了一定的介绍。

而安卓逆向期间，除了`静态分析`去研究`反编译的代码`外，想要了解安卓app的底层机制和逻辑，需要通过`动态调试`。

而目前安卓的动态调试的一些主要方法有：

* 用`Android Studio`去调试（`apk`反编译得到的）`smali`代码
* 用`LLDB`调试安卓app
* 用`Frida`调试安卓app
* 给安卓app编写`XPosed`插件，去调试hook逻辑
  * 详见：[Xposed插件开发 · 安卓逆向调试：XPosed框架](https://book.crifan.org/books/android_re_xposed_framework/website/dev_xposed_plugin/)

此教程主要就是介绍这方面的详细内容。
