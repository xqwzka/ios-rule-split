# ios规则分流

自用。圈X（QuantumultX）分流规则，源自 blackmatrix7/ios_rule_script，合并后自用。

## 圈X

### meat：Facebook + Instagram + Threads

```text
[filter_remote]
https://raw.githubusercontent.com/xqwzka/ios-fenliu-guize/main/QuantumultX/meat.list, tag=meat, force-policy=meat, update-interval=86400, enabled=true
```

- 文件：`QuantumultX/meat.list`
- 规则：572 条（HOST-SUFFIX 545、HOST-KEYWORD 3、IP-CIDR 23、IP-ASN 1）
- 来源：blackmatrix7 的 Facebook（570 条）、Instagram（4 条）、Threads（1 条），按类型+域名去重（cdninstagram.com、instagr.am、instagram.com 三条重复只留一条），策略统一为 `meat`
- 用法：需在圈X里建一个名为 `meat` 的策略组，或把上面 `force-policy=meat` 改成你自己的策略组名
