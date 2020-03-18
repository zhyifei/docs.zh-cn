---
title: 如何：为应用程序设置默认基于时间的缓存策略
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time-based cache policies
- cache [.NET Framework], time-based policies
- default time-based cache policy
ms.assetid: 6bfce066-a2e7-4add-a05e-85c12ec9f07f
ms.openlocfilehash: 0aaa26f67ef1ef191060e682690fa14de328b812
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2020
ms.locfileid: "71048090"
---
# <a name="how-to-set-the-default-time-based-cache-policy-for-an-application"></a><span data-ttu-id="80688-102">如何：为应用程序设置默认基于时间的缓存策略</span><span class="sxs-lookup"><span data-stu-id="80688-102">How to: Set the Default Time-Based Cache Policy for an Application</span></span>
<span data-ttu-id="80688-103">默认基于时间的缓存策略允许应用程序将标头定义的缓存行为与缓存资源和 RFC 2616 的第 13 和 14 节（可在 [工程任务组 (IETF)](https://www.ietf.org/) 中找到）中定义的缓存行为一起发送。</span><span class="sxs-lookup"><span data-stu-id="80688-103">The default time-based cache policy allows an application to have its cache behavior defined by the headers sent with the cached resource and the cache behavior defined in sections 13 and 14 of RFC 2616, available at [Internet Engineering Task Force (IETF)](https://www.ietf.org/) website.</span></span> <span data-ttu-id="80688-104">这是适用于大多数应用程序的缓存行为。</span><span class="sxs-lookup"><span data-stu-id="80688-104">This is the appropriate cache behavior for most applications.</span></span>  
  
### <a name="to-set-the-default-automatic-policy-for-an-application"></a><span data-ttu-id="80688-105">为应用程序设置默认自动策略</span><span class="sxs-lookup"><span data-stu-id="80688-105">To set the default automatic policy for an application</span></span>  
  
1. <span data-ttu-id="80688-106">创建默认基于时间的策略对象。</span><span class="sxs-lookup"><span data-stu-id="80688-106">Create a default time-based policy object.</span></span>  
  
2. <span data-ttu-id="80688-107">将策略对象设置为应用程序域的默认对象。</span><span class="sxs-lookup"><span data-stu-id="80688-107">Set the policy object as the default for the application domain.</span></span>  
  
## <a name="example"></a><span data-ttu-id="80688-108">示例</span><span class="sxs-lookup"><span data-stu-id="80688-108">Example</span></span>  
 <span data-ttu-id="80688-109">此部分中的两个示例生成相同的策略。</span><span class="sxs-lookup"><span data-stu-id="80688-109">The two examples in this section produce identical policies.</span></span>  
  
 <span data-ttu-id="80688-110">以下示例创建默认基于时间的策略，并为应用程序域将其设置为默认。</span><span class="sxs-lookup"><span data-stu-id="80688-110">The following example creates a default time-based policy and sets it as the default for the application domain.</span></span>  
  
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
  
 <span data-ttu-id="80688-111">也可使用 <xref:System.Net.Cache.RequestCachePolicy> 类创建默认基于时间的缓存策略，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="80688-111">You can also create the default time-based cache policy using the <xref:System.Net.Cache.RequestCachePolicy> class as shown in the following example:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="80688-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="80688-112">See also</span></span>

- [<span data-ttu-id="80688-113">网络应用程序的缓存管理</span><span class="sxs-lookup"><span data-stu-id="80688-113">Cache Management for Network Applications</span></span>](cache-management-for-network-applications.md)
- [<span data-ttu-id="80688-114">缓存策略</span><span class="sxs-lookup"><span data-stu-id="80688-114">Cache Policy</span></span>](cache-policy.md)
- [<span data-ttu-id="80688-115">基于位置的缓存策略</span><span class="sxs-lookup"><span data-stu-id="80688-115">Location-Based Cache Policies</span></span>](location-based-cache-policies.md)
- [<span data-ttu-id="80688-116">基于时间的缓存策略</span><span class="sxs-lookup"><span data-stu-id="80688-116">Time-Based Cache Policies</span></span>](time-based-cache-policies.md)
- [<span data-ttu-id="80688-117">\<requestCaching> 元素（网络设置）</span><span class="sxs-lookup"><span data-stu-id="80688-117">\<requestCaching> Element (Network Settings)</span></span>](../configure-apps/file-schema/network/requestcaching-element-network-settings.md)
