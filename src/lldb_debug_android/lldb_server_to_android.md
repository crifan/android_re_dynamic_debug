# Mac中：把lldb-server下载到安卓手机中

从Mac下载lldb-server到此处安卓手机Pixel5中：

```bash
adb push lldb-3.1.4508709-linux-x86_64/android/arm64-v8a/lldb-server /data/local/tmp
```

注：

* 此处安卓手机正常默认情况下，已有路径：`/data/local/tmp`
  * 专门供开发相关用途使用
* adb shell中可以确认
  ```bash
  blueline:/data/local/tmp/ # ls -lh
  total 4.0M
  -rwxrwxrwx 1 shell shell 8.0M 2017-12-18 21:03 lldb-server
  ```
  * 此处确保有`可执行权限`=`x`
    * 如果没有，则要去加上
      ```bash
      chmod +x lldb-server
      ```
