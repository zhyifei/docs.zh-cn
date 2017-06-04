---
title: "如何：为应用程序设置基于位置的缓存策略 | Microsoft Docs"
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
  - "明确定义缓存行为"
  - "基于位置的缓存策略"
  - "本地缓存"
  - "请求缓存策略"
  - "缓存 [.NET Framework]，基于位置的策略"
ms.assetid: 683bb88e-3411-4f46-9686-3411b6ba511c
caps.latest.revision: 10
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 10
---
# 如何：为应用程序设置基于位置的缓存策略
基于位置的缓存策略允许应用程序显式定义根据所请求资源的位置的缓存行为。  本主题演示如何设置缓存策略程序模型。  有关设置一个应用程序策略的信息使用配置文件，请参见 [\<requestCaching\> 元素（网络设置）](../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)。  
  
### 设置应用程序的基于位置的缓存策略  
  
1.  创建一 <xref:System.Net.Cache.RequestCachePolicy> 或 <xref:System.Net.Cache.HttpRequestCachePolicy> 对象。  
  
2.  设置策略对象作为应用程序域的默认值。  
  
### 若要设置接受的策略从缓存请求的资源  
  
-   创建如果具有接受从缓存请求的资源，因此，否则，向服务器发送请求，通过设置缓存级别设置为 <xref:System.Net.Cache.HttpRequestCacheLevel>的策略。  请求可以由客户端和服务器之间的所有缓存执行，包括远程缓存。  
  
    ```csharp  
    public static void UseCacheIfAvailable()  
    {  
        HttpRequestCachePolicy policy = new HttpRequestCachePolicy  
            (HttpRequestCacheLevel.CacheIfAvailable);  
        HttpWebRequest.DefaultCachePolicy = policy;  
    }  
  
    ```  
  
    ```vb  
    Public Shared Sub UseCacheIfAvailable()  
        Dim policy As New HttpRequestCachePolicy _  
             (HttpRequestCacheLevel.CacheIfAvailable)  
        HttpWebRequest.DefaultCachePolicy = policy  
    End Sub  
    ```  
  
### 设置禁止所有缓存配置的资源的策略  
  
-   创建使所有缓存提供请求的资源通过设置缓存级别。 <xref:System.Net.Cache.HttpRequestCacheLevel>的策略。  此策略级别从本地缓存中移除该资源，如果它存在并指示到远程缓存它们还应移除该资源。  
  
    ```csharp  
    public static void DoNotUseCache()  
    {  
    HttpRequestCachePolicy policy = new HttpRequestCachePolicy   
            (HttpRequestCacheLevel.NoCacheNoStore);  
        HttpWebRequest.DefaultCachePolicy = policy;  
    }  
    ```  
  
    ```vb  
    Public Shared Sub DoNotUseCache()  
        Dim policy As New HttpRequestCachePolicy _  
            (HttpRequestCacheLevel.NoCacheNoStore)  
        HttpWebRequest.DefaultCachePolicy = policy  
    End Sub  
    ```  
  
### 若要设置返回的策略请求的资源，才会在本地缓存  
  
-   创建返回请求的资源的策略，才会在本地缓存通过设置缓存级别为 <xref:System.Net.Cache.HttpRequestCacheLevel>。  如果请求的资源不在缓存中， <xref:System.Net.WebException> 引发异常。  
  
    ```csharp  
    public static void OnlyUseCache()  
    {  
        HttpRequestCachePolicy policy = new HttpRequestCachePolicy   
            (HttpRequestCacheLevel.CacheOnly);  
        HttpWebRequest.DefaultCachePolicy = policy;  
    }  
    ```  
  
    ```vb  
    Public Shared Sub OnlyUseCache()  
        Dim policy As New HttpRequestCachePolicy _  
            (HttpRequestCacheLevel.CacheOnly)  
        HttpWebRequest.DefaultCachePolicy = policy  
    End Sub  
    ```  
  
### 设置以防止本地缓存配置的资源的策略  
  
-   创建防止本地缓存提供请求的资源通过设置缓存级别。 <xref:System.Net.Cache.HttpRequestCacheLevel>的策略。  如果请求的资源在中间缓存并成功，并中间缓存可提供请求的资源。  
  
    ```csharp  
    public static void DoNotUseLocalCache()  
    {  
     HttpRequestCachePolicy policy = new HttpRequestCachePolicy   
            (HttpRequestCacheLevel.Refresh);  
        HttpWebRequest.DefaultCachePolicy = policy;  
    }  
    ```  
  
    ```vb  
    Public Shared Sub DoNotUseLocalCache()  
        Dim policy As New HttpRequestCachePolicy _  
            (HttpRequestCacheLevel.Refresh)  
        HttpWebRequest.DefaultCachePolicy = policy  
    End Sub  
    ```  
  
### 设置禁止所有缓存提供请求的资源的策略  
  
-   创建使所有缓存提供请求的资源通过设置缓存级别。 <xref:System.Net.Cache.HttpRequestCacheLevel>的策略。  服务器返回的资源可以存储在缓存中。  
  
    ```csharp  
    public static void SendToServer()  
    {  
    HttpRequestCachePolicy policy = new HttpRequestCachePolicy   
            (HttpRequestCacheLevel.Reload);  
        HttpWebRequest.DefaultCachePolicy = policy;  
    }  
    ```  
  
    ```vb  
    Public Shared Sub SendToServer()  
        Dim policy As New HttpRequestCachePolicy _  
            (HttpRequestCacheLevel.Reload)  
        HttpWebRequest.DefaultCachePolicy = policy  
    End Sub  
    ```  
  
### 若要设置允许所有缓存提供的策略请求的资源，则服务器上的资源与该缓存的副本不新  
  
-   创建允许所有缓存通过设置缓存级别提供请求的资源的策略，如果服务器上的资源与该缓存的副本不新。 <xref:System.Net.Cache.HttpRequestCacheLevel>。  
  
    ```csharp  
    public static void CheckServer()  
    {  
    HttpRequestCachePolicy policy = new HttpRequestCachePolicy  
             (HttpRequestCacheLevel.Revalidate);  
        HttpWebRequest.DefaultCachePolicy = policy;  
    }  
    ```  
  
    ```vb  
    Public Shared Sub CheckServer()  
        Dim policy As New HttpRequestCachePolicy _  
            (HttpRequestCacheLevel.Revalidate)  
        HttpWebRequest.DefaultCachePolicy = policy  
    End Sub  
    ```  
  
## 请参阅  
 [网络应用程序的缓存管理](../../../docs/framework/network-programming/cache-management-for-network-applications.md)   
 [缓存策略](../../../docs/framework/network-programming/cache-policy.md)   
 [基于位置的缓存策略](../../../docs/framework/network-programming/location-based-cache-policies.md)   
 [基于时间的缓存策略](../../../docs/framework/network-programming/time-based-cache-policies.md)   
 [\<requestCaching\> 元素（网络设置）](../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)