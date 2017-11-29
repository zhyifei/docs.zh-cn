---
title: "ICLRAppDomainResourceMonitor::GetCurrentAllocated 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRAppDomainResourceMonitor.GetCurrentAllocated
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRAppDomainResourceMonitor::GetCurrentAllocated
helpviewer_keywords:
- GetCurrentAllocated method [.NET Framework hosting]
- ICLRAppDomainResourceMonitor::GetCurrentAllocated method [.NET Framework hosting]
ms.assetid: 7bab209c-efd4-44c2-af30-61abab0ae2fc
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: dee616e1fbd071662a42af856fa2cd51f7bdd5d4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="iclrappdomainresourcemonitorgetcurrentallocated-method"></a><span data-ttu-id="13812-102">ICLRAppDomainResourceMonitor::GetCurrentAllocated 方法</span><span class="sxs-lookup"><span data-stu-id="13812-102">ICLRAppDomainResourceMonitor::GetCurrentAllocated Method</span></span>
<span data-ttu-id="13812-103">获取用字节表示，已由应用程序域创建以来，不扣除已进行垃圾回收的内存的所有内存分配的总大小。</span><span class="sxs-lookup"><span data-stu-id="13812-103">Gets the total size, in bytes, of all memory allocations that have been made by the application domain since it was created, without subtracting memory that has been garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13812-104">语法</span><span class="sxs-lookup"><span data-stu-id="13812-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentAllocated([in]  DWORD dwAppDomainId,  
                            [out] ULONGLONG* pBytesAllocated);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="13812-105">参数</span><span class="sxs-lookup"><span data-stu-id="13812-105">Parameters</span></span>  
 `dwAppDomainId`  
 <span data-ttu-id="13812-106">[in]请求的应用程序域的 ID。</span><span class="sxs-lookup"><span data-stu-id="13812-106">[in] The ID of the requested application domain.</span></span>  
  
 `pBytesAllocated`  
 <span data-ttu-id="13812-107">[out]指向的所有内存分配的总大小的指针。</span><span class="sxs-lookup"><span data-stu-id="13812-107">[out] A pointer to the total size of all memory allocations.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="13812-108">返回值</span><span class="sxs-lookup"><span data-stu-id="13812-108">Return Value</span></span>  
 <span data-ttu-id="13812-109">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="13812-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="13812-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="13812-110">HRESULT</span></span>|<span data-ttu-id="13812-111">描述</span><span class="sxs-lookup"><span data-stu-id="13812-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="13812-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="13812-112">S_OK</span></span>|<span data-ttu-id="13812-113">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="13812-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="13812-114">COR_E_APPDOMAINUNLOADED</span><span class="sxs-lookup"><span data-stu-id="13812-114">COR_E_APPDOMAINUNLOADED</span></span>|<span data-ttu-id="13812-115">应用程序域已被卸载，或不存在。</span><span class="sxs-lookup"><span data-stu-id="13812-115">The application domain has been unloaded or does not exist.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="13812-116">备注</span><span class="sxs-lookup"><span data-stu-id="13812-116">Remarks</span></span>  
 <span data-ttu-id="13812-117">此方法是托管的非托管等效项<xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType>属性。</span><span class="sxs-lookup"><span data-stu-id="13812-117">This method is the unmanaged equivalent of the managed <xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13812-118">要求</span><span class="sxs-lookup"><span data-stu-id="13812-118">Requirements</span></span>  
 <span data-ttu-id="13812-119">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="13812-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13812-120">**标头：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="13812-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="13812-121">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="13812-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="13812-122">**.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13812-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13812-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="13812-123">See Also</span></span>  
 [<span data-ttu-id="13812-124">ICLRAppDomainResourceMonitor 接口</span><span class="sxs-lookup"><span data-stu-id="13812-124">ICLRAppDomainResourceMonitor Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)  
 [<span data-ttu-id="13812-125">应用程序域资源监视</span><span class="sxs-lookup"><span data-stu-id="13812-125">Application Domain Resource Monitoring</span></span>](../../../../docs/standard/garbage-collection/app-domain-resource-monitoring.md)  
 [<span data-ttu-id="13812-126">承载接口</span><span class="sxs-lookup"><span data-stu-id="13812-126">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="13812-127">承载</span><span class="sxs-lookup"><span data-stu-id="13812-127">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
