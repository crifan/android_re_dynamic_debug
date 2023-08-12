# 安卓手机中：运行lldb-server

```bash
./lldb-server platform --server --listen unix-abstract:///data/local/tmp/dev/lldb_debug.sock &
```

注：
* 此处可以通过ps查看到进程的确在运行
  ```bash
  blueline:/data/local/tmp/dev/lldb # ps -A | grep lldb
  root          27860   7054 10779208  4628 __skb_wait_for_more_packets 0 S lldb-server
  ```
* 参数含义
  * 概述
    * COMMANDS
      * `v[ersion]`
        * Prints lldb-server version and exits
      * `g[dbserver]`
        * Runs the server using the gdb-remote protocol. LLDB can afterwards connect to the server using gdb-remote command
      * `p[latform]`
        * Runs the platform server. LLDB can afterwards connect to the server using platform select, followed by platform connect
    * PLATFORM COMMAND
      * 语法
        ```bash
        lldb-server p[latform] [options] –server –listen [[host]:port]
        ```
      * CONNECTION
        * `--server`
          * Run in server mode, handling multiple connections. If this is not specified, lldb-server will accept only one connection and exit when it is finished
        * `--listen <host>:<port>`
          * Hostname and port to listen on. Obligatory. If port is zero, a random port will be used
        * `--socket-file <path>`
          * `Write the listening socket port number to the specified file`
  * 详解
    * [lldb-server – Server for LLDB Debugging Sessions — The LLDB Debugger](https://lldb.llvm.org/man/lldb-server.html)
