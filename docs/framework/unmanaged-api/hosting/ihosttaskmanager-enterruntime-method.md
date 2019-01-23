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
ms.openlocfilehash: 964e705376a404d3841a3d1de1f4d2a4d71ddfed
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54607090"
---
# <a name="ihosttaskmanagerenterruntime-method"></a><span data-ttu-id="e6f16-102">IHostTaskManager::EnterRuntime 方法</span><span class="sxs-lookup"><span data-stu-id="e6f16-102">IHostTaskManager::EnterRuntime Method</span></span>
<span data-ttu-id="e6f16-103">通知主机，对非托管方法的调用以便为平台调用方法，将执行控制返回到公共语言运行时 (CLR)。</span><span class="sxs-lookup"><span data-stu-id="e6f16-103">Notifies the host that a call to an unmanaged method, such as a platform invoke method, is returning execution control to the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6f16-104">语法</span><span class="sxs-lookup"><span data-stu-id="e6f16-104">Syntax</span></span>  
  
```  
HRESULT EnterRuntime ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="e6f16-105">返回值</span><span class="sxs-lookup"><span data-stu-id="e6f16-105">Return Value</span></span>  
  
|<span data-ttu-id="e6f16-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e6f16-106">HRESULT</span></span>|<span data-ttu-id="e6f16-107">描述</span><span class="sxs-lookup"><span data-stu-id="e6f16-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e6f16-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="e6f16-108">S_OK</span></span>|<span data-ttu-id="e6f16-109">`EnterRuntime` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="e6f16-109">`EnterRuntime` returned successfully.</span></span>|  
|<span data-ttu-id="e6f16-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e6f16-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e6f16-111">CLR 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="e6f16-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e6f16-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e6f16-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e6f16-113">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="e6f16-113">The call timed out.</span></span>|  
|<span data-ttu-id="e6f16-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e6f16-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e6f16-115">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="e6f16-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e6f16-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e6f16-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e6f16-117">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="e6f16-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e6f16-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e6f16-118">E_FAIL</span></span>|<span data-ttu-id="e6f16-119">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="e6f16-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e6f16-120">如果某方法返回 E_FAIL，CLR 不再在进程内可用。</span><span class="sxs-lookup"><span data-stu-id="e6f16-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e6f16-121">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="e6f16-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="e6f16-122">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="e6f16-122">E_OUTOFMEMORY</span></span>|<span data-ttu-id="e6f16-123">没有足够的内存是可用于完成请求的分配。</span><span class="sxs-lookup"><span data-stu-id="e6f16-123">Not enough memory was available to complete the requested allocation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e6f16-124">备注</span><span class="sxs-lookup"><span data-stu-id="e6f16-124">Remarks</span></span>  
 <span data-ttu-id="e6f16-125">`EnterRuntime` 调用以通知主机的非托管的函数，为其以前通过调用[LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md)方法进行、 已完成执行，以及将执行控制返回到运行时。</span><span class="sxs-lookup"><span data-stu-id="e6f16-125">`EnterRuntime` is called to notify the host that an unmanaged function, for which an earlier call to the [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md) method was made, has finished executing, and is returning execution control to the runtime.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e6f16-126">[ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md)调用以通知主机的非托管的函数，为其以前通过调用`LeaveRuntime`进行，正在调用非托管代码。</span><span class="sxs-lookup"><span data-stu-id="e6f16-126">[ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md) is called to notify the host that an unmanaged function, for which an earlier call to `LeaveRuntime` was made, is making a call into managed code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e6f16-127">要求</span><span class="sxs-lookup"><span data-stu-id="e6f16-127">Requirements</span></span>  
 <span data-ttu-id="e6f16-128">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e6f16-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6f16-129">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e6f16-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e6f16-130">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="e6f16-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e6f16-131">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6f16-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6f16-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="e6f16-132">See also</span></span>
- [<span data-ttu-id="e6f16-133">高级 COM 互操作性</span><span class="sxs-lookup"><span data-stu-id="e6f16-133">Advanced COM Interoperability</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bd9cdfyx)
- [<span data-ttu-id="e6f16-134">如何：使用 PInvoke 从托管代码调用本机 Dll</span><span class="sxs-lookup"><span data-stu-id="e6f16-134">How to: Call Native DLLs from Managed Code Using PInvoke</span></span>](/cpp/dotnet/how-to-call-native-dlls-from-managed-code-using-pinvoke)
- [<span data-ttu-id="e6f16-135">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="e6f16-135">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="e6f16-136">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="e6f16-136">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="e6f16-137">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="e6f16-137">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="e6f16-138">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="e6f16-138">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="e6f16-139">LeaveRuntime 方法</span><span class="sxs-lookup"><span data-stu-id="e6f16-139">LeaveRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md)
