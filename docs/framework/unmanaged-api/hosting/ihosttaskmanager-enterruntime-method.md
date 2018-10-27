---
title: IHostTaskManager::EnterRuntime 方法
ms.date: 03/30/2017
api_name:
- IHostTaskManager.EnterRuntime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::EnterRuntime
helpviewer_keywords:
- IHostTaskManager::EnterRuntime method [.NET Framework hosting]
- EnterRuntime method [.NET Framework hosting]
ms.assetid: 1aa7a4b1-636a-4f5e-b834-b406d72f7120
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f22ee94bf4594374071087fbbe93fc8e6a197a89
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2018
ms.locfileid: "50180947"
---
# <a name="ihosttaskmanagerenterruntime-method"></a><span data-ttu-id="08b41-102">IHostTaskManager::EnterRuntime 方法</span><span class="sxs-lookup"><span data-stu-id="08b41-102">IHostTaskManager::EnterRuntime Method</span></span>
<span data-ttu-id="08b41-103">通知主机，对非托管方法的调用以便为平台调用方法，将执行控制返回到公共语言运行时 (CLR)。</span><span class="sxs-lookup"><span data-stu-id="08b41-103">Notifies the host that a call to an unmanaged method, such as a platform invoke method, is returning execution control to the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08b41-104">语法</span><span class="sxs-lookup"><span data-stu-id="08b41-104">Syntax</span></span>  
  
```  
HRESULT EnterRuntime ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="08b41-105">返回值</span><span class="sxs-lookup"><span data-stu-id="08b41-105">Return Value</span></span>  
  
|<span data-ttu-id="08b41-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="08b41-106">HRESULT</span></span>|<span data-ttu-id="08b41-107">描述</span><span class="sxs-lookup"><span data-stu-id="08b41-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="08b41-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="08b41-108">S_OK</span></span>|<span data-ttu-id="08b41-109">`EnterRuntime` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="08b41-109">`EnterRuntime` returned successfully.</span></span>|  
|<span data-ttu-id="08b41-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="08b41-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="08b41-111">CLR 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="08b41-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="08b41-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="08b41-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="08b41-113">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="08b41-113">The call timed out.</span></span>|  
|<span data-ttu-id="08b41-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="08b41-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="08b41-115">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="08b41-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="08b41-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="08b41-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="08b41-117">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="08b41-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="08b41-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="08b41-118">E_FAIL</span></span>|<span data-ttu-id="08b41-119">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="08b41-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="08b41-120">如果某方法返回 E_FAIL，CLR 不再在进程内可用。</span><span class="sxs-lookup"><span data-stu-id="08b41-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="08b41-121">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="08b41-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="08b41-122">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="08b41-122">E_OUTOFMEMORY</span></span>|<span data-ttu-id="08b41-123">没有足够的内存是可用于完成请求的分配。</span><span class="sxs-lookup"><span data-stu-id="08b41-123">Not enough memory was available to complete the requested allocation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="08b41-124">备注</span><span class="sxs-lookup"><span data-stu-id="08b41-124">Remarks</span></span>  
 <span data-ttu-id="08b41-125">`EnterRuntime` 调用以通知主机的非托管的函数，为其以前通过调用[LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md)方法进行、 已完成执行，以及将执行控制返回到运行时。</span><span class="sxs-lookup"><span data-stu-id="08b41-125">`EnterRuntime` is called to notify the host that an unmanaged function, for which an earlier call to the [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md) method was made, has finished executing, and is returning execution control to the runtime.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="08b41-126">[ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md)调用以通知主机的非托管的函数，为其以前通过调用`LeaveRuntime`进行，正在调用非托管代码。</span><span class="sxs-lookup"><span data-stu-id="08b41-126">[ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md) is called to notify the host that an unmanaged function, for which an earlier call to `LeaveRuntime` was made, is making a call into managed code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08b41-127">要求</span><span class="sxs-lookup"><span data-stu-id="08b41-127">Requirements</span></span>  
 <span data-ttu-id="08b41-128">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="08b41-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08b41-129">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="08b41-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="08b41-130">**库：** 作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="08b41-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="08b41-131">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="08b41-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08b41-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="08b41-132">See Also</span></span>  
 [<span data-ttu-id="08b41-133">高级 COM 互操作性</span><span class="sxs-lookup"><span data-stu-id="08b41-133">Advanced COM Interoperability</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bd9cdfyx)  
 [<span data-ttu-id="08b41-134">如何：使用 PInvoke 从托管代码调用本机 DLL</span><span class="sxs-lookup"><span data-stu-id="08b41-134">How to: Call Native DLLs from Managed Code Using PInvoke</span></span>](/cpp/dotnet/how-to-call-native-dlls-from-managed-code-using-pinvoke)  
 [<span data-ttu-id="08b41-135">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="08b41-135">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="08b41-136">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="08b41-136">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="08b41-137">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="08b41-137">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="08b41-138">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="08b41-138">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="08b41-139">LeaveRuntime 方法</span><span class="sxs-lookup"><span data-stu-id="08b41-139">LeaveRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md)
