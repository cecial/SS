# SS

Shadowsocks 一键安装脚本（四合一）</br>
https://www.bbaaz.com/forum.php?mod=viewthread&tid=9&extra=page%3D1%26filter%3Dtypeid%26typeid%3D11

wget --no-check-certificate -O shadowsocks-all.sh https://raw.githubusercontent.com/teddysun/shadowsocks_install/master/shadowsocks-all.sh</br>
chmod +x shadowsocks-all.sh</br>
./shadowsocks-all.sh 2>&1 | tee shadowsocks-all.log</br>


Shadowsocks-Python 版：
/etc/init.d/shadowsocks-python start | stop | restart | status</br>

ShadowsocksR 版：
/etc/init.d/shadowsocks-r start | stop | restart | status</br>

Shadowsocks-Go 版：
/etc/init.d/shadowsocks-go start | stop | restart | status</br>

Shadowsocks-libev 版：
/etc/init.d/shadowsocks-libev start | stop | restart | status</br>

Shadowsocks-Python 版：
/etc/shadowsocks-python/config.json</br>

ShadowsocksR 版：
/etc/shadowsocks-r/config.json</br>

Shadowsocks-Go 版：
/etc/shadowsocks-go/config.json</br>

Shadowsocks-libev 版：
/etc/shadowsocks-libev/config.json</br>

---------------------------------------------------------------------------------
=================================================================================</br>
OpenVZ魔改版BBR一键安装脚本 </br>
https://www.bbaaz.com/thread-91-1-1.html</br>

wget https://makeai.cn/master/ovz-bbr/ovz-bbr-installer.sh && chmod +x ovz-bbr-installer.sh && ./ovz-bbr-installer.sh </br>

端口文件： vi /usr/local/haproxy-lkl/etc/port-rules </br>

在Centos 7 上，有firewalld 需要先关闭（未证实）
systemctl disable firewalld </br>
systemctl stop firewalld </br>

firewalld 打开端口，（已证实可行）</br>
firewall-cmd --permanent --add-port=PORT/tcp </br>
firewall-cmd --reload </br>

=================================================================================</br>
查看端口开放，地址可用等：</br>
http://ping.pe/ 查看地址可用 </br>
https://www.yougetsignal.com/tools/open-ports/ </br>
http://tool.chinaz.com/port </br>

