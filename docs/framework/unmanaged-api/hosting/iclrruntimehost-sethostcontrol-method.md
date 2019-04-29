---
title: ICLRRuntimeHost::SetHostControl 方法
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.SetHostControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::SetHostControl
helpviewer_keywords:
- SetHostControl method [.NET Framework hosting]
- ICLRRuntimeHost::SetHostControl method [.NET Framework hosting]
ms.assetid: 6136be87-e631-4756-81ed-74b66581bad4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6817a2154e876dfa83540e3496f42acdcdb25a83
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61771808"
---
# <a name="iclrruntimehostsethostcontrol-method"></a><span data-ttu-id="e41fa-102">ICLRRuntimeHost::SetHostControl 方法</span><span class="sxs-lookup"><span data-stu-id="e41fa-102">ICLRRuntimeHost::SetHostControl Method</span></span>
<span data-ttu-id="e41fa-103">设置公共语言运行时 (CLR) 可用于获取主机的实现的接口指针[IHostControl 接口](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)。</span><span class="sxs-lookup"><span data-stu-id="e41fa-103">Sets the interface pointer that the common language runtime (CLR) can use to get the host's implementation of [IHostControl Interface](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e41fa-104">语法</span><span class="sxs-lookup"><span data-stu-id="e41fa-104">Syntax</span></span>  
  
```  
HRESULT SetHostControl(  
    [in] IHostControl* pHostControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e41fa-105">参数</span><span class="sxs-lookup"><span data-stu-id="e41fa-105">Parameters</span></span>  
 `pHostControl`  
 <span data-ttu-id="e41fa-106">[in]主机的实现的接口指针[IHostControl 接口](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)。</span><span class="sxs-lookup"><span data-stu-id="e41fa-106">[in] An interface pointer to the host's implementation of [IHostControl Interface](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e41fa-107">返回值</span><span class="sxs-lookup"><span data-stu-id="e41fa-107">Return Value</span></span>  
  
|<span data-ttu-id="e41fa-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e41fa-108">HRESULT</span></span>|<span data-ttu-id="e41fa-109">描述</span><span class="sxs-lookup"><span data-stu-id="e41fa-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e41fa-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="e41fa-110">S_OK</span></span>|<span data-ttu-id="e41fa-111">`SetHostControl` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="e41fa-111">`SetHostControl` returned successfully.</span></span>|  
|<span data-ttu-id="e41fa-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e41fa-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e41fa-113">CLR 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="e41fa-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e41fa-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e41fa-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e41fa-115">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="e41fa-115">The call timed out.</span></span>|  
|<span data-ttu-id="e41fa-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e41fa-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e41fa-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="e41fa-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e41fa-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e41fa-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e41fa-119">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="e41fa-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e41fa-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e41fa-120">E_FAIL</span></span>|<span data-ttu-id="e41fa-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="e41fa-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e41fa-122">如果方法返回 E_FAIL，CLR 不再在该过程中可用。</span><span class="sxs-lookup"><span data-stu-id="e41fa-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e41fa-123">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="e41fa-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="e41fa-124">E_CLR_ALREADY_STARTED</span><span class="sxs-lookup"><span data-stu-id="e41fa-124">E_CLR_ALREADY_STARTED</span></span>|<span data-ttu-id="e41fa-125">CLR 已初始化。</span><span class="sxs-lookup"><span data-stu-id="e41fa-125">The CLR has already been initialized.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e41fa-126">备注</span><span class="sxs-lookup"><span data-stu-id="e41fa-126">Remarks</span></span>  
 <span data-ttu-id="e41fa-127">必须调用`SetHostControl`CLR 初始化时，即，然后再调用之前[Start 方法](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md)或使用任何[元数据接口](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)。</span><span class="sxs-lookup"><span data-stu-id="e41fa-127">You must call `SetHostControl` before the CLR is initialized, that is, before you call [Start Method](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) or use any of the [Metadata Interfaces](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md).</span></span> <span data-ttu-id="e41fa-128">建议您调用`SetHostControl`后立即调用[CorBindToCurrentRuntime 函数](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)或[CorBindToRuntimeEx 函数](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)。</span><span class="sxs-lookup"><span data-stu-id="e41fa-128">It is recommended that you call `SetHostControl` immediately after calling [CorBindToCurrentRuntime Function](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md) or [CorBindToRuntimeEx Function](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e41fa-129">要求</span><span class="sxs-lookup"><span data-stu-id="e41fa-129">Requirements</span></span>  
 <span data-ttu-id="e41fa-130">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e41fa-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e41fa-131">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e41fa-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e41fa-132">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="e41fa-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e41fa-133">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e41fa-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e41fa-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="e41fa-134">See also</span></span>

- [<span data-ttu-id="e41fa-135">ICLRRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="e41fa-135">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
- [<span data-ttu-id="e41fa-136">IHostControl 接口</span><span class="sxs-lookup"><span data-stu-id="e41fa-136">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
