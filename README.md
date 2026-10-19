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
sources.md             燕鹰简介和临时队标的来源
```

## 当前保留的模板

成员、Wiki、新闻等 260 份 Markdown 原文全部保留，没有批量替换其中的战队名称、作者或事实。原有成绩、宣传轮播、媒体和招新联系方式也保留作模板。这些资料来源于原 SDUT Vinci 网站，不代表燕鹰成员、成绩或招新安排。

`data/site.json` 中的 `templateMode` 控制网站资料迁移说明。完成所有正式内容替换后再关闭。

## 维护方式

- 新成员：参考 `member-submission-kit/`，添加 Markdown 与对应头像。
- 新新闻：在 `content/news/` 添加 Markdown，图片放在 `public/images/news/`。
- Wiki：保留现有文件名编号规则，章节使用四位数字开头；更改路径时同步维护站内链接。
- 配图：写 `/images/文件名`，网站会在构建时同步 `public/` 中的资源。
- 联系方式、招新链接与首页介绍：编辑 `data/site.json`，无需修改页面代码。
- 首页背景视频与封面：编辑 `data/site.json` 的 `heroMedia`，分别设置 `video`、`poster`、`sourceLabel` 与 `sourceUrl`。媒体文件放在 `public/images/`。
- 成绩：编辑 `data/achievements.json`；首页轮播：编辑 `data/home-promos.json`。

本地预览时，把网站仓库 `.env` 中的 `CONTENT_LOCAL_PATH` 指向本仓库，然后在网站目录运行 `npm run dev`。内容修改后执行 `npm run content:sync`。

## 内容更新如何触发构建

提交本仓库不会自动修改已经生成的网站。可在网站仓库手动运行 Build 工作流；工作流中的 `content_ref` 可填本仓库的完整提交 SHA。

本仓库也提供可选的自动触发工作流 `notify-website.yml`。网站分仓改造合并到默认分支后，在本仓库设置 Secret `WEBSITE_DISPATCH_TOKEN`，使用仅对网站仓库具有 Actions 写入权限的 token。后续内容提交会触发网站 Build，并传入当前内容 SHA。未设置该 Secret 时工作流正常跳过触发，不影响提交。

可选变量 `WEBSITE_REPOSITORY` 默认 `tungchiahui/ysu_web`，`WEBSITE_REF` 默认 `main`；网站迁移后可调整它们。该工作流只发起构建，不负责线上部署。

## Public 与 Private

公开仓库可直接拉取。若以后改为私有，网站构建环境配置只读 `CONTENT_GIT_TOKEN` 或只读 SSH 部署密钥即可，内容格式和页面代码无需改变。GitHub Actions 的默认 `GITHUB_TOKEN` 不能直接用于读取另一个私有仓库。仓库私有不意味着公开网站上的文章会私有。
