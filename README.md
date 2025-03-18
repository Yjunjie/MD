# MD
记录
## 如何申请证书，让用户无需安装证书？
为了避免用户手动安装证书，你可以使用 公共受信任的 CA 签发的证书。以下是几种常见方式：

### 1. 使用 Let's Encrypt（免费）
Let's Encrypt 是一个公共受信任的证书颁发机构（CA），它提供免费的 SSL/TLS 证书，且证书被所有主流浏览器和操作系统信任。

步骤：

安装 Certbot（Let's Encrypt 的官方客户端）：

<BASH>
sudo apt-get install certbot
申请证书：
对于 HTTP 服务器：

<BASH>
sudo certbot --nginx  # 如果你使用 Nginx
sudo certbot --apache  # 如果你使用 Apache
对于手动模式（适用于任何服务器）：

<BASH>
sudo certbot certonly --manual
按照提示输入域名，并完成验证。

自动续期：
Let's Encrypt 的证书有效期为 90 天。Certbot 会自动配置续期任务：

<BASH>
sudo certbot renew
优点：

完全免费。
证书被所有主流浏览器和操作系统信任。
无需用户手动操作。
