---
title: ICLRDebugManager::IsDebuggerAttached 方法
ms.date: 03/30/2017
api_name:
- ICLRDebugManager.IsDebuggerAttached
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDebugManager::IsDebuggerAttached
helpviewer_keywords:
- IsDebuggerAttached method, ICLRDebugManager interface [.NET Framework hosting]
- ICLRDebugManager::IsDebuggerAttached method [.NET Framework hosting]
ms.assetid: 2f105fe0-f52d-49c5-bda5-583fb27e3aa6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 404d60bf0dfb8de1d7effae01b22b15e8931757c
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57473937"
---
# <a name="iclrdebugmanagerisdebuggerattached-method"></a><span data-ttu-id="145c3-102">ICLRDebugManager::IsDebuggerAttached 方法</span><span class="sxs-lookup"><span data-stu-id="145c3-102">ICLRDebugManager::IsDebuggerAttached Method</span></span>
<span data-ttu-id="145c3-103">获取一个值，它指示调试器是否已附加到进程。</span><span class="sxs-lookup"><span data-stu-id="145c3-103">Gets a value that indicates whether a debugger is attached to the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="145c3-104">语法</span><span class="sxs-lookup"><span data-stu-id="145c3-104">Syntax</span></span>  
  
```  
HRESULT IsDebuggerAttached (  
    [out] BOOL *pbAttached  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="145c3-105">参数</span><span class="sxs-lookup"><span data-stu-id="145c3-105">Parameters</span></span>  
 `pbAttached`  
 <span data-ttu-id="145c3-106">[out]`true`如果调试器已附加到进程; 否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="145c3-106">[out] `true` if a debugger is attached to the process; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="145c3-107">返回值</span><span class="sxs-lookup"><span data-stu-id="145c3-107">Return Value</span></span>  
  
|<span data-ttu-id="145c3-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="145c3-108">HRESULT</span></span>|<span data-ttu-id="145c3-109">描述</span><span class="sxs-lookup"><span data-stu-id="145c3-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="145c3-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="145c3-110">S_OK</span></span>|<span data-ttu-id="145c3-111">`IsDebuggerAttached` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="145c3-111">`IsDebuggerAttached` returned successfully.</span></span>|  
|<span data-ttu-id="145c3-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="145c3-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="145c3-113">公共语言运行时 (CLR) 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="145c3-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="145c3-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="145c3-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="145c3-115">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="145c3-115">The call timed out.</span></span>|  
|<span data-ttu-id="145c3-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="145c3-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="145c3-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="145c3-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="145c3-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="145c3-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="145c3-119">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="145c3-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="145c3-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="145c3-120">E_FAIL</span></span>|<span data-ttu-id="145c3-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="145c3-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="145c3-122">方法返回 E_FAIL 后，CLR 不再在进程中使用。</span><span class="sxs-lookup"><span data-stu-id="145c3-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="145c3-123">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="145c3-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="145c3-124">备注</span><span class="sxs-lookup"><span data-stu-id="145c3-124">Remarks</span></span>  
 <span data-ttu-id="145c3-125">`IsDebuggerAttached` 使查询以确定是否将调试程序附加到进程的 CLR 的主机。</span><span class="sxs-lookup"><span data-stu-id="145c3-125">`IsDebuggerAttached` allows the host to query the CLR to determine whether a debugger is attached to the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="145c3-126">要求</span><span class="sxs-lookup"><span data-stu-id="145c3-126">Requirements</span></span>  
 <span data-ttu-id="145c3-127">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="145c3-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="145c3-128">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="145c3-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="145c3-129">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="145c3-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="145c3-130">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="145c3-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="145c3-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="145c3-131">See also</span></span>
- [<span data-ttu-id="145c3-132">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="145c3-132">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="145c3-133">ICLRDebugManager 接口</span><span class="sxs-lookup"><span data-stu-id="145c3-133">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)
- [<span data-ttu-id="145c3-134">IHostControl 接口</span><span class="sxs-lookup"><span data-stu-id="145c3-134">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
