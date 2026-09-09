# 公路车 AI 教练台（GitHub Pages 部署版）

单文件静态站点，零依赖、全内联、离线可用。适合用 intervals.icu 自动拉数据 + AI 简报 + 分段统计的业余公路车训练者。

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
