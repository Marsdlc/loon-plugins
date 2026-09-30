# Loon 插件库

个人 Loon 插件合集，后续插件统一放在 `plugins/` 目录。

## 插件订阅

| 插件 | 功能 | 订阅地址 |
| --- | --- | --- |
| 小红书屏蔽首页及本地视频 | 过滤首页和本地信息流，仅保留 `type=normal` 的条目 | [订阅](https://raw.githubusercontent.com/Marsdlc/loon-plugins/main/plugins/XiaoHongShuBlockVideo.plugin) |

## 使用方法

1. 在 Loon 的插件页面添加插件，将上面的订阅地址粘贴到 URL 输入框并保存、启用。
2. 开启复写和 MitM，安装并信任 Loon CA 证书。
3. 完全退出小红书后重新打开，刷新首页和本地页。
4. 后续更新通过 Loon 更新此远程插件获取。订阅地址保持不变。

添加新插件时，将 `.plugin` 文件放入 `plugins/`，再在上表添加对应的 Raw 链接。

## 来源与验证

小红书规则来自 ddgksf2013 的 `XiaoHongShuBlockVideo.conf` V1.0.1（2026-04-18）。

- [原始资源](https://ddgksf2013.top/rewrite/XiaoHongShuBlockVideo.conf)
- [本次转换采用的镜像快照](https://github.com/ifflagged/Romeo/blob/5396353603198b21e8716892e69311f8b11bbbbb/Modules/QuantumultX/ddgksf2013/XiaoHongShuBlockVideo.conf)

转换保留原 URL 正则、jq 表达式及 MitM 域名，只改为 Loon 插件格式，不依赖外部 JS。
原站当时无法读取，尚未核实是否有后续更新。已检查 URL 匹配范围及 jq 样例过滤，尚未在 iPhone / Loon 中实测。
过滤规则会移除所有非 `normal` 条目，适用范围为 `homefeed` 和 `localfeed`。
