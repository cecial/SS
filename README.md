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

在Centos 7 上，有firewalld 需要先关闭（未证实）</br>
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

linux ternimal 全局代理 <br>
bash 环境 <br>
export ALL_PROXY=socks5://127.0.0.1:1080


NFP v2ray clients <br>
{
  "inbound": {
    "port": 1080, // 监听端口
    "protocol": "socks", // 入口协议为 SOCKS 5
    "domainOverride": ["tls","http"],
    "settings": {
      "auth": "noauth"  //socks的认证设置，noauth 代表不认证，由于 socks 通常在客户端使用，所以这里不认证
    }
  },
  "outbound": {
    "protocol": "vmess", // 出口协议
    "settings": {
      "vnext": [
        {
          "address": "155.94.190.222", // 服务器地址，请修改为你自己的服务器 IP 或域名
          "port": 19725,  // 服务器端口
          "users": [
            {
              "id": "6ace462f-d47f-43d7-a346-15745a171c70",  // 用户 ID，必须与服务器端配置相同
              "alterId": 64 // 此处的值也应当与服务器相同
            }
          ]
        }
      ]
    },
	"streamSettings": {
      "network": "mkcp",
      "kcpSettings": {
        "mtu": 1350,
        "tti": 20,
        "uplinkCapacity": 100,
        "downlinkCapacity": 100,
        "congestion": true,
        "readBufferSize": 1,
        "writeBufferSize": 1,
        "header": {
          "type": "none"
        }
      }
    }
  }
}

<br>

Google Cloud V2ray clients <br>
// Config file of V2Ray. This file follows standard JSON format, with comments support.
// Uncomment entries below to satisfy your needs. Also read our manual for more detail at
// https://www.v2ray.com/
{
  "log": {
    // By default, V2Ray writes access log to stdout.
    // "access": "/path/to/access/log/file",

    // By default, V2Ray write error log to stdout.
    // "error": "/path/to/error/log/file",

    // Log level, one of "debug", "info", "warning", "error", "none"
    "loglevel": "none"
  },
  // List of inbound proxy configurations.
  "inbounds": [{
    // Port to listen on. You may need root access if the value is less than 1024.
    "port": 1080,

    // IP address to listen on. Change to "0.0.0.0" to listen on all network interfaces.
    "listen": "127.0.0.1",

    // Tag of the inbound proxy. May be used for routing.
    "tag": "socks-inbound",

    // Protocol name of inbound proxy.
    "protocol": "socks",

	//"domainOverride": ["tls","http"],
	
    // Settings of the protocol. Varies based on protocol.
    "settings": {
      "auth": "noauth",
      "udp": true,
      "ip": "127.0.0.1"
    }
  }],
  // List of outbound proxy configurations.
  "outbounds": [{
    // Protocol name of the outbound proxy.
    "protocol": "vmess",

    // Settings of the protocol. Varies based on protocol.
    "settings": {
      "vnext": [
        {
          "address": "35.220.246.243", // 服务器地址，请修改为你自己的服务器 IP 或域名
          "port": 19725,  // 服务器端口
          "users": [
            {
              "id": "716ba90e-4974-439a-87c0-b2f756958c88",  // 用户 ID，必须与服务器端配置相同
              "alterId": 64 // 此处的值也应当与服务器相同
            }
          ]
        }
      ]
	},
	"streamSettings": {
      "network": "mkcp",
      "kcpSettings": {
        "uplinkCapacity": 100,
        "downlinkCapacity": 100,
        "congestion": true,
        "header": {
          "type": "none"
        }
      }
    }
  }]
}


