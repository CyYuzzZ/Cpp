

## 网络服务端

- 如何保证服务程序的稳定性：

心跳机制 调度程序和守护程序协调工作。

> 主进程用于监控和调度。
>
> 程序的功能由子线程实现，把心跳心如全局变量。
>
> 如果心跳超时，取消子线程并重启。


- 异步通信

主进程创建socket

一个线程负责发送请求，另一个线程负责接收回应。



- 流程

登录：与服务端协商文件传输的参数，文件存放目录等

把文件信息发送给服务端：文件名、时间、大小

文件传输系统用于系统内部，对文件传输的时效要求高，不能延迟太长时间，所以客户端程序一直运行在内存，传完一批等待几秒传下一批。

文件上传成功后，删除本地或转存到备份目录。内部系统为了保证效率，上传完直接删除最简单，效率最高，不需要增量上传。如果需要上传到多个服务器，生成文件时多拷贝几份。


- 异步通信的实现

> 多进程：不同进程发送和接收报文
>
> 多线程：不同线程发送和接收报文
>
> I/O复用：select、poll、epoll函数

同步每秒2000条/s，多进程/多线程 80000条/s ，I/O复用 60000条/s

- 总结

基于TCP的网络服务端用于文件传输

采用异步通信提升性能

流量控制：滑动窗口

当网络出现异常，回应报文会丢失，发送的越快丢失的越多，客户端需要设计重发的机制。

信号处理中取消全部线程，
在线程清理函数中释放资源

# 数据服务总线

业务需求






