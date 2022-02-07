# GL-iNet MT1300 路由器OpenWrt系统

## 感谢P3TERX的GitHub Actions项目，感谢Lienol和Lean两位大神所提供的插件。



基于 GL-iNet 官方19.07.7源码，添加了Lienol和Lean两位大神的部分插件。修改 .config.gl 文件触发自动编译。

1. 2021-01-21 新增从Lean源码编译的固件，修改 .config.lean 触发编译
2. 2021-03-01 新增从Lienol源码编译的固件，修改 .config.lienol 触发编译
3. 2021-08-20 新增从Immortal源码编译的固件，修改 .config.immortal 触发编译


#### 默认设置：

主机名：MT1300

IP 地址：192.168.8.1 

WIFI SSID：MT1300

WIFI 密码：password



### 基于GL源码编译：

使用19.07.07分支编译，主要插件 passwall，ssr plus，openclash

1. 2021-08-10新增psw插件和OpenClash，注意OpenClash可能会导致空间不足。

##### 已知问题：

目前GL源码的MT1300 profile不带WIFI驱动，如果需要，可以自己选择7615驱动，但是此驱动好像还有些问题：

1. 不能2.4G和5G两路WIFI，只能有1路。
2. 另外从WIFI连接不知道为什么DHCP拿不到地址。



### 基于Lean源码编译：

使用master分支，主要插件 adbyby，passwall，ssr plus，ttyd，zerotier

1. 有两路WIFI，但是需要两路相同频段和频道，否则不工作



### 基于Lienol源码编译：

使用21.02分支，主要插件 adbyby，openclash，ttyd，zerotier

1. 有两路WIFI，但是需要两路相同频段和频道，否则不工作

##### 2022-02-07备注：

Lienol源21.02源码已经恢复（从2021-08-06发现编译失败，原因是21.02代码从源中移除，什么时候恢复暂时不知道），在2022-01-25重试该编译成功。


### 基于Immortal源码编译：

使用21.02分支，主要插件 adbyby，openclash，passwall, ssr plus，ttyd, zerotier，没有samba

##### 2021-08-20备注：

由于Lienol大侠从代码库移除了20.02的源码，尝试使用Immortal的源码21.02分支进行编译。

### 最佳使用建议:
使用Immortal版本，建议只启用一路WIFI，或者两路使用相同频道。

使用Lienol版本，建议将wlan-0禁用，只使用wlan-1。如果需要设置两路WIFI，建议设置相同频道。
通过一段时间使用，目前比较稳定，建议使用OpenClash。

#### 或者

使用官方原版固件，然后下载这里基于GL官方源码编译的固件，解包后提取mt1300-plugin.tar.gz并上传到GL官方固件的临时目录并解压，然后安装ssrp或者psw。

可以同时安装ssrp和passwall，或者单独安装openclash，因为openclash占用空间比较多，请不要3个插件一起安装。

之前汇报的插件安装问题已于2021-05-05修复。

