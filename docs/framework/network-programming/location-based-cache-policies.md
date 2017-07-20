---
title: "基于位置的缓存策略 | Microsoft Docs"
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
  - "“如果可用则缓存”策略"
  - "重新加载策略"
  - "基于位置的缓存策略"
  - "“仅缓存”策略"
  - "本地缓存"
  - "中间缓存"
  - "“无缓存无存储”策略"
  - "缓存 [.NET Framework]，基于位置的策略"
  - "重新验证策略"
  - "已缓存资源的新鲜度"
  - "“缓存或仅下一个缓存”策略"
  - "刷新策略"
ms.assetid: e41d7f1a-0a6a-4dee-97d1-c6a8b6a07fc2
caps.latest.revision: 12
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 12
---
# 基于位置的缓存策略
基于位置的缓存策略定义基于的有效的缓存项的新鲜度请求的资源可以将来自的位置。  ，如果使用它不违反服务器上指定的重新验证要求，一种缓存的资源是有效的。  使用 <xref:System.Net.Cache.RequestCachePolicy> 或 <xref:System.Net.Cache.HttpRequestCachePolicy> 选件类构造函数，基于位置的缓存策略编程方式创建。  使用 <xref:System.Net.Cache.RequestCacheLevel> 或 <xref:System.Net.Cache.HttpRequestCacheLevel> 枚举值，基于位置的策略的类型传递给构造函数。  有关创建基于位置的缓存策略的代码示例，请参见 [如何:设置应用程序的基于位置的缓存策略](../../../docs/framework/network-programming/how-to-set-a-location-based-cache-policy-for-an-application.md)。  以下各节说明基于位置的缓存策略每种类型的超文本传输协议\(HTTP和https\)资源。  
  
## 如果有缓存策略  
 如果活动的请求的资源本地缓存中，使用已缓存的资源;否则，对资源发送到服务器。  如果请求的资源可用在客户端和服务器之间的任何缓存，请求可由一个中间缓存满足。  
  
## 只缓存策略  
 如果活动的请求的资源本地缓存中，使用已缓存的资源。  在此缓存策略级别指定时， <xref:System.Net.WebException> 引发异常，如果该项不在本地缓存。  
  
## 缓存或仅下一个缓存策略  
 如果活动的请求的资源本地缓存中或一个中间缓存局域网的，使用已缓存的资源。  否则，将引发 <xref:System.Net.WebException> 异常。  使用只能在缓存的缓存控件指令， HTTP缓存协议，则实现。  
  
## 不缓存不存储策略  
 请求的资源从所有缓存从不使用、任何缓存不放置。  如果请求的资源位于本地缓存，请将其删除。  此策略级别指示到中间缓存它们还应移除该资源。  使用NO\-存储缓存控件指令， HTTP缓存协议，则实现。  
  
## 刷新策略  
 请求的资源\(本地缓存外，，则为;如果从服务器获取或在缓存中找到中。  在可以由中间缓存满足请求之前，该缓存必须向服务器重新验证它的缓存项。  在HTTP缓存协议，这是使用最大年龄\=指令0个缓存的控件和NO\-缓存说明标头。  
  
## 重新加载策略  
 必须从服务器获取请求的资源。  响应可能在本地缓存保存。  使用指令NO\-缓存缓存的控件和NO\-缓存说明标头， HTTP缓存协议，则实现。  
  
## 重新验证策略  
 比较缓存中的资源副本和服务器上的副本。  如果服务器上的副本更新，则使用它满足请求并替换缓存中的副本。  如果缓存中的副本和服务器副本一样新，则使用缓存的副本。  在 HTTP 缓存协议中，这是通过条件请求实现的。  
  
## 请参阅  
 [网络应用程序的缓存管理](../../../docs/framework/network-programming/cache-management-for-network-applications.md)   
 [缓存策略](../../../docs/framework/network-programming/cache-policy.md)   
 [基于时间的缓存策略](../../../docs/framework/network-programming/time-based-cache-policies.md)   
 [配置网络应用程序中的缓存](../../../docs/framework/network-programming/configuring-caching-in-network-applications.md)   
 [\<requestCaching\> 元素（网络设置）](../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)