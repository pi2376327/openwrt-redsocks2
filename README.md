RedSocks2 for OpenWrt
===

简介
---

 本项目是 [RedSocks2][1] 在 OpenWrt 上的移植  
 当前版本: 0.66-1  
  

编译
---

 - 从 OpenWrt 的 [SDK][S] 编译  

   ```bash
   # 以 ar71xx 平台为例
   tar xjf OpenWrt-SDK-ar71xx-for-linux-x86_64-gcc-4.8-linaro_uClibc-0.9.33.2.tar.bz2
   cd OpenWrt-SDK-ar71xx-*
   # 获取 Makefile
   git clone https://github.com/pi2376327/openwrt-redsocks2.git package/redsocks2
   # 更新feeds ./scripts/feeds update -a
   # 安装依赖./scripts/feeds install libevent
   # 选择要编译的包 Network -> redsocks2
   make menuconfig
   # 开始编译
   make package/redsocks2/compile V=99
   ```
修改Makefile为最新realease版本
---

   ```bash
   #去原作者github查看最新realease版本
   https://github.com/semigodking/redsocks/releases
   #修改Makefile中PKG_VERSION:后的版本值
   #将0.66改成最新realease版本
   wget https://github.com/semigodking/redsocks/archive/release-0.66.tar.gz
   #找出gz源码包的md5校验码
   find /release-0.66.tar.gz |xargs md5sum|sort
   #修改Makefile中PKG_MD5SUM::后的md5校验码
   ```
----------
