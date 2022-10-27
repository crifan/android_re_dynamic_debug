# AS调试app进程

Android Studio中调试设备端的app进程

* `Attach Debugger to Android Process`
  * ![as_attach_debugger_to_process](../assets/img/as_attach_debugger_to_process.png)

进入`Choose Process`弹框页面

正常会显示出安卓设备，且会列出设备中可调试的众多进程

选择对应的要调试（此处是`YouTube`）的进程：

![choose_debug_youtube_process](../assets/img/choose_debug_youtube_process.jpg)

即可顺利启动调试

并触发之前加的断点了：

![as_smali_breakpoint_hit](../assets/img/as_smali_breakpoint_hit.jpg)

![as_debug_smali_vars](../assets/img/as_debug_smali_vars.jpg)

TODO：

* 【基本解决】安卓AS调试apk的smali：新建和设置远程调试配置
* 【已解决】安卓AS调试apk的smali：初始化配置AS调试环境
* 【未解决】用Android Studio调试YouTube的smali代码：request请求发送相关的位置
* 【未解决】用root的安卓手机OPPO R11s去配合Android Studio调试YouTube的Smali代码
* 【已解决】安卓YouTube逆向：搭建安卓apk动态调试环境
