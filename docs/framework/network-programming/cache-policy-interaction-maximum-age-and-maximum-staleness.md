---
title: "缓存策略交互 — 最长使用期限和最长过期时间 | Microsoft Docs"
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
  - "最长过期时间"
  - "已缓存资源的新鲜度"
  - "时间，已缓存资源"
  - "最长使用期限策略"
  - "已缓存资源的过期时间"
  - "已缓存资源的使用期限"
ms.assetid: 7f775925-89a1-4956-ba90-c869c1749a94
caps.latest.revision: 11
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 11
---
# 缓存策略交互 — 最长使用期限和最长过期时间
若要帮助确保最新内容返回到客户端应用程序，客户端缓存策略的交互和服务器重新验证要求从而总是最保守的缓存策略。  本主题中的所有示例阐释了一月1日在一月4.缓存并已过期的资源的缓存策略。  
  
 在下面的示例中，最大不新鲜值\(`maxStale`\)与了最大年龄\(`maxAge`\)一起使用:  
  
-   如果缓存策略设置 `maxAge` \= 5天，且未指定一个 `maxStale` 值，具体取决于 `maxAge` 值，内容可用直到一月6。  但是，基于服务器的重新验证要求，内容在一月4.过期。  由于内容成熟度较保守（较快），则优先于 `maxAge` 策略。  因此，内容在一月4日过期且必须并，即使它的最大时间戳未到达。  
  
-   如果缓存策略设置 `maxAge` \= 5天和 `maxStale` \= 3天，根据 `maxAge` 值，内容可用直到一月6。  根据 `maxStale` 值，内容可用直到一月7。  因此，内容在一月6.获取并。  
  
-   如果缓存策略设置 `maxAge` \= 5天和 `maxStale` \= 1天，根据 `maxAge` 值，内容可用直到一月6。  根据 `maxStale` 值，内容可用直到一月5。  因此，内容在一月5.获取并。  
  
 当最大年龄小于内容的到期日期时，较保守的缓存行为始终战胜，并最大不新鲜值无效。  下面的示例阐释如何设置了最大不新鲜\(`maxStale`\)值的效果，当最大年龄\(`maxAge`\)时为止，在内容过期之前:  
  
-   如果缓存策略设置 `maxAge` \= 1天，并且不为 `maxStale` 值指定值，内容在一月2日并，即使未过期。  
  
-   如果缓存策略设置`maxAge` \= 1天和 `maxStale` \= 3天，内容在一月2日并强制使用更保守策略设置。  
  
-   如果缓存策略设置 `maxAge` \= 1天和 `maxStale` \= 1天，内容在一月2.并。  
  
## 请参阅  
 [网络应用程序的缓存管理](../../../docs/framework/network-programming/cache-management-for-network-applications.md)   
 [缓存策略](../../../docs/framework/network-programming/cache-policy.md)   
 [基于位置的缓存策略](../../../docs/framework/network-programming/location-based-cache-policies.md)   
 [基于时间的缓存策略](../../../docs/framework/network-programming/time-based-cache-policies.md)   
 [配置网络应用程序中的缓存](../../../docs/framework/network-programming/configuring-caching-in-network-applications.md)   
 [缓存策略交互 — 最长使用期限和最低新鲜度](../../../docs/framework/network-programming/cache-policy-interaction-maximum-age-and-minimum-freshness.md)