# Android逆向：动态调试

* 最新版本：`v1.5.1`
* 更新时间：`20240729`

## 简介

介绍Android逆向开发期间，如何动态调试安卓程序。包括用AndroidStudio调试apk的smali代码、用LLDB调试安卓程序、用Frida调试安卓程序、编写Xposed模块去调试安卓程序。对于AndroidStudio调试安卓Smali代码，此处以YouTube为例，介绍主要步骤：确保安卓已root、调试工具选择、反编译出smali代码、确保app可调试、调试方式启动app、Android Studio中导入smali代码、给smali加断点、配置Android Studio项目、确保adb可获取进程列表、Android Studio调试app进程；对于LLDB调试安卓，包括下载安卓版lldb-server到电脑、把lldb-server传输下载到安卓手机中、电脑中运行lldb、用lldb连接安卓手机中的lldb-server、最后是开始用lldb调试安卓app进程。对于Firda调试安卓，包括初始化Frida调试环境、Frida调试安卓app，以及贴出几个实例包括LiftFileManager、DisplayDemo等。以及Frida方面的常见的问题和心得。然后是动态调试方面的一些常见问题和心得。以及其他一些分析调试工具，包括Unidbg、AndBug、redexer、Fino等；以及用于辅助调试的adb，比如用adb查看内存映射；最后加上心得和实例和附录的参考资料。

## 源码+浏览+下载

本书的各种源码、在线浏览地址、多种格式文件下载如下：

### HonKit源码

* [crifan/android_re_dynamic_debug: Android逆向：动态调试](https://github.com/crifan/android_re_dynamic_debug)

#### 如何使用此HonKit源码去生成发布为电子书

详见：[crifan/honkit_template: demo how to use crifan honkit template and demo](https://github.com/crifan/honkit_template)

### 在线浏览

* [Android逆向：动态调试 book.crifan.org](https://book.crifan.org/books/android_re_dynamic_debug/website/)
* [Android逆向：动态调试 crifan.github.io](https://crifan.github.io/android_re_dynamic_debug/website/)

### 离线下载阅读

* [Android逆向：动态调试 PDF](https://book.crifan.org/books/android_re_dynamic_debug/pdf/android_re_dynamic_debug.pdf)
* [Android逆向：动态调试 ePub](https://book.crifan.org/books/android_re_dynamic_debug/epub/android_re_dynamic_debug.epub)
* [Android逆向：动态调试 Mobi](https://book.crifan.org/books/android_re_dynamic_debug/mobi/android_re_dynamic_debug.mobi)

## 版权和用途说明

此电子书教程的全部内容，如无特别说明，均为本人原创。其中部分内容参考自网络，均已备注了出处。如发现有侵权，请通过邮箱联系我 `admin 艾特 crifan.com`，我会尽快删除。谢谢合作。

各种技术类教程，仅作为学习和研究使用。请勿用于任何非法用途。如有非法用途，均与本人无关。

## 鸣谢

感谢我的老婆**陈雪**的包容理解和悉心照料，才使得我`crifan`有更多精力去专注技术专研和整理归纳出这些电子书和技术教程，特此鸣谢。

## 其他

### 作者的其他电子书

本人`crifan`还写了其他`150+`本电子书教程，感兴趣可移步至：

[crifan/crifan_ebook_readme: Crifan的电子书的使用说明](https://github.com/crifan/crifan_ebook_readme)

### 关于作者

关于作者更多介绍，详见：

[关于CrifanLi李茂 – 在路上](https://www.crifan.org/about/)
