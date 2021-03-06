---
refcn: chapter_02/transport/tcp
refen: configuration/transport/tcp
---
# Доставка через TCP

Configuration:

```javascript
{
  "header": {
    "type": "none"
  }
}
```

Where:

* `header`: Настройки обфускации заголовка: 
  * `type`: Type of obfuscation. Choices are: 
    * `"none"`: Default. No obfuscation at all.
    * `"http"`: HTTP obfuscation. See below.

## Обфускация HTTP

Обфускацию HTTP необходимо настроить (и сопоставить) для входящих и исходящих соединений.

```javascript
{
  "type": "http",
  "request": {
    "version": "1.1",
    "method": "GET",
    "path": ["/"],
    "headers": {
      "Host": ["www.baidu.com", "www.bing.com"],
      "User-Agent": [
        "Mozilla/5.0 (Windows NT 10.0; WOW64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/53.0.2785.143 Safari/537.36",
        "Mozilla/5.0 (iPhone; CPU iPhone OS 10_0_2 like Mac OS X) AppleWebKit/601.1 (KHTML, like Gecko) CriOS/53.0.2785.109 Mobile/14A456 Safari/601.1.46"
      ],
      "Accept-Encoding": ["gzip, deflate"],
      "Connection": ["keep-alive"],
      "Pragma": "no-cache"
    }
  },
  "response": {
    "version": "1.1",
    "status": "200",
    "reason": "OK",
    "headers": {
      "Content-Type": ["application/octet-stream", "video/mpeg"],
      "Transfer-Encoding": ["chunked"],
      "Connection": ["keep-alive"],
      "Pragma": "no-cache"
    }
  }
}
```

Where:

* `type`: тот же `type` что и в `tcpSettings`.
* `request`: Настройки HTTP-запроса: 
  * `version`: Версия HTTP, по умолчанию `"1.1"`
  * `method`: Метод HTTP, по умолчанию `"GET"`
  * `path`: Path. A string array. Default value is `["/"]`. When there are multiple values, value is picked up randomly for each request.
  * `headers`: Заголовки HTTP. Ассоциативный массив, пары ключ-значение. Каждый ключ - заголовок HTTP, а каждое значение - содержимое HTTP заголовка. Если задано несколько элементов, конечные заголовки выбираются случайным образом для каждого запроса. Параметры по умолчанию - в примере выше.
* `response`: Ответ HTTP. 
  * `version`: HTTP version. Default value is `"1.1"`.
  * `status`: HTTP status. Default value is `"200"`.
  * `reason`: HTTP status text. Default value is `"OK"`.
  * `headers`: HTTP header. Same as request headers, but for response.