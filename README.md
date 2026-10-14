# 521jojo.com 静态站

广州帮洁洗涤科技有限公司官网的静态镜像，用于部署到 Cloudflare Pages。

## 目录结构

```
.
├── index.html              # 首页
├── about/                  # 关于我们
├── product/                # 产品中心
│   ├── product_2/          # 产品分页 2
│   └── product_3/          # 产品分页 3
├── news/                   # 新闻中心
├── shebei/                 # 工厂设备
├── shipin/                 # 公司视频
│   └── shipin_2/
├── liuyan/                 # 在线留言（表单，静态化后不可用）
├── contact/                # 联系我们
├── lm1/ ~ lm4/             # 附加栏目
├── list_11/ list_12/ list_14/ list_15/   # 列表分页
├── skin/                   # 样式、脚本、图标
│   ├── css/
│   ├── js/
│   └── images/
├── static/upload/          # 上传资源
│   ├── image/
│   └── video/
├── message/                # 表单提交结果页
├── sitemap.xml
├── _headers                # Cloudflare 缓存策略
└── _redirects              # Cloudflare 重定向规则
```

## 站点统计

| 项目 | 数量 |
|---|---|
| 文件总数 | 207 |
| HTML 页面 | 70 |
| 图片 | 118 |
| 视频 | 11 |
| 总大小 | 74 MB |

## 部署到 Cloudflare Pages

1. 登录 Cloudflare 控制台 → Workers & Pages → Create → Pages → Connect to Git
2. 选择本仓库 `tumu123/521jojo`
3. 构建配置：
   - **Framework preset**: None
   - **Build command**: 留空
   - **Build output directory**: `/`（根目录）
4. 点击 Save and Deploy

> 注：本仓库为纯静态站，无需构建步骤。Cloudflare Pages 免费版限制单文件 25 MB、单站点 500 个文件，当前站点均符合。

## 已知限制

- **在线留言功能不可用**。`liuyan/` 页面为表单提交，纯静态环境无法处理。如需保留，需接入 Cloudflare Workers 或第三方表单服务。
- `message/` 为表单提交结果页，静态化后无实际作用，保留仅为完整性。
- `skin/css/style.css` 中引用的 `syq_09.png`、`se_03.png`、`sy_28.png` 在原站即为 404，属原站遗留问题。

## 域名配置

站点内容中的链接已全部本地化（转为相对路径），可部署至任意域名。若需绑定原域名，在 Cloudflare Pages 的 Custom domains 中添加即可。

---

抓取日期：2026-10-14
