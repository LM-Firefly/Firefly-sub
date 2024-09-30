# Fly.io-Subconverter

在 fly.io 上搭建 subconverter

将配置文件等放在 [base/](https://github.com/LM-Firefly/Firefly-sub/tree/fly/base)文件夹内

fly.io 如若网络不畅，可以自行架设 [cloudflare worker](https://workers.cloudflare.com) 作为中转代理，同时限制他人对接口的滥用：

1. 复制 [cloudflare-worker.js](https://github.com/LM-Firefly/Firefly-sub/blob/fly/cloudflare-worker.js) 中的内容到 cloudflare worker 编辑页面中，并且修改 1-27 行（有注释）
2. 修改第 2 行的网址为你的 Fly.io 后端地址（不带末尾的/斜杠）
3. 匹配黑名单内中的关键词或正则的订阅网址会被屏蔽，默认禁用节点池网站以及放在 github 上的订阅链接
4. 只有白名单中的 IP 会被允许使用（这功能好像没用）

## 提供一个 demo, [fly-sub.fly.dev](https://fly-sub.fly.dev)

## 2026/09/09

- Dockerfile updated to Sub+SimpleWeb.26.0909.1752-c25221f
