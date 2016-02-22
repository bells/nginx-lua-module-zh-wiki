典型应用
============

列举部分：

* 在 Lua 中揉和和处理各种不同的 NGINX 上游输出（proxy, drizzle, postgres, redis, memcached等）
* 在请求真正到达上游服务之前，Lua 可以随心所欲的做复杂的访问控制和安全检测
* 随心所欲的操控响应头里面的信息（通过 Lua）
* 从外部存储服务（比如 redis, memcached, mysql, postgresql）中获取后端信息，并用这些信息来实时选择哪一个后端来完成业务访问
* 在内容 handler 中随意编写复杂的 web 应用，使用同步但依然非阻塞的方式，访问后端数据库和其他存储
* 在 rewrite 阶段，通过 Lua 完成非常复杂的 URL dispatch
* 用 Lua 可以为 NGINX 子请求和任意location，实现高级缓存机制

本模块会把你带入一个拥有无限可能的服务端开发新世界，你可以把 NGINX 的各种功能进行自由拼接，
更重要的是，开发门槛并不高，这一切都是用强大轻巧的 Lua 语言来操控。

本模块的脚本有充分的灵活性，并且性能和原生 C 语言编程相比毫不逊色，无论是 CPU 时间还是内存占用方面。
当然这个需要你使用 LuaJIT 2.x。

其他脚本语言的实现通常很难达到类似性能。

Lua state（Lua VM instance）会被共享给单个 nginx worker 内所有的请求，从而达到最小化内存消耗。

[返回目录](#table-of-contents)

> English source:

Typical Uses
============

Just to name a few:

* Mashup'ing and processing outputs of various nginx upstream outputs (proxy, drizzle, postgres, redis, memcached, and etc) in Lua,
* doing arbitrarily complex access control and security checks in Lua before requests actually reach the upstream backends,
* manipulating response headers in an arbitrary way (by Lua)
* fetching backend information from external storage backends (like redis, memcached, mysql, postgresql) and use that information to choose which upstream backend to access on-the-fly,
* coding up arbitrarily complex web applications in a content handler using synchronous but still non-blocking access to the database backends and other storage,
* doing very complex URL dispatch in Lua at rewrite phase,
* using Lua to implement advanced caching mechanism for Nginx's subrequests and arbitrary locations.

The possibilities are unlimited as the module allows bringing together various elements within Nginx as well as exposing the power of the Lua language to the user. The module provides the full flexibility of scripting while offering performance levels comparable with native C language programs both in terms of CPU time as well as memory footprint. This is particularly the case when LuaJIT 2.x is enabled.

Other scripting language implementations typically struggle to match this performance level.

The Lua state (Lua VM instance) is shared across all the requests handled by a single nginx worker process to minimize memory use.

[Back to TOC](#table-of-contents)
