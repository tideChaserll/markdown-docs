## vpn使用
---

### 一， 使用免费节点
> 获取市面上免费的节点，进行筛选使用

。。。

---

### 二， 使用cf worker/pages 构建免费节点
> 使用 cf 的 workers/pages 搭建节点，最多只需要一个域名

。。。

---

### 三， vps + cf 搭建节点
> 购买各大平台的优惠vps，域名，部署x-ui服务

需要在网上进行搜索目前最优惠的vps服务商，进行购买   
目前优惠的价格大概在每年 10 $ 左右，配置在 1核 ，512 ～768mb左右   

#### 搭建步骤：
###### 1, vps安装xui:
`bash <(curl -Ls https://raw.githubusercontent.com/vaxilu/x-ui/master/install.sh) `
###### 2，访问 xui面板，创建一个节点，此时可以使用了

###### 3，(进阶)利用 cf ，搭建一个 vless + tls + ws 节点:   

1，购买域名， 将域名添加到 cf   

2，将域名的A记录解析到vps的ip   

3，使用xui申请证书（需要提供cf token， 个人资料->api令牌->查看global api令牌）, 生成的cert位于 /root/cert 中   

4，进入xui的web页面，设置中填写cert的路径，开启网站的https访问   

5，在cf中将proxy 按钮打开，此时所有的请求都会经过cf的代理转发，需要保证xui的端口在cf可代理的端口范围，才能继续通过域名访问xui面板   

6，以上处理好之后，在xui中创建一个节点：      
```
类型：vless, tls, ws
tls 证书选中上面生成的证书路径
ws 路径path随意
443 端口
```   

7， 客户端使用（v2ray):   
- host 可以改为任一cf的ip （通常需要借助工具获取到本地访问最快的cf ip）
- 协议设置->请求头 添加: `Host|xxx.xxx.com` (你的域名)
- tls设置->SNI 设置为 `xxx.xxx.com` （你的域名）

8， 常见问题:   
- xui面板显示 xray 状态不正确，需要切换 xray 版本直到正常
- cf ip优选，可在 github 获取开源项目筛选cf ip
