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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1ee76f894d31fd65fd31011f33f7363f1b09de31
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54726801"
---
# <a name="iclrappdomainresourcemonitor-interface"></a><span data-ttu-id="7302c-102">ICLRAppDomainResourceMonitor 接口</span><span class="sxs-lookup"><span data-stu-id="7302c-102">ICLRAppDomainResourceMonitor Interface</span></span>
<span data-ttu-id="7302c-103">提供检查应用程序域的内存和 CPU 使用情况的方法。</span><span class="sxs-lookup"><span data-stu-id="7302c-103">Provides methods that inspect an application domain's memory and CPU usage.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7302c-104">方法</span><span class="sxs-lookup"><span data-stu-id="7302c-104">Methods</span></span>  
  
|<span data-ttu-id="7302c-105">方法</span><span class="sxs-lookup"><span data-stu-id="7302c-105">Method</span></span>|<span data-ttu-id="7302c-106">描述</span><span class="sxs-lookup"><span data-stu-id="7302c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7302c-107">GetCurrentAllocated 方法</span><span class="sxs-lookup"><span data-stu-id="7302c-107">GetCurrentAllocated Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-getcurrentallocated-method.md)|<span data-ttu-id="7302c-108">获取用字节表示，因为它创建的而无需减去已进行垃圾回收的内存进行的应用程序域的所有内存分配的总大小。</span><span class="sxs-lookup"><span data-stu-id="7302c-108">Gets the total size, in bytes, of all memory allocations that have been made by the application domain since it was created, without subtracting memory that has been garbage-collected.</span></span>|  
|[<span data-ttu-id="7302c-109">GetCurrentSurvived 方法</span><span class="sxs-lookup"><span data-stu-id="7302c-109">GetCurrentSurvived Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-getcurrentsurvived-method.md)|<span data-ttu-id="7302c-110">获取上次的完整、 阻碍性垃圾回收后保留下来并由当前的应用程序域引用的字节数。</span><span class="sxs-lookup"><span data-stu-id="7302c-110">Gets the number of bytes that survived the last full, blocking garbage collection and that are referenced by the current application domain.</span></span>|  
|[<span data-ttu-id="7302c-111">GetCurrentCpuTime 方法</span><span class="sxs-lookup"><span data-stu-id="7302c-111">GetCurrentCpuTime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-getcurrentcputime-method.md)|<span data-ttu-id="7302c-112">获取在当前的应用程序域中执行，原因是已创建的应用程序域时使用的所有线程的总处理器时间。</span><span class="sxs-lookup"><span data-stu-id="7302c-112">Gets the total processor time that has been used by all threads while executing in the current application domain, since the application domain was created.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7302c-113">备注</span><span class="sxs-lookup"><span data-stu-id="7302c-113">Remarks</span></span>  
 <span data-ttu-id="7302c-114">`ICLRAppDomainResourceMonitor`接口提供的功能，类似于以下的托管属性：</span><span class="sxs-lookup"><span data-stu-id="7302c-114">The `ICLRAppDomainResourceMonitor` interface provides functionality that is similar to the following managed properties:</span></span>  
  
-   <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType>  
  
-   <xref:System.AppDomain.MonitoringTotalProcessorTime%2A?displayProperty=nameWithType>  
  
-   <xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType>  
  
-   <xref:System.AppDomain.MonitoringSurvivedProcessMemorySize%2A?displayProperty=nameWithType>  
  
-   <xref:System.AppDomain.MonitoringSurvivedMemorySize%2A?displayProperty=nameWithType>  
  
## <a name="requirements"></a><span data-ttu-id="7302c-115">要求</span><span class="sxs-lookup"><span data-stu-id="7302c-115">Requirements</span></span>  
 <span data-ttu-id="7302c-116">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7302c-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7302c-117">**标头：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="7302c-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="7302c-118">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="7302c-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7302c-119">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7302c-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7302c-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="7302c-120">See also</span></span>
- [<span data-ttu-id="7302c-121">\<appDomainResourceMonitoring > 元素</span><span class="sxs-lookup"><span data-stu-id="7302c-121">\<appDomainResourceMonitoring> Element</span></span>](../../../../docs/framework/configure-apps/file-schema/runtime/appdomainresourcemonitoring-element.md)
- [<span data-ttu-id="7302c-122">应用程序域资源监视</span><span class="sxs-lookup"><span data-stu-id="7302c-122">Application Domain Resource Monitoring</span></span>](../../../../docs/standard/garbage-collection/app-domain-resource-monitoring.md)
- [<span data-ttu-id="7302c-123">承载接口</span><span class="sxs-lookup"><span data-stu-id="7302c-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="7302c-124">承载</span><span class="sxs-lookup"><span data-stu-id="7302c-124">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
