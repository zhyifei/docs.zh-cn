---
title: ICLRAppDomainResourceMonitor::GetCurrentAllocated 方法
ms.date: 03/30/2017
api_name:
- ICLRAppDomainResourceMonitor.GetCurrentAllocated
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAppDomainResourceMonitor::GetCurrentAllocated
helpviewer_keywords:
- GetCurrentAllocated method [.NET Framework hosting]
- ICLRAppDomainResourceMonitor::GetCurrentAllocated method [.NET Framework hosting]
ms.assetid: 7bab209c-efd4-44c2-af30-61abab0ae2fc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7fcd7a3aa1a6c034985099c24071429384563700
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59129384"
---
# <a name="iclrappdomainresourcemonitorgetcurrentallocated-method"></a><span data-ttu-id="970f8-102">ICLRAppDomainResourceMonitor::GetCurrentAllocated 方法</span><span class="sxs-lookup"><span data-stu-id="970f8-102">ICLRAppDomainResourceMonitor::GetCurrentAllocated Method</span></span>
<span data-ttu-id="970f8-103">获取用字节表示，因为它创建的而无需减去已进行垃圾回收的内存进行的应用程序域的所有内存分配的总大小。</span><span class="sxs-lookup"><span data-stu-id="970f8-103">Gets the total size, in bytes, of all memory allocations that have been made by the application domain since it was created, without subtracting memory that has been garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="970f8-104">语法</span><span class="sxs-lookup"><span data-stu-id="970f8-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentAllocated([in]  DWORD dwAppDomainId,  
                            [out] ULONGLONG* pBytesAllocated);  
```  
  
## <a name="parameters"></a><span data-ttu-id="970f8-105">参数</span><span class="sxs-lookup"><span data-stu-id="970f8-105">Parameters</span></span>  
 `dwAppDomainId`  
 <span data-ttu-id="970f8-106">[in]请求的应用程序域的 ID。</span><span class="sxs-lookup"><span data-stu-id="970f8-106">[in] The ID of the requested application domain.</span></span>  
  
 `pBytesAllocated`  
 <span data-ttu-id="970f8-107">[out]指向所有内存分配的总大小的指针。</span><span class="sxs-lookup"><span data-stu-id="970f8-107">[out] A pointer to the total size of all memory allocations.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="970f8-108">返回值</span><span class="sxs-lookup"><span data-stu-id="970f8-108">Return Value</span></span>  
 <span data-ttu-id="970f8-109">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="970f8-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="970f8-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="970f8-110">HRESULT</span></span>|<span data-ttu-id="970f8-111">描述</span><span class="sxs-lookup"><span data-stu-id="970f8-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="970f8-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="970f8-112">S_OK</span></span>|<span data-ttu-id="970f8-113">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="970f8-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="970f8-114">COR_E_APPDOMAINUNLOADED</span><span class="sxs-lookup"><span data-stu-id="970f8-114">COR_E_APPDOMAINUNLOADED</span></span>|<span data-ttu-id="970f8-115">应用程序域已被卸载，或不存在。</span><span class="sxs-lookup"><span data-stu-id="970f8-115">The application domain has been unloaded or does not exist.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="970f8-116">备注</span><span class="sxs-lookup"><span data-stu-id="970f8-116">Remarks</span></span>  
 <span data-ttu-id="970f8-117">此方法相当于非托管的托管<xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType>属性。</span><span class="sxs-lookup"><span data-stu-id="970f8-117">This method is the unmanaged equivalent of the managed <xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="970f8-118">要求</span><span class="sxs-lookup"><span data-stu-id="970f8-118">Requirements</span></span>  
 <span data-ttu-id="970f8-119">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="970f8-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="970f8-120">**标头：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="970f8-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="970f8-121">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="970f8-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="970f8-122">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="970f8-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="970f8-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="970f8-123">See also</span></span>

- [<span data-ttu-id="970f8-124">ICLRAppDomainResourceMonitor 接口</span><span class="sxs-lookup"><span data-stu-id="970f8-124">ICLRAppDomainResourceMonitor Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)
- [<span data-ttu-id="970f8-125">应用程序域资源监视</span><span class="sxs-lookup"><span data-stu-id="970f8-125">Application Domain Resource Monitoring</span></span>](../../../../docs/standard/garbage-collection/app-domain-resource-monitoring.md)
- [<span data-ttu-id="970f8-126">承载接口</span><span class="sxs-lookup"><span data-stu-id="970f8-126">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="970f8-127">承载</span><span class="sxs-lookup"><span data-stu-id="970f8-127">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
