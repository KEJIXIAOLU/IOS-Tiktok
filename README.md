# 小火箭Shadowrocket 解锁 TikTok 代码

### 找到 <code>[URL Rewrite]</code> 字段，复制并粘贴Tiktok 重写规则（URL Rewrite）代码：


    [URL Rewrite]
    (?<=_region=)CN(?=&) JP 307
    (?<=&mcc_mnc=)4 2 307
    ^(https?:\/\/(tnc|dm)[\w-]+\.\w+\.com\/.+)(\?)(.+) $1$3 302
    (^https?:\/\/*\.\w{4}okv.com\/.+&.+)(\d{2}\.3\.\d)(.+) $118.0$3 302
    
    [MITM]
    hostname = *.tiktokv.com,*.byteoversea.com,*.tik-tokapi.com

### 换区操作
- 修改 <code>[URL Rewrite]</code> 下方代码中的JP，并将JP改为想看的国家/地区的2位大写英文简写US（美国）｜KR（韩国）｜UK（英国）｜TW（台湾）
  
       [URL Rewrite]
       (?<=_region=)CN(?=&) US 307
       (?<=&mcc_mnc=)4 2 307
       ^(https?:\/\/(tnc|dm)[\w-]+\.\w+\.com\/.+)(\?)(.+) $1$3 302
       (^https?:\/\/*\.\w{4}okv.com\/.+&.+)(\d{2}\.3\.\d)(.+) $118.0$3 302
       
       [MITM]
       hostname = *.tiktokv.com,*.byteoversea.com,*.tik-tokapi.com
       
       
## 抖音无法观看
- 在 <code>[mitm]</code> hostname后加上以下代码

      -*snssdk.com, -*amemv.com


  
  

### 说明:
- 香港印度节点不可用，刷不出来，建议换节点 。
- 建议看完视频，并按照视频步骤来操作
