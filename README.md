Cloudflare API v4 Dynamic DNS Update in Bash, without unnecessary requests
Now the script also supports v6(AAAA DDNS Recoards)

```
# incorrect api-key results in E_UNAUTH error
# 填写 Global API Key
CFKEY=

# Username, eg: user@example.com
# 填写 CloudFlare 登陆邮箱
CFUSER=

# Zone name, eg: example.com
# 填写需要用来 DDNS 的一级域名
CFZONE_NAME=

# Hostname to update, eg: homeserver.example.com
# 填写 DDNS 的二级域名(只需填写前缀)
CFRECORD_NAME=

#首次运行脚本,输出内容会显示当前IP，进入cloudflare查看 确保IP已变更为当前IP
./cf-v4-ddns.sh

#定时任务，每两分钟执行一次
*/2 * * * * /root/cf-v4-ddns.sh >/dev/null 2>&1

#如果需要日志，替换上一行代码
*/2 * * * * /root/cf-v4-ddns.sh >> /var/log/cf-ddns.log 2>&1

#参考文章：
https://www.imiku.com/archives/330.html

```
