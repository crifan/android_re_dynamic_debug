# 心得

TODO：

* smali断点不生效
  * 【未解决】再次出现AS调试Google Pixel3中的YouTube的问题：Smali断点不生效
  * 【记录】Android 11的Google Pixel3中确认adb shell是否工作正常
  * 【未解决】尝试解决Android Studio中smali断点不生效：调试相关设置
  * 【未解决】尝试解决Android Studio中smali断点不生效：smali文件类型File type
  * 【未解决】尝试解决Android Studio中smali断点不生效：卸载重装smalidea插件
  * 【未解决】尝试解决Android Studio中smali断点不生效：故意打开ADM的DDMS有冲突多试试
  * 【未解决】尝试解决Android Studio中smali断点不生效：Android Studio中adb相关设置
  * 【未解决】尝试解决Android Studio中smali断点不生效：用DDMS和monitor配合试试
  * 【未解决】尝试解决Android Studio中smali断点不生效：USB数据线和端口相关
  * 【未解决】Android Studio调试Smali：通过Remote JVM Debug的attach to remote VM的调试按钮去调试
  * 【已解决】Android Device Monitor的DDMS中看不到app包名进程的名称都是问号
  * 【未解决】尝试解决Android Studio中smali断点不生效：JDWP进程相关
  * 【未解决】尝试解决Android Studio中smali断点不生效：Smali插件相关

---

安卓逆向期间，折腾Android Studio去调试smali代码，其实更麻烦的不在于搞懂本身的流程，而在于：

找到一个好用的调试设备：已root好的，可以顺利调试的安卓手机

因为期间遇到Google Pixel 3的adb异常，导致adb shell各种命令无法正常运行，包括adb的ps无法正常获取进程列表

从而导致后续调试时AS中看不到进程，折腾了很长时间，才确认，就是adb方面的问题导致的。

解决了该问题了，AS中能attach到进程，后续就顺利多了。

并且另外Google Pixel 3本身不稳定，导致虽然开始能调试，但是后来出现开发者选项崩溃的问题，无法进入设置了。对于正常安卓逆向开发，也有很大影响。

总之：还是要找个靠谱的root后的安卓手机，才能保证后续安卓逆向的顺利。

## 如何调试逻辑

TODO：

* 【记录】用Android Studio调试YouTube的smali代码：smali/anwu.smali
* 【记录】用Android Studio调试YouTube的smali代码：smali_classes2/azfv.smali
* 【记录】用Android Studio调试YouTube的smali代码：smali/anuh.smali
* 【记录】用Android Studio调试YouTube的smali代码：smali_classes2的WatchWhileActivity.smali
* 
* 【记录】用AS调试YouTube的Smali代码：调试相关业务逻辑
* 【未解决】给AS调试YouTube的Smali代码：加url过滤
* 【已解决】Xposed如何hook混淆后的安卓应用中的类名和函数名

---
