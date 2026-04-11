# koishi-plugin-rollpig

`koishi-plugin-rollpig` 是一个 Koishi 插件，用于提供“今日小猪”“随机小猪”“找猪”等功能。

当前行为：

- `今日小猪`、`随机小猪`、`找猪` 三组指令都会注册到 Koishi
- `今日小猪` 及其别名输出图片卡片
- `今日小猪 @某人`、`今日小猪@某人` 和 `@某人 今日小猪` 都可查看被提及用户当天对应的今日小猪
- `随机小猪` 和 `找猪` 保持原始图片直出样式
- 对应功能被禁用时，指令仍可触发，但会返回“当前已被禁用”的提示
- 当前内置 `128` 条本地“今日小猪”词条与配套图片资源

## 声明

- 本仓库中的 Koishi 适配代码与当前实现，全部由 AI 协助完成。
- 本项目基于原始项目的功能思路进行 Koishi 移植与图片样式适配，不是原作者发布的官方 Koishi 版本。

## 原始项目

- NoneBot 版本原始仓库：[Bearlele/nonebot-plugin-rollpig](https://github.com/Bearlele/nonebot-plugin-rollpig)
- AstrBot 图片输出参考仓库：[MegSopern/astrbot_plugin_rollpig](https://github.com/MegSopern/astrbot_plugin_rollpig)
- PigHub 图片来源：[https://pighub.top/](https://pighub.top/)

## 功能

- `今日小猪`：按用户维度记录当天的小猪人格，并输出图片卡片
- `今日小猪 @某人` / `今日小猪@某人`：查看被提及用户当天对应的今日小猪
- `@某人 今日小猪`：查看被提及用户当天对应的今日小猪
- `今天是什么小猪`、`本日小猪`、`当日小猪`：`今日小猪` 的兼容别名
- `随机小猪 [数量]`：从 PigHub 随机抽取猪猪图片
- `找猪 [关键词]`：按标题关键词搜索 PigHub 图片
- `找猪 -i <图片ID>`：按图片 ID 精确查找 PigHub 图片
- `搜猪`：`找猪` 的兼容别名

## 安装

```bash
npm i koishi-plugin-rollpig
```

然后在 Koishi 配置中：

- 启用 `rollpig` 插件
- 如需关闭某项功能，使用对应开关；关闭后命令仍会保留，但调用时会返回“当前已被禁用”的提示

配置示例：

```yaml
plugins:
  rollpig:
    enableTodayPig: true
    enableRandomPig: true
    enableFindPig: true
```

## 配置项

- `dataDir`：插件缓存目录，默认 `data/rollpig`
- `maxRandomCount`：`随机小猪` 最大允许数量，默认 `20`
- `maxFindResults`：`找猪` 最大返回结果数，默认 `20`
- `remoteCacheHours`：PigHub 远程缓存刷新间隔，默认 `12`
- `startupRefresh`：启动后是否后台刷新 PigHub 缓存，默认 `true`
- `timezone`：`今日小猪` 使用的时区，留空表示跟随宿主环境
- `enableTodayPig`：是否启用“今日小猪”相关指令，默认 `true`
- `enableRandomPig`：是否启用“随机小猪”指令，默认 `true`
- `enableFindPig`：是否启用“找猪 / 搜猪”指令，默认 `true`
- 功能被禁用时，对应指令仍可触发，但会返回“当前已被禁用”的提示

## 使用示例

```text
今日小猪
今日小猪 @某人
今日小猪@某人
@某人 今日小猪
随机小猪
随机小猪 3
找猪 可爱
找猪 -i 3
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

- [nonebot-plugin-rollpig](https://github.com/Bearlele/nonebot-plugin-rollpig)
- [astrbot_plugin_rollpig](https://github.com/MegSopern/astrbot_plugin_rollpig)
- [PigHub](https://pighub.top/)
