### ECJiaWiki:Ecjia后台RC Http使用说明

#### 方法列表

| 编号 |              方法名称              |                           简单描述                           |
| :--: | :--------------------------------: | :----------------------------------------------------------: |
|  1   |       safe_remote_request()        |                从安全的HTTP请求中检索原始响应                |
|  2   |         safe_remote_get()          |           使用GET方法从安全HTTP请求中检索原始响应            |
|  3   |         safe_remote_post()         |           使用POST方法从安全HTTP请求中检索原始响应           |
|  4   |         safe_remote_head()         |           使用HEAD方法从安全HTTP请求中检索原始响应           |
|  5   |          remote_request()          |                   从HTTP请求中检索原始响应                   |
|  6   |            remote_get()            |             使用GET方法从HTTP请求中检索原始响应              |
|  7   |           remote_post()            |             使用POST方法从HTTP请求中检索原始响应             |
|  8   |           remote_head()            |             使用HEAD方法从HTTP请求中检索原始响应             |
|  9   |     remote_retrieve_headers()      |                    仅检索原始响应中的标头                    |
|  10  |      remote_retrieve_header()      |                从原始响应中按名称检索单个标头                |
|  11  |  remote_retrieve_response_code()   |                  仅检索原始响应中的响应代码                  |
|  12  | remote_retrieve_response_message() |                  仅检索原始响应中的响应消息                  |
|  13  |       remote_retrieve_body()       |                    仅从原始响应中检索主体                    |
|  14  |     remote_retrieve_cookies()      |                   仅检索原始响应中的cookie                   |
|  15  |      remote_retrieve_cookie()      |               从原始响应中按名称检索单个cookie               |
|  16  |   remote_retrieve_cookie_value()   |             从原始响应中按名称检索单个cookie的值             |
|  16  |          http_supports()           |             确定是否存在可以处理此请求的HTTP传输             |
|  17  |         get_http_origin()          |                  获取当前请求的HTTP Origin                   |
|  18  |     get_allowed_http_origins()     |                    检索允许的HTTP源的列表                    |
|  19  |      is_allowed_http_origin()      |                    确定HTTP源是否是授权的                    |
|  20  |       send_origin_headers()        | 如果当前请求来自允许的来源，则发送Access-Control-Allow-Origin和相关标头 |
|  21  |        http_validate_url()         |               验证URL以便在HTTP API中安全使用                |
|  22  |    allowed_http_request_hosts()    |          白名单也允许重定向主机以获取安全的HTTP请求          |

#### 方法详细说明

safe_remote_request()

- 从安全的HTTP请求中检索原始响应：

```
$request = RC_Http::safe_remote_request($url, $args = array());
```

| 1    | $url  | string | 要检索的网站网址   |
| ---- | ----- | ------ | ------------------ |
| 2    | $args | array  | 可选的。请求参数。 |

safe_remote_get()

- 使用GET方法从安全HTTP请求中检索原始响应：

```
$request = RC_Http::safe_remote_get($url, $args = array());
```

| 1    | $url  | string | 要检索的网站网址   |
| ---- | ----- | ------ | ------------------ |
| 2    | $args | array  | 可选的。请求参数。 |

safe_remote_post()

- 使用POST方法从安全HTTP请求中检索原始响应：

```
$request = RC_Http::safe_remote_post($url, $args = array());
```

| 1    | $url  | string | 要检索的网站网址   |
| ---- | ----- | ------ | ------------------ |
| 2    | $args | array  | 可选的。请求参数。 |


safe_remote_head()

- 使用HEAD方法从安全HTTP请求中检索原始响应：

```
$request = RC_Http::safe_remote_head($url, $args = array());
```

| 1    | $url  | string | 要检索的网站网址   |
| ---- | ----- | ------ | ------------------ |
| 2    | $args | array  | 可选的。请求参数。 |

remote_request()

- 从HTTP请求中检索原始响应：

```
$request = RC_Http::remote_request($url, $args = array());
```

| 1    | $url  | string | 要检索的网站网址   |
| ---- | ----- | ------ | ------------------ |
| 2    | $args | array  | 可选的。请求参数。 |


remote_get()

- 使用GET方法从HTTP请求中检索原始响应：

```
$request = RC_Http::remote_get($url, $args = array());
```

| 1    | $url  | string | 要检索的网站网址   |
| ---- | ----- | ------ | ------------------ |
| 2    | $args | array  | 可选的。请求参数。 |


remote_post()

- 使用POST方法从HTTP请求中检索原始响应：

```
$request = RC_Http::remote_post($url, $args = array());
```

| 1    | $url  | string | 要检索的网站网址   |
| ---- | ----- | ------ | ------------------ |
| 2    | $args | array  | 可选的。请求参数。 |


remote_head()

- 使用HEAD方法从HTTP请求中检索原始响应：

```
$request = RC_Http::remote_head($url, $args = array());
```

| 1    | $url  | string | 要检索的网站网址   |
| ---- | ----- | ------ | ------------------ |
| 2    | $args | array  | 可选的。请求参数。 |

remote_retrieve_headers()

- 仅检索原始响应中的标头：

```
$request = RC_Http::remote_retrieve_headers($response);
```

| 1    | $response | string | HTTP响应 |
| ---- | --------- | ------ | -------- |
|      |           |        |          |


remote_retrieve_header()

- 从原始响应中按名称检索单个标头：

```
$request = RC_Http::remote_retrieve_header($$response, $header);
```

| 1    | $response | string | HTTP响应                   |
| ---- | --------- | ------ | -------------------------- |
| 2    | $header   | string | 用于从中检索值的标头名称。 |


remote_retrieve_response_code()

- 仅检索原始响应中的响应代码：

```
$request = RC_Http::remote_retrieve_response_code($response);
```

| 1    | $response | string | HTTP响应 |
| ---- | --------- | ------ | -------- |
|      |           |        |          |


remote_retrieve_response_message()

- 仅检索原始响应中的响应消息：

```
$request = RC_Http::remote_retrieve_response_message($response);
```

| 1    | $response | string | HTTP响应 |
| ---- | --------- | ------ | -------- |
|      |           |        |          |


remote_retrieve_body()

- 仅从原始响应中检索主体：

```
$request = RC_Http::remote_retrieve_body($response);
```

| 1    | $response | string | HTTP响应 |
| ---- | --------- | ------ | -------- |
|      |           |        |          |


remote_retrieve_cookies()

- 仅检索原始响应中的cookie：

```
$request = RC_Http::remote_retrieve_cookies($response);
```

| 1    | $response | string | HTTP响应 |
| ---- | --------- | ------ | -------- |
|      |           |        |          |


remote_retrieve_cookie()

- 从原始响应中按名称检索单个cookie：

```
$request = RC_Http::remote_retrieve_cookie($response, $name);
```

| 1    | $response | string | HTTP响应             |
| ---- | --------- | ------ | -------------------- |
| 2    | $name     | string | 要检索的cookie的名称 |

remote_retrieve_cookie_value()

- 从原始响应中按名称检索单个cookie的值：

```
$request = RC_Http::remote_retrieve_cookie_value($response, $name);
```

| 1    | $response | string | HTTP响应             |
| ---- | --------- | ------ | -------------------- |
| 2    | $name     | string | 要检索的cookie的名称 |


http_supports()

- 确定是否存在可以处理此请求的HTTP传输：

```
$request = RC_Http::http_supports($capabilities = array(), $url = null);
```

| 1    | $capabilities | array  | 要测试的函数数组                       |
| ---- | ------------- | ------ | -------------------------------------- |
| 2    | $url          | string | 可选的。如果给定，将检查URL是否需要SSL |


get_http_origin()

- 获取当前请求的HTTP Origin：

```
$request = RC_Http::get_http_origin();
```

get_allowed_http_origins()

- 检索允许的HTTP源的列表：

```
$request = RC_Http::get_allowed_http_origins();
```

is_allowed_http_origin($origin = null )

- 确定HTTP源是否是授权的：

```
$request = RC_Http::is_allowed_http_origin();
```

| 1    | $origin | string | 原始网址 |
| ---- | ------- | ------ | -------- |
|      |         |        |          |

send_origin_headers()

- 如果当前请求来自允许的来源，则发送Access-Control-Allow-Origin和相关标头：

```
$request = RC_Http::send_origin_headers();
```

http_validate_url()

- 验证URL以便在HTTP API中安全使用：

```
$request = RC_Http::http_validate_url($url);
```


allowed_http_request_hosts()

- 白名单也允许重定向主机以获取安全的HTTP请求：

```
$request = RC_Http::allowed_http_request_hosts($is_external, $host);
```

| 1    | $is_external | bool   | 是否是外在的 |
| ---- | ------------ | ------ | ------------ |
| 2    | $host        | string | 主机         |