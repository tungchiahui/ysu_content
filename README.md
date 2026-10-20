# 燕鹰战队网站内容

用于燕山大学机器人创新团队（燕鹰战队）官网的独立内容仓库。网站使用 Nuxt，构建时拉取本仓库。仓库名和所属账号可以更改，修改网站的 `content-source.json` 即可。

## 目录

```text
content/members/       成员资料 Markdown
content/news/          新闻 Markdown
content/wiki/          Wiki 教程 Markdown
public/images/         图片、头像与视频
data/site.json         战队身份、简介、联系方式、招新链接、首页介绍
data/achievements.json 赛事成绩
data/home-promos.json  首页宣传轮播
member-submission-kit/ 成员资料填写说明、模板和示例
sources.md             简介、队标与视频的来源
```

## 当前保留的模板

初始迁移时，原 SDUT Vinci 网站的成员、Wiki、新闻等 260 份 Markdown 原文全部保留。新闻已替换为 5 篇燕鹰战队新闻与公告，成果页展示简洁的 RoboMaster 历年获奖记录，出处保留在仓库供维护；招新群、报名表及邮箱、微信、地址已按燕鹰战队资料更新。成员档案现仅保留董佳辉及原站三位指导老师，使用新的按赛季任职格式，详见 `docs/成员资料规范.md`。首页轮播及栏目配图已按燕鹰主题更新，照片来自用户指定的 TTT 文件夹。

Wiki 最初按用户指定的本地 `tungchiahui_content/content/wiki/` 工作目录整体更新为 292 篇。此后按要求删除 OpenCV、Flutter、Nuxt.js、OpenWrt、ROS1 五套独立教程及其首页、章节，当前保留 271 篇。旧目录独有的文档已删除，不保留归档；未改动最初的来源仓库。

新闻、成果页均展示燕鹰战队资料，原站两篇新闻模板及其排球赛配图已删除。网站已移除顶部资料迁移提示和首页来源链接；引用来源继续记录于 `sources.md`。

## 视觉资源

当前网站恢复系统无衬线字体。旧版标题字体 `public/fonts/noto-serif-sc-ui-700.woff2` 及同目录的 SIL OFL 许可保留为历史资源，目前页面不加载该字体；来源见 `sources.md`。

## 维护方式

- 学生与指导老师均不填写学校字段 `university`，学院字段保留；页面赛季值显示 `2027`，顶部筛选显示 `27赛季`，资料中仍填写四位整数。
- 新成员与指导老师：参考 [Markdown 填写说明书](member-submission-kit/说明书.md) 和 `docs/成员资料规范.md`，添加 Markdown 与对应头像；学生只使用机械组、电控组、硬件组、算法组，无梯队字段。
- 新新闻：在 `content/news/` 添加 `YYYY-MM-DD-短标题.md`，frontmatter 仅写 `title`、`authors`；日期、封面和摘要自动提取，详见 [新闻资料规范](docs/新闻资料规范.md)。图片放在 `public/images/news/`。
- Wiki：frontmatter 使用 `title` 和 `authors`，详见 `docs/Wiki资料规范.md`。保留现有文件名编号规则，章节使用四位数字开头；更改路径时同步维护站内链接。
- 配图：写 `/images/文件名`，网站会在构建时同步 `public/` 中的资源。
- 联系方式、招新链接与首页介绍：编辑 `data/site.json`，无需修改页面代码。
- 首页背景视频与封面：编辑 `data/site.json` 的 `heroMedia`，分别设置 `video`、`poster`、`sourceLabel` 与 `sourceUrl`。媒体文件放在 `public/images/`。
- RoboMaster 成绩：编辑 `data/achievements.json`，在 `records` 中按年份维护奖项，每项包含 `title` 和官方出处 `source.title`、`source.url`；未核实的年份不填。文件同时保存首次参赛年份、官方公告入口及核实日期。首页轮播：编辑 `data/home-promos.json`。

成果的收录口径、暂缺年份和逐年公告链接见 [RoboMaster 成果来源](docs/RoboMaster成果来源.md)。

本地预览时，把网站仓库 `.env` 中的 `CONTENT_LOCAL_PATH` 指向本仓库，然后在网站目录运行 `npm run dev`。内容修改后执行 `npm run content:sync`。

## 内容更新如何触发构建

提交本仓库不会自动修改已经生成的网站。可在网站仓库手动运行 Build 工作流；工作流中的 `content_ref` 可填本仓库的完整提交 SHA。

本仓库也提供可选的自动触发工作流 `notify-website.yml`。网站分仓改造合并到默认分支后，在本仓库设置 Secret `WEBSITE_DISPATCH_TOKEN`，使用仅对网站仓库具有 Actions 写入权限的 token。后续内容提交会触发网站 Build，并传入当前内容 SHA。未设置该 Secret 时工作流正常跳过触发，不影响提交。

可选变量 `WEBSITE_REPOSITORY` 默认 `tungchiahui/ysu_web`，`WEBSITE_REF` 默认 `main`；网站迁移后可调整它们。该工作流只发起构建，不负责线上部署。

## Public 与 Private

公开仓库可直接拉取。若以后改为私有，网站构建环境配置只读 `CONTENT_GIT_TOKEN` 或只读 SSH 部署密钥即可，内容格式和页面代码无需改变。GitHub Actions 的默认 `GITHUB_TOKEN` 不能直接用于读取另一个私有仓库。仓库私有不意味着公开网站上的文章会私有。
