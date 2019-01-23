---
title: ICLRAppDomainResourceMonitor::GetCurrentSurvived 方法
ms.date: 03/30/2017
api_name:
- ICLRAppDomainResourceMonitor.GetCurrentSurvived
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAppDomainResourceMonitor::GetCurrentSurvived
helpviewer_keywords:
- ICLRAppDomainResourceMonitor::GetCurrentSurvived method [.NET Framework hosting]
- GetCurrentSurvived method [.NET Framework hosting]
ms.assetid: 392e9009-40ef-40e3-ad4d-7ce93a989e78
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 648a2c044920b7524ad96ff656e83268ffd55652
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54612211"
---
# <a name="iclrappdomainresourcemonitorgetcurrentsurvived-method"></a><span data-ttu-id="d3929-102">ICLRAppDomainResourceMonitor::GetCurrentSurvived 方法</span><span class="sxs-lookup"><span data-stu-id="d3929-102">ICLRAppDomainResourceMonitor::GetCurrentSurvived Method</span></span>
<span data-ttu-id="d3929-103">获取上次的完整、 阻碍性垃圾回收后保留下来并由当前的应用程序域引用的字节数。</span><span class="sxs-lookup"><span data-stu-id="d3929-103">Gets the number of bytes that survived the last full, blocking garbage collection and that are referenced by the current application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3929-104">语法</span><span class="sxs-lookup"><span data-stu-id="d3929-104">Syntax</span></span>  
  
```  
HRESULT STDMETHODCALLTYPE GetCurrentSurvived(  
             [in]  DWORD dwAppDomainId,  
             [out] ULONGLONG *pAppDomainBytesSurvived,  
             [out] ULONGLONG *pTotalBytesSurvived);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d3929-105">参数</span><span class="sxs-lookup"><span data-stu-id="d3929-105">Parameters</span></span>  
 `dwAppDomainId`  
 <span data-ttu-id="d3929-106">[in]请求的应用程序域的 ID。</span><span class="sxs-lookup"><span data-stu-id="d3929-106">[in] The ID of the requested application domain.</span></span>  
  
 `pAppDomainBytesSurvived`  
 <span data-ttu-id="d3929-107">[out]指向最后一个垃圾回收后仍存在于此应用程序域所持有的字节数的指针。</span><span class="sxs-lookup"><span data-stu-id="d3929-107">[out] A pointer to the number of bytes that survived after the last garbage collection that are held by this application domain.</span></span> <span data-ttu-id="d3929-108">完整回收之后，此数字是准确和完整。</span><span class="sxs-lookup"><span data-stu-id="d3929-108">After a full collection, this number is accurate and complete.</span></span> <span data-ttu-id="d3929-109">暂时回收之后，此数字是可能不完整。</span><span class="sxs-lookup"><span data-stu-id="d3929-109">After an ephemeral collection, this number is potentially incomplete.</span></span> <span data-ttu-id="d3929-110">此参数可以为 `null`。</span><span class="sxs-lookup"><span data-stu-id="d3929-110">This parameter can be `null`.</span></span>  
  
 `pRuntimeBytesSurvived`  
 <span data-ttu-id="d3929-111">[out]指向最后一个垃圾回收后保留的字节总数的指针。</span><span class="sxs-lookup"><span data-stu-id="d3929-111">[out] A pointer to the total number of bytes that survived from the last garbage collection.</span></span> <span data-ttu-id="d3929-112">完整回收之后，此数字表示托管堆中保留的字节数。</span><span class="sxs-lookup"><span data-stu-id="d3929-112">After a full collection, this number represents the number of the bytes that are held in managed heaps.</span></span> <span data-ttu-id="d3929-113">暂时回收之后，此数字表示暂时生成中实时保留的字节数。</span><span class="sxs-lookup"><span data-stu-id="d3929-113">After an ephemeral collection, this number represents the number of bytes that are held live in ephemeral generations.</span></span> <span data-ttu-id="d3929-114">此参数可以为 `null`。</span><span class="sxs-lookup"><span data-stu-id="d3929-114">This parameter can be `null`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d3929-115">返回值</span><span class="sxs-lookup"><span data-stu-id="d3929-115">Return Value</span></span>  
 <span data-ttu-id="d3929-116">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="d3929-116">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="d3929-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d3929-117">HRESULT</span></span>|<span data-ttu-id="d3929-118">描述</span><span class="sxs-lookup"><span data-stu-id="d3929-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d3929-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="d3929-119">S_OK</span></span>|<span data-ttu-id="d3929-120">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="d3929-120">The method completed successfully.</span></span>|  
|<span data-ttu-id="d3929-121">COR_E_APPDOMAINUNLOADED</span><span class="sxs-lookup"><span data-stu-id="d3929-121">COR_E_APPDOMAINUNLOADED</span></span>|<span data-ttu-id="d3929-122">应用程序域已被卸载，或不存在。</span><span class="sxs-lookup"><span data-stu-id="d3929-122">The application domain has been unloaded or does not exist.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d3929-123">备注</span><span class="sxs-lookup"><span data-stu-id="d3929-123">Remarks</span></span>  
 <span data-ttu-id="d3929-124">仅在完整、 阻碍性垃圾回收; 后更新统计信息也就是说，其中包括所有的生成和停止应用程序，同时集合的集合时发生。</span><span class="sxs-lookup"><span data-stu-id="d3929-124">Statistics are updated only after a full, blocking garbage collection; that is, a collection that includes all generations and that stops the application while collection occurs.</span></span> <span data-ttu-id="d3929-125">例如，<xref:System.GC.Collect?displayProperty=nameWithType>方法重载执行完整、 阻碍性回收。</span><span class="sxs-lookup"><span data-stu-id="d3929-125">For example, the <xref:System.GC.Collect?displayProperty=nameWithType> method overload performs a full, blocking collection.</span></span> <span data-ttu-id="d3929-126">并发垃圾回收在后台发生，并不会阻止应用程序。</span><span class="sxs-lookup"><span data-stu-id="d3929-126">Concurrent garbage collection occurs in the background and does not block the application.</span></span>  
  
 <span data-ttu-id="d3929-127">`GetCurrentSurvived`方法是托管的非托管等效项<xref:System.AppDomain.MonitoringSurvivedMemorySize%2A?displayProperty=nameWithType>属性。</span><span class="sxs-lookup"><span data-stu-id="d3929-127">The `GetCurrentSurvived` method is the unmanaged equivalent of the managed <xref:System.AppDomain.MonitoringSurvivedMemorySize%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d3929-128">要求</span><span class="sxs-lookup"><span data-stu-id="d3929-128">Requirements</span></span>  
 <span data-ttu-id="d3929-129">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d3929-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d3929-130">**标头：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="d3929-130">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="d3929-131">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="d3929-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d3929-132">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d3929-132">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3929-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="d3929-133">See also</span></span>
- [<span data-ttu-id="d3929-134">ICLRAppDomainResourceMonitor 接口</span><span class="sxs-lookup"><span data-stu-id="d3929-134">ICLRAppDomainResourceMonitor Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)
- [<span data-ttu-id="d3929-135">应用程序域资源监视</span><span class="sxs-lookup"><span data-stu-id="d3929-135">Application Domain Resource Monitoring</span></span>](../../../../docs/standard/garbage-collection/app-domain-resource-monitoring.md)
- [<span data-ttu-id="d3929-136">承载接口</span><span class="sxs-lookup"><span data-stu-id="d3929-136">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="d3929-137">承载</span><span class="sxs-lookup"><span data-stu-id="d3929-137">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
