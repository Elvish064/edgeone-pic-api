<div align="center">
  <img src="logo.webp" alt="EdgeOne Pic API Logo" width="120" />
  <h1>EdgeOne Pic API</h1>
  <p>基于腾讯云 EdgeOne Pages 构建的高性能、自适应随机图片 API 服务</p>

  <a href="https://pic.elvish.me/ua">演示地址</a> ·
  <a href="https://pic.elvish.me">项目主页</a>
</div>

## ✨ 功能特性

- **🖼️ 精选图源**：高质量的横屏和竖屏随机图片，均来源于[SomeACG](https://www.someacg.top/)。
- **📱 自动适应**：智能识别桌面/移动端设备，自动路由适配尺寸比例。
- **⚡ 边缘加速**：基于腾讯云 EdgeOne 全局边缘节点网络，实现极速图片分发。
- **🔒 开箱即用**：FORK项目并部署即可使用，简单快速。

## 🚀 API 接口

提供三种核心路由模式，均支持标准查询参数及短链方式：

| 功能 | 简写路由 | 标准路由 | 说明 |
| :--- | :--- | :--- | :--- |
| **获取横屏图片** | `GET /pc` | `GET /api?type=pc` | 适合桌面端展示 (宽屏) |
| **获取竖屏图片** | `GET /pe` | `GET /api?type=pe` | 适合移动端展示 (竖屏) |
| **设备自适应** | `GET /ua` | `GET /api?type=ua` | 根据 User-Agent 智能调度 |

> **防止缓存/重复** (可选)：在地址末尾加上`/<number>`，例如 `https://pic.elvish.me/ua/1`

## 💻 调用示例

### 在 HTML 中原生使用

可直接将链接填入 `<img>` 标签：

```html
<!-- 【推荐】根据访问者设备自动选择图片横竖比例 -->
<img src="https://your-domain.com/ua" alt="自适应随机图片">

<!-- 强制获取横屏图片 -->
<img src="https://your-domain.com/pc" alt="横屏图片">

<!-- 强制获取竖屏图片 -->
<img src="https://your-domain.com/pe" alt="竖屏图片">
```


## 🛠️ 私有化部署指南

本项目原生适配腾讯云 EdgeOne Pages，您可以将其零成本部署到您的个人账户下。

### 1. 准备图片资源
需将准备好的图片存放在对应路径：（**推荐 WebP 格式**，兼顾高画质与小体积）
- **桌面端（横屏）**：`/images/pc/`
- **移动端（竖屏）**：`/images/pe/`

并更新脚本中的图片列表。

### 2. 部署到 EdgeOne Pages
1. 点击 `Fork` 将本项目克隆到您的 GitHub。
2. 放入您新增的图片并更新图片名列表。(如有)
3. 登录并进入腾讯云 EdgeOne Pages 控制台，创建项目。
4. 关联您的 GitHub 仓库，**项目构建类型（Framework）请选择 `Other`**。
5. 部署完成后，在设置中绑定您的自定义域名即可。

## 项目结构说明
```text
├── edgeone.json           # EdgeOne Pages 静态路由及重定向匹配配置
├── index.html             # API 可视化介绍主页
├── images/                # 图片储备库
│   ├── pc/                # 横屏素材池
│   └── pe/                # 竖屏素材池
├── functions/
│   └── api.js             # 运行在 Edge Functions 的核心处理逻辑
└── README.md              # 项目说明文档
```

## 💡 技术细节

- **服务宿主**：腾讯云 EdgeOne Pages
- **技术栈**：JavaScript (Edge Function) / HTML
- **自适应策略**：通过分析 Request Headers 中的 User-Agent 嗅探设备类型分发图片。

## 🙏 致谢

本项目受到以下开源项目的启发和帮助，在此表示诚挚谢意：

- **[EdgeOne_Function_PicAPI](https://github.com/afoim/EdgeOne_Function_PicAPI)** - 提供了 EdgeOne Function 部署 API 的思路与基础。
- **[PicFlow-API](https://github.com/matsuzaka-yuki/PicFlow-API)** - 提供了丰富的图片格式转换和优化的脚本工具参考。
- **[SomeACG](https://www.someacg.top/)** - 提供大量优质高清ACG源图。

## 📄 开源许可证

本项目基于 **MIT License** 协议开源，请查阅根目录下的 `LICENSE` 文件了解详情。

## 🤝 参与与支持

欢迎提交 Issue 报告错误，或随时发起 Pull Request 提交代码！
如果您在使用过程中有任何疑问，可通过以下方式联系：
- 提交 GitHub Issue
- 发送邮件至：[elvish@elvish.me](mailto:elvish@elvish.me)
