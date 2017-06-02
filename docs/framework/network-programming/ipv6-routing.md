---
title: "IPv6 路由 | Microsoft Docs"
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
ms.assetid: c98731b4-b542-46a2-9947-1cea63c186b2
caps.latest.revision: 4
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 4
---
# IPv6 路由
一个灵活的路由机制是IPv6的优点。  由于IPv4网络ID和分配的方法，用course表需要由是在Internet主干线的路由器维护。  这些路由器必须知道所有路由为了向前可能会处理在Internet上的所有节点的数据包。  与其功能复合地址， IPv6允许灵活解决和极大地减少course表的大小。  在此新解决的体系结构方面，中间路由器必须只保留跟踪其网络上的本地部分为了能正确转发消息。  
  
## 周围看到  
 周围看到提供某些功能是:  
  
-   路由器发现。  这允许宿主标识本地路由器。  
  
-   地址转换。  这允许节点解决相应的NeXT跳跃地址\(地址转换协议的 \[ARP\] 一个链接层地址\)。  
  
-   地址自动配置。  这允许宿主自动配置站点本地和全局地址。  
  
 周围看到针对IPv6 \(ICMPv6\)包含的消息使用internet协议\(smtp\)控件信息:  
  
-   路由器广告。  发送由路由器基于一个虚拟时间基类型或响应路由器垦请使用。  IPv6路由器使用对它们的可用性、地址标题和其他参数播发的路由器广告。  
  
-   请看垦。  发送由宿主请求该链接的路由器立即发送一个路由器广告。  
  
-   周围垦请使用。  发送由地址转换的节点，请重复地址检测，或验证相邻元素进行访问。  
  
-   周围广告。  发送按节点响应周围垦请或通知一个不同的邻近在链接层地址上的。  
  
-   重定向。  发送由路由器指示一种更好的NeXT跳跃地址到一个发送的节点的特定目标。  
  
## 请参阅  
 [Internet 协议版本 6](../../../docs/framework/network-programming/internet-protocol-version-6.md)   
 [套接字](../../../docs/framework/network-programming/sockets.md)