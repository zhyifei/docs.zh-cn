---
title: "对等名称和 PNRP ID | Microsoft Docs"
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
ms.assetid: afa538e8-948f-4a98-aa9f-305134004115
caps.latest.revision: 5
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 5
---
# 对等名称和 PNRP ID
对等类名称表示通信的终结点，可以是计算机、用户、组，服务或任何与对等类可以将其解析为 IPv6 地址。  对等类名称解析协议\(PNRP\)采用统计上一个同级名称PNRP ID的创建，后者用于标识云成员。  
  
## 对等类名称  
 对等类名称可以注册为不安全或获取。  不安全的名称是假冒受约束的文本字符串，，任何人都能注册重复不安全的名称。  不安全的名称最适于私有或受保护的网络。  获取的名称保护证书和数字签名。  仅当原始发行者可证明一个get名称的所有权。  
  
 云和大小的组合为参与PNRP事件的对等类提供一个合理安全环境。  但是，使用一个获取对等类名称不保证网络连接应用程序的总体安全性。  应用程序的安全依赖于实现。  
  
 获取对等类名称由其所有者只注册和保护公钥加密。  一个获取对等类名称被视为拥有具有对实体对应的私钥。  所有权可以通过认证的对等类地址\(CPA\)证书，使用私钥，签名。  恶意用户无法伪造对等类名称的所有权没有对应的私钥。  
  
## PNRP ID  
 ![PNRP ID](../../../docs/framework/network-programming/media/fdc9e8a0-4a1c-488d-a019-bc3a1973220c.png "fdc9e8a0\-4a1c\-488d\-a019\-bc3a1973220c")  
  
 PNRP ID组成的如下:  
  
-   高位128位，即对\(P2P\) ID，是对等类名称的哈希分配给终结点。  对等类名称具有以下格式: *Authority.Classifier*.  用于捕获的名称， *权限* 是对等类名称的公钥的安全哈希算法1 \(SHA1\) 哈希，十六进制字符的。  对于不安全的名称， *权限* 是单个字符“0 "。  *分类器* 是标识应用程序的字符串。  对等类名称分类器超过149个字符的最大长度不大，包括 `null` 结束符。  
  
-   低序128位用于服务位置使用，为生成的数字标识同一个P2P ID不同的实例在同一朵云的。  
  
 P2P ID和服务位置的这种组合允许多个PNRP ID从一台计算机上注册。  
  
## 请参阅  
 <xref:System.Net.PeerToPeer.PeerName>   
 <xref:System.Net.PeerToPeer>