---
title: "IPv6 寻址 | Microsoft Docs"
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
  - "Internet 协议版本 6，地址"
  - "邻居发现"
  - "IPv6，启用"
  - "IPv6，移动性和"
  - "Internet 协议版本 6，任意广播地址"
  - "IPv6，邻居发现"
  - "Internet 协议版本 6，自动配置"
  - "Internet 协议版本 6，启用"
  - "IPv6，单播地址"
  - "IPv6，自动配置"
  - "Internet 协议版本 6，路由"
  - "IPv6，RFC 文档"
  - "IPv6，路由"
  - "Internet 协议版本 6，禁用"
  - "Internet 协议版本 6，单播地址"
  - "IPv6，多播地址"
  - "Internet 协议版本 6，移动性和"
  - "Internet 协议版本 6，RFC 文档"
  - "Internet 协议版本 6，邻居发现"
  - "IPv6，任意广播地址"
  - "Internet 协议版本 6，多播地址"
  - "IPv6，地址"
  - "IPv6，禁用"
ms.assetid: 20a104ae-1649-4649-a005-531a5cf74c93
caps.latest.revision: 10
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 10
---
# IPv6 寻址
在internet协议版本6 \(IPv6\)，则address长度为128位。  这样一个用地址空间中的一个原因是分解可用地址到的路由字段层次结构反映Internet的拓扑。  另一个原因是映射的网络适配器\(或接口\)地址计算机连接到网络。  IPv6以固有功能的功能解决地址在其最低级别，在网络接口级别，并具有自动配置功能。  
  
## 文本表示形式  
 下面是用于的三个约定窗体表示 IPv6 地址作为文本字符串:  
  
-   **Colon\-hexadecimal form**。  这是一个首选窗体 n:n:n:n:n:n:n:n。  每个n表示十六进制值的地址的八个16位组件之一。  例如：`3FFE:FFFF:7654:FEDA:1245:BA98:3210:4562`。  
  
-   **Compressed form**。  由于地址长度，通常会包含零的长字符串地址。  为了简化编写这些地址，请使用压缩的窗体，一个连续顺序0块由双冒号符号表示\(::\)。  此符号只能出现一次于地址。  例如，多路广播地址 `FFED:0:0:0:0:BA98:3210:4562` 以压缩的形式是 `FFED::BA98:3210:4562`。  unicast地址 `3FFE:FFFF:0:0:8:800:20C4:0` 以压缩的形式是 `3FFE:FFFF::8:800:20C4:0`。  启用地址 `0:0:0:0:0:0:0:1` 以压缩的形式是 `::`1。  未指定的地址 `0:0:0:0:0:0:0:0` 以压缩的形式是 `::`。  
  
-   **Mixed form**。  此窗体将IPv4和 IPv6 地址。  在这种情况下，地址格式为 n:n:n:n:n:n:d.d.d.d，每个 n 表示六个 IPv6 高 16 位地址元素的十六进制值，每个 d 表示 IPv4 地址的十进制值。  
  
## 地址类型  
 在地址上的前导位定义特定 IPv6 地址类型。  包含这些驱动的位的可变长度字段调用窗体的标题\(FP\)。  
  
 IPv6 unicast地址分为两部分。  第一部分包含地址，前缀，第二部分包含接口标识符。  一个简洁方式表示 IPv6 地址\/前缀组合如下所示: IPv6 地址\/前缀长。  
  
 下面是一个地址的示例使用64位标题。  
  
 `3FFE:FFFF:0:CD30:0:0:0:0/64`.  
  
 在此示例中的标题由 `3FFE:FFFF:0:CD30`。  该地址可能还会写入速率压缩的形式，作为 `3FFE:FFFF:0:CD30::/64`。  
  
 IPv6定义以下地址类型:  
  
-   **Unicast address**。  单个接口的标识符。  数据包发送到该地址被传递给标识的接口。  unicast当从多路广播地址是已知的。高位八位字节的值。  多路广播地址的高位八位字节具有FF的十六进制值。  此八位字节的其他值标识一个unicast地址。  下面是unicast地址的不同类型:  
  
    -   **Link\-local addresses**。  这些地址在单个链接使用它具有以下格式:FE80::*InterfaceID*。  链接本地地址使用在链接的节点之间的自动地址配置，周围查看，或者，在路由器不存在。  链接本地地址使用主要在启动，因此，当系统没有获得更大的范围地址。  
  
    -   **Site\-local addresses**。  这些地址在一个网站使用它具有以下格式:FEC0::*SubnetID*:*InterfaceID*。  站点本地地址为解决使用站点内，而无需进行全局前缀。  
  
    -   **Global IPv6 unicast addresses**。  这些地址可以通过Internet使用和具有以下格式:010 \(FP， 3位\) TLA ID \(13位\)保留了\(8位\) NLA ID \(24位\) SLA ID \(16位\) *InterfaceID* \(64位\)。  
  
-   **Multicast address**。  中的标识符设置接口\(通常为属于不同的节点\)。  数据包发送到该地址被传递给该地址确定的所有接口。  多路广播地址类型取代IPv4广播地址。  
  
-   **Anycast address**。  中的标识符设置接口\(通常为属于不同的节点\)。  数据包发送到该地址只发送到该地址确定的接口。  这是最新的接口标识的由路由指标。  Anycast当从unicast地址空间中采用并不是语法上的可区分。  作为其配置功能，解析的接口实现unicast和anycast地址之间的差异。  
  
 通常，节点始终有一个链接本地地址。  它可能有站点本地地址和一个或多个全局地址。  
  
## 请参阅  
 [Internet 协议版本 6](../../../docs/framework/network-programming/internet-protocol-version-6.md)   
 [套接字](../../../docs/framework/network-programming/sockets.md)