# 简介与队标来源

- 用户确认名称：燕山大学机器人创新团队燕鹰战队，归属机械工程学院。
- 简介根据[燕山大学第五届 RoboMaster 校内选拔赛通知](https://notice.ysu.edu.cn/info/2264/23979.htm)归纳，涵盖赛事、机械、电控、算法、硬件与运营方向。简介没有推断建队年份、人数或燕鹰获奖记录；后续核实的成果见下述专节。
- 临时队标：用户指定的[战队微博](https://weibo.com/u/5743556072)头像，获取日期 2026-10-19，原图 180×180，保存为 `public/images/ysu-avatar.jpg`，未重绘。
- 初始迁移保留原站成员、Wiki、新闻、成绩、宣传轮播、机器人照片及招新联系方式作为模板。Wiki 后续按下述来源整体更新。

## RoboMaster 首页背景视频

- 来源页面：[RoboMaster 中文官网](https://www.robomaster.com/zh-CN)，获取日期 2026-10-19。
- 取自来源页唯一的首页 `<video>` 元素，使用公开直接提供的 MP4 与 poster，未截取或转码。
- [视频原地址](https://vod.robomaster.com/7044fd3699ee71f180776723a78f0102/cd8b8d1d7ac548bbb164d9cae725676b-46fee4569b9077498bbcaeb99ff668ed-ld.mp4)；本地文件 `public/images/robomaster-home.mp4`，20.009 秒，1920×1080，H.264，25 fps。
- [封面原地址](https://rm-static.djicdn.com/documents/156026/3a6abe59ed2521787813782561764809.jpg)；本地文件 `public/images/robomaster-home.jpg`。
- 首页背景通过 `data/site.json` 的 `heroMedia` 配置，静音循环播放；官方来源保留在本文件中。
- 原站 `backgroundvideo.mp4` 与 `background.jpg` 继续保留作为模板。

## Wiki 更新来源

- 2026-10-19 按用户指定的 `/home/tungchiahui/UserFolder/MySource/tungchiahui_content/content/wiki/` 当前工作文件同步，292 篇原文逐文件比对一致，包括来源工作目录中的未提交修改。
- 按用户要求删除旧目录独有的文档，不保留旧文档归档。

## 战队照片

2026-10-19 从用户提供的 `/home/tungchiahui/Downloads/TTT/` 选择 8 张原图，用于首页栏目、轮播、各栏目横幅及招新/联系配图。原图直接复制，未裁剪、重绘或移除水印。原有新闻正文配图与成员头像保持对应资料的内容。

| 网站文件 | 来源文件 |
| --- | --- |
| `public/images/team/robot-collaboration.jpg` | `30374729D79C9EF95EF15A001E349416.jpg` |
| `public/images/team/electronics-detail.jpg` | `3963A2F29FB8B7549F5D457F7B6D05DC.jpg` |
| `public/images/team/robot-preparation.jpg` | `465A72DD6BE0A129576031530640F3FF.jpg` |
| `public/images/team/robot-workbench.jpg` | `540C9BA9190965D9DEB7A4EE3F3CDAA0.jpg` |
| `public/images/team/team-cheer.jpg` | `6BF32788D69D31512D26A98B997E904D.jpg` |
| `public/images/team/arena-testing.jpg` | `88A66D6A9A7B0601EA723507F2B99312.jpg` |
| `public/images/team/team-moment.jpg` | `D662CBA7A4570845BB9AE2B4812EA627.jpg` |
| `public/images/team/robot-pit.jpg` | `DFAD09C94FAA47CF965A4A33EF20DB99.jpg` |

## RoboMaster 历年成果

- 2026-10-19 根据 RoboMaster 官方公告与官方论坛核实获奖名单，替换原站 Robocon 成绩模板；首次参赛年份以燕山大学官方报道为依据。
- 成果数据：`data/achievements.json`。每项均保留官方来源链接；完整收录口径、暂缺年份和逐年依据见 [RoboMaster 成果来源](docs/RoboMaster成果来源.md)。

## 燕鹰视觉标题字体（历史版本）

- 2026-10-20 新增本地标题字体 `public/fonts/noto-serif-sc-ui-700.woff2`，来源为 [Google Fonts 的 Noto Serif SC](https://fonts.google.com/noto/specimen/Noto+Serif+SC)，字重 700。
- 通过 Google Fonts 的 `text` 子集接口获取，包含当时网站 Vue 界面及 `data/site.json` 中的 461 个汉字字形，文件约 87 KiB。正文、文章标题和成员姓名标题使用系统字体，新增界面字形可更新子集或使用系统字体回退。
- 使用 SIL Open Font License 1.1；[上游许可](https://github.com/notofonts/noto-cjk/blob/main/Serif/LICENSE)随文件保存为 `public/fonts/OFL-NotoSerifSC.txt`。网站从同域提供字体，无需访客连接 Google 字体服务。

- 2026-10-20 按用户反馈恢复原有布局与系统无衬线字体，以上字体不再由页面加载，文件与许可保留为历史资源。成果页同时取消来源、核实说明和早期队名的页面展示，原始出处继续在本仓库保存。

## 燕鹰新闻与公告

2026-10-20 删除两篇山东理工大学 Vinci 新闻模板及其独占排球赛图片，以以下原文为依据做简短整理，保留原文链接，不把历史比赛报名写成当前招新。正文未凭空补充采访、比赛过程或获奖情况。

| 新闻文件日期 | 依据 | 署名处理 |
| --- | --- | --- |
| 2019-08-28 | [燕山大学 RoboMaster 2019 获奖报道](https://www.ysu.edu.cn/info/5415/13631.htm) | 原文明确署名“机械工程学院 陈子明”，填写 `authors: [陈子明]`；不将编辑褚玉晶列为作者 |
| 2024-02-28 | [第三届燕鹰机器人对抗赛通知](https://notice.ysu.edu.cn/info/2264/17807.htm) | 未明确个人作者，留空 |
| 2024-08-26 | [RoboMaster 2024 机器人竞技奖名单](https://www.robomaster.com/zh-CN/resource/pages/announcement/1761) | 未明确个人作者，留空 |
| 2025-11-14 | [第五届 RoboMaster 校内选拔赛通知](https://notice.ysu.edu.cn/info/2264/23979.htm) | 原文页面发布日期为 11 月 14 日、通知落款为 11 月 13 日；按页面发布日期命名，个人作者留空 |
| 2026-04-14 | [RoboMaster 2026 高校联盟赛名单](https://www.robomaster.com/zh-CN/resource/pages/announcement/1913) | 未明确个人作者，留空；仅记录山东站 3V3 对抗赛二等奖 |

2019 年新闻的两张配图直接下载自学校原报道，保留原图，不裁剪、不重绘。原文说明图片由机械工程学院提供，正文已注明图片来源：

- `public/images/news/2019-robomaster/team.jpg`：[合影原图](https://www.ysu.edu.cn/__local/B/D1/F8/4ED16B4F3E417253E3345AC3C59_346B0402_44EEE.jpg)，600×400。
- `public/images/news/2019-robomaster/engineer-results.jpg`：[获奖名单原图](https://www.ysu.edu.cn/__local/4/B1/11/769FA70B83514B085B42FB85F28_DB1E19E1_245EC.jpg)，600×644。
