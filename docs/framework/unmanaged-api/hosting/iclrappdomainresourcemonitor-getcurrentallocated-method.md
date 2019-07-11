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
ms.openlocfilehash: 19aced41860002081caaf6436bad08f5f9a09e9a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67766654"
---
# <a name="iclrappdomainresourcemonitorgetcurrentallocated-method"></a><span data-ttu-id="6e8fa-102">ICLRAppDomainResourceMonitor::GetCurrentAllocated 方法</span><span class="sxs-lookup"><span data-stu-id="6e8fa-102">ICLRAppDomainResourceMonitor::GetCurrentAllocated Method</span></span>
<span data-ttu-id="6e8fa-103">获取用字节表示，因为它创建的而无需减去已进行垃圾回收的内存进行的应用程序域的所有内存分配的总大小。</span><span class="sxs-lookup"><span data-stu-id="6e8fa-103">Gets the total size, in bytes, of all memory allocations that have been made by the application domain since it was created, without subtracting memory that has been garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e8fa-104">语法</span><span class="sxs-lookup"><span data-stu-id="6e8fa-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentAllocated([in]  DWORD dwAppDomainId,  
                            [out] ULONGLONG* pBytesAllocated);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6e8fa-105">参数</span><span class="sxs-lookup"><span data-stu-id="6e8fa-105">Parameters</span></span>  
 `dwAppDomainId`  
 <span data-ttu-id="6e8fa-106">[in]请求的应用程序域的 ID。</span><span class="sxs-lookup"><span data-stu-id="6e8fa-106">[in] The ID of the requested application domain.</span></span>  
  
 `pBytesAllocated`  
 <span data-ttu-id="6e8fa-107">[out]指向所有内存分配的总大小的指针。</span><span class="sxs-lookup"><span data-stu-id="6e8fa-107">[out] A pointer to the total size of all memory allocations.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6e8fa-108">返回值</span><span class="sxs-lookup"><span data-stu-id="6e8fa-108">Return Value</span></span>  
 <span data-ttu-id="6e8fa-109">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="6e8fa-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="6e8fa-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6e8fa-110">HRESULT</span></span>|<span data-ttu-id="6e8fa-111">描述</span><span class="sxs-lookup"><span data-stu-id="6e8fa-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6e8fa-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="6e8fa-112">S_OK</span></span>|<span data-ttu-id="6e8fa-113">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="6e8fa-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="6e8fa-114">COR_E_APPDOMAINUNLOADED</span><span class="sxs-lookup"><span data-stu-id="6e8fa-114">COR_E_APPDOMAINUNLOADED</span></span>|<span data-ttu-id="6e8fa-115">应用程序域已被卸载，或不存在。</span><span class="sxs-lookup"><span data-stu-id="6e8fa-115">The application domain has been unloaded or does not exist.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6e8fa-116">备注</span><span class="sxs-lookup"><span data-stu-id="6e8fa-116">Remarks</span></span>  
 <span data-ttu-id="6e8fa-117">此方法相当于非托管的托管<xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType>属性。</span><span class="sxs-lookup"><span data-stu-id="6e8fa-117">This method is the unmanaged equivalent of the managed <xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e8fa-118">要求</span><span class="sxs-lookup"><span data-stu-id="6e8fa-118">Requirements</span></span>  
 <span data-ttu-id="6e8fa-119">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6e8fa-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6e8fa-120">**标头：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="6e8fa-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="6e8fa-121">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="6e8fa-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6e8fa-122">**.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6e8fa-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e8fa-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="6e8fa-123">See also</span></span>

- [<span data-ttu-id="6e8fa-124">ICLRAppDomainResourceMonitor 接口</span><span class="sxs-lookup"><span data-stu-id="6e8fa-124">ICLRAppDomainResourceMonitor Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)
- [<span data-ttu-id="6e8fa-125">应用程序域资源监视</span><span class="sxs-lookup"><span data-stu-id="6e8fa-125">Application Domain Resource Monitoring</span></span>](../../../../docs/standard/garbage-collection/app-domain-resource-monitoring.md)
- [<span data-ttu-id="6e8fa-126">承载接口</span><span class="sxs-lookup"><span data-stu-id="6e8fa-126">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="6e8fa-127">承载</span><span class="sxs-lookup"><span data-stu-id="6e8fa-127">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
