---
layout: post_item
title:  '更快的可靠传输--QUIC研究'
date:   2014-03-12
author: 薛笛
categories : [技术分析]
tags: [传输技术]
---

![QUIC-Logo](http://t2.qpic.cn/mblogpic/94b166a547515743e832/2000 "QUIC-Logo")

**[QUIC](#)**（Quick UDP Internet Connections，读做quick）是Google为自家浏览器专门定制的、基于UDP的可靠传输协议。无论是协议名字本身还是协议产生的动因，都充分体现了Google对于“快”的极致追求。虽然Google也在IETF推动了多项关于TCP提速方面的草案/标准，但Chrome项目的这些开发者终究还是焦虑于内核实现的落地和普及速度，决定以UDP为基础从应用层另起炉灶。虽然这种选择还存在争议、效果也有待验证，但其基本思路还是很有借鉴意义。无论该项目最终成功与否，都对我们做无线网络、Long-Fat-Pipe下的数据传输业务提供了一种新思路。

<!--more-->

##QUIC的主要[优点][QUIC_BLOG]
- 与[TLS(Transport Layer Security)][TLS_WIKI]等同的安全性
- 实现0-RTT建连接
- Packet Pacing（即不要一股脑丢一大坨数据给对端，要有节奏地搞）来减少重传时延
- 用UDP实现多通道来避免TCP中的head-of-line阻塞（即同一个连接中的包被排队发送的情况）
- 利用专门的连接标识，以减少移动终端的重连
- 可拔插的拥塞控制机制

##目前仅有的一些参考资料
- [QUIC_PPT][QUIC_PPT]：一个对QUIC的感性认识，很有用
- [QUIC_FAQ][QUIC_FAQ]
- [QUIC__DESIGN__SPEC][QUIC_DESIGN_SPEC]
- [QUIC__PROTO__SPEC][QUIC_PROTO_SPEC]
- [QUIC_BLOG][QUIC_BLOG]

未完待续。。。

[QUIC_PPT]: https://docs.google.com/presentation/d/13LSNCCvBijabnn1S4-Bb6wRlm79gN6hnPFHByEXXptk/edit#slide=id.g176a9a2e9_0143
[QUIC_FAQ]: https://docs.google.com/document/d/1lmL9EF6qKrk7gbazY8bIdvq3Pno2Xj_l_YShP40GLQE/edit#heading=h.h3jsxme7rovm
[QUIC_DESIGN_SPEC]: https://docs.google.com/document/d/1RNHkx_VvKWyWg6Lr8SZ-saqsQx7rFV-ev2jRFUoVD34/edit#heading=h.nvk2biis6bpk
[QUIC_PROTO_SPEC]: https://docs.google.com/document/d/1WJvyZflAO2pq77yOLbp9NsGjC1CHetAXV8I0fQe-B_U/edit#
[QUIC_GOOGLE_GROUP]: https://groups.google.com/a/chromium.org/forum/#!forum/proto-quic
[QUIC_BLOG]: http://blog.chromium.org/2013/06/experimenting-with-quic.html
[TLS_WIKI]: https://en.wikipedia.org/wiki/Transport_Layer_Security
