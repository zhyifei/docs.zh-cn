---
title: "Internet 协议版本 6 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "IPv6，改进"
  - "IPv4"
  - "IPv6"
  - "Internet 协议版本 6，改进"
  - "Internet 协议版本 6"
ms.assetid: e6fa8ebd-010a-4c48-a5ec-a5102c53c06f
caps.latest.revision: 11
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 11
---
# Internet 协议版本 6
internet协议版本6 \(IPv6\)是标准协议新套件Internet的网络层的。  IPv6旨在解决许多internet协议套件的最新版本的问题\(称为IPv4\)有关地址获取尽，安全性，自动配置，扩展性，依此类推。  IPv6展开Internet的功能使新类型的应用程序，包括对和移动应用程序。  以下主要问题当前IPv4协议:  
  
-   地址空间的快速获取尽。  
  
     这将导致使用网络地址转换器\(NATs\)一个多个私人地址一个公共IP地址。  此结构所产生的主要问题开销和"端到端连接。  
  
-   缺少层次结构支持。  
  
     由于其继承的预定义的选件类组织， IPv4缺少真正层次结构支持。  不能对结构IP地址的正确映射网络拓扑的方法。  此键的设计缺陷创建需要用course表发送IPv4数据包到Internet上的任意位置。  
  
-   复杂的网络配置。  
  
     使用IPv4，必须静态分配地址或使用其他配置协议\(如、。  在理想的情况下，宿主无需依赖于、基础结构的管理。  相反，它们可以配置自己根据其网络段。  
  
-   缺少内置身份验证和保密性。  
  
     IPv4不提供交换的数据的身份验证或加密的任何框架要求支持。  这将使用IPv6。  Internet协议安全\(IPSec\)是IPv6需要支持。  
  
 新的协议组都必须符合以下基本要求:  
  
-   大型路由和解决与低开销。  
  
-   各种连接的情况下自动配置。  
  
-   内置身份验证和保密性。  
  
 有关更多信息，请参见[IPv6 寻址](../../../docs/framework/network-programming/ipv6-addressing.md)、[IPv6 路由](../../../docs/framework/network-programming/ipv6-routing.md)、[IPv6 自动配置](../../../docs/framework/network-programming/ipv6-auto-configuration.md)、[启用和禁用 IPv6](../../../docs/framework/network-programming/enabling-and-disabling-ipv6.md)和[如何：修改计算机配置文件以启用 IPv6 支持](../../../docs/framework/network-programming/how-to-modify-the-computer-configuration-file-to-enable-ipv6-support.md)。  
  
## 引用  
 下面是选定的RFC文档可以在internet工程特殊工作组站点找到\([http:\/\/www.ietf.org](http://www.ietf.org/)\):  
  
-   在将来的Internet体系结构的RFC 1287，。  
  
-   RFC 1454，主张比较对于IP的下一个版本。  
  
-   RFC 2373，则IP 6版解决的体系结构。  
  
-   RFC 2374， IPv6可聚集的全局Unicast地址格式。  
  
 还可以找到有关的 [IPv6 Technet的区域](http://go.microsoft.com/fwlink/?LinkID=179658)IPv6相关的信息。  
  
## 请参阅  
 [IPv6套接字示例](http://go.microsoft.com/fwlink/?LinkID=179568)   
 [网络编程示例](../../../docs/framework/network-programming/network-programming-samples.md)   
 [套接字](../../../docs/framework/network-programming/sockets.md)