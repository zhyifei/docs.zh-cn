---
title: "ICLRRuntimeHost::SetHostControl 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeHost.SetHostControl
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRRuntimeHost::SetHostControl
helpviewer_keywords:
- SetHostControl method [.NET Framework hosting]
- ICLRRuntimeHost::SetHostControl method [.NET Framework hosting]
ms.assetid: 6136be87-e631-4756-81ed-74b66581bad4
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9727144e9504a5a3ad7ae2529286440d07633b2a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iclrruntimehostsethostcontrol-method"></a><span data-ttu-id="eaa1a-102">ICLRRuntimeHost::SetHostControl 方法</span><span class="sxs-lookup"><span data-stu-id="eaa1a-102">ICLRRuntimeHost::SetHostControl Method</span></span>
<span data-ttu-id="eaa1a-103">设置公共语言运行时 (CLR) 可用于获取主机的实现的接口指针[IHostControl 接口](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)。</span><span class="sxs-lookup"><span data-stu-id="eaa1a-103">Sets the interface pointer that the common language runtime (CLR) can use to get the host's implementation of [IHostControl Interface](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eaa1a-104">语法</span><span class="sxs-lookup"><span data-stu-id="eaa1a-104">Syntax</span></span>  
  
```  
HRESULT SetHostControl(  
    [in] IHostControl* pHostControl  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="eaa1a-105">参数</span><span class="sxs-lookup"><span data-stu-id="eaa1a-105">Parameters</span></span>  
 `pHostControl`  
 <span data-ttu-id="eaa1a-106">[in]主机的实现的接口指针[IHostControl 接口](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)。</span><span class="sxs-lookup"><span data-stu-id="eaa1a-106">[in] An interface pointer to the host's implementation of [IHostControl Interface](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="eaa1a-107">返回值</span><span class="sxs-lookup"><span data-stu-id="eaa1a-107">Return Value</span></span>  
  
|<span data-ttu-id="eaa1a-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="eaa1a-108">HRESULT</span></span>|<span data-ttu-id="eaa1a-109">描述</span><span class="sxs-lookup"><span data-stu-id="eaa1a-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="eaa1a-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="eaa1a-110">S_OK</span></span>|<span data-ttu-id="eaa1a-111">`SetHostControl`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="eaa1a-111">`SetHostControl` returned successfully.</span></span>|  
|<span data-ttu-id="eaa1a-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="eaa1a-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="eaa1a-113">CLR 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="eaa1a-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="eaa1a-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="eaa1a-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="eaa1a-115">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="eaa1a-115">The call timed out.</span></span>|  
|<span data-ttu-id="eaa1a-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="eaa1a-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="eaa1a-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="eaa1a-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="eaa1a-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="eaa1a-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="eaa1a-119">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="eaa1a-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="eaa1a-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="eaa1a-120">E_FAIL</span></span>|<span data-ttu-id="eaa1a-121">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="eaa1a-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="eaa1a-122">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="eaa1a-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="eaa1a-123">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="eaa1a-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="eaa1a-124">E_CLR_ALREADY_STARTED</span><span class="sxs-lookup"><span data-stu-id="eaa1a-124">E_CLR_ALREADY_STARTED</span></span>|<span data-ttu-id="eaa1a-125">已初始化 CLR。</span><span class="sxs-lookup"><span data-stu-id="eaa1a-125">The CLR has already been initialized.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eaa1a-126">备注</span><span class="sxs-lookup"><span data-stu-id="eaa1a-126">Remarks</span></span>  
 <span data-ttu-id="eaa1a-127">必须调用`SetHostControl`初始化 CLR 时，即，然后才能调用之前[启动方法](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md)或使用任何[元数据接口](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)。</span><span class="sxs-lookup"><span data-stu-id="eaa1a-127">You must call `SetHostControl` before the CLR is initialized, that is, before you call [Start Method](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) or use any of the [Metadata Interfaces](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md).</span></span> <span data-ttu-id="eaa1a-128">建议您调用`SetHostControl`后立即调用[CorBindToCurrentRuntime 函数](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)或[CorBindToRuntimeEx 函数](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)。</span><span class="sxs-lookup"><span data-stu-id="eaa1a-128">It is recommended that you call `SetHostControl` immediately after calling [CorBindToCurrentRuntime Function](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md) or [CorBindToRuntimeEx Function](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eaa1a-129">惠?</span><span class="sxs-lookup"><span data-stu-id="eaa1a-129">Requirements</span></span>  
 <span data-ttu-id="eaa1a-130">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="eaa1a-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eaa1a-131">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="eaa1a-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="eaa1a-132">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="eaa1a-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="eaa1a-133">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eaa1a-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eaa1a-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="eaa1a-134">See Also</span></span>  
 [<span data-ttu-id="eaa1a-135">ICLRRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="eaa1a-135">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)  
 [<span data-ttu-id="eaa1a-136">IHostControl 接口</span><span class="sxs-lookup"><span data-stu-id="eaa1a-136">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
