---
title: "对等名称解析协议 | Microsoft Docs"
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
ms.assetid: 11940511-c124-4d91-ae31-d4ed6e81ee58
caps.latest.revision: 14
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 14
---
# 对等名称解析协议
在对环境，解决彼此的网络位置的对等类使用特定名称解析系统中\(地址、协议和端口\)从名称或标识符的其他类型。  过去，对等类名称解析由本身临时连接以及其他缺点复杂在域名系统\(DNS\)中。  
  
 Microsoft® Windows®对网络连接平台解决对等类名称解析协议\(PNRP\)，一个在Windows vista ™首先开发对于Windows XP然后升级的安全性，可升级和动态名称注册和名称解析协议的此问题。  PNRP工作很与传统名称解析系统不同，打开应用程序开发人员的令人激动的新的可能性。  
  
 使用PNRP，对等类名称可应用于设备或单独的应用程序或服务在计算机。  对等类名称变换包括一个地址、端口和可扩展的负载。  此系统的优点包括到了容错能力、瓶颈而不会返回过时的地址的名称解析;使协议找到的移动用户极好的解决方案。  
  
 根据安全，对等类名称可以公布如受保护\(保护\)或不安全\(无\)保护。  PNRP使用公钥加密保护安全对等类名称以防止电子欺骗;计算机和服务可以将名称与PNRP。  
  
-   对等类名称解析协议演示以下属性:  
  
-   分配和几乎完全serverless。  服务器仅对于所需的自持过程。  
  
-   没有第三方参与的安全性名称释放。  没有财务成本不同， DNS名称释放， PNRP名称释放是瞬间和。  
  
-   PNRP更新时间，防止过时的地址解析。  
  
-   名称的分辨率通过PNRP在计算机以外的扩展通过还允许服务的名称转换。  
  
## System.Net.PeerToPeer命名空间  
  
-   PNRP功能由在.NET Framework 3.5版中的 <xref:System.Net.PeerToPeer> 命名空间定义。  它提供可用于将使用一个可用的PNRP服务注册和解析对等类名称的一组类型。  
  
-   \(PNRP和自定义对等解析器可以创建和实例化使用提供的类型在 <xref:System.ServiceModel.PeerResolvers> 命名空间。\)  
  
-   基本类型用于个可用的PNRP服务注册和解析名称如下所示:  
  
-   <xref:System.Net.PeerToPeer.Cloud>:定义描述一朵可用PNRP云，包括其大小的信息。  
  
-   <xref:System.Net.PeerToPeer.PeerName>:定义可用于注册和后续解决在云中的一对等类的一个对等类名称。  
  
-   <xref:System.Net.PeerToPeer.PeerNameRecord>:定义在包含对等类的注册信息，包括网络结束对等类可以联系的PNRP云的记录。  
  
-   <xref:System.Net.PeerToPeer.PeerNameRegistration>:定义为一个对等类名称注册过程，包括方法来启动和停止对等类名称注册。  
  
-   <xref:System.Net.PeerToPeer.PeerNameResolver>:定义解决的对等类名称定向到其网络末尾，包括解析的同步和异步方法。  
  
## 请参阅  
 <xref:System.ServiceModel.PeerResolvers>   
 <xref:System.Net.PeerToPeer>   
 [网络编程示例](../../../docs/framework/network-programming/network-programming-samples.md)   
 [对技术示例](http://go.microsoft.com/fwlink/?LinkID=179571)