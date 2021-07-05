---
title: curl简明教程
tags:
  - curl
categories:
  - curl
date: 2021-07-05 23:24:30
---

```
curl -L https://yt-dl.org/downloads/latest/youtube-dl -o /usr/local/bin/youtube-dl
```

- -L：跟随服务器的重定向
- -o filename：将服务器的回应保存成文件
- -O 同-o,不需要指定文件名，将 URL 的最后部分当作文件名

```
curl --location --request GET 'https://api.xxx.com/auth?feature_code=tts' \
--header 'X-Prod-Id: 100' \
--header 'Authorization: Bearer 09Xqm8I1aAbxdw'
```

## 参考

https://www.ruanyifeng.com/blog/2019/09/curl-reference.html
