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
ms.openlocfilehash: 314ffb143e99f9490bcd4a6489f2afed314b7c2c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67768756"
---
# <a name="iclrruntimehostexecuteinappdomain-method"></a><span data-ttu-id="708e8-102">ICLRRuntimeHost::ExecuteInAppDomain 方法</span><span class="sxs-lookup"><span data-stu-id="708e8-102">ICLRRuntimeHost::ExecuteInAppDomain Method</span></span>
<span data-ttu-id="708e8-103">指定<xref:System.AppDomain>在其中执行指定的托管的代码。</span><span class="sxs-lookup"><span data-stu-id="708e8-103">Specifies the <xref:System.AppDomain> in which to execute the specified managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="708e8-104">语法</span><span class="sxs-lookup"><span data-stu-id="708e8-104">Syntax</span></span>  
  
```cpp  
HRESULT ExecuteInAppDomain(  
    [in] DWORD AppDomainId,   
    [in] FExecuteInDomainCallback pCallback,   
    [in] void* cookie  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="708e8-105">参数</span><span class="sxs-lookup"><span data-stu-id="708e8-105">Parameters</span></span>  
 `AppDomainId`  
 <span data-ttu-id="708e8-106">[in]数字 ID<xref:System.AppDomain>在其中执行指定的方法。</span><span class="sxs-lookup"><span data-stu-id="708e8-106">[in] The numeric ID of the <xref:System.AppDomain> in which to execute the specified method.</span></span>  
  
 `pCallback`  
 <span data-ttu-id="708e8-107">[in]指向要执行在指定的函数的指针<xref:System.AppDomain>。</span><span class="sxs-lookup"><span data-stu-id="708e8-107">[in] A pointer to the function to execute within the specified <xref:System.AppDomain>.</span></span>  
  
 `cookie`  
 <span data-ttu-id="708e8-108">[in]指向不透明调用方分配的内存的指针。</span><span class="sxs-lookup"><span data-stu-id="708e8-108">[in] A pointer to opaque caller-allocated memory.</span></span> <span data-ttu-id="708e8-109">此参数由公共语言运行时 (CLR) 传递给域回调。</span><span class="sxs-lookup"><span data-stu-id="708e8-109">This parameter is passed by the common language runtime (CLR) to the domain callback.</span></span> <span data-ttu-id="708e8-110">它不是运行时托管堆内存;分配和此内存的生存期由调用方控制。</span><span class="sxs-lookup"><span data-stu-id="708e8-110">It is not runtime-managed heap memory; both the allocation and lifetime of this memory are controlled by the caller.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="708e8-111">返回值</span><span class="sxs-lookup"><span data-stu-id="708e8-111">Return Value</span></span>  
  
|<span data-ttu-id="708e8-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="708e8-112">HRESULT</span></span>|<span data-ttu-id="708e8-113">描述</span><span class="sxs-lookup"><span data-stu-id="708e8-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="708e8-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="708e8-114">S_OK</span></span>|<span data-ttu-id="708e8-115">`ExecuteInAppDomain` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="708e8-115">`ExecuteInAppDomain` returned successfully.</span></span>|  
|<span data-ttu-id="708e8-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="708e8-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="708e8-117">CLR 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="708e8-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="708e8-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="708e8-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="708e8-119">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="708e8-119">The call timed out.</span></span>|  
|<span data-ttu-id="708e8-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="708e8-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="708e8-121">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="708e8-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="708e8-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="708e8-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="708e8-123">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="708e8-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="708e8-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="708e8-124">E_FAIL</span></span>|<span data-ttu-id="708e8-125">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="708e8-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="708e8-126">如果方法返回 E_FAIL，CLR 不再在该过程中可用。</span><span class="sxs-lookup"><span data-stu-id="708e8-126">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="708e8-127">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="708e8-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="708e8-128">备注</span><span class="sxs-lookup"><span data-stu-id="708e8-128">Remarks</span></span>  
 <span data-ttu-id="708e8-129">`ExecuteInAppDomain` 允许主机以控制在哪个托管<xref:System.AppDomain>应在执行指定的托管的方法。</span><span class="sxs-lookup"><span data-stu-id="708e8-129">`ExecuteInAppDomain` allows the host to exercise control over which managed <xref:System.AppDomain> the specified managed method should be executed in.</span></span> <span data-ttu-id="708e8-130">可以获取应用程序域的标识符，对应的值的值<xref:System.AppDomain.Id%2A>属性，通过调用[GetCurrentAppDomainId 方法](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md)。</span><span class="sxs-lookup"><span data-stu-id="708e8-130">You can get the value of an application domain's identifier, which corresponds to the value of the <xref:System.AppDomain.Id%2A> property, by calling [GetCurrentAppDomainId Method](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="708e8-131">要求</span><span class="sxs-lookup"><span data-stu-id="708e8-131">Requirements</span></span>  
 <span data-ttu-id="708e8-132">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="708e8-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="708e8-133">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="708e8-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="708e8-134">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="708e8-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="708e8-135">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="708e8-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="708e8-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="708e8-136">See also</span></span>

- [<span data-ttu-id="708e8-137">ICLRRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="708e8-137">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
