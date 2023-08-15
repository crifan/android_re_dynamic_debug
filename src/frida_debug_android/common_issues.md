# 常见问题

## Failed to spawn timeout was reached

* 现象
  ```bash
  ➜  frida frida-trace -U -f com.example.displaydemo -i JIN_OnLoad -i RegisterNatives
  Spawning `com.example.displaydemo`...

  Failed to spawn: timeout was reached
  ```
* 原因：偶发的bug
* 解决办法
  * 多试试几次
  * 重启安卓手机
  * 杀掉frida-server后，手动重启几次
    * 注：此处由于之前是Magisk安装的插件MagiskFrida，好像是：
      * 发现frida-server被杀掉后，会自动重启frida-server
