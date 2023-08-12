# Unidbg

* Unidbg
  * Github
    * https://github.com/zhkl0228/unidbg
      * Allows you to emulate an Android native library, and an experimental iOS emulation
  * 概述
    * unidbg是unicorn的一个实现，它可以让你在电脑上跑arm的可执行文件或共享库文件
    * unidbg是一个基于`unicorn`的逆向工具，可以在PC端直接调用Android（的apk中）和iOS（的ipa中）的`so`动态库文件（中的native函数方法）
  * 背景
    * 目前很多 App 的加密签名算法都在so文件中，强行逆向so的话可能会消耗大量时间和资源
  * 规避方式
    * 用 xposed 采用 hook 的方法从程序计算签名
      * 缺点：需要模拟器或者真机运行这个应用，使用效率不高
    * 用过 jtype 启动JVM，然后通过 native 对so文件进行调用
      * 缺点：因为每次都需要启动JVM，所以效率也不高
    * unidbg
      * 原理：通过在 app 中找到对应的 JNI 接口，然后用 unicorn 引擎直接调用 so 文件
      * 优点：不需要运行 app，也无需逆向 so 文件，所以效率相对要高不少
