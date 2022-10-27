# adb可获取进程列表

确保adb可以获取到安卓设备的进程列表

确保：

```bash
adb shell ps
```

可以获取到：

* 安卓设备中的进程的列表

目的：防止后续无法看到进程，无法调试

比如，我此处的遇到的特殊情况：

`adb shell`的子命令，包括`ps`，无法直接运行（要么报错，要么没权限，要么没返回结果）

则意味着后续`Android Studio`中`Attach Debugger to Android Process`的`Choose Process`中，无法看到设备的进程列表，就无法继续调试。

TODO：

* 【已解决】Android Studio和DDMS中看不到安卓设备中的所有进程
* 【已解决】Mac中运行adb shell无需su超级用户即可正常运行输出结果
* 【未解决】Android Studio调试报错：Unable to open debugger port localhost handshake failed connection prematurally closed
* 【未解决】Android Studio中smali断点不生效无法触发断点
