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
ms.openlocfilehash: 68b06a2840de277bdaed1dc9ce0b51e6b363c897
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120454"
---
# <a name="iclrruntimehostsethostcontrol-method"></a><span data-ttu-id="4efcb-102">ICLRRuntimeHost::SetHostControl 方法</span><span class="sxs-lookup"><span data-stu-id="4efcb-102">ICLRRuntimeHost::SetHostControl Method</span></span>
<span data-ttu-id="4efcb-103">设置公共语言运行时（CLR）可用于获取宿主的[IHostControl 接口](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)实现的接口指针。</span><span class="sxs-lookup"><span data-stu-id="4efcb-103">Sets the interface pointer that the common language runtime (CLR) can use to get the host's implementation of [IHostControl Interface](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4efcb-104">语法</span><span class="sxs-lookup"><span data-stu-id="4efcb-104">Syntax</span></span>  
  
```cpp  
HRESULT SetHostControl(  
    [in] IHostControl* pHostControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4efcb-105">参数</span><span class="sxs-lookup"><span data-stu-id="4efcb-105">Parameters</span></span>  
 `pHostControl`  
 <span data-ttu-id="4efcb-106">中指向主机的[IHostControl 接口](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)实现的接口指针。</span><span class="sxs-lookup"><span data-stu-id="4efcb-106">[in] An interface pointer to the host's implementation of [IHostControl Interface](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4efcb-107">返回值</span><span class="sxs-lookup"><span data-stu-id="4efcb-107">Return Value</span></span>  
  
|<span data-ttu-id="4efcb-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4efcb-108">HRESULT</span></span>|<span data-ttu-id="4efcb-109">描述</span><span class="sxs-lookup"><span data-stu-id="4efcb-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4efcb-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="4efcb-110">S_OK</span></span>|<span data-ttu-id="4efcb-111">`SetHostControl` 成功返回。</span><span class="sxs-lookup"><span data-stu-id="4efcb-111">`SetHostControl` returned successfully.</span></span>|  
|<span data-ttu-id="4efcb-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4efcb-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4efcb-113">CLR 未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="4efcb-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4efcb-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4efcb-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4efcb-115">调用超时。</span><span class="sxs-lookup"><span data-stu-id="4efcb-115">The call timed out.</span></span>|  
|<span data-ttu-id="4efcb-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4efcb-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4efcb-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="4efcb-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4efcb-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4efcb-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4efcb-119">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="4efcb-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4efcb-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4efcb-120">E_FAIL</span></span>|<span data-ttu-id="4efcb-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="4efcb-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4efcb-122">如果某个方法返回 E_FAIL，则 CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="4efcb-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4efcb-123">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="4efcb-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="4efcb-124">E_CLR_ALREADY_STARTED</span><span class="sxs-lookup"><span data-stu-id="4efcb-124">E_CLR_ALREADY_STARTED</span></span>|<span data-ttu-id="4efcb-125">CLR 已初始化。</span><span class="sxs-lookup"><span data-stu-id="4efcb-125">The CLR has already been initialized.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4efcb-126">备注</span><span class="sxs-lookup"><span data-stu-id="4efcb-126">Remarks</span></span>  
 <span data-ttu-id="4efcb-127">必须在初始化 CLR 之前调用 `SetHostControl`，即，在调用[Start 方法](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md)或使用任何[元数据接口](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)之前。</span><span class="sxs-lookup"><span data-stu-id="4efcb-127">You must call `SetHostControl` before the CLR is initialized, that is, before you call [Start Method](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) or use any of the [Metadata Interfaces](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md).</span></span> <span data-ttu-id="4efcb-128">建议在调用[CorBindToCurrentRuntime 函数](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)或[CorBindToRuntimeEx 函数](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)后立即调用 `SetHostControl`。</span><span class="sxs-lookup"><span data-stu-id="4efcb-128">It is recommended that you call `SetHostControl` immediately after calling [CorBindToCurrentRuntime Function](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md) or [CorBindToRuntimeEx Function](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4efcb-129">要求</span><span class="sxs-lookup"><span data-stu-id="4efcb-129">Requirements</span></span>  
 <span data-ttu-id="4efcb-130">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4efcb-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4efcb-131">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="4efcb-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4efcb-132">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="4efcb-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4efcb-133">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4efcb-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4efcb-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="4efcb-134">See also</span></span>

- [<span data-ttu-id="4efcb-135">ICLRRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="4efcb-135">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
- [<span data-ttu-id="4efcb-136">IHostControl 接口</span><span class="sxs-lookup"><span data-stu-id="4efcb-136">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
