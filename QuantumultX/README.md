# Quantumult X 规则与配置说明

本文件夹是自用 Quantumult X 分流规则库，全部免登录、无节点、无证书，直接订阅使用。

## 主配置

- **主配置**（[config.conf 原始链接](https://raw.githubusercontent.com/xqwzka/ios-rule-split/main/QuantumultX/config.conf)）：Quantumult X 的完整配置，策略组、订阅引用、重写脚本都在里面。圈 X 里直接订阅这个文件即可，在线地址：https://qx.beatsr.shop/config.conf

## 规则文件（按 config.conf 里的订阅顺序）

- **交易所**（[exchange.list 原始链接](https://raw.githubusercontent.com/xqwzka/ios-rule-split/main/QuantumultX/exchange.list)）：币安、欧易、Bybit 等交易所域名，78 条，走日本节点。
- **屏蔽更新**（[ios-update.list 原始链接](https://raw.githubusercontent.com/xqwzka/ios-rule-split/main/QuantumultX/ios-update.list)）：屏蔽 iOS 系统更新的域名，91 条，全部 reject。
- **TG**（[telegram.list 原始链接](https://raw.githubusercontent.com/xqwzka/ios-rule-split/main/QuantumultX/telegram.list)）：Telegram 的 IP 段，72 条，按国家分流（日本 / 美国等）。
- **抖音 IP**（[dyip.list 原始链接](https://raw.githubusercontent.com/xqwzka/ios-rule-split/main/QuantumultX/dyip.list)）：抖音相关域名，16 条；其中媒体 CDN 走直连，网关走代理。
- **Meta 系**（[meat.list 原始链接](https://raw.githubusercontent.com/xqwzka/ios-rule-split/main/QuantumultX/meat.list)）：Facebook / Instagram 等 Meta 系域名，592 条，走 ig 策略组。文件本身不写策略，策略由订阅行的 force-policy 指定。
- **Emby**（[emby.list 原始链接](https://raw.githubusercontent.com/xqwzka/ios-rule-split/main/QuantumultX/emby.list)）：Emby 相关域名，6 条。
- **推送**（[apple-push.list 原始链接](https://raw.githubusercontent.com/xqwzka/ios-rule-split/main/QuantumultX/apple-push.list)）：苹果推送服务相关域名和 IP，24 条，手写，不参与自动同步。
- **广告终结者**（[adblock.list 原始链接](https://raw.githubusercontent.com/xqwzka/ios-rule-split/main/QuantumultX/adblock.list)）：广告拦截规则，321345 条；前面 33 条是 Unbreak 白名单（直连），其余全部 reject。不要用 force-policy=reject 覆盖它。
- **全球分流**（[global.list 原始链接](https://raw.githubusercontent.com/xqwzka/ios-rule-split/main/QuantumultX/global.list)）：通用分流规则，44635 条；国内网站走直连，国际网站走代理。放在具体分流规则之后，作为兜底。
- **AI**（[ai.list 原始链接](https://raw.githubusercontent.com/xqwzka/ios-rule-split/main/QuantumultX/ai.list)）：海外 AI 服务域名，1066 条。注意：当前 config.conf 里的 AI 订阅用的是 VPSDance 的版本，这个文件是本仓库自备的备用。

## 说明

- 规则数量会随上游更新变化，以文件实际内容为准（上面数字是 2026-11-08 核对的）。
- 订阅顺序很重要：具体分流（交易所、抖音、TG 等）在前，广告在中，全球分流在最后兜底。
- 想单独用某一个文件时，在圈 X 的 `[filter_remote]` 里加一行，照抄 config.conf 里对应那行的写法即可。
