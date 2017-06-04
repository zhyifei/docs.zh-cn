---
title: "缓存策略交互 — 最长使用期限和最低新鲜度 | Microsoft Docs"
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
  - "重新验证策略"
  - "缓存 [.NET Framework]，基于时间的策略"
  - "已缓存资源的新鲜度"
  - "最长使用期限策略"
  - "最低新鲜度策略"
  - "已缓存资源的使用期限"
ms.assetid: 6567d451-ecec-496c-95a3-a415b99ba52a
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# 缓存策略交互 — 最长使用期限和最低新鲜度
若要帮助确保最新内容返回到客户端应用程序，客户端缓存策略的交互和服务器重新验证要求从而总是最保守的缓存策略。  本主题中的所有示例阐释了一月1日在一月4.缓存并已过期的资源的缓存策略。  
  
 下面的示例演示产生最大年龄的缓存策略\(`maxAge`\)和最小的新鲜度\(`minFresh`\)值的交互。  
  
-   如果缓存策略设置 `maxAge` \= 2天，并 `minFresh` 未指定，内容在一月3.并。  
  
-   如果缓存策略设置 `maxAge` \= 2天和 `minFresh` \= 1天，根据 `maxAge`，内容为新鲜的直到一月3。  根据 `minFresh`，内容为新鲜的直到一月3。  因此，内容在一月3.必须并。  
  
-   如果缓存策略设置 `maxAge`\= 2天和 `minFresh` \= 2天，根据 `maxAge`，内容为新鲜的直到一月3。  根据 `minFresh` 内容为新鲜的直到一月2。  因此，内容在一月2.必须并。  
  
## 请参阅  
 [网络应用程序的缓存管理](../../../docs/framework/network-programming/cache-management-for-network-applications.md)   
 [缓存策略](../../../docs/framework/network-programming/cache-policy.md)   
 [基于位置的缓存策略](../../../docs/framework/network-programming/location-based-cache-policies.md)   
 [基于时间的缓存策略](../../../docs/framework/network-programming/time-based-cache-policies.md)   
 [配置网络应用程序中的缓存](../../../docs/framework/network-programming/configuring-caching-in-network-applications.md)   
 [缓存策略交互 — 最长使用期限和最长过期时间](../../../docs/framework/network-programming/cache-policy-interaction-maximum-age-and-maximum-staleness.md)