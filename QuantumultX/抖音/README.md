# 抖音

抖音 IP 分流，由 `QuantumultX/dyip.list` 拆分而来，规则内容不变，两个文件配合使用，缺一不可。

- **走代理**（[dyip-proxy.list](https://raw.githubusercontent.com/xqwzka/ios-rule-split/main/QuantumultX/%E6%8A%96%E9%9F%B3/dyip-proxy.list)）：3 条，走 `抖音` 策略组
  - `snssdk.com`、`amemv.com`、`zijieapi.com`
- **走直连**（[dyip-direct.list](https://raw.githubusercontent.com/xqwzka/ios-rule-split/main/QuantumultX/%E6%8A%96%E9%9F%B3/dyip-direct.list)）：13 条，走 `direct`
  - 抖音 CDN、图片、音乐等域名

`config.conf` 里 `[filter_remote]` 的顺序是 proxy 在前、direct 在后，都在原来 `dyip.list` 的位置。

`抖音` 策略组只含地区策略（日本、香港、新加坡、美国、台湾、韩国、英国、加拿大、德国、法国、荷兰、泰国、马来西亚），不含具体节点。
