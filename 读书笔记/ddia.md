## 一 数据系统的基石

### 可靠性 可扩展 可维护

现今很多应用程序都是数据密集型（data-intensive)的，而非计算密集型（compute-
intensive)的。因此CPU很少成为这类应用的瓶颈，更大的问题通常来自数据量、数据复
性、以及数据的变更速度。
数据密集型应用通常由标准组件构建而成，标准组件提供了很多通用的功能；例如，许多应
用程序都需要：
·存储数据，以便自己或其他应用程序之后能再次找到（数据库（database))
·记住开销昂贵操作的结果，加快读取速度（缓存（cache))
·允许用户按关键字搜索数据，或以各种方式对数据进行过滤（搜索索引（search
indexes))
·向其他进程发送消息，进行异步处理（流处理（stream processing))
·定期处理累积的大批量数据（批处理（batch processing))
如果这些功能听上去平淡无奇，那是因为这些数据系统（data system)是非常成功的抽
象：我们一直不假思索地使用它们并习以为常。绝大多数工程师不会幻想从零开始编写存储
引擎，因为在开发应用时，数据库已经是足够完美的工具了。

