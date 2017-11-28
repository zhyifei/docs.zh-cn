---
title: "ICLRAppDomainResourceMonitor::GetCurrentCpuTime 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRAppDomainResourceMonitor.GetCurrentCpuTime
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRAppDomainResourceMonitor::GetCurrentCpuTime
helpviewer_keywords:
- ICLRAppDomainResourceMonitor::GetCurrentCpuTime method [.NET Framework hosting]
- GetCurrentCpuTime method [.NET Framework hosting]
ms.assetid: ebc9cc33-fcd6-4cae-9ecb-ea21c51874e6
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2483165de54cd5ec76abad9d8472e0deef28f149
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="iclrappdomainresourcemonitorgetcurrentcputime-method"></a><span data-ttu-id="52a3f-102">ICLRAppDomainResourceMonitor::GetCurrentCpuTime 方法</span><span class="sxs-lookup"><span data-stu-id="52a3f-102">ICLRAppDomainResourceMonitor::GetCurrentCpuTime Method</span></span>
<span data-ttu-id="52a3f-103">获取自应用程序域创建以来在当前的应用程序域中，执行时使用的所有线程的总处理器时间。</span><span class="sxs-lookup"><span data-stu-id="52a3f-103">Gets the total processor time that has been used by all threads while executing in the current application domain, since the application domain was created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52a3f-104">语法</span><span class="sxs-lookup"><span data-stu-id="52a3f-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentCpuTime([in]  DWORD dwAppDomainId,  
                          [out] ULONGLONG* pMilliseconds);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="52a3f-105">参数</span><span class="sxs-lookup"><span data-stu-id="52a3f-105">Parameters</span></span>  
 `dwAppDomainId`  
 <span data-ttu-id="52a3f-106">[in]请求的应用程序域的 ID。</span><span class="sxs-lookup"><span data-stu-id="52a3f-106">[in] The ID of the requested application domain.</span></span>  
  
 `pMilliseconds`  
 <span data-ttu-id="52a3f-107">[out]指向自应用程序域创建以来在当前的应用程序域中执行时使用的所有线程的总处理器时间的指针。</span><span class="sxs-lookup"><span data-stu-id="52a3f-107">[out] A pointer to the total processor time that has been used by all threads while executing in the current application domain since the application domain was created.</span></span> <span data-ttu-id="52a3f-108">此参数可以为 `null`。</span><span class="sxs-lookup"><span data-stu-id="52a3f-108">This parameter can be `null`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="52a3f-109">返回值</span><span class="sxs-lookup"><span data-stu-id="52a3f-109">Return Value</span></span>  
  
|<span data-ttu-id="52a3f-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="52a3f-110">HRESULT</span></span>|<span data-ttu-id="52a3f-111">描述</span><span class="sxs-lookup"><span data-stu-id="52a3f-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="52a3f-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="52a3f-112">S_OK</span></span>|<span data-ttu-id="52a3f-113">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="52a3f-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="52a3f-114">COR_E_APPDOMAINUNLOADED</span><span class="sxs-lookup"><span data-stu-id="52a3f-114">COR_E_APPDOMAINUNLOADED</span></span>|<span data-ttu-id="52a3f-115">应用程序域已被卸载，或不存在。</span><span class="sxs-lookup"><span data-stu-id="52a3f-115">The application domain has been unloaded or does not exist.</span></span>|  
|<span data-ttu-id="52a3f-116">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="52a3f-116">E_FAIL</span></span>|<span data-ttu-id="52a3f-117">未启用应用程序域资源监视。</span><span class="sxs-lookup"><span data-stu-id="52a3f-117">Application domain resource monitoring is not enabled.</span></span><br /><br /> <span data-ttu-id="52a3f-118">- 或 -</span><span class="sxs-lookup"><span data-stu-id="52a3f-118">-or-</span></span><br /><br /> <span data-ttu-id="52a3f-119">所有其他故障。</span><span class="sxs-lookup"><span data-stu-id="52a3f-119">All other failures.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="52a3f-120">备注</span><span class="sxs-lookup"><span data-stu-id="52a3f-120">Remarks</span></span>  
 <span data-ttu-id="52a3f-121">此方法是托管的非托管等效项<xref:System.AppDomain.MonitoringTotalProcessorTime%2A?displayProperty=nameWithType>属性。</span><span class="sxs-lookup"><span data-stu-id="52a3f-121">This method is the unmanaged equivalent of the managed <xref:System.AppDomain.MonitoringTotalProcessorTime%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="52a3f-122">要求</span><span class="sxs-lookup"><span data-stu-id="52a3f-122">Requirements</span></span>  
 <span data-ttu-id="52a3f-123">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="52a3f-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="52a3f-124">**标头：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="52a3f-124">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="52a3f-125">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="52a3f-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="52a3f-126">**.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="52a3f-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52a3f-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="52a3f-127">See Also</span></span>  
 [<span data-ttu-id="52a3f-128">ICLRAppDomainResourceMonitor 接口</span><span class="sxs-lookup"><span data-stu-id="52a3f-128">ICLRAppDomainResourceMonitor Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)  
 [<span data-ttu-id="52a3f-129">承载接口</span><span class="sxs-lookup"><span data-stu-id="52a3f-129">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="52a3f-130">应用程序域资源监视</span><span class="sxs-lookup"><span data-stu-id="52a3f-130">Application Domain Resource Monitoring</span></span>](../../../../docs/standard/garbage-collection/app-domain-resource-monitoring.md)  
 [<span data-ttu-id="52a3f-131">承载</span><span class="sxs-lookup"><span data-stu-id="52a3f-131">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
