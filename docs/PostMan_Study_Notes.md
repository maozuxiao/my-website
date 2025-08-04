# PostMan Study Note



## 功能概述

Postman 是一款广泛用于 API 开发与测试的工具，其请求窗口可创建、发送各类 HTTP 请求（如 GET、POST 等 ），模拟客户端与服务器交互，验证 API 功能、调试接口问题。



## 界面与核心操作





### 请求方法与 URL 栏

- **请求方法选择**：点击左侧下拉框（默认显示 `GET` ），可切换 `POST`、`PUT`、`DELETE` 等 HTTP 方法，按需选对应请求类型。
- **URL 输入**：在右侧输入框，填写 API 的完整 URL 。若为 `GET` 请求带查询参数，可直接拼接（如 `https://api.example.com/data?key1=value1` ），也可后续在 `Params` 栏添加。

### 参数（Params）设置

切换到 `Params` 标签，用于配置查询参数（Query Params ）：

- **Key - Value 录入**：在表格 `Key` 列填参数名，`Value` 列填对应值，`Description` 可写参数说明（选填 ）。点击行末尾 “+” 可新增参数，“×” 删除参数，批量编辑点 `Bulk Edit` ，输入 `key1=value1&key2=value2` 格式内容快速设置。

### 授权（Authorization）配置

若 API 需授权（如 Token、Basic Auth 等 ），切到 `Authorization` 标签：

- **类型选择**：下拉框选授权类型（如 `Bearer Token` ），按需填对应凭证（如 Token 值 ），部分类型需填用户名、密码等，按接口要求设置。

### 请求头（Headers）管理

切到 `Headers` 标签，默认显示常用头信息：

- **添加头字段**：点击 “+”，`Key` 填头名称（如 `Content - Type` ），`Value` 填对应值（如 `application/json` ），描述选填，快速设置常用头可点右侧预设按钮（若有 ）。

### 请求体（Body）设置

仅 `POST`、`PUT` 等方法常用，切到 `Body` 标签：

- **类型选择**：选 `form - data`（表单数据，传文件、键值对 ）、`x - www - form - urlencoded`（普通表单 ）、`raw`（传 JSON、XML 等原始数据，选对应格式后填内容 ）、`binary`（传二进制文件 ），按需选类型并录入数据。

### 发送请求（Send）与查看响应

填好请求信息后，点右上角黄色 `Send` 按钮发送请求。下方 `Response` 区域显示服务器返回：

- **响应内容**：展示状态码、响应头、响应体（如 JSON 数据、文本等 ），可切 `History` 看请求历史记录，对比不同请求响应差异。

## 进阶功能

### 脚本（Scripts）

- **前置脚本（Pre - request Script）**：切到 `Scripts` 标签，写 JavaScript 代码，发送请求前执行（如设置动态变量、加密参数 ）。
- **测试脚本（Tests）**：请求后执行，写断言验证响应（如检查状态码是否 200、响应体某字段是否符合预期 ），自动判断接口是否正常。

### 设置（Settings）

切到 `Settings` 标签，可精细调整请求行为，适配特殊测试场景：

1. **HTTP 版本（HTTP version）**：下拉选择发送请求使用的 HTTP 协议版本（如 `HTTP/1.x` ），影响请求传输规则，部分旧服务需指定版本适配。
2. **SSL 证书验证（Enable SSL certificate verification）**：默认 `OFF` ，开启（`ON` ）后发送请求会验证 SSL 证书，验证失败则请求终止，用于模拟严格安全校验场景。
3. **自动跟随重定向（Automatically follow redirects）**：默认 `ON` ，请求遇重定向时自动跟随；关闭（`OFF` ）则需手动处理重定向响应，便于调试重定向逻辑。
4. **重定向时保留原 HTTP 方法（Follow original HTTP Method）**：默认 `OFF` ，开启后重定向时用原请求方法（如原 `POST` 重定向仍用 `POST` ），否则默认转为 `GET` ，适配需维持方法的接口。
5. **重定向时保留授权头（Follow Authorization header）**：默认 `OFF` ，开启后重定向到不同主机时，保留授权头信息，用于跨域且需授权的重定向场景。
6. **重定向时移除引用头（Remove referer header on redirect）**：默认 `OFF` ，开启则重定向时移除 `referer` 头，按需控制请求头内容。
7. **启用严格 HTTP 解析（Enable strict HTTP parser）**：默认 `OFF` ，开启后严格校验 HTTP 头格式，头格式有误则请求失败，用于模拟严格客户端环境。
8. **自动编码 URL（Encode URL automatically）**：默认 `ON` ，自动编码 URL 路径、查询参数等特殊字符，避免因字符非法导致请求错误；关闭可手动控制编码。
9. **禁用 Cookie Jar（Disable cookie jar）**：默认 `OFF` ，开启后本次请求的 Cookie 不存入 Postman Cookie Jar ，且 Jar 中已有 Cookie 也不随请求发送，用于隔离 Cookie 场景。
10. **使用服务器加密套件顺序（Use server cipher suite order instead of the client's during handshake）**：默认 `OFF` ，开启后 TLS 握手时用服务器指定的加密套件顺序，影响加密连接建立，适配服务端特殊加密要求。
11. **最大重定向次数（Maximum number of redirects）**：默认 `10` ，可设置请求允许跟随的最大重定向次数，防止无限重定向导致请求挂起。
12. **禁用的 TLS/SSL 协议（TLS/SSL protocols disabled during handshake）**：填写需禁用的 TLS/SSL 协议版本，如指定禁用老旧不安全协议，仅允许安全协议用于握手。
13. **加密套件选择（Cipher suite selection）**：输入服务器建立安全连接时使用的加密套件顺序，自定义加密套件优先级，适配特定加密环境。

### Cookie 管理

切到 `Cookies` 标签，查看、添加、删除与请求域名相关的 Cookie ，模拟带 Cookie 认证的请求场景。

## HTTP 请求方法

> **参考资料**：[HTTP方法详解](https://maozuxiao.github.io/my-website/HTTP方法详解.html)

| HTTP 方法 | 英文全称 | 作用描述                                                     | 特点与注意事项                                               | 示例                                                         |
| --------- | -------- | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| GET       | Get      | 向服务器请求指定资源，用于获取数据                           | 1. 请求参数附加在 URL 中，长度有限制 2. 是幂等的（多次请求结果一致） 3. 不应该用于修改资源的操作 | 访问网页：`GET https://www.example.com/index.html` 查询数据：`GET https://api.example.com/users?id=123` |
| POST      | Post     | 向服务器提交数据，用于创建新资源或执行需要处理数据的操作     | 1. 请求参数放在请求体中，可传输大量数据 2. 非幂等（多次请求可能产生不同结果，如重复提交订单） | 提交表单：`POST https://www.example.com/login`（请求体包含用户名和密码） 创建资源：`POST https://api.example.com/articles`（请求体包含文章内容） |
| PUT       | Put      | 向服务器发送数据，用于更新指定资源（全量更新）               | 1. 需要指定资源的完整 URL 2. 是幂等的（多次执行结果相同） 3. 通常用于替换资源的全部内容 | 更新用户信息（全量）：`PUT https://api.example.com/users/123`（请求体包含用户所有字段的新值） |
| PATCH     | Patch    | 向服务器发送部分数据，用于更新指定资源（部分更新）           | 1. 只传输需要修改的部分数据，更高效 2. 非幂等（取决于具体实现） 3. 是对 PUT 的补充 | 部分更新用户信息：`PATCH https://api.example.com/users/123`（请求体仅包含`{"nickname": "newname"}`） |
| DELETE    | Delete   | 请求服务器删除指定资源                                       | 1. 是幂等的（多次删除结果一致） 2. 实际应用中可能只是标记资源为删除状态 | 删除文章：`DELETE https://api.example.com/articles/456`      |
| HEAD      | Head     | 类似于 GET，但只返回响应头，不返回响应体                     | 1. 可用于检查资源是否存在、获取资源的元数据（如大小、修改时间） 2. 不传输响应体，节省带宽 | 检查文件是否存在及大小：`HEAD https://www.example.com/files/report.pdf` |
| OPTIONS   | Options  | 用于请求服务器支持的 HTTP 方法，或跨域请求中的预检请求       | 1. 常用于跨域资源共享（CORS）中，检查服务器是否允许特定的请求方法和头部 2. 服务器会返回允许的方法列表 | 跨域预检请求：`OPTIONS https://api.example.com/data`（浏览器自动发起，检查是否允许 POST 请求） |
| CONNECT   | Connect  | 用于建立与服务器的隧道连接，通常用于 HTTPS 协议中的代理服务器 | 1. 让客户端与服务器通过代理建立直接的 TCP 连接 2. 主要用于 SSL 加密通信场景 | 代理建立 HTTPS 隧道：`CONNECT www.example.com:443 HTTP/1.1`（通过代理访问 HTTPS 网站） |
| TRACE     | Trace    | 用于测试服务器返回的请求信息，追踪请求的传输路径             | 1. 服务器会将收到的请求原样返回，供客户端查看 2. 存在安全风险，实际应用中较少使用 | 追踪请求路径：`TRACE /test HTTP/1.1`（服务器返回请求的完整内容，用于调试） |



