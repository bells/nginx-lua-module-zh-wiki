ngx.resp.get_headers
--------------------
**语法:** *headers = ngx.resp.get_headers(max_headers?, raw?)*

**环境:** *set_by_lua&#42;, rewrite_by_lua&#42;, access_by_lua&#42;, content_by_lua&#42;, header_filter_by_lua&#42;, body_filter_by_lua, log_by_lua&#42;, balancer_by_lua&#42;*

返回一个 Lua 表，包含当前请求的所有响应头信息。

```lua

 local h = ngx.resp.get_headers()
 for k, v in pairs(h) do
     ...
 end
```

此函数与 [ngx.req.get_headers](#ngxreqget_headers) 有相似之处，唯一区别是获取的是响应头信息而不是请求头信息。

这个 API 最早出现在 `v0.9.5` 版中。

> English Source

**syntax:** *headers = ngx.resp.get_headers(max_headers?, raw?)*

**context:** *set_by_lua&#42;, rewrite_by_lua&#42;, access_by_lua&#42;, content_by_lua&#42;, header_filter_by_lua&#42;, body_filter_by_lua, log_by_lua&#42;, balancer_by_lua&#42;*

Returns a Lua table holding all the current response headers for the current request.

```lua

 local h = ngx.resp.get_headers()
 for k, v in pairs(h) do
     ...
 end
```

This function has the same signature as [ngx.req.get_headers](#ngxreqget_headers) except getting response headers instead of request headers.

This API was first introduced in the `v0.9.5` release.

[返回目录](#nginx-api-for-lua)