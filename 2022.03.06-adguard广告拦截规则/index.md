# adguard广告拦截规则分享


> 转载，侵删。本文由 [简悦 SimpRead](http://ksria.com/simpread/) 转码， 原文地址 [chjina.com](https://chjina.com/archives/11/)

> Ad Guard 过滤规则最近用上了 Ad Guard , 发现软件里面显示的屏蔽的记录还挺多的。遂分享下收集的规则和 DNS 官方网站及项目地址 AdGuard 官网：https://adguard.c...

最近用上了 Ad Guard , 发现软件里面显示的屏蔽的记录还挺多的。遂分享下收集的规则和 DNS  
![](https://cdn.jsdelivr.net/gh/xyzz-by/imge@main/2021/02/20210302231620.png)  
官方网站及项目地址  
AdGuard 官网：[https://adguard.com](https://adguard.com/)  
AdGuardHome 项目地址：[https://github.com/AdguardTeam/AdGuardHome](https://github.com/AdguardTeam/AdGuardHome)  
现在记录下日常使用的规则

anti-AD （推荐）
------------

*   规则
    
    *   GitHub：  
        [https://raw.githubusercontent.com/privacy-protection-tools/anti-AD/master/anti-ad-easylist.txt](https://raw.githubusercontent.com/privacy-protection-tools/anti-AD/master/anti-ad-easylist.txt)
    *   官网地址：  
        [https://anti-ad.net/easylist.txt](https://anti-ad.net/easylist.txt)

乘风规则 （推荐）
---------

简介：xinggsf，乘风广告过滤规则（含贴吧, 屏蔽电信挟持弹窗）

*   广告规则

[https://gitee.com/xinggsf/Adblock-Rule/raw/master/rule.txt](https://gitee.com/xinggsf/Adblock-Rule/raw/master/rule.txt)

*   视频规则

[https://gitee.com/xinggsf/Adblock-Rule/raw/master/mv.txt](https://gitee.com/xinggsf/Adblock-Rule/raw/master/mv.txt)

*   其他规则

[https://raw.githubusercontent.com/xinggsf/Adblock-Plus-Rule/master/ABP-FX.txt](https://raw.githubusercontent.com/xinggsf/Adblock-Plus-Rule/master/ABP-FX.txt)

ADgk（针对安卓手机**推荐**）
------------------

简介：适用于 AdGuard for Android 的去广告规则

*   规则

[https://raw.githubusercontent.com/banbendalao/ADgk/master/ADgk.txt](https://raw.githubusercontent.com/banbendalao/ADgk/master/ADgk.txt)

cjx82630
--------

简介：无

*   规则

[https://gitee.com/cjx82630/cjxlist/raw/master/cjx-annoyance.txt](https://gitee.com/cjx82630/cjxlist/raw/master/cjx-annoyance.txt)

知乎（探索版）
-------

简介：无

*   普通版

[https://raw.githubusercontent.com/zsakvo/AdGuard-Custom-Rule/master/rule/zhihu.txt](https://raw.githubusercontent.com/zsakvo/AdGuard-Custom-Rule/master/rule/zhihu.txt)

*   严格版

[https://raw.githubusercontent.com/zsakvo/AdGuard-Custom-Rule/master/rule/zhihu-strict.txt](https://raw.githubusercontent.com/zsakvo/AdGuard-Custom-Rule/master/rule/zhihu-strict.txt)

其他规则
----

*   HalfLife，规则合并自 EasylistChina、EasylistLite、CJX’sAnnoyance 合并规则 (**推荐**)

[https://halflife.coding.net/p/list/d/list/git/raw/master/ad.txt](https://halflife.coding.net/p/list/d/list/git/raw/master/ad.txt)

*   EasyPrivacy : EasyPrivacy 是隐私保护，不被跟踪（**推荐**）

[https://easylist-downloads.adblockplus.org/easyprivacy.txt](https://easylist-downloads.adblockplus.org/easyprivacy.txt)

*   EasyList China : 国内网站广告过滤的主规则

[https://easylist-downloads.adblockplus.org/easylistchina.txt](https://easylist-downloads.adblockplus.org/easylistchina.txt)

*   EasyList ：去广告主规则列表。主要面向英文网站，包含大量通用规则

[https://easylist-downloads.adblockplus.org/easylist.txt](https://easylist-downloads.adblockplus.org/easylist.txt)

*   CJX’s Annoyance List : 过滤烦人的自我推广，并补充 EasyPrivacy 隐私规则

[https://raw.githubusercontent.com/cjx82630/cjxlist/master/cjx-annoyance.txt](https://raw.githubusercontent.com/cjx82630/cjxlist/master/cjx-annoyance.txt)

*   don’t care about cookies：我不关心 Cookie 的问题，屏蔽网站的 cookies 相关的警告

[https://www.i-dont-care-about-cookies.eu/abp/](https://www.i-dont-care-about-cookies.eu/abp/)

*   大圣净化（主要针对国内视频网站）

[https://raw.githubusercontent.com/jdlingyu/ad-wars/master/hosts](https://raw.githubusercontent.com/jdlingyu/ad-wars/master/hosts)

*   yhosts(国内维护者屏蔽国内网站广告)

[https://raw.githubusercontent.com/vokins/yhosts/master/hosts](https://raw.githubusercontent.com/vokins/yhosts/master/hosts)

小计
--

如果你觉得过滤得还不够，也可以在 “自定义过滤器规则” 按照以下过滤规则自己编写：

```
||example.org^ – 拦截 example.org 域名及其所有子域名
@@||example.org^ – 放行 example.org 及其所有子域名
127.0.0.1 example.org – 将会把 example.org（但不包括它的子域名）解析到 127.0.0.1
! 注释符号，表示这是一行注释

这也是注释符号，同样表示这是一行注释

/REGEX/ – 正则表达式模式
```

AdGuard Home 优化部署
-----------------

一、上游 DNS 设置

1、不使用 ISP 默认 DNS 的好处是可以避免 ISP 通过 DNS 分析和掌握你的上网行为。我们把上游 DNS 更换成 DNS over TLS 的：

```
tls://dns.adguard.com tls://dns.quad9.net

tls://dns.google 

tls://1.1.1.1

tls://1.0.0.1
```

2、当然，你也可以使用其他的公共 DNS，不过国内公共的 DNS 暂不支持 DNS over TLS（博主用的是 223.5.5.5），比如：

```
223.5.5.5

223.6.6.6 

114.114.114.114

114.114.115.115 

119.29.29.29 

119.28.28.28

180.76.76.76
```

3、如果你想启用 ipv6 的 DNS，可以添加以下几个（但是启用 ipv6 后，不能过滤视频中的广告）：

```
2409:8028:2000::1111 

2409:8028:2000::2222

2620:0:ccc::2 2620:0:ccd::2
```

> 最后
> --
> 
> 感谢各位大佬的辛勤付出
> -----------

参考：

```
1.https://github.com/otobtc/ADhosts/blob/master/README.md
    2.https://github.com/233Bazinga/AdGuardHome
    3.https://wp.gxnas.com/4393.html
```
