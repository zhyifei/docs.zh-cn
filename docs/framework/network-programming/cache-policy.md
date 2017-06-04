---
title: "缓存策略 | Microsoft Docs"
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
  - "基于位置的缓存策略"
  - "缓存 [.NET Framework]，策略"
  - "请求缓存策略"
  - "已缓存资源的新鲜度"
  - "内容缓存策略"
  - "过期内容"
ms.assetid: 1a7e04ec-7872-41c2-96c6-52566dcb412b
caps.latest.revision: 11
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 11
---
# 缓存策略
缓存策略定义的规则可用于确定是否可以使用所请求资源的缓存副本来满足请求。  应用程序指定客户端新鲜度的缓存要求，但是，客户端缓存要求、服务器上的内容过期要求和服务器的重新验证要求取决于有效的缓存策略。  客户端缓存策略和服务器要求的交互从而总是最保守的缓存策略，以帮助确保最新内容返回到客户端应用程序。  
  
 缓存策略的位置因或时间根据。  基于位置的缓存策略定义基于的缓存项的新鲜度请求的资源可以将来自的位置。  使用资源检索的时间，标头返回与资源和当前时间，基于时间的缓存策略定义缓存项的新鲜度。  大多数应用程序只能使用默认的基于时间的缓存策略，实现RFC指定的缓存策略2616，在 [http:\/\/www.ietf.org](http://www.ietf.org/)中可用。  
  
 下表中描述的选件类用于指定缓存策略。  
  
|类名|描述|  
|--------|--------|  
|<xref:System.Net.Cache.HttpRequestCachePolicy>|represents位置基于和时间根据使用 <xref:System.Net.HttpWebRequest> 对象请求的资源的缓存策略。|  
|<xref:System.Net.Cache.RequestCachePolicy>|represents位置因缓存策略或 <xref:System.Net.Cache.RequestCacheLevel> 时间根据使用 <xref:System.Net.WebRequest> 对象请求的资源的缓存策略。|  
|<xref:System.Net.Cache.HttpCacheAgeControl>|指定用于的值创建基于时间的 <xref:System.Net.Cache.HttpRequestCachePolicy> 对象。|  
|<xref:System.Net.Cache.HttpRequestCacheLevel>|指定用于的值创建基于位置的和基于时间的 <xref:System.Net.Cache.HttpRequestCachePolicy> 对象。|  
|<xref:System.Net.Cache.RequestCacheLevel>|指定用于的值创建基于位置或 <xref:System.Net.Cache.RequestCacheLevel> 基于时间的 <xref:System.Net.Cache.RequestCachePolicy> 对象。|  
  
 可以定义缓存策略您的应用程序执行的所有请求的或各个请求的。  当您指定一个应用程序级别缓存策略和一个请求级别缓存策略，使用该请求级别的策略。  使用应用程序或机器配置文件，可以指定一个应用程序级别缓存策略编程方式或。  有关更多信息，请参见[\<requestCaching\> 元素（网络设置）](../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)。  
  
 若要创建缓存策略，则必须通过创建 <xref:System.Net.Cache.RequestCachePolicy> 或 <xref:System.Net.Cache.HttpRequestCachePolicy> 选件类的实例创建策略对象。  若要指定策略在请求，找到请求的 <xref:System.Net.WebRequest.CachePolicy%2A> 属性设置策略对象。  当设置一个应用程序级别的策略以编程方式，设置 <xref:System.Net.HttpWebRequest.DefaultCachePolicy%2A> 属性设置策略对象。  
  
 有关演示如何创建和使用缓存策略的代码示例，请参见 [在web应用程序中配置缓存](../../../docs/framework/network-programming/configuring-caching-in-network-applications.md)。  
  
## 请参阅  
 [网络应用程序的缓存管理](../../../docs/framework/network-programming/cache-management-for-network-applications.md)   
 [基于位置的缓存策略](../../../docs/framework/network-programming/location-based-cache-policies.md)   
 [基于时间的缓存策略](../../../docs/framework/network-programming/time-based-cache-policies.md)   
 [配置网络应用程序中的缓存](../../../docs/framework/network-programming/configuring-caching-in-network-applications.md)