#### cf-proxy
---
> cloudflare 不仅仅是全球最大的dns服务商，还可以免费为网站提供cdn加速代理服务

##### cf代理的过程   
修改domain的ns到cf提供的ns地址，即可接入域名到cf中，访问域名时由cf提供dns解析服务   
另外cf还有一个重要的功能，可以提供免费的proxy服务, 
整体的过程是:   
![process](../image/cfproxy1.png)

##### cf代理的好处  
假设你的域名是：`http://a.xxx.com`, 服务器的公网ip是 1.1.1.1, 在代理之前通过 nslookup 查询域名的ip，依旧是 1.1.1.1   
在启用了cfproxy之后，nslookup查询的ip则是cf的cdn ip，这样有下面几个好处:
- 可以隐藏网站的真实服务器ip地址，可以一定程度上防止服务器被攻击（得益于cf的免费代理）   
- 可以极大的优化网站的访问速度，因为cf的cdn服务器遍布全球，不管是哪个地区的用户访问都可用获取到很好的加速服务，尤其是网站的静态资源都会有缓存

##### cf代理的限制
一般情况下，cf可以代理网站的 http/https 请求，但是对于端口有一些限制     

**对于http请求，cf可以代理的端口如下：**
- 80
- 8080
- 8880
- 2052
- 2082
- 2086
- 2095   

**对于https请求，cf可以代理如下端口:**
- 443
- 2053
- 2083
- 2087
- 2096
- 8443  

当然最好的情况是将你的服务运行在 80、443端口，如果有其他需求，需要对照上面的要求，将服务运行到可以代理的端口   

> 具体的文档说明：https://developers.cloudflare.com/fundamentals/reference/network-ports/

同时这些端口的将不会提供缓存:
- 2052
- 2053
- 2082
- 2083
- 2086
- 2087
- 2095
- 2096
- 8880
- 8443


