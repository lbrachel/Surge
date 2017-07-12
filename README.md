# 使用手册

### 简介

本项目最早是基于 [scomper/surge.conf](https://gist.github.com/scomper/915b04a974f9e11952babfd0bbb241a8) 定制修改而来，现已形成独有风格。

---
* [可实现功能](#可实现功能)
* 导入方式
    * [URL](#url)
    * [Workflow](#workflow)
    	* User Data
    	* Rule OTA
    * [~~在线更新（暂弃）~~](https://github.com/lhie1/RuleList)
* [MitM 证书的安装及信任](#mitm证书的安装及信任)
* [Hosts（免服务器翻墙）](#hosts)
* [Android SSR ACL](#android-ssr-acl)
* [浏览器广告](#浏览器广告)
* [联系方式](#line)
* [Q&A](#qa)
	* [☁️ Proxy & 🔰 Proxy & 🍎 Proxy](#%EF%B8%8F-proxy---proxy---proxy)
	* [🚀 混淆模式](#-混淆模式)
	* [🔋 Surge 耗电](#-surge-耗电)
	* [☑️ Set as System Proxy](#%EF%B8%8F-set-as-systemproxy)
	* [📶 Surge for iOS 开启共享模式](#-surge-开启共享模式)
	* [🏃 Auto](#-auto)
* [客户端](#客户端有r标示表示支持-ssr)
* [配置文件样例](#配置文件样例)
* [鸣谢](#鸣谢)
* [License](#license)

---

### 可实现功能
* 自动代理 / 全局代理
* 解决本地 DNS 可能带来的干扰
* 可突破部分内网限制（公司、学校）
* 拦截常用应用程序的行为分析
* 拦截常用应用程序的数据统计
* 拦截常用应用程序的隐私跟踪
* 拦截各大购物网站的运营商劫持
* 屏蔽部分应用程序的启动广告
* 屏蔽部分运营商劫持网页弹出的流量统计
* 屏蔽部分运营商劫持网页弹出的漂浮球广告
* 屏蔽常用视频广告
* 屏蔽常用网站广告、其他流媒体网站广告
* 所有国内网站直线连接
* Apple 服务加速（App Store、Apple Music、Apple流媒体、iCloud备份、iCloud Drive、iTunes 等）
* 国外常用网站加速（Google/Youtube/Twitter/Facebook/instagram/wikipedia/Github 等）

---

### URL
````
Surge：https://raw.githubusercontent.com/lhie1/Surge/master/Surge_Lite.conf

Shadowrocket：https://raw.githubusercontent.com/lhie1/Surge/master/Shadowrocket_Lite.conf
````
导入后请务必[安装证书](#mitm证书的安装及信任)

![URL](https://raw.githubusercontent.com/lhie1/Surge/master/images/URL.jpeg)

---

### Workflow

* [User Data](#user-data)
    * 自定义[Proxy]节点
    * 自动根据[Proxy]内容生成[Proxy Group]
    * 自定义添加[Rule]规则
    * 自定义添加[Host]规则
    * 自定义添加[URL Rewrite]规则
    * 自定义添加[SSID Setting]规则
    * 自定义删除规则（All）
    * 生成证书
* [Rule OTA](#rule-ota)
    * [Special_Proxy](#special_proxy)
        * [AuthKey](#authkey)
        * [Google](#google)
        * [Netflix](#netflix)
        * [MytvSUPER](#mytvsuper)
	* [Spotify](#spotify)
    * Features_Module
        * [Adblocker](#adblocker)
        * [TestFlight](#testflinght)
        * [Emoji](#emoji)
        * ~~Youku~~
    * 运行时检查更新并自动下载
    * 自动修复`module`模块地址
    * 更新规则
    * 生成规则

#### User Data
[下载地址](https://workflow.is/workflows/6c05e2bb808a44bdb1d5337c07feff0b)

#### Rule OTA
[下载地址](https://workflow.is/workflows/1178156c473b45cb9b10205b39e46faa)

---

#### Special_Proxy
* ##### AuthKey
````
1. 目前多个地方去广告等需要使用 AuthKey 进行认证，防止接口被拷贝盗用
2. 使用过程中需要对生成 AuthKey 的 IP 地址进行认证，所以需要选择代理服务器生成，避免直连情况下的 IP 地址的频繁变换导致认证失败
3. AuthKey 字段为接口加密数据定位符,使用 OpenSSL RSA4096 加密生成的下载用户唯一权限标识符
4. 无 AuthKey 将导致无法请求接口返回 400 错误，AuthKey 包含唯一信息,请求过多将导致 AuthKey 加入黑名单
5. 网络请求 Header 可以看到 I P及 TimeStamp 信息
````

* ##### Google
````
某些服务器/节点访问 Google 将会出现验证码，开启此功能为 Google 选择一个单独的节点
````

* ##### Netflix
````
某些服务器/节点不可以观看 Netflix，开启此功能为 Netflix 选择一个单独的节点
````

* ##### MytvSUPRE
````
某些服务器/节点不可以观看 MytvSUPRE，开启此功能为 MytvSUPRE 选择一个单独的节点
````

* ##### Spotify
````
某些服务器/节点的 Spotify 的内容不同，开启此功能为 Spotify 选择一个单独的节点

---

#### Features_Module
* ##### Adblocker
````
关闭此功能将不再屏蔽广告
````

* ##### TestFlinght
````
开启此功能会在有只支持 TestFlinght 版本的规则时加载新规则
````

* ##### Emoji
````
关闭此功能 [Proxy Group] 则不再使用 Emoji 表情
````

---

### MitM 证书的安装及信任
````
简介：MitM（即 Man-in-the-middle attack 简称 MitM，用于解密 HTTPS 的流量）

安装：
* Surge：配置 - 编辑配置 - HTTPS 解密 - 安装证书
* Shadowrocket：设置 - 证书 - 安装证书

信任：
设置 - 通用 - 关于本机 - 证书信任设置 - 信任

````
---

### line

购买翻墙服务：[https://爱兔联盟.com](https://爱兔联盟.com)

---

### Hosts
````
https://async.be/Rule/Basic/Hosts

（免服务器 / 自动更新 ／ 支持 google、instagram、twitter 等主流外网）
````
---

### Android SSR ACL
````
项目主页：https://github.com/ACL4SSR/ACL4SSR

1. banAD.acl（默认代理）去广告+局域网直连+国内IP段直连+国内常用域名直连+国外代理
https://raw.githubusercontent.com/ACL4SSR/ACL4SSR/master/banAD.acl
	
2. gfwlist-banAD.acl（默认直连）去广告+局域网直连+国外gfwlist列表代理
https://raw.githubusercontent.com/ACL4SSR/ACL4SSR/master/gfwlist-banAD.acl

3. onlybanAD.acl（默认代理）去广告+局域网直连+全局代理
https://raw.githubusercontent.com/ACL4SSR/ACL4SSR/master/onlybanAD.acl
	
4. fullgfwlist.acl（默认直连）国外gfwlist列表代理，没有去广告，没有白名单（原版SS可直接复制文件内容使用）
https://raw.githubusercontent.com/ACL4SSR/ACL4SSR/master/fullgfwlist.acl
	
5. backcn-banAD.acl（默认直连）去广告+国内IP段代理+国内常用域名代理+局域网直连+国外直连
https://raw.githubusercontent.com/ACL4SSR/ACL4SSR/master/backcn-banAD.acl
````
---

### 浏览器广告
````
Adguard：https://adguard.com/en/welcome.html
````
---

### Q&A

#### ☁️ Proxy & 🔰 Proxy & 🍎 Proxy
````
☁️ Proxy：管控国外的流量；🌍 Direct - 直连，不可访问外网；代理服务器 - 可访问外网

🔰 Proxy：管控国内的流量；🌍 Direct - 智能分流 (Pac)；☁️ Proxy - 全局代理

🍎 Proxy： 管控苹果的流量；如果苹果某些服务直连困难，设其为代理，可能会改善一些问题：🍎 Proxy - 代理服务器

建议 ： ☁️ Proxy - 代理服务器；🔰 Proxy - 🌍 Direct ；🍎 Proxy - 🌍 Direct/代理服务器
````

#### 🚀 [混淆模式](https://github.com/breakwa11/shadowsocks-rss/blob/master/ssr.md)
````
理论上开启混淆模式的时候可以利用混淆做到乱序大小的发送和接收，至少可以在某种程度上可以避开 GFW 的探测，那就应当会获得更好的速度、稳定性以及安全性。
````

#### 🔋 Surge 耗电
````
Surge 会接管全局的（几乎）所有通信，所以所有的网络方面电量消耗都会被算在 Surge 头上，实际使用中不会感到 Surge 对电量有明显影响。
````

#### ☑️ Set as System Proxy
````
启用 Surge for Mac 后勾选下拉菜单中的 Set as System Proxy 即可自动向系统网络设置添加必要的参数，因为需要修改系统网络设置，首次勾选时需要输入管理员密码进行确认，去掉 Set as System Proxy 的勾选，会清除网络设置中的代理相关设置
````

#### 📶 [Surge 开启共享模式](https://medium.com/@scomper/局域网其他设备共享上网-dd29e18853da#.6w19tdsh9)
````
Surge 在增加了代理共享模式，只需要开启就能让 Wi-Fi 网络中的其他设备通过这台 iPhone 代理访问网络

到高级设置中开启 Allow Wi-Fi Access ，或者直接修改配置文件，添加一行参数 allow-wifi-access = true

其他 Wi-Fi 网络环境下的设备可以输入已经开启共享代理的 Surge 设备的 IP 地址和端口号，（技巧：Surge Log 中能看到开启后本机的 IP 地址和监听端口）将 IP 地址填写到需要共享设备的 Wi-Fi 信息的 HTTP 代理里即可
````

#### 🏃 Auto
````
测试结果仅供参考，无法检测出 VPS 的带宽

请不要使用 google.com 作为测试目标，有可能导致 proxy 服务器 ip 被加入黑名单，导致各种操作需要输入验证码
目标 URL 对所有的 policy 是基本公平的，所以请选择像 gstatic.com 这样的在全球都有节点的 URL 作为测试目标
作者建议：http://www.gstatic.com/generate_204
````
---

#### 客户端（有“R”标示表示支持 SSR）：
````
• iOS

Surge：https://appsto.re/cn/D0Q_9.i

Shadowrocket (R)：https://appsto.re/cn/UDjM3.i
        
• Android

ShadowsocksR (R)：https://github.com/shadowsocksr/shadowsocksr-android/releases

Postern (R)：http://www.tunnel-workshop.com

• macOS

ShadowsocksX：https://github.com/shadowsocks/shadowsocks-iOS/releases

ShadowsocksX-R (R)：https://github.com/yichengchen/ShadowsocksX-R/releases

ShadowsocksX-NG (R)：https://github.com/qinyuhang/ShadowsocksX-NG/releases

Flora：https://github.com/huacnlee/flora-kit

Specht Lite：https://github.com/zhuhaow/SpechtLite/releases
        
Surge：http://nssurge.com

• Windows
    
ShadowsocksR (R)：https://github.com/shadowsocksr/shadowsocksr-csharp/releases
````

---

📋 教程 / 说明：
````
Surge for iOS：https://medium.com/@scomper/surge-配置文件-a1533c10e80b#.9fpdjn34f
    
Surge for macOS：https://medium.com/@scomper/surge-for-mac-简明指南-f6f357b8f09c#.n55zdnvnd

Shadowrocket for iOS：http://matrix.sspai.com/p/c113cba0
    
SSR for Windows：https://ocvpn.wordpress.com/2016/10/15/shadowsocksr-for-windows设置教程
    
SSR for Android：https://yhyy135.github.io/how-to-use-ssr-android/
    
Specht Lite for macOS：http://www.jianshu.com/p/2acfcbfee27f
````

---
### 配置文件样例
````
# Surge Config Example (Chinese)
# Version 2.0

[General]
# 日志等级: warning, notify, info, verbose (默认值: notify)
loglevel = notify
# 跳过某个域名或者 IP 段，这些目标主机将不会由 Surge Proxy 处理。(在 macOS 
# 版本中，如果启用了 Set as System Proxy,  那么这些值会被写入到系统网络代理
# 设置中.)
skip-proxy = 127.0.0.1, 192.168.0.0/16, 10.0.0.0/8, 172.16.0.0/12, 100.64.0.0/10, localhost, *.local
# 强制使用特定的 DNS 服务器
dns-server = 8.8.8.8, 8.8.4.4
# 允许外部控制器访问 Surge， 如 Surge-CLI。
external-controller-access = apassword@127.0.0.1:8888

# 以下参数仅供 iOS 版本使用
# 将系统相关请求交给 Surge TUN 处理，并自动追加规则 
# "IP-CIDR,17.0.0.0/8,DIRECT,no-resolve"
bypass-system = true
# 将特定 IP 段跳过 Surge TUN，详见 Manual
bypass-tun = 192.168.0.0/16, 10.0.0.0/8, 172.16.0.0/12
# 是否启动完整的 IPv6 支持 (默认值: false)
ipv6 = false

# 以下参数仅供 macOS 版本使用
# 监听地址 (默认值: 127.0.0.1)
interface = 0.0.0.0
# HTTP 服务端口 (默认值: 6152)
port = 6152
# SOCKS5 监听地址 (默认值: 127.0.0.1)
socks-interface = 0.0.0.0
# SOCKS5 服务端口 (默认值: 6153)
socks-port = 6153

# 该段定义可用的代理策略
# 针对所有类型代理的选项:
#   interface: 可选 (默认值: null)
#   强制使用特定的出口地址或网络设备 (仅 macOS 版可用)
#   例如: ProxyHTTP = http, 1.2.3.4, 443, username, password, interface = en2
#        en1 = direct, interface = en1
# 针对启用了 TLS 的代理的选项:
#   skip-common-name-verify: "true" 或 "false" (默认值: false)
#   如果启动该选择, Surge 不会校验证书名是否符合.
[Proxy]
ProxyHTTP = http, 1.2.3.4, 443, username, password, skip-common-name-verify=false
ProxyHTTPS = http, 1.2.3.4, 443, username, password, tls=true // 等价于 "https, 1.2.3.4, 443, username, password"
ProxySOCKS5 = socks5, 1.2.3.4, 443, username, password
ProxySOCKS5TLS = socks5, 1.2.3.4, 443, username, password, tls=true

# 该段定义可用的策略组
# 一个策略组可以包括多个子策略. 
# 子策略可以是一个代理策略，或者另一个策略组，或者是一个内置策略 (DIRECT 或 REJECT).
# 有 3 种策略组类型: "select", "url-test" 和 "ssid"
# select: 具体哪个子策略将被使用，由用户界面上进行选择。
# url-test: 具体哪个子策略将被使用，通过测试到具体 URL 的访问速度选择
#   参数:
#   url: 必填
#   测试时用到的目标 URL.
#   interval: 可选, 秒 (默认值: 600s)
#   指定在多长时间后，上次的测试结果将被抛弃。
#   tolerance: 可选, 毫秒 (默认值: 100ms)
#   只有当新的优选线路，比原优选线路的响应时间，大于该值的时候，才会触发线路变更。
#   timeout: 可选, 秒 (默认值: 5s)
#   如果某策略在该时间后依然没有完成，放弃该策略。
# ssid: 具体哪个子策略将被使用，根据 Wi-FI 的 SSID 决定
#   参数:
#   default: 必填
#   默认策略。
#   cellular: 可选
#   在数据网络下的策略。 若不填，那么默认策略将被使用。
[Proxy Group]
SelectGroup = select, ProxyHTTP, ProxyHTTPS, DIRECT, REJECT
AutoTestGroup = url-test, ProxySOCKS5, ProxySOCKS5TLS, url = http://www.google.com/generate_204
SSIDGroup = ssid, default = ProxyHTTP, cellular = ProxyHTTP, SSIDName = ProxySOCKS5

# 该段定义请求处理规则
# 一个规则有三个基础部分:
#          类型,          值,            策略
# 比如:     DOMAIN-SUFFIX,apple.com,     DIRECT
#          IP-CIDR,      192.168.0.0/16,ProxyA
# 有 3 种基于域名的规则: "DOMAIN", "DOMAIN-SUFFIX" 和 "DOMAIN-KEYWORD"
#   参数:
#   force-remote-dns: 可选 (默认值: false)
#   如果某请求被该规则匹配, 且策略不是DIRECT. 那么 DNS 查询将永远在远端代理服务
#   器执行, 即使该请求由 Surge TUN 处理. 
#   更多信息请参见手册.
# 有 2 种基于 IP 的规则: "IP-CIDR" and "GEOIP".
# 如果是一个使用域名进行访问的请求，那么 Surge 将进行 DNS 查询以确认是否应该被
# 该规则匹配. 若 DNS 查询失败，将放弃规则匹配过程并直接给出错误。
#   OPTIONS:
#   no-resolve: 可选 (默认值: false)
#   如果是一个使用域名进行访问的请求，跳过该条规则，不触发 DNS 查询。
[Rule]
DOMAIN-SUFFIX,appldnld.apple.com,DIRECT
DOMAIN-SUFFIX,adcdownload.apple.com,DIRECT
DOMAIN-SUFFIX,swcdn.apple.com,DIRECT
DOMAIN-SUFFIX,phobos.apple.com,DIRECT

DOMAIN-KEYWORD,google,ProxyHTTP,force-remote-dns
DOMAIN-KEYWORD,facebook,SelectGroup
DOMAIN-KEYWORD,blogspot,AutoTestGroup
DOMAIN-KEYWORD,youtube,SSIDGroup

DOMAIN-SUFFIX,apple.com,ProxyHTTPS
DOMAIN-SUFFIX,ad.com,REJECT

IP-CIDR,192.168.0.0/16,DIRECT,no-resolve
IP-CIDR,10.0.0.0/8,DIRECT
IP-CIDR,172.16.0.0/12,DIRECT
IP-CIDR,127.0.0.0/8,DIRECT

GEOIP,CN,DIRECT
FINAL,ProxyHTTP

# 该段定义本地 DNS 记录
# 该功能等同于 /etc/hosts，加上了泛解析和别名支持。
[Host]
abc.com = 1.2.3.4
*.dev = 6.7.8.9
foo.com = bar.com
bar.com = server:8.8.8.8
computer = server:system

# 该段定义针对 HTTP 请求的 URL 重定向规则
# 有两种重定向方式: "header" 和 "302"
# 
# Header 模式
# Surge 会修改发出的 http header，必要时还会修改 Host 字段。客户端将
# 感知不到这个重定向过程. 不支持重定向到一个 HTTPS 的地址。
# 
# 302 模式
# Surge 直接简单的返回一个 302 重定向回应。
[URL Rewrite]
^http://www.google.cn http://www.google.com header
^http://yachen.com https://yach.me 302

# 该段仅在 iOS 版本下生效。 
# 你可以为某些特定的 WiFi 网络设置设置参数
# 参数:
# suspend: "true" 或 "false"
# 在该网络下 Surge 将暂停工作。 请注意，如果你在该网络下直接启动 Surge，那么 
# Surge 依然会工作。只有当从其他网络切换到该网络时，Surge 才会暂停。
[SSID Setting]
"SSID Here" suspend=true

# 详细使用方法请参见使用手册: http://manual.nssurge.com/mitm.html
[MITM]
enable = true
# Surge 仅会对在此定义的主机名进行 HTTPS 解密，允许使用 * 通配符。
# 某些应用会使用加强的安全策略，仅允许特定的服务器证书或者 CA。启动 MitM 可能
# 导致这些应用出现问题。
hostname = *google.com
ca-p12 = MIIJtQ.........
ca-passphrase = password
````
---
        
### 鸣谢
* [@Eval](https://twitter.com/OAuth4)
* [@Scomper](https://medium.com/@scomper)
* [@Neurogram](http://www.taguage.com/user?id=181456)
* @suisr9255
* [@Hackl0us](https://github.com/Hackl0us)

---

### License
* 可以拷贝、转发，但是必须提供原作者信息，同时也不能将本项目用于商业用途。
