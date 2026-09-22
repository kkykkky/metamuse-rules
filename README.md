# metamuse-rules

Meta Muse（Muse Spark / Model API / Muse Code）的 Surge 规则集，由本机 launchd 任务每天 02:00 自动维护。

| 文件 | 类型 | 说明 |
|---|---|---|
| `MetaMuse.domainset` | DOMAIN-SET | Muse 相关域名（`+.meta.ai`、`ai.developer.meta.com`、`ai.meta.com`、`+.llama.com`） |
| `MetaMuse.ipcidr` | RULE-SET | IP 兜底网段 + 自动补充的实测端点（基线未覆盖时追加 /32、/128） |

Surge 模块（经 iCloud 同步到 Mac / iPhone）引用：

```
DOMAIN-SET,https://raw.githubusercontent.com/kkykkky/metamuse-rules/main/MetaMuse.domainset,🤖AI,extended-matching
RULE-SET,https://raw.githubusercontent.com/kkykkky/metamuse-rules/main/MetaMuse.ipcidr,🤖AI,no-resolve
```

维护任务：`~/Library/LaunchAgents/com.chengchen.metamuse-maintain.plist`
日志：`~/Library/Logs/metamuse-maintain.log`
