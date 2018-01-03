---
title: "如何：为应用程序设置默认基于时间的缓存策略"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time-based cache policies
- cache [.NET Framework], time-based policies
- default time-based cache policy
ms.assetid: 6bfce066-a2e7-4add-a05e-85c12ec9f07f
caps.latest.revision: "9"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 1d5166090a0682b71f74565e666c96ddadb7c6c1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-set-the-default-time-based-cache-policy-for-an-application"></a><span data-ttu-id="ce4df-102">如何：为应用程序设置默认基于时间的缓存策略</span><span class="sxs-lookup"><span data-stu-id="ce4df-102">How to: Set the Default Time-Based Cache Policy for an Application</span></span>
<span data-ttu-id="ce4df-103">默认基于时间的缓存策略允许应用程序将标头定义的缓存行为与缓存资源和 RFC 2616 的第 13 和 14 节（可在 [http://www.ietf.org](http://www.ietf.org/) 中找到）中定义的缓存行为一起发送。这是适用于大多数应用程序的缓存行为。</span><span class="sxs-lookup"><span data-stu-id="ce4df-103">The default time-based cache policy allows an application to have its cache behavior defined by the headers sent with the cached resource and the cache behavior defined in sections 13 and 14 of RFC 2616, available at [http://www.ietf.org](http://www.ietf.org/). This is the appropriate cache behavior for most applications.</span></span>  
  
### <a name="to-set-the-default-automatic-policy-for-an-application"></a><span data-ttu-id="ce4df-104">为应用程序设置默认自动策略</span><span class="sxs-lookup"><span data-stu-id="ce4df-104">To set the default automatic policy for an application</span></span>  
  
1.  <span data-ttu-id="ce4df-105">创建默认基于时间的策略对象。</span><span class="sxs-lookup"><span data-stu-id="ce4df-105">Create a default time-based policy object.</span></span>  
  
2.  <span data-ttu-id="ce4df-106">将策略对象设置为应用程序域的默认对象。</span><span class="sxs-lookup"><span data-stu-id="ce4df-106">Set the policy object as the default for the application domain.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ce4df-107">示例</span><span class="sxs-lookup"><span data-stu-id="ce4df-107">Example</span></span>  
 <span data-ttu-id="ce4df-108">此部分中的两个示例生成相同的策略。</span><span class="sxs-lookup"><span data-stu-id="ce4df-108">The two examples in this section produce identical policies.</span></span>  
  
 <span data-ttu-id="ce4df-109">以下示例创建默认基于时间的策略，并为应用程序域将其设置为默认。</span><span class="sxs-lookup"><span data-stu-id="ce4df-109">The following example creates a default time-based policy and sets it as the default for the application domain.</span></span>  
  
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
  
 <span data-ttu-id="ce4df-110">也可使用 <xref:System.Net.Cache.RequestCachePolicy> 类创建默认基于时间的缓存策略，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="ce4df-110">You can also create the default time-based cache policy using the <xref:System.Net.Cache.RequestCachePolicy> class as shown in the following example:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ce4df-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="ce4df-111">See Also</span></span>  
 [<span data-ttu-id="ce4df-112">网络应用程序的缓存管理</span><span class="sxs-lookup"><span data-stu-id="ce4df-112">Cache Management for Network Applications</span></span>](../../../docs/framework/network-programming/cache-management-for-network-applications.md)  
 [<span data-ttu-id="ce4df-113">缓存策略</span><span class="sxs-lookup"><span data-stu-id="ce4df-113">Cache Policy</span></span>](../../../docs/framework/network-programming/cache-policy.md)  
 [<span data-ttu-id="ce4df-114">基于位置的缓存策略</span><span class="sxs-lookup"><span data-stu-id="ce4df-114">Location-Based Cache Policies</span></span>](../../../docs/framework/network-programming/location-based-cache-policies.md)  
 [<span data-ttu-id="ce4df-115">基于时间的缓存策略</span><span class="sxs-lookup"><span data-stu-id="ce4df-115">Time-Based Cache Policies</span></span>](../../../docs/framework/network-programming/time-based-cache-policies.md)  
 [<span data-ttu-id="ce4df-116">\<requestCaching> 元素（网络设置）</span><span class="sxs-lookup"><span data-stu-id="ce4df-116">\<requestCaching> Element (Network Settings)</span></span>](../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)
