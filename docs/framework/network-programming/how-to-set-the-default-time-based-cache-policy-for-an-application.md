---
title: "如何：为应用程序设置默认基于时间的缓存策略 | Microsoft Docs"
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
  - "缓存 [.NET Framework]，基于时间的策略"
  - "默认基于时间的缓存策略"
ms.assetid: 6bfce066-a2e7-4add-a05e-85c12ec9f07f
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# 如何：为应用程序设置默认基于时间的缓存策略
默认基于时间的缓存策略允许应用程序具有标头定义其缓存行为发送的已缓存的资源和中定义的缓存行为的第13节和第14部分RFC 2616，在 [http:\/\/www.ietf.org](http://www.ietf.org/)中可用。  这是大多数应用程序中合适的缓存行为。  
  
### 设置应用程序的默认自动策略  
  
1.  创建一个默认基于时间的策略对象。  
  
2.  设置策略对象作为应用程序域的默认值。  
  
## 示例  
 本节中的两个示例产生相同的策略。  
  
 下面的示例创建一个默认基于时间的策略并将其设置为应用程序域的默认值。  
  
```csharp  
public static void SetDefaultTimeBasedPolicy ()  
{  
    HttpRequestCachePolicy policy = new HttpRequestCachePolicy ();  
    HttpWebRequest.DefaultCachePolicy = policy ;  
}  
```  
  
```vb  
Public Shared Sub SetDefaultTimeBasedPolicy ()  
    Dim policy = New HttpRequestCachePolicy ()  
    HttpWebRequest.DefaultCachePolicy = policy  
End Sub  
```  
  
 如下面的示例所示，还可以创建默认基于时间的缓存策略使用 <xref:System.Net.Cache.RequestCachePolicy> 选件类:  
  
```csharp  
public static void SetDefaultTimeBasedPolicy2()  
{  
    RequestCachePolicy policy = new RequestCachePolicy ();  
    HttpWebRequest.DefaultCachePolicy = policy ;  
}  
```  
  
```vb  
Public Shared Sub SetDefaultTimeBasedPolicy2()  
    Dim policy As New RequestCachePolicy()  
    HttpWebRequest.DefaultCachePolicy = policy  
End Sub  
  
```  
  
## 请参阅  
 [网络应用程序的缓存管理](../../../docs/framework/network-programming/cache-management-for-network-applications.md)   
 [缓存策略](../../../docs/framework/network-programming/cache-policy.md)   
 [基于位置的缓存策略](../../../docs/framework/network-programming/location-based-cache-policies.md)   
 [基于时间的缓存策略](../../../docs/framework/network-programming/time-based-cache-policies.md)   
 [\<requestCaching\> 元素（网络设置）](../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)