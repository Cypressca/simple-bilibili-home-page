# simple-bilibili-home-page

一个用于 Tampermonkey 的哔哩哔哩主页精简脚本，提供更简洁、聚焦搜索的首页体验。

## 功能

- 左上角快捷入口：动态、历史、稍后再看、收藏
- 中央搜索框：直接跳转哔哩哔哩搜索
- Logo 使用内联 SVG，避免本地文件或跨域加载失败
- 支持暗色模式并自动跟随系统主题
- `document-start` 提前注入，减少原主页闪屏
- 禁止主页滚动，避免“覆盖层 + 原页面可滚动”问题
- 对 Bilibili Evolved 等扩展更友好
- 收藏链接自动识别 UID：`https://space.bilibili.com/$UID$/favlist`

## 安装方式（简体中文）

### 方式一：推荐（可自动更新）

1. 浏览器安装 Tampermonkey：
	- Chrome/Edge/Firefox 均可使用。
2. 打开脚本直链（Raw）：
	- `https://raw.githubusercontent.com/Cypressca/simple-bilibili-home-page/main/simple-bilibili.js`
3. Tampermonkey 会弹出安装页面，点击“安装”。
4. 安装后访问：
	- `https://www.bilibili.com/`

说明：
- 本脚本头部已包含 `@updateURL` 和 `@downloadURL`。
- 通过上面的 Raw 链接安装后，Tampermonkey 可自动检查新版本。

### 方式二：手动安装（不推荐）

1. 打开仓库中的 `simple-bilibili.js`。
2. 复制全部内容。
3. Tampermonkey 新建脚本并粘贴保存。

说明：
- 手动粘贴方式通常不会自动跟进上游更新。
- 若继续使用此方式，需要你手动替换脚本内容。

## 更新说明

- 发布新版本时会提升 `@version`。
- Tampermonkey 在下次检查更新时会提示或自动更新（取决于你的扩展设置）。

## 兼容性说明

- 仅作用于 `https://www.bilibili.com/` 根路径。
- 与 Bilibili Evolved 共存时，若出现样式冲突，建议在 Tampermonkey 中调整脚本顺序或优先级。

## 文件结构

- `simple-bilibili.js`：主脚本
- `Bilibili_logo_blue.svg`：Logo 源文件（用于生成内联 SVG）

## 许可证

MIT
