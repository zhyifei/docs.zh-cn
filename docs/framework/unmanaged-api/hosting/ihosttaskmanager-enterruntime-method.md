---
title: "IHostTaskManager::EnterRuntime 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostTaskManager.EnterRuntime
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostTaskManager::EnterRuntime
helpviewer_keywords:
- IHostTaskManager::EnterRuntime method [.NET Framework hosting]
- EnterRuntime method [.NET Framework hosting]
ms.assetid: 1aa7a4b1-636a-4f5e-b834-b406d72f7120
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0617ce6960c5afbdad77c28de8284531ae976f3b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ihosttaskmanagerenterruntime-method"></a><span data-ttu-id="e4000-102">IHostTaskManager::EnterRuntime 方法</span><span class="sxs-lookup"><span data-stu-id="e4000-102">IHostTaskManager::EnterRuntime Method</span></span>
<span data-ttu-id="e4000-103">通知主机的调用非托管方法，如平台调用方法，是执行将控制返回到公共语言运行时 (CLR)。</span><span class="sxs-lookup"><span data-stu-id="e4000-103">Notifies the host that a call to an unmanaged method, such as a platform invoke method, is returning execution control to the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4000-104">语法</span><span class="sxs-lookup"><span data-stu-id="e4000-104">Syntax</span></span>  
  
```  
HRESULT EnterRuntime ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="e4000-105">返回值</span><span class="sxs-lookup"><span data-stu-id="e4000-105">Return Value</span></span>  
  
|<span data-ttu-id="e4000-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e4000-106">HRESULT</span></span>|<span data-ttu-id="e4000-107">描述</span><span class="sxs-lookup"><span data-stu-id="e4000-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e4000-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="e4000-108">S_OK</span></span>|<span data-ttu-id="e4000-109">`EnterRuntime`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="e4000-109">`EnterRuntime` returned successfully.</span></span>|  
|<span data-ttu-id="e4000-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e4000-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e4000-111">CLR 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="e4000-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e4000-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e4000-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e4000-113">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="e4000-113">The call timed out.</span></span>|  
|<span data-ttu-id="e4000-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e4000-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e4000-115">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="e4000-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e4000-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e4000-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e4000-117">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="e4000-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e4000-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e4000-118">E_FAIL</span></span>|<span data-ttu-id="e4000-119">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="e4000-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e4000-120">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="e4000-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e4000-121">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="e4000-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="e4000-122">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="e4000-122">E_OUTOFMEMORY</span></span>|<span data-ttu-id="e4000-123">没有足够的内存的可用，无法完成请求的分配。</span><span class="sxs-lookup"><span data-stu-id="e4000-123">Not enough memory was available to complete the requested allocation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e4000-124">备注</span><span class="sxs-lookup"><span data-stu-id="e4000-124">Remarks</span></span>  
 <span data-ttu-id="e4000-125">`EnterRuntime`调用以通知主机的非托管的函数，为其以前调用[LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md)方法而进行、 已完成执行，并且正在将执行控制权返回给运行时。</span><span class="sxs-lookup"><span data-stu-id="e4000-125">`EnterRuntime` is called to notify the host that an unmanaged function, for which an earlier call to the [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md) method was made, has finished executing, and is returning execution control to the runtime.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e4000-126">[ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md)调用以通知主机的非托管的函数，为其以前调用`LeaveRuntime`进行，正在调用非托管代码。</span><span class="sxs-lookup"><span data-stu-id="e4000-126">[ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md) is called to notify the host that an unmanaged function, for which an earlier call to `LeaveRuntime` was made, is making a call into managed code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e4000-127">惠?</span><span class="sxs-lookup"><span data-stu-id="e4000-127">Requirements</span></span>  
 <span data-ttu-id="e4000-128">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e4000-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e4000-129">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e4000-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e4000-130">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="e4000-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e4000-131">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e4000-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4000-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="e4000-132">See Also</span></span>  
 [<span data-ttu-id="e4000-133">高级 COM 互操作性</span><span class="sxs-lookup"><span data-stu-id="e4000-133">Advanced COM Interoperability</span></span>](http://msdn.microsoft.com/en-us/3ada36e5-2390-4d70-b490-6ad8de92f2fb)  
 [<span data-ttu-id="e4000-134">如何：使用 PInvoke 从托管代码调用本机 DLL</span><span class="sxs-lookup"><span data-stu-id="e4000-134">How to: Call Native DLLs from Managed Code Using PInvoke</span></span>](/cpp/dotnet/how-to-call-native-dlls-from-managed-code-using-pinvoke)  
 [<span data-ttu-id="e4000-135">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="e4000-135">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="e4000-136">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="e4000-136">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="e4000-137">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="e4000-137">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="e4000-138">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="e4000-138">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="e4000-139">LeaveRuntime 方法</span><span class="sxs-lookup"><span data-stu-id="e4000-139">LeaveRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md)
