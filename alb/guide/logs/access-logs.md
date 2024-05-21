# 访问日志

ALB通常作为业务的首要访问入口，承载着庞大的访问请求流量。ALB会实时将业务日志投递至US3存储服务，通过分析业务日志，可以让您能够深入了解客户端的访问行为、地域分布特点。有助于更全面地了解用户的使用习惯，更能协助你高效排查和解决潜在的故障问题。

# 费用说明

访问日志功能本身并不收费，但ALB将日志投递到指定的US3内后，US3会收取存储空间，和请求数量和读取流量的费用。

# 开启访问日志

目前仅支持US3上线的地域开启访问，详情请查看[US3地域](https://docs.ucloud.cn/ufile/introduction/region)。

1. 登录应用型负载均衡ALB控制台。
2. 在顶部导航栏，选择ALB实例所属的地域。
3. 在**实例**页面，点击目标实例ID。
4. 在**实例详情**页，选择概览页签，在基本信息模块下，选择点击日志管理。

![1713867191288](/images/1713867191288.png)

5. 选择开启访问日志，选择创建的US3存储空间，和US3令牌，然后点击确定。
6. 访问日志每5分钟会生成一个日志文件，并存储在所选的存储空间中。

# 查看访问日志

1. 登录应用型负载均衡ALB控制台。
2. 在顶部导航栏，选择ALB实例所属的地域。
3. 在**实例**页面，点击目标实例ID。
4. 在**实例详情**页，选择概览页签，在基本信息模块下，如您已开通日志管理，点击**查看日志**。

![1713867658563](/images/1713867658563.png)

5. 跳转到US3存储空间详情页，根据自己的需要可以查询该LB的访问日志。
6. 日志内容如下所示

```Plaintext
192.168.5.198 - - [24/Feb/2021:17:33:21 +0800] 200 5068 18070 192.168.5.208:8080 "" "curl/7.29.0" - - 192.168.5.30:80 2 ms 3 ms "GET / HTTP/1.1"
客户端ip -- [本地时间] 状态码 服务端返回客户端的字节大小 客户端端口 CLB的ip:CLB的端口 "http_referer"(没有则为""或"-") "http_user_agent"(没有则为""或"-") ssl_version(没有则为-) ssl_ciphers(没有则为-) rs服务ip:rs服务端口 响应时间 请求时间 "请求"
```

# 修改/删除访问日志

1. 登录应用型负载均衡ALB控制台。
2. 在顶部导航栏，选择ALB实例所属的地域。
3. 在**实例**页面，点击目标实例ID。
4. 在**实例详情**页，选择概览页签，在基本信息模块下，选择点击日志管理的编辑按钮。

![1713867714313](/images/1713867714313.png)

5. 可以在日志管理弹窗，关闭日志功能，或更换US3存储空间和令牌。