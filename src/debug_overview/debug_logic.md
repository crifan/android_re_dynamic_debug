# 安卓逆向动态调试的总体思路


TODO：

【未解决】Android的YouTube逆向：研究request请求api和protobuf相关部分代码

---

此处介绍安卓逆向的总体思路：

* 找到要hook的点 = 找到核心代码的入口点
  * 对于Android来说，往往是`java`中相关的`基础的类`，`内置的类`
  * 比如
    * `网络请求`类
    * `url`相关的类
      * 比如
        * `new URL`
    * `字符串`相关的类
      * 可能会用到URL拼接，其内部涉及到`字符串`的拼接
      * 比如
        * `append`
        * `getBytes`
        * `String builder`
* 再去动态调试逻辑，hook代码逻辑
  * 相关工具：`Xposed`、`frida`、`LLDB`、`AS`等
* 期间配合抓包
  * 先要`抓包`找相关`url`
    * 后续才知道要过滤哪些url

## 找到要hook的点

其中关于找到要hook的点，值得就是：

* java层：找到对应的，实现你要的功能的类
  * 其中切入点，可以从Java基础的类去入手
    * 详见下面的解释
* Native层=C/C++代码=`so`库文件：找到C/C++的函数

### Java基础的内置的类

#### URL

```java
URL myURL = new URL("http://example.com/pages/");
URL page1URL = new URL(myURL, "page1.html");
URL page2URL = new URL(myURL, "page2.html");
```

或：

```java
new URL("http", "example.com", "/pages/page1.html");
```

或：

```java
//URLDemo.java
import java.net.*;

public class URLDemo {

  public static void main(String[] args) {
    try {
      URL url = new URL("http://www.javatpoint.com/java-tutorial");

      System.out.println("Protocol: " + url.getProtocol());
      System.out.println("Host Name: " + url.getHost());
      System.out.println("Port Number: " + url.getPort());
      System.out.println("File Name: " + url.getFile());
    } catch (Exception e) {
      System.out.println(e);
    }
  }
}
```

或：

```java
import java.net.*;

URL url = new URL("/a-guide-to-java-sockets");

URL home = new URL("http://baeldung.com");
URL url = new URL(home, "a-guide-to-java-sockets");
```

或：

```java
@Test
public void givenBaseUrl_whenCreatesRelativeUrl_thenCorrect() {
    URL baseUrl = new URL("http://baeldung.com");
    URL relativeUrl = new URL(baseUrl, "a-guide-to-java-sockets");
    
    assertEquals("http://baeldung.com/a-guide-to-java-sockets", 
      relativeUrl.toString());
}
```

或：

```java
URL url = new URL(yourUrl, "/api/v1/status.xml");
```

或：

```java
URL domain = new URL("http://example.com");
URL url = new URL(domain + "/files/resource.xml");
```



# hook插件与开发

TODO：

* 把如何用XPosed写Android的hook插件的帖子整理过来
* 
* 【已解决】Android 11的Magisk中安装EdXposed 0.5.2.2结果失败：请先从Magisk Manager中安装Riru Installation failed
* 【已解决】在Android 11中安装EdXposed框架

---

* Android的Hook插件开发框架
  * [XPosed](https://book.crifan.org/books/crack_assistant_xposed_framework/website/)
  * `Cydia Substrate`
