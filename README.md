<!-- This README Template See: https://github.com/othneildrew/Best-README-Template -->
<div align="center">
  <p>
    <a href="https://github.com/fordes123/ITEM">
      <img src="https://github.com/user-attachments/assets/56136bb1-fc1d-4dee-a3db-6fb8f5c64aa6" alt="Logo" width="80" height="80"></a>
    <h3 align="center">ITEM</h3></p>
  <p>网址导航仪表盘型的 Typecho 主题</p>
  <p>
    <img src="https://img.shields.io/github/v/release/fordes123/ITEM?style=flat-square" alt="last releases" />
    <img src="https://img.shields.io/github/actions/workflow/status/fordes123/ITEM/build.yaml?style=flat-square" alt="build status" />
    <img src="https://img.shields.io/github/license/fordes123/ITEM?style=flat-square" alt="license" />
    <img src="https://img.shields.io/github/contributors/fordes123/ITEM.svg?style=flat-square" alt="contributors" />
    <img src="https://img.shields.io/github/forks/fordes123/ITEM?style=flat-square" alt="forks" />
    <img src="https://img.shields.io/github/stars/fordes123/ITEM?style=flat-square" alt="stars" />
    <img src="https://img.shields.io/github/issues/fordes123/ITEM?style=flat-square" alt="open issues" /></p>
  <h4>
    <a href="#a">项目说明</a>
    <span>·</span>
    <a href="#b">快速开始</a>
    <span>·</span>
    <a href="#c">配置说明</a>
    <span>·</span>
    <a href="#d">交流反馈</a></h4>
</div>

## 修复原项目站内搜索不生效的问题

主题没有重写 /search/ 路由到主页，导致跳转到404报错

修改两处地方：

在根目录新建 .htaccess 文件，内容：

```php
<IfModule mod_rewrite.c>
    Options +FollowSymLinks
    RewriteEngine On
    RewriteBase /
    RewriteCond %{REQUEST_FILENAME} !-f
    RewriteCond %{REQUEST_FILENAME} !-d
    RewriteRule ^(.*)$ /index.php/$1 [L]
</IfModule>
```

**初始化之后**修改根目录 `config.inc.php` 文件，增加一行：

```php
/** 开启 URL 重写 */
define('__TYPECHO_REWRITE__', true);
```

现在搜索会正确跳转到 `https://daoyi.hidns.vip/search/关键词`

----

## 后台外观设置

### 搜索引擎设置

<details>
<summary>点击展开/折叠内容</summary>

```json
[
    {
        "name": "Bing",
        "url": "https://www.bing.com/search?q=",
        "icon": "fab fa-microsoft"
    },
    {
        "name": "谷歌",
        "url": "https://www.google.com/search?q=",
        "icon": "fab fa-google"
    },
    {
        "name": "百度",
        "url": "https://www.baidu.com/s?wd=",
        "icon": "fas fa-bold"
    },
    {
        "name": "Github",
        "url": "https://github.com/search?q=",
        "icon": "fab fa-github"
    },
    {
        "name": "站内搜索",
        "url": "/search/",
        "icon": "fas fa-search-location"
    }
]
```
</details>

### 工具直达

<details>
<summary>点击展开/折叠内容</summary>

```json
[
    {
        "name": "今日热榜",
        "url": "https://newsnow.busiyi.world",
        "icon": "fas fa-fire",
        "background": "linear-gradient(45deg, #e04a4a, #e6a82d)"
    },
    {
        "name": "Github",
        "url": "https://github.com",
        "icon": "fab fa-github",
        "background": "linear-gradient(45deg, #2c2f33, #4b5aa0)"
    },
    {
        "name": "Cloudflare",
        "url": "https://dash.cloudflare.com",
        "icon": "fas fa-cloud",
        "background": "linear-gradient(45deg, #e6892c, #e6b25a)"
    },
    {
        "name": "ITDog",
        "url": "https://www.itdog.cn/ping",
        "icon": "fas fa-dog",
        "background": "linear-gradient(45deg, #9440a0, #4a78c0)"
    },
    {
        "name": "谷歌测速",
        "url": "https://fiber.google.com/speedtest",
        "icon": "fas fa-tachometer-alt",
        "background": "linear-gradient(45deg, #457de0, #4ca95a)"
    },
    {
        "name": "ProxyIP检测",
        "url": "https://kaic.hidns.co/",
        "icon": "fas fa-shield-alt",
        "background": "linear-gradient(45deg, #29b0e0, #2a80e0)"
    },
    {
        "name": "IP纯净度",
        "url": "https://ping0.cc/",
        "icon": "fas fa-filter",
        "background": "linear-gradient(45deg, #409a40, #ddca44)"
    },
    {
        "name": "IP查询",
        "url": "https://ip125.com/myip/",
        "icon": "fas fa-map-marker-alt",
        "background": "linear-gradient(45deg, #596db0, #2b3870)"
    },
    {
        "name": "DNS大全",
        "url": "https://dns.icoa.cn/#china",
        "icon": "fas fa-server",
        "background": "linear-gradient(45deg, #3aa494, #63cfcf)"
    },
    {
        "name": "短链接生成",
        "url": "https://slink.yuzong.nyc.mn/duanlian",
        "icon": "fas fa-link",
        "background": "linear-gradient(45deg, #e64ce6, #4cbfdf)"
    },
    {
        "name": "订阅转换",
        "url": "https://subweb.dayutian.com/",
        "icon": "fas fa-exchange-alt",
        "background": "linear-gradient(45deg, #e64a7a, #e67b3f)"
    },
    {
        "name": "优选订阅器",
        "url": "https://dy.yomoh.ggff.net/",
        "icon": "fas fa-rss",
        "background": "linear-gradient(45deg, #e67d4f, #e6a05f)"
    },
    {
        "name": "WebSSH",
        "url": "https://ssh.yuzong.nyc.mn/",
        "icon": "fas fa-terminal",
        "background": "linear-gradient(45deg, #222222, #555555)"
    },
    {
        "name": "Cron-job",
        "url": "https://console.cron-job.org/",
        "icon": "fas fa-clock",
        "background": "linear-gradient(45deg, #7948a5, #6574a5)"
    },
    {
        "name": "兰空图床",
        "url": "https://img.811520.xyz/",
        "icon": "fas fa-images",
        "background": "linear-gradient(45deg, #4dbde0, #5a7be0)"
    },
    {
        "name": "封面图制作",
        "url": "https://cover.ruom.top/",
        "icon": "fas fa-image",
        "background": "linear-gradient(45deg, #e6809e, #e69acc)"
    },
    {
        "name": "接口调试",
        "url": "https://hoppscotch.io/",
        "icon": "fas fa-plug",
        "background": "linear-gradient(45deg, #7b87e0, #8752b8)"
    },
    {
        "name": "即时工具箱",
        "url": "https://www.67tool.com/",
        "icon": "fas fa-tools",
        "background": "linear-gradient(45deg, #4db0e0, #b04de0)"
    }
]
```
</details>

### 自定义css

<details>
<summary>点击展开/折叠内容</summary>

```css
/* 白色半透明毛玻璃效果 */
.card-header,
.card-body,
.site-wrapper,
.list-item.block {
    backdrop-filter: blur(10px) !important;
    -webkit-backdrop-filter: blur(10px) !important;
    border: 1px solid rgba(255, 255, 255, 0.3) !important;
    border-radius: 8px !important;
    box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1) !important;
}

.card-header {
    background: #565656 !important;
    margin-bottom: 0px !important;    
    padding: 9px 18px 9px 18px !important;
    border-radius: 8px 8px 0 0 !important;
}

.card-body {
    border-radius: 0 0 8px 8px !important;
}

.card-body,
.site-wrapper,
.list-item.block {
    background: rgba(255, 255, 255, 0.7) !important;
}

.card-header * {
    color: #FFFFFF !important;
}

.form-control {
  background: #E8E8E8 !important;
}

/* 暗色模式覆盖 */
[data-bs-theme="dark"] .card-header,
[data-bs-theme="dark"] .card-body,
[data-bs-theme="dark"] .site-wrapper,
[data-bs-theme="dark"] .list-item.block {
    border: 1px solid rgba(255, 255, 255, 0.1) !important;
    box-shadow: 0 4px 20px rgba(0, 0, 0, 0.3) !important;
}

[data-bs-theme="dark"] .card-header {
    background: #2D2D2D !important;
}

[data-bs-theme="dark"] .card-body,
[data-bs-theme="dark"] .site-wrapper,
[data-bs-theme="dark"] .list-item.block {
    background: rgba(30, 30, 30, 0.4) !important;
}

[data-bs-theme="dark"] .form-control {
  background: #2D2D2D !important;
}

/* 文字颜色适配 */
.card-body * {
    color: inherit !important;
}
.list-item .btn-icon i {
    color: white !important;
}
```
</details>

----

## 原项目说明

<details>
<summary>点击展开/折叠内容</summary>

<h2 id='a'>🎉 项目说明</h2>

![screenshot][screenshot]

> ✨ Hugo 版现已推出：[hugo-theme-item][hugo-theme-item]

在编程语言中，"item" 这个单词常用来代表一个元素、一个选项  
所以我们以此来命名这个网址导航主题，希望它能够承载更多的 "item"，链接每一个选项~

---

<h2 id='b'>🛠️ 快速开始</h2>

### 本地部署

1. 下载 [正式版][last-releases] 或者从工作流中获取即时构建的 [开发版][build]
2. 将解压后的主题文件重名为 <code>ITEM</code> 并移动至 Typecho 根目录<code>usr/themes</code> 文件夹中
3. 在 Typecho 管理面板中选择更换外观并启用主题

> [!WARNING]
> 必须使用 MySQL，不支持 SQLite 以及 PostgreSQL  
> 推荐 `Typecho 1.2+`、 `PHP 7.4+`、 `MySQL 8+` 低于这些版本不保证兼容性

### Vercel 部署

<a href="https://vercel.com/new/clone?project-name=ITEM&repository-name=ITEM&repository-url=https://github.com/fordes123/ITEM/tree/vercel&from=templates&integration-ids=oac_coKBVWCXNjJnCEth1zzKoF1j"><img src="https://vercel.com/button"></a>

点击上方 `Deploy` 按钮 或者 Fork 本仓库 [vercel][item-vercel] 分支并手动导入 Vercel。

> [!TIP]
> 通过 Vercel 托管需要添加一个 MySQL 集成，如 [TiDB][tidb]、[PlanetScale][planetscale]，参考: [Vercel 托管 Typecho][typecho-vercel-post]

### 本地开发

1. 安装 Docker 以及 Docker Compose 后，在项目根目录下执行以下命令：
   ```shell
   cd .docker
   docker compose up -d
   ```
2. 在项目根目录执行以下命令：
   ```shell
   yarn
   yarn watch
   ```

完成以上步骤后，浏览器打开 `http://localhost:80` 即可查看前台页面（账号: `dev`，密码: `12345678`）  
此时对源码的任何修改都将实时生效

---

<h2 id='c'>📄️ 配置说明</h2>

### 文章

在本主题中，我们将文章分为以下 3 类

- **网址导航**（默认）：点击图标前往文章详情页，点击其他位置直接跳转至对应 url
- **站内文章**：顾名思义，与网址导航对应，点击会直接前往文章详情页
- **微信小程序**：作为网址导航的分支，点击会直接前往文章详情页

### 分类

分类略缩名表示对应图标名称，可用图标可在 [FontAwesome 5][fontawesome-free] 图标库中浏览；  
(例: FontAwesome 图标类名为 `<i class="fas fa-vihara"></i>` 那么对应略缩名应为 `vihara`)

### 搜索引擎

配置格式为 JSON，其中 icon 为 [FontAwesome 5][fontawesome-free] 图标， 需要使用 **完整类名**。
示例如下：

（站内搜索 url 请指向站点 `/search/` 路径）

```json
[
    {
        "name": "站内",
        "url": "/search/",
        "icon": "fas fa-search-location"
    },
    {
        "name": "谷歌",
        "url": "https://www.google.com/search?q=",
        "icon": "fab fa-google"
    },
    {
        "name": "Github",
        "url": "https://github.com/search?q=",
        "icon": "fab fa-github"
    }
]
```

### 工具直达

配置格式为 JSON，结构类似 搜索引擎配置，增加了 `background` 控制背景色，填写 css 格式的颜色值即可。
示例如下：

```json
[
  {
    "name": "热榜速览",
    "url": "https://www.hsmy.fun",
    "icon": "fas fa-fire",
    "background": "linear-gradient(45deg, #97b3ff, #2f66ff)"
  },
  {
    "name": "地图",
    "url": "https://ditu.amap.com/",
    "icon": "fas fa-fire",
    "background": "red"
  },
  {
    "name": "微信文件助手",
    "url": "https://filehelper.weixin.qq.com",
    "icon": "fab fa-weixin",
    "background": "#1ba784"
  }
]
```

### 时间线

请在后台 `管理` > `独立页面` > `新增`，将其模板设置为 `目录/时间线`，文章类型设置为 站内文章

---

<h2 id='d'>💬 交流反馈</h2>

请在 [issues][issues] 和 [discussions][discussions] 发表和交换意见，同时也欢迎贡献代码帮助我们完善项目

</details>

---

<h2 id='4'>📃 开源许可</h2>

基于 [GNU General Public License v3.0][license-url] 协议开源.

<!-- MARKDOWN LINKS & IMAGES -->
[screenshot]: https://github.com/user-attachments/assets/aa9dd5d5-1a19-478f-b147-d346d19d1df4
[hugo-theme-item]: https://github.com/fordes123/hugo-theme-item/
[last-releases]: https://github.com/fordes123/ITEM/releases/latest/download/ITEM.zip
[build]: https://github.com/fordes123/ITEM/actions/workflows/build.yaml
[item-vercel]: https://github.com/fordes123/ITEM/tree/vercel
[tidb]: https://tidbcloud.com/
[planetscale]: https://planetscale.com/
[typecho-vercel-post]: https://www.fordes.dev/posts/tutorials/typecho-vercel/
[fontawesome-free]: https://fontawesome.com/v5/search?o=r&m=free
[issues]: https://github.com/fordes123/ITEM/issues
[discussions]: https://github.com/fordes123/ITEM/discussions
[issues-url]: https://github.com/fordes123/ITEM/issues
[license-url]: https://github.com/fordes123/ITEM/blob/master/LICENSE.txt
