# koishi-plugin-rollpig

`koishi-plugin-rollpig` 是一个 Koishi 插件，用于提供“今日小猪”“随机小猪”“找猪”等功能。

当前行为：

- `/今日小猪` 输出图片卡片
- `/随机小猪` 和 `/找猪` 保持原始图片直出样式

## 声明

- 本仓库中的 Koishi 适配代码与当前实现，全部由 AI 协助完成。
- 本项目基于原始项目的功能思路进行 Koishi 移植与图片样式适配，不是原作者发布的官方 Koishi 版本。

## 原始项目

- NoneBot 版本原始仓库：[Bearlele/nonebot-plugin-rollpig](https://github.com/Bearlele/nonebot-plugin-rollpig)
- AstrBot 图片输出参考仓库：[MegSopern/astrbot_plugin_rollpig](https://github.com/MegSopern/astrbot_plugin_rollpig)
- PigHub 图片来源：[https://pighub.top/](https://pighub.top/)

## 功能

- `/今日小猪`：按用户维度记录当天的小猪人格，并输出图片卡片
- `/随机小猪 [数量]`：从 PigHub 随机抽取猪猪图片
- `/找猪 [关键词] -i <图片ID>`：按标题关键词或图片 ID 搜索 PigHub 图片
- 兼容触发词：`/今天是什么小猪`、`/本日小猪`、`/当日小猪`、`/搜猪`
- 命令需使用 `/` 或 `／` 触发

## 安装

```bash
npm i koishi-plugin-rollpig
```

然后在 Koishi 配置中启用插件：

```yaml
prefix:
  - /
  - ／

plugins:
  rollpig: {}
```

## 配置项

- `dataDir`：插件缓存目录，默认 `data/rollpig`
- `maxRandomCount`：`/随机小猪` 最大允许数量，默认 `20`
- `maxFindResults`：`/找猪` 最大返回结果数，默认 `20`
- `remoteCacheHours`：PigHub 远程缓存刷新间隔，默认 `12`
- `startupRefresh`：启动后是否后台刷新 PigHub 缓存，默认 `true`
- `timezone`：`/今日小猪` 使用的时区，留空表示跟随宿主环境

## 使用示例

```text
/今日小猪
/随机小猪
/随机小猪 3
/找猪 可爱
/找猪 -i 3
```

## 开发

```bash
npm install
npm run check
npm run build
```

打包发布：

```bash
npm pack
```

## 仓库

- GitHub: [ouy0328/koishi-plugin-rollpig](https://github.com/ouy0328/koishi-plugin-rollpig)
- npm: [koishi-plugin-rollpig](https://www.npmjs.com/package/koishi-plugin-rollpig)

## 致谢

- [Koishi 插件开发文档](https://koishi.chat/zh-CN/guide/plugin)
- [nonebot-plugin-rollpig](https://github.com/Bearlele/nonebot-plugin-rollpig)
- [astrbot_plugin_rollpig](https://github.com/MegSopern/astrbot_plugin_rollpig)
- [PigHub](https://pighub.top/)
