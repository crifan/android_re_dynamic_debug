# Mac中：用lldb客户端去连接lldb-server

* 进入=启动=运行 lldb
  ```bash
  lldb
  ```
* 设置要连接的类型是：远端的安卓手机
  ```bash
  platform select remote-android
  ```
  * 输出举例
    ```bash
    (lldb) platform select remote-android
      Platform: remote-android
    Connected: no
    ```
* 连接安卓（中的lldb-server）
  ```bash
  platform connect unix-abstract-connect:///data/local/tmp/dev/lldb_debug.sock
  ```
  * 输出举例
    ```bash
    (lldb) platform connect unix-abstract-connect:///data/local/tmp/dev/lldb_debug.sock
      Platform: remote-android
        Triple: aarch64-unknown-linux-android
    OS Version: 30 (4.9.248-gc4689af91bc5-ab7425221)
      Hostname: localhost
    Connected: yes
    WorkingDir: /data/local/tmp/dev/lldb
        Kernel: #0 SMP PREEMPT Fri Jun 4 06:01:28 UTC 2021
    ```

注：
* 可以用`platform list`查看全部的支持的类型有哪些
  ```bash
  (lldb) platform list
  Available platforms:
  host: Local Mac OS X user platform plug-in.
  remote-linux: Remote Linux user platform plug-in.
  remote-android: Remote Android user platform plug-in.
  remote-freebsd: Remote FreeBSD user platform plug-in.
  remote-gdb-server: A platform that uses the GDB remote protocol as the communication transport.
  darwin: Darwin platform plug-in.
  remote-ios: Remote iOS platform plug-in.
  remote-macosx: Remote Mac OS X user platform plug-in.
  ios-simulator: iPhone simulator platform plug-in.
  tvos-simulator: tvOS simulator platform plug-in.
  watchos-simulator: Apple Watch simulator platform plug-in.
  darwin-kernel: Darwin Kernel platform plug-in.
  remote-tvos: Remote Apple TV platform plug-in.
  remote-watchos: Remote Apple Watch platform plug-in.
  remote-bridgeos: Remote BridgeOS platform plug-in.
  host: Local Mac OS X user platform plug-in.
  remote-netbsd: Remote NetBSD user platform plug-in.
  remote-openbsd: Remote OpenBSD user platform plug-in.
  qemu-user: Platform for debugging binaries under user mode qemu
  remote-windows: Remote Windows user platform plug-in.
  ```
* 连接前后，都可以去查看和验证实际状态（是否是希望的已连接）
  ```bash
  platform status
  ```
  * 举例
    * 连接前
      ```bash
      (lldb) platform status
        Platform: remote-android
      Connected: no
      ```
    * 连接后
      ```bash
      (lldb) platform status
        Platform: remote-android
          Triple: aarch64-unknown-linux-android
      OS Version: 30 (4.9.248-gc4689af91bc5-ab7425221)
        Hostname: localhost
      Connected: yes
      WorkingDir: /data/local/tmp/dev/lldb
          Kernel: #0 SMP PREEMPT Fri Jun 4 06:01:28 UTC 2021
      ```
