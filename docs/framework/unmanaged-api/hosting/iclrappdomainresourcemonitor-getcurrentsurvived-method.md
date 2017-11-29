---
title: "ICLRAppDomainResourceMonitor::GetCurrentSurvived 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRAppDomainResourceMonitor.GetCurrentSurvived
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRAppDomainResourceMonitor::GetCurrentSurvived
helpviewer_keywords:
- ICLRAppDomainResourceMonitor::GetCurrentSurvived method [.NET Framework hosting]
- GetCurrentSurvived method [.NET Framework hosting]
ms.assetid: 392e9009-40ef-40e3-ad4d-7ce93a989e78
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b9fe624c83be5dcf762f1c6036f8e4264f0e45c5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="iclrappdomainresourcemonitorgetcurrentsurvived-method"></a><span data-ttu-id="e3167-102">ICLRAppDomainResourceMonitor::GetCurrentSurvived 方法</span><span class="sxs-lookup"><span data-stu-id="e3167-102">ICLRAppDomainResourceMonitor::GetCurrentSurvived Method</span></span>
<span data-ttu-id="e3167-103">获取最后一个完整、 阻碍性垃圾回收后保留下来的、 由当前的应用程序域引用的字节数。</span><span class="sxs-lookup"><span data-stu-id="e3167-103">Gets the number of bytes that survived the last full, blocking garbage collection and that are referenced by the current application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3167-104">语法</span><span class="sxs-lookup"><span data-stu-id="e3167-104">Syntax</span></span>  
  
```  
HRESULT STDMETHODCALLTYPE GetCurrentSurvived(  
             [in]  DWORD dwAppDomainId,  
             [out] ULONGLONG *pAppDomainBytesSurvived,  
             [out] ULONGLONG *pTotalBytesSurvived);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e3167-105">参数</span><span class="sxs-lookup"><span data-stu-id="e3167-105">Parameters</span></span>  
 `dwAppDomainId`  
 <span data-ttu-id="e3167-106">[in]请求的应用程序域的 ID。</span><span class="sxs-lookup"><span data-stu-id="e3167-106">[in] The ID of the requested application domain.</span></span>  
  
 `pAppDomainBytesSurvived`  
 <span data-ttu-id="e3167-107">[out]指向最后一个垃圾回收后仍存在此应用程序域所持有的字节数的指针。</span><span class="sxs-lookup"><span data-stu-id="e3167-107">[out] A pointer to the number of bytes that survived after the last garbage collection that are held by this application domain.</span></span> <span data-ttu-id="e3167-108">完整回收之后，此数字应准确且完整。</span><span class="sxs-lookup"><span data-stu-id="e3167-108">After a full collection, this number is accurate and complete.</span></span> <span data-ttu-id="e3167-109">暂时回收之后，此编号是可能不完整。</span><span class="sxs-lookup"><span data-stu-id="e3167-109">After an ephemeral collection, this number is potentially incomplete.</span></span> <span data-ttu-id="e3167-110">此参数可以为 `null`。</span><span class="sxs-lookup"><span data-stu-id="e3167-110">This parameter can be `null`.</span></span>  
  
 `pRuntimeBytesSurvived`  
 <span data-ttu-id="e3167-111">[out]指向的从上一次垃圾回收后保留下来的字节总数的指针。</span><span class="sxs-lookup"><span data-stu-id="e3167-111">[out] A pointer to the total number of bytes that survived from the last garbage collection.</span></span> <span data-ttu-id="e3167-112">完整回收之后，此数字表示托管堆中保留的字节数。</span><span class="sxs-lookup"><span data-stu-id="e3167-112">After a full collection, this number represents the number of the bytes that are held in managed heaps.</span></span> <span data-ttu-id="e3167-113">暂时回收之后，此数字表示暂时生成中实时保留的字节数。</span><span class="sxs-lookup"><span data-stu-id="e3167-113">After an ephemeral collection, this number represents the number of bytes that are held live in ephemeral generations.</span></span> <span data-ttu-id="e3167-114">此参数可以为 `null`。</span><span class="sxs-lookup"><span data-stu-id="e3167-114">This parameter can be `null`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e3167-115">返回值</span><span class="sxs-lookup"><span data-stu-id="e3167-115">Return Value</span></span>  
 <span data-ttu-id="e3167-116">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="e3167-116">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="e3167-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e3167-117">HRESULT</span></span>|<span data-ttu-id="e3167-118">描述</span><span class="sxs-lookup"><span data-stu-id="e3167-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e3167-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="e3167-119">S_OK</span></span>|<span data-ttu-id="e3167-120">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="e3167-120">The method completed successfully.</span></span>|  
|<span data-ttu-id="e3167-121">COR_E_APPDOMAINUNLOADED</span><span class="sxs-lookup"><span data-stu-id="e3167-121">COR_E_APPDOMAINUNLOADED</span></span>|<span data-ttu-id="e3167-122">应用程序域已被卸载，或不存在。</span><span class="sxs-lookup"><span data-stu-id="e3167-122">The application domain has been unloaded or does not exist.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e3167-123">备注</span><span class="sxs-lookup"><span data-stu-id="e3167-123">Remarks</span></span>  
 <span data-ttu-id="e3167-124">只有在完整、 阻碍性垃圾回收; 之后更新统计信息也就是说，的集合包含所有代并停止应用程序时集合时发生。</span><span class="sxs-lookup"><span data-stu-id="e3167-124">Statistics are updated only after a full, blocking garbage collection; that is, a collection that includes all generations and that stops the application while collection occurs.</span></span> <span data-ttu-id="e3167-125">例如，<xref:System.GC.Collect?displayProperty=nameWithType>方法重载执行的完整、 阻碍性回收。</span><span class="sxs-lookup"><span data-stu-id="e3167-125">For example, the <xref:System.GC.Collect?displayProperty=nameWithType> method overload performs a full, blocking collection.</span></span> <span data-ttu-id="e3167-126">并发垃圾回收发生在后台，并且不会阻止应用程序。</span><span class="sxs-lookup"><span data-stu-id="e3167-126">Concurrent garbage collection occurs in the background and does not block the application.</span></span>  
  
 <span data-ttu-id="e3167-127">`GetCurrentSurvived`方法是托管的非托管等效项<xref:System.AppDomain.MonitoringSurvivedMemorySize%2A?displayProperty=nameWithType>属性。</span><span class="sxs-lookup"><span data-stu-id="e3167-127">The `GetCurrentSurvived` method is the unmanaged equivalent of the managed <xref:System.AppDomain.MonitoringSurvivedMemorySize%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e3167-128">要求</span><span class="sxs-lookup"><span data-stu-id="e3167-128">Requirements</span></span>  
 <span data-ttu-id="e3167-129">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e3167-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e3167-130">**标头：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="e3167-130">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="e3167-131">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="e3167-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e3167-132">**.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e3167-132">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3167-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e3167-133">See Also</span></span>  
 [<span data-ttu-id="e3167-134">ICLRAppDomainResourceMonitor 接口</span><span class="sxs-lookup"><span data-stu-id="e3167-134">ICLRAppDomainResourceMonitor Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)  
 [<span data-ttu-id="e3167-135">应用程序域资源监视</span><span class="sxs-lookup"><span data-stu-id="e3167-135">Application Domain Resource Monitoring</span></span>](../../../../docs/standard/garbage-collection/app-domain-resource-monitoring.md)  
 [<span data-ttu-id="e3167-136">承载接口</span><span class="sxs-lookup"><span data-stu-id="e3167-136">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="e3167-137">承载</span><span class="sxs-lookup"><span data-stu-id="e3167-137">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
