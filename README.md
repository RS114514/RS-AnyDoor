# RS-AnyDoor

RS 的个人导航页（任意门），一个纯前端、零依赖的单页网站。  
用于聚合常用网站、个人服务入口和全网搜索，打开即用。

## 功能亮点

- 多搜索引擎切换：Google / Bing / 百度 / 搜狗 / ChatGPT
- 快捷卡片导航：个人服务、常用网站、管理服务分区
- 自动站点图标：对标记为 `data-favicon="auto"` 的卡片自动加载 favicon
- 搜索记录管理：最近记录、完整记录弹窗、单条删除、清空记录
- 无痕模式：开启后不写入搜索历史
- 主题切换：深色/浅色模式 + 系统主题同步
- 使用统计：访问次数、上次访问、搜索次数、卡片点击、趋势图
- 个性化问候：在设置中自定义昵称
- 动效增强：背景粒子、卡片入场、悬停 3D 倾斜、主题扫描线
- 键盘支持：`/` 快速聚焦搜索框，`Esc` 关闭弹窗

## 技术栈

- HTML5
- CSS3（变量、响应式、动画）
- 原生 JavaScript（无框架、无构建）
- 浏览器本地存储（`localStorage`）

## 项目结构

```text
.
├── index.html
├── README.md
└── web_images/
    └── illus_webstation_enabled.jpg
```

## 快速开始

1. 克隆仓库
2. 直接用浏览器打开 `index.html`

也可以在本地起一个静态服务（可选）：

```bash
cd /Volumes/web
python3 -m http.server 8080
```

然后访问：`http://localhost:8080`

## 自定义指南

所有主要配置都在 `index.html` 中，可直接修改：

- 修改卡片内容：编辑各分区里的 `<a class="card card-link ...">`
- 修改搜索引擎：编辑脚本内 `const engines = { ... }`
- 修改默认搜索引擎：调整 `<select id="engine-select">` 的 `selected` 选项
- 修改文案和标题：编辑 `<title>`、`hero` 区域和各 `small` 描述

## 本地存储键说明

页面会在浏览器保存以下数据：

- `rsSearchHistory`：搜索历史（最多 50 条）
- `rsUsageStats`：访问与交互统计
- `rsSearchIncognito`：无痕模式开关
- `rsUserProfile`：用户昵称配置
- `rsTheme`：主题偏好（light/dark）

## 数据与隐私

- 本项目不依赖后端，页面数据默认仅保存在本地浏览器
- 搜索行为会跳转到对应搜索引擎站点执行
- 外部链接和 favicon 请求会访问第三方域名

## 部署建议

- 可直接部署到任意静态托管平台（GitHub Pages、Nginx、Netlify、Vercel 等）
- 推荐开启 HTTPS，避免混合内容和浏览器拦截

## 许可证

当前仓库未声明开源许可证。  
如需开源分发，建议补充 `LICENSE` 文件（例如 MIT）。
