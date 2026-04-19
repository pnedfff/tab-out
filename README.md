# Tab Out

**Keep tabs on your tabs.**

Tab Out is a Chrome extension that replaces your new tab page with a dashboard of everything you have open. Tabs are grouped by domain, with homepages (Gmail, X, LinkedIn, etc.) pulled into their own group. Close tabs with a satisfying swoosh + confetti.

No server. No account. No external API calls. Just a Chrome extension.

---

## Install with a coding agent

Send your coding agent (Claude Code, Codex, etc.) this repo and say **"install this"**:

```
https://github.com/zarazhangrui/tab-out
```

The agent will walk you through it. Takes about 1 minute.

---

## Features

- **See all your tabs at a glance** on a clean grid, grouped by domain
- **Homepages group** pulls Gmail inbox, X home, YouTube, LinkedIn, GitHub homepages into one card
- **Close tabs with style** with swoosh sound + confetti burst
- **Duplicate detection** flags when you have the same page open twice, with one-click cleanup
- **Click any tab to jump to it** across windows, no new tab opened
- **Save for later** bookmark tabs to a checklist before closing them
- **Localhost grouping** shows port numbers next to each tab so you can tell your vibe coding projects apart
- **Expandable groups** show the first 8 tabs with a clickable "+N more"
- **100% local** your data never leaves your machine
- **Pure Chrome extension** no server, no Node.js, no npm, no setup beyond loading the extension

---

## Manual Setup

**1. Clone the repo**

```bash
git clone https://github.com/zarazhangrui/tab-out.git
```

**2. Load the Chrome extension**

1. Open Chrome and go to `chrome://extensions`
2. Enable **Developer mode** (top-right toggle)
3. Click **Load unpacked**
4. Navigate to the `extension/` folder inside the cloned repo and select it

**3. Open a new tab**

You'll see Tab Out.

---

## How it works

```
You open a new tab
  -> Tab Out shows your open tabs grouped by domain
  -> Homepages (Gmail, X, etc.) get their own group at the top
  -> Click any tab title to jump to it
  -> Close groups you're done with (swoosh + confetti)
  -> Save tabs for later before closing them
```

Everything runs inside the Chrome extension. No external server, no API calls, no data sent anywhere. Saved tabs are stored in `chrome.storage.local`.

---

## Tech stack

| What | How |
|------|-----|
| Extension | Chrome Manifest V3 |
| Storage | chrome.storage.local |
| Sound | Web Audio API (synthesized, no files) |
| Animations | CSS transitions + JS confetti particles |

---

## License

MIT

---

Built by [Zara](https://x.com/zarazhangrui)

---

## 修改摘要（Kevin Fork）

本 Fork 在原版基础上新增以下功能：

### 🔍 Google 搜索框
- Header 右侧嵌入搜索框，与问候语同行
- 框内显示彩色 **Google** 字样（蓝红黄绿）
- 按 `/` 快速聚焦，回车跳转搜索，`Esc` 取消

### 🕐 时间感知问候语主题
根据当前时段自动切换 Header 背景和文字颜色：

| 时段 | 问候 | 主题色 |
|------|------|--------|
| 05–12 | Good morning | 琥珀橙，暖金渐变 |
| 12–17 | Good afternoon | 谷歌蓝，蓝绿渐变 |
| 17–21 | Good evening | 石板蓝，蓝紫渐变 |
| 21–05 | Good night | 深紫，暗紫渐变 |

### 🔖 Chrome 书签栏横向列表
- Header 下方展示 Chrome 书签栏书签，最多显示 2 行
- 每个书签显示 favicon + 名称
- **右键菜单**：编辑名称 / 删除书签
- **拖拽排序**：直接拖动 chip 调整顺序，实时同步到 Chrome 书签
