---
title: IHostTaskManager::CallNeedsHostHook 方法
ms.date: 03/30/2017
api_name:
- IHostTaskManager.CallNeedsHostHook
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::CallNeedsHostHook
helpviewer_keywords:
- CallNeedsHostHook method [.NET Framework hosting]
- IHostTaskManager::CallNeedsHostHook method [.NET Framework hosting]
ms.assetid: b60f1f59-9825-4b57-961f-d2979518e6a7
topic_type:
- apiref
ms.openlocfilehash: 5bc5752d4d2b772b1d18f438c4daaa1b8938da9e
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/26/2020
ms.locfileid: "83842343"
---
# <a name="ihosttaskmanagercallneedshosthook-method"></a><span data-ttu-id="2693c-102">IHostTaskManager::CallNeedsHostHook 方法</span><span class="sxs-lookup"><span data-stu-id="2693c-102">IHostTaskManager::CallNeedsHostHook Method</span></span>
<span data-ttu-id="2693c-103">使宿主可以指定公共语言运行时（CLR）是否可以将指定的调用内联到非托管函数。</span><span class="sxs-lookup"><span data-stu-id="2693c-103">Enables the host to specify whether the common language runtime (CLR) can inline the specified call to an unmanaged function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2693c-104">语法</span><span class="sxs-lookup"><span data-stu-id="2693c-104">Syntax</span></span>  
  
```cpp  
HRESULT CallNeedsHostHook (  
    [in]  SIZE_T target,
    [out] BOOL   *pbCallNeedsHostHook  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2693c-105">参数</span><span class="sxs-lookup"><span data-stu-id="2693c-105">Parameters</span></span>  
 `target`  
 <span data-ttu-id="2693c-106">中要调用的非托管函数的映射可移植可执行（PE）文件中的地址。</span><span class="sxs-lookup"><span data-stu-id="2693c-106">[in] The address within the mapped portable executable (PE) file of the unmanaged function that is to be called.</span></span>  
  
 `pbCallNeedsHostHook`  
 <span data-ttu-id="2693c-107">弄一个指向布尔值的指针，该布尔值指示宿主是否需要挂钩调用。</span><span class="sxs-lookup"><span data-stu-id="2693c-107">[out] A pointer to a Boolean value that indicates whether the host requires the call to be hooked.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2693c-108">返回值</span><span class="sxs-lookup"><span data-stu-id="2693c-108">Return Value</span></span>  
  
|<span data-ttu-id="2693c-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2693c-109">HRESULT</span></span>|<span data-ttu-id="2693c-110">说明</span><span class="sxs-lookup"><span data-stu-id="2693c-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2693c-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="2693c-111">S_OK</span></span>|<span data-ttu-id="2693c-112">`CallNeedsHostHook`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="2693c-112">`CallNeedsHostHook` returned successfully.</span></span>|  
|<span data-ttu-id="2693c-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2693c-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2693c-114">CLR 未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="2693c-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2693c-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2693c-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2693c-116">调用超时。</span><span class="sxs-lookup"><span data-stu-id="2693c-116">The call timed out.</span></span>|  
|<span data-ttu-id="2693c-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2693c-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2693c-118">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="2693c-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2693c-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2693c-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2693c-120">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="2693c-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2693c-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2693c-121">E_FAIL</span></span>|<span data-ttu-id="2693c-122">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="2693c-122">An unknown catastrophic failure has occurred.</span></span> <span data-ttu-id="2693c-123">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="2693c-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2693c-124">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="2693c-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2693c-125">备注</span><span class="sxs-lookup"><span data-stu-id="2693c-125">Remarks</span></span>  
 <span data-ttu-id="2693c-126">为了帮助优化代码执行，CLR 会在编译期间执行每个平台调用调用的分析，以确定是否可以内联调用。</span><span class="sxs-lookup"><span data-stu-id="2693c-126">To help optimize code execution, the CLR performs an analysis of each platform invoke call during compilation to determine whether the call can be inlined.</span></span> <span data-ttu-id="2693c-127">`CallNeedsHostHook`通过要求挂钩对非托管函数的调用，使宿主可以重写该决策。</span><span class="sxs-lookup"><span data-stu-id="2693c-127">`CallNeedsHostHook` enables the host to override that decision by requiring that a call to an unmanaged function be hooked.</span></span> <span data-ttu-id="2693c-128">如果主机需要挂钩，则运行时不会内联调用。</span><span class="sxs-lookup"><span data-stu-id="2693c-128">If the host requires a hook, the runtime does not inline the call.</span></span>  
  
 <span data-ttu-id="2693c-129">主机通常需要挂钩，要求在该挂钩上调整浮点状态，或在收到通知时调用进入状态，在该状态下，主机无法跟踪运行时的内存请求或所执行的任何锁。</span><span class="sxs-lookup"><span data-stu-id="2693c-129">The host typically would require a hook where it must adjust a floating-point state, or upon receiving notification that a call is entering a state where the host cannot track the runtime's requests for memory or any locks taken.</span></span> <span data-ttu-id="2693c-130">当宿主要求挂钩调用时，运行时将通过调用[EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md)、 [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md)、 [ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md)和[ReverseLeaveRuntime](ihosttaskmanager-reverseleaveruntime-method.md)，通知主机与托管代码之间的转换。</span><span class="sxs-lookup"><span data-stu-id="2693c-130">When the host requires that the call be hooked, the runtime notifies the host of transitions to and from managed code by using calls to [EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md), [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md), [ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md), and [ReverseLeaveRuntime](ihosttaskmanager-reverseleaveruntime-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2693c-131">要求</span><span class="sxs-lookup"><span data-stu-id="2693c-131">Requirements</span></span>  
 <span data-ttu-id="2693c-132">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2693c-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2693c-133">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="2693c-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2693c-134">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="2693c-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2693c-135">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2693c-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2693c-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2693c-136">See also</span></span>

- [<span data-ttu-id="2693c-137">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="2693c-137">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="2693c-138">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="2693c-138">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="2693c-139">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="2693c-139">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="2693c-140">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="2693c-140">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
