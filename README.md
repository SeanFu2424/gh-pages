# 公路车 AI 教练台（GitHub Pages 部署版）

单文件静态站点，零依赖、全内联、离线可用。适合用 intervals.icu 自动拉数据 + AI 简报 + 分段统计的业余公路车训练者。

**当前版本：v1.0** ｜ 在线地址：https://seanfu2424.github.io/gh-pages/

## 一键部署到 GitHub Pages（约 2 分钟）

1. 在 GitHub 新建一个**空仓库**（不要勾选 README / LICENSE / .gitignore）。记下仓库地址，例如：
   `https://github.com/你的用户名/cycling-coach.git`

2. 本目录已经 `git init` 并完成首次提交，你只需补上远程并推送：
   ```bash
   git remote add origin https://github.com/你的用户名/cycling-coach.git
   git push -u origin main
   ```

3. 仓库页面 → **Settings → Pages** → Source 选 `main` 分支 / `(root)` → Save。
   等待约 1 分钟，访问 `https://你的用户名.github.io/cycling-coach/` 即可。

## 手机每天用
浏览器打开上面的链接 → 分享 → **添加到主屏幕**（iOS Safari / 安卓 Chrome）。
图标已内联为 PWA，会像 App 一样全屏打开，每天点开即用。

## 数据说明（重要）
- 数据存浏览器 `localStorage`（按域名隔离）。**PC 与手机是两套独立数据，不互通。**
- 换设备请用页面内的「导出 JSON 备份 / 导入恢复」迁移。
- 部署后是公开链接，任何拿到链接的人都能打开页面，但**看不到你的数据**——数据只在本机浏览器里。

## 更新
改完 `index.html` 后：
```bash
git add index.html && git commit -m "update" && git push
```
再到 Pages 设置确认已发布分支，通常自动生效（最多等 1 分钟）。

## 功能速览
- 今日训练 + 一键「拉取今日数据」（intervals.icu API 直连，CORS 已开放）
- 一键生成 / 复制给 AI 的简报（含分段统计、历史同课对比）
- 趋势看板（CTL/ATL/TSB）、教练档案、目标计划
- 移动端适配 + PWA，PC / 手机同源可用

## 使用动线

每天的闭环就三步，都在「今日训练」页：

1. 顶部「拉取今日数据」→ 自动同步 intervals.icu 的活动与体能数据
2. 「AI 教练简报」→ 生成 → 复制，粘给 GPT / Claude
3. 把 AI 的回复粘回「把 AI 的结论存回档案」→ 自动抽成长期记忆，下次简报会带上

**第一次用**：点右上角「连接设置」，填 intervals.icu 的 API Key 即可。
配置区平时收在页面最底部，不干扰日常操作。

## 更新日志

### v1.0（2026-09-09）
首个正式版本。

- **UI 重排**：「数据源」配置区从页面顶部移到「今日训练」页最底部，并做视觉弱化；
  顶栏新增「连接设置」入口，一键跳转并展开配置面板
- **手动补录精简**：默认只显示 日期 / 名称 / 时长 / 距离 / TSS / NP 六项；
  心率、爬升、平均功率、做功、功率心率解耦 等次要项收进「更多维度」
- **页面聚焦**：「今天要处理」只在「今日训练」页显示，翻趋势 / 档案 / 目标时不再占用首屏
- **移动端**：顶栏操作按钮瘦身，导出 / 导入 / 连接设置 / 清空数据 在窄屏一行放得下
