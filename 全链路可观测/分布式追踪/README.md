# 分布式追踪

2010 年，Google 的一篇 Dapper 论文开启了分布式追踪的序章。CNCF 的 OpenTracing 作为分布式追踪的标准协议，定义了一套厂商无关、语言无关的规范，也有 Jaeger 、Zipkin 等项目的实现和支持。随后 Google 和微软提出了 OpenCensus 项目，在定义分布式追踪协议的基础上，也规范了应用性能指标，并实现了一套标准的 API ，为可观测性能力统一奠定了基础。经过对已有的标准协议不停的打磨和演变，CNCF 提出了 OpenTelemetry，它结合了 OpenTracing 与 OpenCensus 两个项目，成为了一个厂商无关、平台无关的支撑可观测性三大支柱的标准协议和开源实现。
