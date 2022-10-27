# Android逆向：动态调试

* 最新版本：`v0.9`
* 更新时间：`20221027`

## 简介

介绍Android逆向开发期间，如何动态调试apk的smali代码。此处以YouTube为例，介绍主要步骤：确保安卓已root、调试工具选择、反编译出smali代码、确保app可调试、调试方式启动app、Android Studio中导入smali代码、给smali加断点、配置Android Studio项目、确保adb可获取进程列表、Android Studio调试app进程；以及一些心得。

## 源码+浏览+下载

本书的各种源码、在线浏览地址、多种格式文件下载如下：

### HonKit源码

* [crifan/android_re_dynamic_debug: Android逆向：动态调试](https://github.com/crifan/android_re_dynamic_debug)

#### 如何使用此HonKit源码去生成发布为电子书

详见：[crifan/honkit_template: demo how to use crifan honkit template and demo](https://github.com/crifan/honkit_template)

### 在线浏览

* [Android逆向：动态调试 book.crifan.org](https://book.crifan.org/books/android_re_dynamic_debug/website)
* [Android逆向：动态调试 crifan.github.io](https://crifan.github.io/android_re_dynamic_debug/website)

### 离线下载阅读

* [Android逆向：动态调试 PDF](https://book.crifan.org/books/android_re_dynamic_debug/pdf/android_re_dynamic_debug.pdf)
* [Android逆向：动态调试 ePub](https://book.crifan.org/books/android_re_dynamic_debug/epub/android_re_dynamic_debug.epub)
* [Android逆向：动态调试 Mobi](https://book.crifan.org/books/android_re_dynamic_debug/mobi/android_re_dynamic_debug.mobi)

## 版权和用途说明

此电子书教程的全部内容，如无特别说明，均为本人原创。其中部分内容参考自网络，均已备注了出处。如有版权，请通过邮箱联系我 `admin 艾特 crifan.com`，我会尽快删除。谢谢合作。

各种技术类教程，仅作为学习和研究使用。请勿用于任何非法用途。如有非法用途，均与本人无关。

## 鸣谢

感谢我的老婆**陈雪**的包容理解和悉心照料，才使得我`crifan`有更多精力去专注技术专研和整理归纳出这些电子书和技术教程，特此鸣谢。

## 更多其他电子书

本人`crifan`还写了其他`100+`本电子书教程，感兴趣可移步至：

[crifan/crifan_ebook_readme: Crifan的电子书的使用说明](https://github.com/crifan/crifan_ebook_readme)