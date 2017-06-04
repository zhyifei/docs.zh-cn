---
title: "网络应用程序的缓存管理 | Microsoft Docs"
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
  - "缓存 [.NET Framework]，网络应用程序"
  - "网络资源，缓存"
  - "Internet，缓存"
ms.assetid: fc258a40-f370-434f-ae09-4a8cb11ddaeb
caps.latest.revision: 13
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 13
---
# 网络应用程序的缓存管理
本主题及其相关子主题描述如何使用 <xref:System.Net.WebClient>、 <xref:System.Net.WebRequest>、 <xref:System.Net.HttpWebRequest>和 <xref:System.Net.FtpWebRequest> 选件类获取资源的缓存。  
  
 缓存为应用程序已请求的资源提供临时存储。  如果应用程序多次请求同一资源，该资源可以从缓存返回，避免开销再次请求它从服务器。  缓存可通过减少获取改进应用程序性能的请求的资源。  缓存可以通过减少行程降低数或减小网络通信量到服务器。  当缓存提高性能时，它会增加该资源返回到应用程序已过时的风险，这意味着它与将服务器发送的资源是不同的，如果缓存未被使用。  
  
 缓存可允许未经授权的用户或进程读取敏感数据。  缓存的一种验证的响应能从缓存中检索，不使用一种附加权限。  如果启用了缓存，转到 <xref:System.Net.WebRequest.CachePolicy%2A> 到 <xref:System.Net.Cache.RequestCacheLevel> 或 <xref:System.Net.Cache.RequestCacheLevel> 到此请求中禁用缓存。  
  
 由于安全问题，缓存用于中间层方案建议的 **not** 。  
  
## 本节内容  
 [缓存策略](../../../docs/framework/network-programming/cache-policy.md)  
 解释什么缓存策略以及定义一个。  
  
 [基于位置的缓存策略](../../../docs/framework/network-programming/location-based-cache-policies.md)  
 定义了基于位置的缓存策略的每种类型可用于超文本传输协议\(HTTP和https\)的资源。  
  
 [基于时间的缓存策略](../../../docs/framework/network-programming/time-based-cache-policies.md)  
 描述可用于自定义基于时间的缓存策略的条件。  
  
 [配置网络应用程序中的缓存](../../../docs/framework/network-programming/configuring-caching-in-network-applications.md)  
 描述如何以编程方式创建缓存策略并请求使用缓存。  
  
## 参考  
 <xref:System.Net.Cache>  
 定义用于的类型和枚举定义使用 <xref:System.Net.WebRequest>、 <xref:System.Net.HttpWebRequest>和 <xref:System.Net.FtpWebRequest> 选件类获取资源的缓存策略。