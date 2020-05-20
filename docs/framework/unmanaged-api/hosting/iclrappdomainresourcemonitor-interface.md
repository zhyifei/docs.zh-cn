---
title: ICLRAppDomainResourceMonitor 接口
ms.date: 03/30/2017
api_name:
- ICLRAppDomainResourceMonitor
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAppDomainResourceMonitor
helpviewer_keywords:
- ICLRAppDomainResourceMonitor interface [.NET Framework hosting]
ms.assetid: 72fa83a1-8997-41d7-b355-ab177a24a303
topic_type:
- apiref
ms.openlocfilehash: 08dc0f0891d960cb7b402b30455e606aaff7bcea
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616003"
---
# <a name="iclrappdomainresourcemonitor-interface"></a><span data-ttu-id="461f3-102">ICLRAppDomainResourceMonitor 接口</span><span class="sxs-lookup"><span data-stu-id="461f3-102">ICLRAppDomainResourceMonitor Interface</span></span>
<span data-ttu-id="461f3-103">提供检查应用程序域的内存和 CPU 使用情况的方法。</span><span class="sxs-lookup"><span data-stu-id="461f3-103">Provides methods that inspect an application domain's memory and CPU usage.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="461f3-104">方法</span><span class="sxs-lookup"><span data-stu-id="461f3-104">Methods</span></span>  
  
|<span data-ttu-id="461f3-105">方法</span><span class="sxs-lookup"><span data-stu-id="461f3-105">Method</span></span>|<span data-ttu-id="461f3-106">说明</span><span class="sxs-lookup"><span data-stu-id="461f3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="461f3-107">GetCurrentAllocated 方法</span><span class="sxs-lookup"><span data-stu-id="461f3-107">GetCurrentAllocated Method</span></span>](iclrappdomainresourcemonitor-getcurrentallocated-method.md)|<span data-ttu-id="461f3-108">获取应用程序域创建后所做的所有内存分配的总大小（以字节为单位），而不会减去已进行垃圾回收的内存。</span><span class="sxs-lookup"><span data-stu-id="461f3-108">Gets the total size, in bytes, of all memory allocations that have been made by the application domain since it was created, without subtracting memory that has been garbage-collected.</span></span>|  
|[<span data-ttu-id="461f3-109">GetCurrentSurvived 方法</span><span class="sxs-lookup"><span data-stu-id="461f3-109">GetCurrentSurvived Method</span></span>](iclrappdomainresourcemonitor-getcurrentsurvived-method.md)|<span data-ttu-id="461f3-110">获取当前应用程序域引用的最后一个完整的、阻止的垃圾回收和所引用的字节数。</span><span class="sxs-lookup"><span data-stu-id="461f3-110">Gets the number of bytes that survived the last full, blocking garbage collection and that are referenced by the current application domain.</span></span>|  
|[<span data-ttu-id="461f3-111">GetCurrentCpuTime 方法</span><span class="sxs-lookup"><span data-stu-id="461f3-111">GetCurrentCpuTime Method</span></span>](iclrappdomainresourcemonitor-getcurrentcputime-method.md)|<span data-ttu-id="461f3-112">获取自应用程序域创建以来在当前应用程序域中执行时所有线程已使用的总处理器时间。</span><span class="sxs-lookup"><span data-stu-id="461f3-112">Gets the total processor time that has been used by all threads while executing in the current application domain, since the application domain was created.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="461f3-113">备注</span><span class="sxs-lookup"><span data-stu-id="461f3-113">Remarks</span></span>  
 <span data-ttu-id="461f3-114">`ICLRAppDomainResourceMonitor`接口提供类似于以下托管属性的功能：</span><span class="sxs-lookup"><span data-stu-id="461f3-114">The `ICLRAppDomainResourceMonitor` interface provides functionality that is similar to the following managed properties:</span></span>  
  
- <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType>  
  
- <xref:System.AppDomain.MonitoringTotalProcessorTime%2A?displayProperty=nameWithType>  
  
- <xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType>  
  
- <xref:System.AppDomain.MonitoringSurvivedProcessMemorySize%2A?displayProperty=nameWithType>  
  
- <xref:System.AppDomain.MonitoringSurvivedMemorySize%2A?displayProperty=nameWithType>  
  
## <a name="requirements"></a><span data-ttu-id="461f3-115">要求</span><span class="sxs-lookup"><span data-stu-id="461f3-115">Requirements</span></span>  
 <span data-ttu-id="461f3-116">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="461f3-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="461f3-117">**标头：** MetaHost</span><span class="sxs-lookup"><span data-stu-id="461f3-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="461f3-118">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="461f3-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="461f3-119">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="461f3-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="461f3-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="461f3-120">See also</span></span>

- [<span data-ttu-id="461f3-121">\<appDomainResourceMonitoring> 元素</span><span class="sxs-lookup"><span data-stu-id="461f3-121">\<appDomainResourceMonitoring> Element</span></span>](../../configure-apps/file-schema/runtime/appdomainresourcemonitoring-element.md)
- [<span data-ttu-id="461f3-122">应用程序域资源监视</span><span class="sxs-lookup"><span data-stu-id="461f3-122">Application Domain Resource Monitoring</span></span>](../../../standard/garbage-collection/app-domain-resource-monitoring.md)
- [<span data-ttu-id="461f3-123">承载接口</span><span class="sxs-lookup"><span data-stu-id="461f3-123">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="461f3-124">承载</span><span class="sxs-lookup"><span data-stu-id="461f3-124">Hosting</span></span>](index.md)
