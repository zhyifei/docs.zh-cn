---
title: "如何：自定义基于时间的缓存策略 | Microsoft Docs"
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
  - "自定义基于时间的缓存策略"
  - "缓存 [.NET Framework]，基于时间的策略"
ms.assetid: 8d84f936-2376-4356-9264-03162e0f9279
caps.latest.revision: 15
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 15
---
# 如何：自定义基于时间的缓存策略
当创建基于时间的缓存策略时，可以通过指定值的自定义缓存行为。最大年龄、最小的新鲜度、最大不新鲜或缓存同步日期。  <xref:System.Net.Cache.HttpRequestCachePolicy> 对象提供允许您指定这些值的有效组合的若干构造函数。  
  
### 创建一个使用缓存同步日期的基于时间的缓存策略  
  
-   创建传递给 <xref:System.Net.Cache.HttpRequestCachePolicy> 构造函数的一 <xref:System.DateTime> 对象使用一个缓存同步日期的基于时间的缓存策略。  
  
    ```csharp  
    public static HttpRequestCachePolicy CreateLastSyncPolicy(DateTime when)  
    {  
        HttpRequestCachePolicy policy =   
            new HttpRequestCachePolicy(when);  
        Console.WriteLine("When: {0}", when);  
        Console.WriteLine(policy.ToString());  
        return policy;  
    }  
    ```  
  
    ```vb  
    Public Shared Function CreateLastSyncPolicy([when] As DateTime) As HttpRequestCachePolicy  
        Dim policy As New HttpRequestCachePolicy([when])  
        Console.WriteLine("When: {0}", [when])  
        Console.WriteLine(policy.ToString())  
        Return policy  
    End Function  
    ```  
  
 输出如下所示:  
  
```  
When: 1/14/2004 8:07:30 AM  
Level:Default CacheSyncDate:1/14/2004 8:07:30 AM  
```  
  
### 创建基于最小的新鲜度的基于时间的缓存策略  
  
-   创建基于最小的新鲜度通过指定 <xref:System.Net.Cache.HttpCacheAgeControl> 作为 `cacheAgeControl` 参数值并传递到 <xref:System.Net.Cache.HttpRequestCachePolicy> 构造函数的一 <xref:System.TimeSpan> 对象的一个基于时间的缓存策略。  
  
    ```csharp  
    public static HttpRequestCachePolicy CreateMinFreshPolicy(TimeSpan span)  
    {  
        HttpRequestCachePolicy policy =   
            new HttpRequestCachePolicy(HttpCacheAgeControl.MinFresh, span);  
        Console.WriteLine(policy.ToString());  
        return policy;  
    }  
    ```  
  
    ```vb  
    Public Shared Function CreateMinFreshPolicy(span As TimeSpan) As HttpRequestCachePolicy  
        Dim policy As New HttpRequestCachePolicy(HttpCacheAgeControl.MinFresh, span)  
        Console.WriteLine(policy.ToString())  
        Return policy  
    End Function  
    ```  
  
 对以下调用:  
  
```  
CreateMinFreshPolicy(new TimeSpan(1,0,0));  
```  
  
```  
Level:Default MinFresh:3600  
  
```  
  
### 创建基于最小的新鲜度和最大值年龄的基于时间的缓存策略  
  
-   创建基于最小的新鲜度和最大值年龄通过指定 <xref:System.Net.Cache.HttpCacheAgeControl> 作为 `cacheAgeControl` 参数值并传递到 <xref:System.Net.Cache.HttpRequestCachePolicy> 构造函数的两 <xref:System.TimeSpan> 对象的一个基于时间的缓存策略，指定最大年龄的一个在资源和一个用于从缓存返回的对象指定允许的最小的新鲜度。  
  
    ```csharp  
    public static HttpRequestCachePolicy CreateFreshAndAgePolicy(TimeSpan freshMinimum, TimeSpan ageMaximum)  
    {  
        HttpRequestCachePolicy policy =   
        new HttpRequestCachePolicy(HttpCacheAgeControl.MaxAgeAndMinFresh, ageMaximum, freshMinimum);  
        Console.WriteLine(policy.ToString());  
        return policy;  
    }  
    ```  
  
    ```vb  
    Public Shared Function CreateFreshAndAgePolicy(freshMinimum As TimeSpan, ageMaximum As TimeSpan) As HttpRequestCachePolicy  
        Dim policy As New HttpRequestCachePolicy(HttpCacheAgeControl.MaxAgeAndMinFresh, ageMaximum, freshMinimum)  
        Console.WriteLine(policy.ToString())  
        Return policy  
    End Function  
    ```  
  
 对以下调用:  
  
```  
CreateFreshAndAgePolicy(new TimeSpan(5,0,0), new TimeSpan(10,0,0));  
```  
  
```  
Level:Default MaxAge:36000 MinFresh:18000  
```  
  
## 请参阅  
 [网络应用程序的缓存管理](../../../docs/framework/network-programming/cache-management-for-network-applications.md)   
 [缓存策略](../../../docs/framework/network-programming/cache-policy.md)   
 [基于位置的缓存策略](../../../docs/framework/network-programming/location-based-cache-policies.md)   
 [基于时间的缓存策略](../../../docs/framework/network-programming/time-based-cache-policies.md)   
 [\<requestCaching\> 元素（网络设置）](../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)