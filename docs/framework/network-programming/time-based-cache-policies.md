---
title: "基于时间的缓存策略 | Microsoft Docs"
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
  - "基于时间的缓存策略"
  - "缓存同步日期策略"
  - "缓存 [.NET Framework]，基于时间的策略"
  - "已缓存资源的新鲜度"
  - "时间，已缓存资源"
  - "最长使用期限策略"
  - "同步，缓存"
  - "已缓存资源的过期时间"
  - "默认基于时间的缓存策略"
  - "最长过期时间策略"
  - "内容缓存策略"
  - "过期内容"
  - "最低新鲜度策略"
  - "已缓存资源的使用期限"
ms.assetid: 74f0bcaf-5c95-40c1-9967-f3bbf1d2360a
caps.latest.revision: 11
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 11
---
# 基于时间的缓存策略
基于时间的缓存策略定义缓存项的新鲜度使用资源检索的时间，标头返回具有这种资源和当前时间。  当设置基于时间的缓存策略时，可以使用该 <xref:System.Net.Cache.HttpRequestCacheLevel> 基于时间的策略或创建自定义的基于时间的策略。  在使用该默认时间基于使用超文本传输协议\(ftp\)获取资源的策略\(HTTP\)，则指定的行为取决于具体的缓存行为由已缓存的响应中包含的标头和第13部分和第14部分RFC 2616，在 [http:\/\/www.ietf.org](http://www.ietf.org/)中可用。  有关演示设置的代码示例中的默认时间基于HTTP资源的策略，请参见 [如何:设置应用程序的默认基于时间的缓存策略](../../../docs/framework/network-programming/how-to-set-the-default-time-based-cache-policy-for-an-application.md)。  有关演示如何创建和使用缓存策略的代码示例，请参见 [在web应用程序中配置缓存](../../../docs/framework/network-programming/configuring-caching-in-network-applications.md)。  
  
## 确定缓存项的新鲜度的标准  
 若要自定义基于时间的缓存策略，可以指定以下一个或多个标准用于确定缓存项的新鲜度:  
  
-   最大年龄  
  
-   最大不新鲜  
  
-   最小的新鲜度  
  
-   缓存同步日期  
  
> [!NOTE]
>  使用默认基于时间的缓存策略不应与设置应用程序的默认缓存策略混淆。  默认值基于时间的策略是可在请求下使用或应用程序级别的特定策略。  您的应用程序的默认缓存策略是策略\(基于位置或基于时间\)。生效，如果策略在请求时未设置为。  有关设置一个默认的缓存策略的详细信息您的应用程序，请参见 <xref:System.Net.WebRequest.DefaultCachePolicy%2A>。  
  
### 最大年龄  
 最大年龄策略标准指定可使用资源中缓存的副本的时间。  如果资源的缓存副本比指定的时间早，该资源必须通过检查它并在服务器的内容。  如果将允许该资源使用最大年龄，在某后，此标准不将起作用，除非了最大不新鲜值来指定。  
  
### 最大不新鲜  
 最大不新鲜策略标准在内容过期后指定时间长度可以使用资源的缓存副本。  这是允许使用的资源唯一的缓存策略标准，在到期之后。  
  
### 最小的新鲜度  
 最小的新鲜度策略标准在内容过期之前指定时间长度可以使用资源的缓存副本。  此策略有导致缓存项的效果在其截止日期过期之前;因此，最小的新鲜度和最大值不新鲜组互相排斥。  
  
## 缓存同步日期  
 缓存同步日期策略标准确定资源中缓存的副本时必须通过检查它并在服务器的内容。  如果内容已更改，则缓存该项目时，它从服务器检索，存储在缓存中，并返回给应用程序。  如果内容没有更改，其时间戳更新，并应用程序获取已缓存的内容。  
  
 缓存同步日期允许您指定必须重新验证缓存内容的绝对日期。  如果新缓存项将在缓存同步日期之前最后，并与服务器的重新验证仍发生。  如果缓存项将在缓存同步日期之后并，而不是无效的缓存项的附加的新鲜度或服务器重新验证要求，从缓存中使用项。  如果缓存同步日期被设置为某个将来的日期，则每次请求项时都重新验证它，直到缓存同步日期已过去。  
  
 下列主题提供有关将基于时间的缓存策略标准的影响的信息:  
  
-   [缓存策略交互 — 最长使用期限和最长过期时间](../../../docs/framework/network-programming/cache-policy-interaction-maximum-age-and-maximum-staleness.md)  
  
-   [缓存策略交互 — 最长使用期限和最低新鲜度](../../../docs/framework/network-programming/cache-policy-interaction-maximum-age-and-minimum-freshness.md)  
  
## 请参阅  
 [网络应用程序的缓存管理](../../../docs/framework/network-programming/cache-management-for-network-applications.md)   
 [缓存策略](../../../docs/framework/network-programming/cache-policy.md)   
 [基于位置的缓存策略](../../../docs/framework/network-programming/location-based-cache-policies.md)   
 [配置网络应用程序中的缓存](../../../docs/framework/network-programming/configuring-caching-in-network-applications.md)   
 [\<requestCaching\> 元素（网络设置）](../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)