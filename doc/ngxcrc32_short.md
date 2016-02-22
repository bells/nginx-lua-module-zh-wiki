ngx.crc32_short
---------------
**语法:** *intval = ngx.crc32_short(str)*

**环境:** set_by_lua&#42;, rewrite_by_lua&#42;, access_by_lua&#42;, content_by_lua&#42;, header_filter_by_lua&#42;, body_filter_by_lua&#42;, log_by_lua&#42;, ngx.timer.&#42;

通过一个字符串计算循环冗余校验码。

这个方法最好在字符串较少时调用（比如少于30-60字节），他的结果和 `ngx.crc32_long` 是一样的。

本质上，它只是 Nginx 内核函数 `ngx_crc32_short` 的简单封装。

这个方法最早出现在版本 `v0.3.1rc8` 中。

> English Source

**syntax:** *intval = ngx.crc32_short(str)*

**context:** set_by_lua&#42;, rewrite_by_lua&#42;, access_by_lua&#42;, content_by_lua&#42;, header_filter_by_lua&#42;, body_filter_by_lua&#42;, log_by_lua&#42;, ngx.timer.&#42;

Calculates the CRC-32 (Cyclic Redundancy Code) digest for the str argument.

This method performs better on relatively short str inputs (i.e., less than 30 ~ 60 bytes), as compared to `ngx.crc32_long`. The result is exactly the same as `ngx.crc32_long`.

Behind the scene, it is just a thin wrapper around the ngx_crc32_short function defined in the Nginx core.

This API was first introduced in the `v0.3.1rc8` release.

[返回目录](#nginx-api-for-lua)