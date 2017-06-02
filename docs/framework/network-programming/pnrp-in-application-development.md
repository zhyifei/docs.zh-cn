---
title: "应用程序开发中的 PNRP | Microsoft Docs"
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
ms.assetid: 265615d6-4423-4b5d-8626-752e456f4f4e
caps.latest.revision: 6
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 6
---
# 应用程序开发中的 PNRP
在Windows vista中，网络连接应用程序通过简化的PNRP应用程序编程接口\(API\)可以访问名称、发布解析函数访问。  
  
## 实现对等类名称解析协议  
 简化的PNRP API，云未显式指定注册名称和地址;PNRP元素自动确定适当云连接和地址发布在云中。  
  
 对于Windows vista的高度简化的PNRP名称转换， PNRP名称现在集成getaddrinfo\(\) Windows套接字功能。  若要使用PNRP解决名称到 IPv6 地址，应用程序可以使用 getaddrinfo\(\)函数解析为完全限定域名\(FQDN\) name.prnp。  net，名称是对等类的名字。  pnrp。  net字段是在Windows vista中保留字段PNRP名称转换。  
  
 通过在对应用程序之间的消息由基础结构仍在处理例如PeerChannel和WCF [用数据和流](http://go.microsoft.com/fwlink/?LinkID=179652)。  
  
## 请参阅  
 <xref:System.Net.PeerToPeer>