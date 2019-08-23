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
ms.openlocfilehash: 7d02478c2421823ce2acb533d2abea2ea8b13c74
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69950293"
---
# <a name="iclrappdomainresourcemonitorgetcurrentallocated-method"></a><span data-ttu-id="1631c-102">ICLRAppDomainResourceMonitor::GetCurrentAllocated 方法</span><span class="sxs-lookup"><span data-stu-id="1631c-102">ICLRAppDomainResourceMonitor::GetCurrentAllocated Method</span></span>
<span data-ttu-id="1631c-103">获取应用程序域创建后所做的所有内存分配的总大小 (以字节为单位), 而不会减去已进行垃圾回收的内存。</span><span class="sxs-lookup"><span data-stu-id="1631c-103">Gets the total size, in bytes, of all memory allocations that have been made by the application domain since it was created, without subtracting memory that has been garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1631c-104">语法</span><span class="sxs-lookup"><span data-stu-id="1631c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentAllocated([in]  DWORD dwAppDomainId,  
                            [out] ULONGLONG* pBytesAllocated);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1631c-105">参数</span><span class="sxs-lookup"><span data-stu-id="1631c-105">Parameters</span></span>  
 `dwAppDomainId`  
 <span data-ttu-id="1631c-106">中请求的应用程序域的 ID。</span><span class="sxs-lookup"><span data-stu-id="1631c-106">[in] The ID of the requested application domain.</span></span>  
  
 `pBytesAllocated`  
 <span data-ttu-id="1631c-107">弄一个指针, 指向所有内存分配的总大小。</span><span class="sxs-lookup"><span data-stu-id="1631c-107">[out] A pointer to the total size of all memory allocations.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1631c-108">返回值</span><span class="sxs-lookup"><span data-stu-id="1631c-108">Return Value</span></span>  
 <span data-ttu-id="1631c-109">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="1631c-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="1631c-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1631c-110">HRESULT</span></span>|<span data-ttu-id="1631c-111">描述</span><span class="sxs-lookup"><span data-stu-id="1631c-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1631c-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="1631c-112">S_OK</span></span>|<span data-ttu-id="1631c-113">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="1631c-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="1631c-114">COR_E_APPDOMAINUNLOADED</span><span class="sxs-lookup"><span data-stu-id="1631c-114">COR_E_APPDOMAINUNLOADED</span></span>|<span data-ttu-id="1631c-115">应用程序域已卸载或不存在。</span><span class="sxs-lookup"><span data-stu-id="1631c-115">The application domain has been unloaded or does not exist.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1631c-116">备注</span><span class="sxs-lookup"><span data-stu-id="1631c-116">Remarks</span></span>  
 <span data-ttu-id="1631c-117">此方法是托管<xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType>属性的非托管等效项。</span><span class="sxs-lookup"><span data-stu-id="1631c-117">This method is the unmanaged equivalent of the managed <xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1631c-118">要求</span><span class="sxs-lookup"><span data-stu-id="1631c-118">Requirements</span></span>  
 <span data-ttu-id="1631c-119">**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1631c-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1631c-120">**标头：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="1631c-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="1631c-121">**类库**作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="1631c-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1631c-122">**.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1631c-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1631c-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="1631c-123">See also</span></span>

- [<span data-ttu-id="1631c-124">ICLRAppDomainResourceMonitor 接口</span><span class="sxs-lookup"><span data-stu-id="1631c-124">ICLRAppDomainResourceMonitor Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)
- [<span data-ttu-id="1631c-125">应用程序域资源监视</span><span class="sxs-lookup"><span data-stu-id="1631c-125">Application Domain Resource Monitoring</span></span>](../../../standard/garbage-collection/app-domain-resource-monitoring.md)
- [<span data-ttu-id="1631c-126">承载接口</span><span class="sxs-lookup"><span data-stu-id="1631c-126">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="1631c-127">承载</span><span class="sxs-lookup"><span data-stu-id="1631c-127">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
