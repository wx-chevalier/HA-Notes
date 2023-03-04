# 分布式追踪

2010 年，Google 的一篇 Dapper 论文开启了分布式追踪的序章。CNCF 的 OpenTracing 作为分布式追踪的标准协议，定义了一套厂商无关、语言无关的规范，也有 Jaeger 、Zipkin 等项目的实现和支持。随后 Google 和微软提出了 OpenCensus 项目，在定义分布式追踪协议的基础上，也规范了应用性能指标，并实现了一套标准的 API ，为可观测性能力统一奠定了基础。经过对已有的标准协议不停的打磨和演变，CNCF 提出了 OpenTelemetry，它结合了 OpenTracing 与 OpenCensus 两个项目，成为了一个厂商无关、平台无关的支撑可观测性三大支柱的标准协议和开源实现。

另一方面，基于 Dapper 论文的思想，国内也有 SkyWalking 开源项目实现了分布式追踪，由于探针的无侵入性，SkyWalking 获得了大量的用户，并且有越来越多的贡献者推动着它的高速迭代。以 Dapper 的定义作为基准，一个标准的分布式 Trace 示例如下图所示。一个 Trace 是由 Span 构成的有向无环图 (DAG)，Span 是一个最小粒度的调用，既可以指代一个程序块执行，也可以指代一次 HTTP 等应用协议的远程调用。

![基于 Span 的调用](https://assets.ng-tech.icu/item/20230303143405.png)

目前在做分布式追踪的开源项目很多，接下来挑选几个社区活跃度高，且生产环境使用多的项目对比一下传输协议的差异，大致如下：

![协议解读](https://assets.ng-tech.icu/item/20230303143508.png)
