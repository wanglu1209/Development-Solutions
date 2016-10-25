### 本文介绍了4种跨进程通讯的方式

**Activity:** 其中Activity可以跨进程调用其他应用程序的Activity

**ContentProvider:** ContentProvider可以访问其他应用程序返回的 Cursor对象

**Broadcast:** Broadcast采用的是被动接收的方法，也就是说，客户端只能接收广播数据，而不能向发送广播的程序发送信息

**AIDL Service:** AIDL Service可以将程序中的某个接口公开，这样在其他的应用程序中就可以象访问本地对象一样访问AIDL服务对象了

其中Activity这4种跨进程通讯的方式可以应用在不同的场合。例如，在需要显示可视化的界面时可以用Activity，需要返回记录集时可以用ContentProvider。至于在应用程序中具体要用到哪一种或几种方式进行跨进程通讯，可以根据实际情况进行选择。

原文链接：[Andorid中跨进程通讯的4种方式]()http://blog.csdn.net/yan8024/article/details/6444368)
