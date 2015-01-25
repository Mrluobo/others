# CentOS7安装nginx,io.js小记

标签（空格分隔）： io.js nginx CentOS7

---
为什么用CentOS7?
新的io.js需要gcc4.8以上才能编译，对于我这种菜逼来说显然太过吃力。开始尝试着用CentOS6.5进行gcc升级，然后安装，折腾了好久最终放弃治疗。而 CentOS7已经自带gcc4.8.2，所以干脆全换了吧，而且毕竟新的好。
##安装nginx
nginx在用普通的编译安装的方式各种报错，查了好久依旧放弃治疗，真不是我懒，是真的弄不明白。最后选择用`yum`进行安装。
###yum换源
yum的自带源里面并没有nginx所以:
```
wget https://dl.fedoraproject.org/pub/epel/7/x86_64/e/epel-release-7-5.noarch.rpm
```
获取到EPEL7的源。
```
rpm -ivh epel-release-7-5.noarch.rpm
yum repolist all
```
安装EPEL7源。
```
yum install nginx
```
安装nginx。
值得一提的是在CentOS里使用systemctl来代替旧的service命令。所以原来的
```
service nginx start
```
要使用
```
systemctl start nginx.service
```
来代替。具体可以看[Linux Systemd——在RHEL/CentOS 7中启动/停止/重启服务](http://www.linuxidc.com/Linux/2014-08/105975.htm)。
##安装io.js
io.js如果直接从iojs.org上下载的是已经编译好的。换句话说就是我不会用的。所以安装io.js需要先从github上clone。
CentOS并没有自带git,所以要先安装git。
```
yum install git
```
安装之后就要从github上将io.js clone下来。
```
git clone https://github.com/iojs/io.js.git
```
进入io.js
```
cd io.js
```
configure
```
./configure
```
可能会报错，需要安装gcc-c++
```
yum install gcc-c++
```
再次configure
```
./configure
```
成功，然后编译
```
make
```
时间比较长，这期间可以去上个厕所喝喝茶什么的。成功之后安装。
```
make install
```
然后`iojs -v`测试是否安装成功。




