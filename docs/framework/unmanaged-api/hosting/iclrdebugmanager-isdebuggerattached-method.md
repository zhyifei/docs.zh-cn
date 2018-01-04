---
title: "ICLRDebugManager::IsDebuggerAttached 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDebugManager.IsDebuggerAttached
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRDebugManager::IsDebuggerAttached
helpviewer_keywords:
- IsDebuggerAttached method, ICLRDebugManager interface [.NET Framework hosting]
- ICLRDebugManager::IsDebuggerAttached method [.NET Framework hosting]
ms.assetid: 2f105fe0-f52d-49c5-bda5-583fb27e3aa6
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5abd854e224b19efa72100db0163d61b42b0b63c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iclrdebugmanagerisdebuggerattached-method"></a><span data-ttu-id="71847-102">ICLRDebugManager::IsDebuggerAttached 方法</span><span class="sxs-lookup"><span data-stu-id="71847-102">ICLRDebugManager::IsDebuggerAttached Method</span></span>
<span data-ttu-id="71847-103">获取一个值，它指示调试器是否已附加到进程。</span><span class="sxs-lookup"><span data-stu-id="71847-103">Gets a value that indicates whether a debugger is attached to the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71847-104">语法</span><span class="sxs-lookup"><span data-stu-id="71847-104">Syntax</span></span>  
  
```  
HRESULT IsDebuggerAttached (  
    [out] BOOL *pbAttached  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="71847-105">参数</span><span class="sxs-lookup"><span data-stu-id="71847-105">Parameters</span></span>  
 `pbAttached`  
 <span data-ttu-id="71847-106">[out]`true`如果调试程序附加到进程; 否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="71847-106">[out] `true` if a debugger is attached to the process; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="71847-107">返回值</span><span class="sxs-lookup"><span data-stu-id="71847-107">Return Value</span></span>  
  
|<span data-ttu-id="71847-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="71847-108">HRESULT</span></span>|<span data-ttu-id="71847-109">描述</span><span class="sxs-lookup"><span data-stu-id="71847-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="71847-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="71847-110">S_OK</span></span>|<span data-ttu-id="71847-111">`IsDebuggerAttached`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="71847-111">`IsDebuggerAttached` returned successfully.</span></span>|  
|<span data-ttu-id="71847-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="71847-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="71847-113">公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="71847-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="71847-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="71847-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="71847-115">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="71847-115">The call timed out.</span></span>|  
|<span data-ttu-id="71847-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="71847-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="71847-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="71847-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="71847-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="71847-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="71847-119">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="71847-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="71847-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="71847-120">E_FAIL</span></span>|<span data-ttu-id="71847-121">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="71847-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="71847-122">方法返回 E_FAIL 后，CLR 不再进程内中使用。</span><span class="sxs-lookup"><span data-stu-id="71847-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="71847-123">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="71847-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="71847-124">备注</span><span class="sxs-lookup"><span data-stu-id="71847-124">Remarks</span></span>  
 <span data-ttu-id="71847-125">`IsDebuggerAttached`允许宿主查询 CLR，以确定是否将调试器附加到进程。</span><span class="sxs-lookup"><span data-stu-id="71847-125">`IsDebuggerAttached` allows the host to query the CLR to determine whether a debugger is attached to the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71847-126">惠?</span><span class="sxs-lookup"><span data-stu-id="71847-126">Requirements</span></span>  
 <span data-ttu-id="71847-127">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="71847-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71847-128">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="71847-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="71847-129">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="71847-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="71847-130">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71847-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71847-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="71847-131">See Also</span></span>  
 [<span data-ttu-id="71847-132">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="71847-132">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="71847-133">ICLRDebugManager 接口</span><span class="sxs-lookup"><span data-stu-id="71847-133">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)  
 [<span data-ttu-id="71847-134">IHostControl 接口</span><span class="sxs-lookup"><span data-stu-id="71847-134">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
