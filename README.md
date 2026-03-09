# simple-bilibili-home-page

一个 Tampermonkey 用户脚本，用于把哔哩哔哩首页改造成简洁启动页，并补充常用入口与主题联动能力。

[![Tampermonkey 一键安装](https://img.shields.io/badge/Tampermonkey-一键安装-00AEEC?style=for-the-badge)](https://raw.githubusercontent.com/Cypressca/simple-bilibili-home-page/main/simple-bilibili.user.js)

## 项目目标

- 首页更干净：减少视觉噪音，聚焦搜索和常用入口。
- 登录态更清晰：显示个人头像入口，未登录显示登录/注册。
- 系统主题联动：全站跟随系统亮暗模式。

## 当前功能

### 首页改造

- 中央搜索框（跳转哔哩哔哩搜索）
- 左上快捷入口：`消息`、`动态`、`历史`、`稍后再看`、`收藏`
- `消息` 入口支持未读红点数字（`99+` 封顶显示）
- Logo 使用内联 SVG，避免本地文件加载失败
- 首页禁滚动，减少原页面闪动和穿透操作

### 账号入口

- 已登录：右上显示头像与用户名，点击进入个人主页
- 未登录：右上显示 `登录 / 注册` 入口

### 主题能力

- 监听系统主题变化：`prefers-color-scheme`
- 同步 B 站主题相关状态（例如 `theme_style`、`pbp_theme_v4`）
- 首页与全站页面都可感知系统亮暗变化

### 兼容性优化

- `document-start` 提前注入
- `@noframes` + 顶层窗口判断，避免 iframe 重复执行
- 对不同域名访问形态兼容：`bilibili.com` / `www.bilibili.com`

## 安装

### 推荐安装（支持自动更新）

1. 安装 Tampermonkey（Chrome / Edge / Firefox 均可）。
2. 打开安装链接：
	 - `https://raw.githubusercontent.com/Cypressca/simple-bilibili-home-page/main/simple-bilibili.user.js`
3. Tampermonkey 弹出安装页后点击安装。
4. 打开 `https://www.bilibili.com/` 验证效果。

### 手动安装（不推荐）

1. 打开 `simple-bilibili.js`
2. 复制脚本内容到 Tampermonkey 新建脚本
3. 保存并启用

说明：手动安装不利于后续自动升级。

## 更新机制

- 脚本已配置 `@updateURL` 与 `@downloadURL`
- 通过 `.user.js` 链接安装后，Tampermonkey 可自动检查更新
- 每次发布会提升 `@version`

## 作用范围

- 首页改造仅在：
	- `https://www.bilibili.com/`
	- `https://www.bilibili.com/index.html`
	- `https://bilibili.com/`
	- `https://bilibili.com/index.html`
- 全站主题联动可作用于其他 `*.bilibili.com` 页面

## 依赖与权限

- 依赖：Tampermonkey 或兼容 Userscript 管理器
- 脚本本身无第三方 npm 依赖
- 需要浏览器允许脚本在 bilibili 域名运行

## 常见问题

### 安装链接不弹脚本安装页

- 必须使用 `.user.js` 直链：
	- `https://raw.githubusercontent.com/Cypressca/simple-bilibili-home-page/main/simple-bilibili.user.js`
- 检查 Tampermonkey 是否安装并启用

### 脚本显示“执行多次”

- 通常由 iframe 注入导致
- 本项目已加 `@noframes` 和 `window.top === window.self` 保护

### 其他用户安装后不生效

建议按顺序排查：

1. 确认脚本启用且已更新到最新版本
2. 扩展站点权限设为允许 bilibili（建议“所有网站”）
3. 确认没有其他“首页改造类脚本”冲突
4. 访问首页根路径复测：`https://www.bilibili.com/`

## 隐私说明

- 脚本仅在浏览器本地执行
- 仅请求 B 站官方接口（用于登录态、消息未读等显示）
- 不上传你的账号数据到第三方服务

## 文件说明

- `simple-bilibili.js`：主开发文件
- `simple-bilibili.user.js`：发布/安装入口文件
- `Bilibili_logo_blue.svg`：Logo 源文件（脚本内使用内联 SVG）

## 仓库与反馈

- 仓库地址：`https://github.com/Cypressca/simple-bilibili-home-page`
- 问题反馈：`https://github.com/Cypressca/simple-bilibili-home-page/issues`

## License

MIT
