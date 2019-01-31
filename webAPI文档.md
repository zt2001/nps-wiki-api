### 客户端

#### 添加客户端
```
POST /client/add/
```
参数 | 含义
---|---
remark | 备注
u | 用户名
p | 密码
compress | 压缩（snappy或空）
crypt | 是否加密（1或者0）
rate_limit|带宽限制
flow_limit|流量限制

#### 添加客户端
```
POST /client/edit/
```
参数 | 含义
---|---
id | id
remark | 备注
u | 用户名
p | 密码
compress | 压缩（snappy或空）
crypt | 是否加密（1或者0）
rate_limit|带宽限制
flow_limit|流量限制

#### 更改状态
```
POST /client/changestatus/
```
参数 | 含义
---|---
id | id
status|1或0

#### 删除客户端
```
POST /client/del/
```
参数 | 含义
---|---
id | id
#### 获取单个客户端
```
POST /client/getclient/
```
参数 | 含义
---|---
id | id
#### 获取客户端列表
```
POST /client/list/
```

参数 | 含义
---|---
start | 开始
length | 长度

### 域名代理

#### 添加域名代理

```
POST /index/addhost/
```

参数 | 含义
---|---
host | 域名
target | 内网目标地址
header | header修改
hostchange | host修改
remark | 备注
client_id | 客户端id
#### 删除域名代理
```
POST /index/delhost/
```

参数 | 含义
---|---
host | 域名

#### 修改域名代理
```
POST /index/edithost/
```

参数 | 含义
---|---
nhost | 修改后的域名
host | 修改之前的域名
target | 内网目标地址
header | header修改
hostchange | host修改
remark | 备注
client_id | 客户端id

#### 获取域名代理列表
```
POST /index/hostlist/
```

参数 | 含义
---|---
start | 开始
length | 长度
client_id | 客户端id（为空获取所有）
#### 获取单个host
```
POST /index/gethost/
```

参数 | 含义
---|---
host|域名


### 其他代理

#### 获取隧道列表

```
POST /index/gettunnel/
```

参数 | 含义
---|---
client_id|客户端id(为空则忽略客户端限制)
type|类型(udpServer、tunnelServer、socks5Server、httpProxyServer，为空则忽略类型限制)
start|开始
length|长度

#### 添加

```
POST /index/add/
```

参数 | 含义
---|---
port|监听端口
type|类型(udpServer、tunnelServer、socks5Server、httpProxyServer)
start|开始
u|验证用户名
p|验证密码
compress|压缩（空或snappy）
crypt|是否加密（1或0）
use_client|是否使用客户端配置（1或0）
remark|备注
client_id|客户端id

#### 修改

```
POST /index/edit/
```

参数 | 含义
---|---
id|id
port|监听端口
type|类型(udpServer、tunnelServer、socks5Server、httpProxyServer)
start|开始
u|验证用户名
p|验证密码
compress|压缩（空或snappy）
crypt|是否加密（1或0）
use_client|是否使用客户端配置（1或0）
remark|备注
client_id|客户端id

#### 停止隧道

```
POST /index/stop/
```

参数 | 含义
---|---
id|id

#### 删除隧道

```
POST /index/del/
```

参数 | 含义
---|---
id|id
#### 开始隧道

```
POST /index/start/
```

参数 | 含义
---|---
id|id
#### 获取单条隧道详细

```
POST /index/getonetunnel/
```

参数 | 含义
---|---
id|id