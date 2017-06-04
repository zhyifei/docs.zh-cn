---
title: "PNRP 云 | Microsoft Docs"
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
ms.assetid: a82e2bf1-62ab-4c2d-83f3-3217a6aead2e
caps.latest.revision: 4
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 4
---
# PNRP 云
PNRP “云”表示能够彼此通信通过网络的设置节点。  该术语“云”与“对等类网格”和“对关系图”是同义词的。  
  
 节点之间的通信永远不应跨群进行。  <xref:System.Net.PeerToPeer.Cloud> 实例通过其区分大小写的名称来唯一标识。  一个对等方或节点可以连接到多个群。  
  
 群与网络接口之间的连接非常紧密。  在一台通过两个网卡连接不同子网的多宿主计算机上，将返回三个群：每个接口的每个链接本地地址一个群，还有一个全局范围群。  
  
 PNRP使用三个云“范围”，范围是分组计算机上进行查找:  
  
-   全局云对应于全局 IPv6 地址范围和全局地址并表示在整个IPv6 Internet的所有计算机。  只有一朵唯一全局云。  
  
-   链接本地云对应于链接本地 IPv6 地址范围和链接本地地址。  链接本地云用于特定链接，通常会与附加本地子网。  可以有多个链接本地云。  
  
 第三朵云，则朵特定于站点云，对应于站点 IPv6 地址范围和网站本地地址。  此云已弃用，不过，它在PNRP仍支持。  
  
## 云  
 PNRP云由 <xref:System.Net.PeerToPeer.Cloud> 选件类的实例表示的。  云的组使用一对等类由可枚举的 <xref:System.Net.PeerToPeer.CloudCollection> 选件类的实例表示的。  PNRP云的集合为当前对等类知道可通过调用静态 <xref:System.Net.PeerToPeer.Cloud.GetAvailableClouds%2A> 方法获取。  
  
 单个云具有唯一的名称，表示为一个256个字符Unicode字符串。  这些名称，与上面的范围外，用于构造单个实例云选件类。  这些实例可用于不使用序列化并重新生成。  
  
 对于云实例中创建或获取，对等类名称可以向它注册创建已知的对等类网格。  
  
## 请参阅  
 <xref:System.Net.PeerToPeer.Cloud>   
 [对等名称解析协议](../../../docs/framework/network-programming/peer-name-resolution-protocol.md)