# mihomo (clash-meta) rulesets

## ru-bundle
include: [itdoginfo-inside-russia](https://github.com/itdoginfo/allow-domains/) + [no-russia-hosts](https://github.com/dartraiden/no-russia-hosts) + [antifilter-community](https://community.antifilter.download/)
<details>
  <summary>how to add</summary>
  
<details>
  <summary>binary rule-set .mrs</summary>
  
```yaml
rule-providers:
  ru-bundle:
    type: http
    behavior: domain
    format: mrs
    url: https://github.com/legiz-ru/mihomo-rule-sets/raw/main/ru-bundle/rule.mrs
    path: ./ru-bundle/rule.mrs
    interval: 86400
rules:
  - RULE-SET,ru-bundle,PROXY
  - MATCH,DIRECT
```

</details>
<details>
  <summary>add to vpnbot</summary>
  
```shell
PROXY:domain:86400:https://github.com/legiz-ru/mihomo-rule-sets/blob/main/ru-bundle/rule.mrs
```

</details>
</details>

## oisd
include all list from [oisd](oisd.nl)
<details>
  <summary>how to add</summary>
  
<details>
  <summary>binary rule-set .mrs</summary>
  
```yaml
rule-providers:
  oisd_big:
    type: http
    behavior: domain
    format: mrs
    url: https://github.com/legiz-ru/mihomo-rule-sets/raw/main/oisd/big.mrs
    path: ./oisd/big.mrs
    interval: 86400
  oisd_small:
    type: http
    behavior: domain
    format: mrs
    url: https://github.com/legiz-ru/mihomo-rule-sets/raw/main/oisd/small.mrs
    path: ./oisd/small.mrs
    interval: 86400
  oisd_nsfw_small:
    type: http
    behavior: domain
    format: mrs
    url: https://github.com/legiz-ru/mihomo-rule-sets/raw/main/oisd/nsfw_small.mrs
    path: ./oisd/nsfw_small.mrs
    interval: 86400
  oisd_nsfw_big:
    type: http
    behavior: domain
    format: mrs
    url: https://github.com/legiz-ru/mihomo-rule-sets/raw/main/oisd/nsfw.mrs
    path: ./oisd/nsfw_big.mrs
    interval: 86400
rules:
  - RULE-SET,oisd_small,REJECT
  - RULE-SET,oisd_big,REJECT
  - RULE-SET,oisd_nsfw_small,REJECT
  - RULE-SET,oisd_nsfw_big,REJECT
  - MATCH,DIRECT
```

</details>
<details>
  <summary>add to vpnbot</summary>
  
**BIG LIST:**

```shell
REJECT:domain:86400:https://github.com/legiz-ru/mihomo-rule-sets/raw/main/oisd/big.mrs
```
**SMALL LIST:**

```shell
REJECT:domain:86400:https://github.com/legiz-ru/mihomo-rule-sets/raw/main/oisd/small.mrs
```
**NSFW BIG LIST:**

```shell
REJECT:domain:86400:https://github.com/legiz-ru/mihomo-rule-sets/raw/main/oisd/nsfw.mrs
```
**NSFW SMALL LIST:**

```shell
REJECT:domain:86400:https://github.com/legiz-ru/mihomo-rule-sets/raw/main/oisd/nsfw_small.mrs
```

</details>
</details>

## re-filter
include domain & ip list from [re-filter](https://github.com/1andrevich/Re-filter-lists)
<details>
  <summary>how to add</summary>
  
<details>
  <summary>binary rule-set .mrs</summary>
  
```yaml
rule-providers:
  refilter_domains:
    type: http
    behavior: domain
    format: mrs
    url: https://github.com/legiz-ru/mihomo-rule-sets/raw/main/re-filter/domain-rule.mrs
    path: ./re-filter/domain-rule.mrs
    interval: 86400
  refilter_ipsum:
    type: http
    behavior: ipcidr
    format: mrs
    url: https://github.com/legiz-ru/mihomo-rule-sets/raw/main/re-filter/ip-rule.mrs
    path: ./re-filter/ip-rule.mrs
    interval: 86400
rules:
  - RULE-SET,refilter_domains,PROXY
  - RULE-SET,refilter_ipsum,PROXY
  - MATCH,DIRECT
```

</details>
<details>
  <summary>add to vpnbot</summary>
  
```shell
REJECT:domain:86400:https://github.com/legiz-ru/mihomo-rule-sets/raw/main/re-filter/domain-rule.mrs
```
```shell
REJECT:ipcidr:86400:https://github.com/legiz-ru/mihomo-rule-sets/raw/main/re-filter/ip-rule.mrs
```

</details>
</details>

# another mihomo rulesets
- [mihomo rule-sets](https://github.com/MetaCubeX/meta-rules-dat/tree/meta) by MetaCubeX include: asn/geoip/geosite

