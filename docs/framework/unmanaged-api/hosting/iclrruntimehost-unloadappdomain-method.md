---
title: "ICLRRuntimeHost::UnloadAppDomain 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICLRRuntimeHost.UnloadAppDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::UnloadAppDomain
helpviewer_keywords:
- ICLRRuntimeHost::UnloadAppDomain method [.NET Framework hosting]
- UnloadAppDomain method [.NET Framework hosting]
ms.assetid: 571912bc-3429-4ff8-8eb2-ea993ffbd901
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 481f701ae4db15b66596c3af89c2e7aff7a28f88
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iclrruntimehostunloadappdomain-method"></a><span data-ttu-id="35e47-102">ICLRRuntimeHost::UnloadAppDomain 方法</span><span class="sxs-lookup"><span data-stu-id="35e47-102">ICLRRuntimeHost::UnloadAppDomain Method</span></span>
<span data-ttu-id="35e47-103">卸载托管<xref:System.AppDomain>对应于指定的数字标识符。</span><span class="sxs-lookup"><span data-stu-id="35e47-103">Unloads the managed <xref:System.AppDomain> that corresponds to the specified numeric identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35e47-104">语法</span><span class="sxs-lookup"><span data-stu-id="35e47-104">Syntax</span></span>  
  
```  
HRESULT UnloadAppDomain(  
    [in] DWORD dwAppDomainId  
    [in] BOOL  fWaitUntilDone  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="35e47-105">参数</span><span class="sxs-lookup"><span data-stu-id="35e47-105">Parameters</span></span>  
 `dwAppDomainId`  
 <span data-ttu-id="35e47-106">[in]要卸载的应用程序域的数字标识符。</span><span class="sxs-lookup"><span data-stu-id="35e47-106">[in] The numeric identifier of the application domain to unload.</span></span>  
  
 `fWaitUntilDone`  
 <span data-ttu-id="35e47-107">[in]`true`以指示公共语言运行时 (CLR) 必须等待它完成，然后再尝试卸载的应用程序域中执行应用程序的当前线程。</span><span class="sxs-lookup"><span data-stu-id="35e47-107">[in] `true` to indicate that the common language runtime( CLR) must wait until it has finished executing the application's current thread before attempting to unload the application domain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="35e47-108">返回值</span><span class="sxs-lookup"><span data-stu-id="35e47-108">Return Value</span></span>  
  
|<span data-ttu-id="35e47-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="35e47-109">HRESULT</span></span>|<span data-ttu-id="35e47-110">描述</span><span class="sxs-lookup"><span data-stu-id="35e47-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="35e47-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="35e47-111">S_OK</span></span>|<span data-ttu-id="35e47-112">`UnloadAppDomain`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="35e47-112">`UnloadAppDomain` returned successfully.</span></span>|  
|<span data-ttu-id="35e47-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="35e47-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="35e47-114">CLR 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="35e47-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="35e47-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="35e47-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="35e47-116">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="35e47-116">The call timed out.</span></span>|  
|<span data-ttu-id="35e47-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="35e47-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="35e47-118">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="35e47-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="35e47-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="35e47-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="35e47-120">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="35e47-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="35e47-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="35e47-121">E_FAIL</span></span>|<span data-ttu-id="35e47-122">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="35e47-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="35e47-123">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="35e47-123">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="35e47-124">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="35e47-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="35e47-125">备注</span><span class="sxs-lookup"><span data-stu-id="35e47-125">Remarks</span></span>  
 <span data-ttu-id="35e47-126">你可以获取当前线程正在其中执行通过调用应用程序域的数字标识符[GetCurrentAppDomainId](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md)。</span><span class="sxs-lookup"><span data-stu-id="35e47-126">You can get the numeric identifier of the application domain in which the current thread is executing by calling [GetCurrentAppDomainId](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md).</span></span> <span data-ttu-id="35e47-127">此标识符对应于<xref:System.AppDomain.Id%2A>属性托管的<xref:System.AppDomain>类型。</span><span class="sxs-lookup"><span data-stu-id="35e47-127">This identifier corresponds to the <xref:System.AppDomain.Id%2A> property of the managed <xref:System.AppDomain> type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="35e47-128">惠?</span><span class="sxs-lookup"><span data-stu-id="35e47-128">Requirements</span></span>  
 <span data-ttu-id="35e47-129">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="35e47-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35e47-130">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="35e47-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="35e47-131">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="35e47-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="35e47-132">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35e47-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35e47-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="35e47-133">See Also</span></span>  
 [<span data-ttu-id="35e47-134">ICLRRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="35e47-134">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
