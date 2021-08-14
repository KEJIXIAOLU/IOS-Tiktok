# IOS苹果手机TikTok （免拔卡）方法
### 视频教学：https://youtu.be/INujpQttw84
## 必要准备
- 1.拥有Shadowrocket 最新版本授权用户（设置-关于中查看版本：2.1.24及以上版本均可）；
- 2.并已配置有机场/服务器；
- 3.拥有非大陆地区AppleID并已下载Tiktok；

- *本教程基于 Shadowrocket 为中文的操作界面，打开Shadowrocket-Settings-Language 设置语言为Chinese/中文简体；

### 注册美国苹果ID方法：https://youtu.be/H6GtrR1OFfU
### 小火箭Shadowrocket下载和使用方法：https://youtu.be/1e7D_SGUAqY

## 详细步骤
### 第一步，生成证书文件
- 1.Shadowrocket 2.1.24（717）之后版本：配置 – 点击一个配置文件（默认是default.conf） – 编辑配置 – 开启 HTTPS 解密 – 生成新的 CA证书 – `安装证书；

- 2.点右上角 – 安装 – 输入手机锁屏密码 – 再次点右上角 – 安装 – 安装 – 右上角 – 完成；

- 3.打开手机 – 设置 – 通用 – 关于本机 – 证书信任设置 – 找到 – Shadowrocket开头的选项 – 打开右侧开关 – 弹出警告框 – 继续；

 ### 第二步，编辑配置文件
 适用：Tiktok 新版本 v19.3.0（2021.05.16）
1.打开Shadowrocket – 配置 – 找到本地文件内的配置文件，默认是default.conf （举例） – 点击 default.conf 点击编辑纯文本；

2.找到[URL Rewrite]字段，复制并粘贴Tiktok 重写规则（URL Rewrite）代码：

  [URL Rewrite]
  (?<=_region=)CN(?=&) JP 307
  (?<=&mcc_mnc=)4 2 307
  ^(https?:\/\/(tnc|dm)[\w-]+\.\w+\.com\/.+)(\?)(.+) $1$3 302
  (?<=\d\/\?\w{7}_\w{4}=)1[6-9]..(?=.?.?&) 18.4 307
  
  [MITM]
  hostname = *.tiktokv.com,*.byteoversea.com,*.tik-tokapi.com

### Shadowrocket Tiktok 如何换区操作
如果需要观看不同国家的TikTok视频，只需要修改[URL Rewrite]下方代码中的JP，比如
想看韩国的，则将代码JP改为KR，如下：
    CN $1 KR 302
    (?<=\?version_code=)16.. $11 302
