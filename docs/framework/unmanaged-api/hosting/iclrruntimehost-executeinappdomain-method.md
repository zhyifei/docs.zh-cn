---
title: ICLRRuntimeHost::ExecuteInAppDomain 方法
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.ExecuteInAppDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::ExecuteInAppDomain
helpviewer_keywords:
- ICLRRuntimeHost::ExecuteInAppDomain method [.NET Framework hosting]
- ExecuteInAppDomain method [.NET Framework hosting]
ms.assetid: e2b0e2db-3fae-4b56-844e-d30a125a660c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 86348c35a023e22d10c4ad2e08f5cb1104b895a8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59165457"
---
# <a name="iclrruntimehostexecuteinappdomain-method"></a><span data-ttu-id="44146-102">ICLRRuntimeHost::ExecuteInAppDomain 方法</span><span class="sxs-lookup"><span data-stu-id="44146-102">ICLRRuntimeHost::ExecuteInAppDomain Method</span></span>
<span data-ttu-id="44146-103">指定<xref:System.AppDomain>在其中执行指定的托管的代码。</span><span class="sxs-lookup"><span data-stu-id="44146-103">Specifies the <xref:System.AppDomain> in which to execute the specified managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44146-104">语法</span><span class="sxs-lookup"><span data-stu-id="44146-104">Syntax</span></span>  
  
```  
HRESULT ExecuteInAppDomain(  
    [in] DWORD AppDomainId,   
    [in] FExecuteInDomainCallback pCallback,   
    [in] void* cookie  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="44146-105">参数</span><span class="sxs-lookup"><span data-stu-id="44146-105">Parameters</span></span>  
 `AppDomainId`  
 <span data-ttu-id="44146-106">[in]数字 ID<xref:System.AppDomain>在其中执行指定的方法。</span><span class="sxs-lookup"><span data-stu-id="44146-106">[in] The numeric ID of the <xref:System.AppDomain> in which to execute the specified method.</span></span>  
  
 `pCallback`  
 <span data-ttu-id="44146-107">[in]指向要执行在指定的函数的指针<xref:System.AppDomain>。</span><span class="sxs-lookup"><span data-stu-id="44146-107">[in] A pointer to the function to execute within the specified <xref:System.AppDomain>.</span></span>  
  
 `cookie`  
 <span data-ttu-id="44146-108">[in]指向不透明调用方分配的内存的指针。</span><span class="sxs-lookup"><span data-stu-id="44146-108">[in] A pointer to opaque caller-allocated memory.</span></span> <span data-ttu-id="44146-109">此参数由公共语言运行时 (CLR) 传递给域回调。</span><span class="sxs-lookup"><span data-stu-id="44146-109">This parameter is passed by the common language runtime (CLR) to the domain callback.</span></span> <span data-ttu-id="44146-110">它不是运行时托管堆内存;分配和此内存的生存期由调用方控制。</span><span class="sxs-lookup"><span data-stu-id="44146-110">It is not runtime-managed heap memory; both the allocation and lifetime of this memory are controlled by the caller.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="44146-111">返回值</span><span class="sxs-lookup"><span data-stu-id="44146-111">Return Value</span></span>  
  
|<span data-ttu-id="44146-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="44146-112">HRESULT</span></span>|<span data-ttu-id="44146-113">描述</span><span class="sxs-lookup"><span data-stu-id="44146-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="44146-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="44146-114">S_OK</span></span>|<span data-ttu-id="44146-115">`ExecuteInAppDomain` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="44146-115">`ExecuteInAppDomain` returned successfully.</span></span>|  
|<span data-ttu-id="44146-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="44146-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="44146-117">CLR 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="44146-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="44146-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="44146-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="44146-119">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="44146-119">The call timed out.</span></span>|  
|<span data-ttu-id="44146-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="44146-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="44146-121">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="44146-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="44146-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="44146-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="44146-123">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="44146-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="44146-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="44146-124">E_FAIL</span></span>|<span data-ttu-id="44146-125">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="44146-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="44146-126">如果方法返回 E_FAIL，CLR 不再在该过程中可用。</span><span class="sxs-lookup"><span data-stu-id="44146-126">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="44146-127">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="44146-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="44146-128">备注</span><span class="sxs-lookup"><span data-stu-id="44146-128">Remarks</span></span>  
 <span data-ttu-id="44146-129">`ExecuteInAppDomain` 允许主机以控制在哪个托管<xref:System.AppDomain>应在执行指定的托管的方法。</span><span class="sxs-lookup"><span data-stu-id="44146-129">`ExecuteInAppDomain` allows the host to exercise control over which managed <xref:System.AppDomain> the specified managed method should be executed in.</span></span> <span data-ttu-id="44146-130">可以获取应用程序域的标识符，对应的值的值<xref:System.AppDomain.Id%2A>属性，通过调用[GetCurrentAppDomainId 方法](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md)。</span><span class="sxs-lookup"><span data-stu-id="44146-130">You can get the value of an application domain's identifier, which corresponds to the value of the <xref:System.AppDomain.Id%2A> property, by calling [GetCurrentAppDomainId Method](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="44146-131">要求</span><span class="sxs-lookup"><span data-stu-id="44146-131">Requirements</span></span>  
 <span data-ttu-id="44146-132">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="44146-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44146-133">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="44146-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="44146-134">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="44146-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="44146-135">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44146-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44146-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="44146-136">See also</span></span>

- [<span data-ttu-id="44146-137">ICLRRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="44146-137">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
