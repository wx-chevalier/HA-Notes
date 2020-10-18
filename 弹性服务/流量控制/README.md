# 流量控制

QPS 流量控制:对特定 URL 做单机维度的限流。CC 攻击防护:对特定黑名单进行拦截（黑名单可以根据策略生成，也可以手工添加)。CC = Challenge Collapsar，意为“挑战黑洞”，其前身名为 Fatboy 攻击，是 DDOS（分布式拒绝服务）的一种，是利用不断对网站发送连接请求致使形成拒绝服务的目的。业界赋予这种攻击名称为 CC（Challenge Collapsar，挑战黑洞），是由于在 DDOS 攻击发展前期，绝大部分都能被业界知名的“黑洞”（Collapsar）抗拒绝服务攻击系统所防护，于是在黑客们研究出一种新型的针对 http 的 DDOS 攻击后，即命名 Challenge Collapsar，声称黑洞设备无法防御，后来大家就延用 CC 这个名称至今。

CC 攻击一般使用 IP 代理工具，使你见不到攻击者真实源 IP，见不到特别大的异常流量，但造成服务器无法进行正常连接。TMD 系统是典型的 C/S 架构，由 Client 收集数据和执行防御动作，Server 进行攻击检测及生成防御策略。同时在 client 或 server 异常时不会阻塞正常业务，保障系统稳定性。对原有链路的 RT 不会有影响。另外策略的生成及下发一般需要 3~5 秒。

![image](https://user-images.githubusercontent.com/5803001/52053233-c4948a00-2593-11e9-9257-3733ec9df311.png)

Server 部署在独立节点上，由安全团队负责运维，单台 Server 可以接入多个应用，并且对不同的应用执行不同的防御策略，server 多数使用物理机，单机处理能力在 50Wqps 左右；另外 TMD 也支持 cluster mode 部署，Server 可以水平扩展。
