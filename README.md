# Verge Frost

Clash Verge 透明壁纸 + 简约主题。

---

## 截图

<img title="" src="https://cdn.nodeimage.com/i/DfJl50csgTapxkKkInmUlTah4dvL4zGO.webp" alt="home" data-align="inline">

![settings](https://cdn.nodeimage.com/i/9Nlf8SAzgCWA3gyrFB1mZzryfbBMxjQi.webp)

![editor](https://cdn.nodeimage.com/i/JcAjWJaP65c0KEh49LqHNcHSfGGHY0BT.webp)

---

## 特性

- 大部分颜色与样式都可调，注释给出了相应的介绍
- 可自定义背景图片样式，可调用本地图片或者图床图片
- 整体美观、简洁

---

## 安装

1. 打开 Clash Verge
2. 进入 设置 → 主题设置 → CSS 注入
3. 将 `verge-frost.css` 中的全部内容粘贴进去
4. 点击「保存」，然后重启 Clash Verge 让样式生效

---

## 常用参数

所有可调项都在 CSS 顶部的 `:root` 里，下面是最常改的几处。

### 全局

| 变量                   | 作用             | 默认值                         |
| -------------------- | -------------- | --------------------------- |
| `--cv-sidebar-bg`    | 侧边栏底色          | `rgba(5, 20, 48, 0.82)`     |
| `--cv-text`          | 全局文字颜色         | `rgba(255, 255, 255, 0.95)` |
| `--cv-accent`        | 主色（选中条、左侧蓝条）   | `rgba(94, 129, 244, 0.80)`  |
| `--cv-accent-strong` | 强主色（Badge、焦点框） | `#0a84ff`                   |

### 壁纸

在文件开头的 `body::before` 里：

```css
/* 换壁纸改这里的 URL */
background: url('你的图片地址') center / cover no-repeat !important;

/* blur 越大越糊；brightness 越大越亮；saturate 越大越鲜艳 */
filter: blur(10px) brightness(0.72) saturate(120%) !important;
```

整体暗雾浓度在 `body::after`：

```css
/* 最后一位越大越暗，文字越清晰 */
background: rgba(5, 15, 35, 0.40) !important;
```

### 代码编辑器背景

文件末尾的 `.monaco-editor` 内，三处背景各一行，统一改一个颜色：

```css
--vscode-editor-background:             rgba(5, 15, 35, 0.4) !important; /* 代码区 */
--vscode-editorGutter-background:       rgba(5, 15, 35, 0.4) !important; /* 行号区 */
--vscode-editorStickyScroll-background: rgba(5, 15, 35, 0.4) !important; /* 粘性滚动区 */
```

`alpha` 越大越实，越小越透。

### Chip 颜色浓度

每个彩色 Chip（Success / Error / Warning / Info / Primary / Secondary）都有三处可调：

```css
background-color: rgba(76, 175, 80, 0.10) !important;  /* 底色浓度 */
border: 1px solid rgba(76, 175, 80, 0.55) !important;   /* 边框浓度 */
color: rgba(120, 220, 130, 0.95) !important;            /* 文字浓度 */
```

---

## 测试环境

- Clash Verge Rev v2.5.5
- Windows 11

理论上也适用于其他系统，但本人并未测试。

如果在其他平台遇到问题，欢迎提 Issue。

---

## 常见问题

**改完 CSS 没生效？**
检查三步：① 是否点了「保存」；② 是否重启了 Clash Verge；③ 编辑器背景色需要重新打开编辑器才会刷新。

**自己的壁纸不显示 / 显示为空白？**
确认您图床的稳定性，或者把壁纸下载到本地，改成绝对路径。

**某些文字被强制变白？**
第 9 节末尾有一份「豁免名单」（延迟数字、Chip），如遇其他彩色元素被刷白，把它的稳定类名加进 `:not()` 列表即可

---

## 相关链接

- [Clash Verge Rev](https://github.com/clash-verge-rev/clash-verge-rev) 

---

## 声明

本主题仅涉及界面外观定制，不涉及任何代理配置、节点信息或网络功能。
使用者需自行确保遵守当地法律法规。

背景图片来源于网络
