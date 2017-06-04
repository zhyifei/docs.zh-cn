---
title: "IPv6 自动配置 | Microsoft Docs"
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
ms.assetid: 581c1d21-1013-43a3-bf3e-2d9ead62b79c
caps.latest.revision: 5
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 5
---
# IPv6 自动配置
IPv6的一个重要的目标是支持即插即用的节点。  即插入节点到IPv6网络并将其自动配置，而无需任何人工干预应是可能的。  
  
## 自动配置的类型  
 IPv6支持自动配置的以下类型:  
  
-   **Stateful auto\-configuration**。  此配置要求人工干预的某个特定级别，因为它需要IPv6 \(DHCPv6\)服务器的项宿主动态配置协议节点的安装和管理的。  DHCPv6服务器保留它提供配置信息的节点列表。  它还维护状态信息，这样服务器了解每个地址处于正在使用，，以及何时可能适用于重新分配。  
  
-   **Stateless auto\-configuration**。  此配置适用于小型组织和个人。  在此情况下，每个宿主确定其地址从接收的路由器广告内容。  使用定义IEEE EUI\-64的标准该地址的网络ID部分，假定主机地址的唯一性在链接的是合理的。  
  
 无论该地址如何确定的，节点必须验证其潜在的地址到本地链接是唯一的。  这是通过发送周围垦请信息完成上载的潜在的地址。  如果该节点接收任何答复;它知道该地址已被使用，并且必须确定另一个地址。  
  
## IPv6移动性  
 移动设备的增殖引入了新的要求:计算机必须能够随意更改IPv6 Internet的位置和保持现有连接。  为了提供此功能，移动节点分配它总能达到home地址。  当移动节点"主页"时，它连接到主页链接并使用其home地址。  当移动节点是从主页"，家庭代理，通常是一路由器、中转消息在节点之间移动和节点它进行通信。  
  
## 请参阅  
 [Internet 协议版本 6](../../../docs/framework/network-programming/internet-protocol-version-6.md)   
 [套接字](../../../docs/framework/network-programming/sockets.md)