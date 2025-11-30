# 随机图片API

一个基于腾讯云EdgeOne Pages的随机图片API服务，提供高质量的横屏和竖屏随机图片。

## 功能特性

- 🖼️ 提供高质量的随机图片
- 📱 支持设备自适应（自动识别桌面/移动设备）
- ⚡ 基于边缘计算，全球加速
- 🔒 无需API密钥，开箱即用
- 🆓 完全免费使用

## API接口

### 获取横屏图片
```
GET /api?type=pc
GET /pc
```
返回适合桌面设备的横屏随机图片。

### 获取竖屏图片
```
GET /api?type=pe
GET /pe
```
返回适合移动设备的竖屏随机图片。

### 设备自适应
```
GET /api?type=ua
GET /ua
```
根据用户设备类型自动选择图片格式（桌面设备返回横屏，移动设备返回竖屏）。

## 部署方法

### 1. 准备图片资源
- 横屏图片放置在 `/images/pc/` 目录
- 竖屏图片放置在 `/images/pe/` 目录
- 支持WebP格式以获得最佳性能

### 2. 部署到EdgeOne Pages
1. Fork本项目
2. 在Edgeone Pages部署该项目，项目类型选择`Other`
3. 绑定自己的域名

### 3. 目录结构
```
├── edgeone.json           # Edgeone 重定向逻辑
├── index.html             # API介绍页面
├── images/
│   ├── pc/               # 横屏图片目录
│   └── pe/               # 竖屏图片目录
├── functions/
│   └── api.js            # API脚本文件
└── README.md             # 项目说明文档
```

## 使用示例

### 在HTML中使用
```html
<!-- 根据设备自动选择图片 -->
<img src="https://your-domain.com/ua" alt="随机图片">

<!-- 强制使用横屏图片 -->
<img src="https://your-domain.com/pc" alt="横屏随机图片">

<!-- 强制使用竖屏图片 -->
<img src="https://your-domain.com/pe" alt="竖屏随机图片">
```

### 直接访问
- 横屏图片：`https://your-domain.com/pc`
- 竖屏图片：`https://your-domain.com/pe`
- 设备自适应：`https://your-domain.com/ua`

## 技术细节

- **平台**：腾讯云EdgeOne Pages
- **编程语言**：JavaScript
- **图片格式**：WebP（推荐）
- **设备检测**：基于User-Agent字符串分析

## 致谢

本项目受到以下项目的启发和帮助：

- **[EdgeOne_Function_PicAPI](https://github.com/afoim/EdgeOne_Function_PicAPI)** - 提供了EdgeOne Function部署随机图片API的思路和基础实现
- **[PicFlow-API](https://github.com/matsuzaka-yuki/PicFlow-API)** - 提供了图片格式转换和优化的脚本工具
- **[SomeACG](https://www.someacg.top/)** - 为本项目提供大量优质图片

感谢这些优秀的开源项目为开发提供的宝贵参考！

## 许可证

本项目采用MIT许可证，详情请查看LICENSE文件。

## 贡献

欢迎提交Issue和Pull Request来改进这个项目！

## 支持

如果您在使用过程中遇到任何问题，请通过以下方式联系：
- 提交GitHub Issue
- 发送邮件至：[elvish@elvish.me]

---
