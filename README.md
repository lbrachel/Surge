# Surge.conf / Shadowrocket.conf

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

♻️ Download

    User Data：https://workflow.is/workflows/7100cebf06ad4adead9aac76e45e50b2

    Rule OTA：https://workflow.is/workflows/5506a2e1fe68496a92ed9087475e1b25


    Surge 视频教程：https://youtu.be/IRJOAnPZWJM

    Shadowrocket 视频教程：https://youtu.be/nPFHi99PYww

    PS：基于 爱兔联盟.com 提供的节点快速获取并使用



    Hosts：https://async.be/Rule/Basic/Hosts
    （免服务器 / 自动更新 ／ 支持 google、instagram、twitter 等主流外网）

    Telegram：https://telegram.me/rulenews
    （更新日志 / 新内容发布 ／ 更方便快捷获取更新内容 ／ 进阶功能教程）

🤖️ Android SSR ACL

	ACL4SSR：https://github.com/ACL4SSR/ACL4SSR

🈲️ 浏览器广告

    全平台：Adguard - https://adguard.com/en/welcome.html
    
    
# line

About | Raw |
---------|:---------:
新浪微博 | [@lhie1](http://www.weibo.com/1748625493)
Telegram 讨论组| https://telegram.me/lhie1x
Telegram 通知频道| https://t.me/rulenews
购买翻墙服务| [爱兔联盟（通往新宇宙的船票）](https://爱兔联盟.com)

Tutor | Raw |
---------|:---------:
@Eval | https://twitter.com/OAuth4
@Scomper| https://medium.com/@scomper
@Neurogram| http://www.taguage.com/user?id=181456
@suisr9255| -
@Hackl0us| https://github.com/Hackl0us
    

# Q&A

### ☁️ Proxy & 🔰 Proxy & 🍎 Proxy

	☁️ Proxy：管控国外的流量；🌍 Direct - 直连，不可访问外网；代理服务器 - 可访问外网

    🔰 Proxy：管控国内的流量；🌍 Direct - 智能分流 (Pac)；☁️ Proxy - 全局代理

    🍎 Proxy： 管控苹果的流量；如果苹果某些服务直连困难，设其为代理，可能会改善一些问题：🍎 Proxy - 代理服务器

    建议 ： ☁️ Proxy - 代理服务器；🔰 Proxy - 🌍 Direct ；🍎 Proxy - 🌍 Direct/代理服务器


#### 🚀 SSR 混淆模式 https://github.com/breakwa11/shadowsocks-rss/blob/master/ssr.md

    理论上开启混淆模式的时候可以利用混淆做到乱序大小的发送和接收，至少可以在某种程度上可以避开GFW的探测，那就应当会获得更好的速度、稳定性以及安全性。


#### 🔋 Surge for iOS 耗电

    Surge 会接管全局的（几乎）所有通信，所以所有的网络方面电量消耗都会被算在 Surge 头上，实际使用中不会感到 Surge 对电量有明显影响。

#### ☑️ Set as System Proxy

    启用 Surge for Mac 后勾选下拉菜单中的 Set as System Proxy 即可自动向系统网络设置添加必要的参数，因为需要修改系统网络设置，首次勾选时需要输入管理员密码进行确认，去掉 Set as System Proxy 的勾选，会清除网络设置中的代理相关设置。


#### 📶 Surge for iOS 开启共享模式 https://medium.com/@scomper/局域网其他设备共享上网-dd29e18853da#.6w19tdsh9

    Surge 在增加了代理共享模式，只需要开启就能让 Wi-Fi 网络中的其他设备通过这台 iPhone 代理访问网络。
    到高级设置中开启 Allow Wi-Fi Access ，或者直接修改配置文件，添加一行参数 allow-wifi-access = true。

    其他 Wi-Fi 网络环境下的设备可以输入已经开启共享代理的 Surge 设备的 IP 地址和端口号，（技巧：Surge Log 中能看到开启后本机的 IP 地址和监听端口）将 IP 地址填写到需要共享设备的 Wi-Fi 信息的 HTTP 代理里即可。


#### 🛠Auto Test Group / Benchmarik

    测试结果仅供参考，无法检测出 VPS 的带宽

    请不要使用 google.com 作为测试目标，有可能导致 proxy 服务器 ip 被加入黑名单，导致各种操作需要输入验证码。
    目标 URL 对所有的 policy 是基本公平的，所以请选择像 gstatic.com 这样的在全球都有节点的 URL 作为测试目标。
    作者建议：http://www.gstatic.com/generate_204
