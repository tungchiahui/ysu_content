# 简介与队标来源

- 用户确认名称：燕山大学机器人创新团队燕鹰战队，归属机械工程学院。
- 简介根据[燕山大学第五届 RoboMaster 校内选拔赛通知](https://notice.ysu.edu.cn/info/2264/23979.htm)归纳，涵盖赛事、机械、电控、算法、硬件与运营方向。没有推断建队年份、人数或燕鹰获奖记录。
- 临时队标：用户指定的[战队微博](https://weibo.com/u/5743556072)头像，获取日期 2026-10-19，原图 180×180，保存为 `public/images/ysu-avatar.jpg`，未重绘。
- 除上述身份信息，现有成员、Wiki、新闻、成绩、宣传轮播、机器人照片及招新联系方式均保留原站模板，来源中的名称、作者和事实保持原样。

## RoboMaster 首页背景视频

- 来源页面：[RoboMaster 中文官网](https://www.robomaster.com/zh-CN)，获取日期 2026-10-19。
- 取自来源页唯一的首页 `<video>` 元素，使用公开直接提供的 MP4 与 poster，未截取或转码。
- [视频原地址](https://vod.robomaster.com/7044fd3699ee71f180776723a78f0102/cd8b8d1d7ac548bbb164d9cae725676b-46fee4569b9077498bbcaeb99ff668ed-ld.mp4)；本地文件 `public/images/robomaster-home.mp4`，20.009 秒，1920×1080，H.264，25 fps。
- [封面原地址](https://rm-static.djicdn.com/documents/156026/3a6abe59ed2521787813782561764809.jpg)；本地文件 `public/images/robomaster-home.jpg`。
- 首页背景通过 `data/site.json` 的 `heroMedia` 配置，静音循环播放并提供官方来源链接。
- 原站 `backgroundvideo.mp4` 与 `background.jpg` 继续保留作为模板。
