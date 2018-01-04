---
title: "IHostCrst::Leave 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostCrst.Leave
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostCrst::Leave
helpviewer_keywords:
- IHostCrst::Leave method [.NET Framework hosting]
- Leave method [.NET Framework hosting]
ms.assetid: dfc51d9e-b36d-4dba-9ea1-4f63fa0601ae
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 391aff3920e7ea2ef010ce7d97bdedb4e636dc86
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ihostcrstleave-method"></a><span data-ttu-id="483c4-102">IHostCrst::Leave 方法</span><span class="sxs-lookup"><span data-stu-id="483c4-102">IHostCrst::Leave Method</span></span>
<span data-ttu-id="483c4-103">离开临界区的当前实例所表示[IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)。</span><span class="sxs-lookup"><span data-stu-id="483c4-103">Leaves the critical section that is represented by the current instance of [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="483c4-104">语法</span><span class="sxs-lookup"><span data-stu-id="483c4-104">Syntax</span></span>  
  
```  
HRESULT Leave ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="483c4-105">返回值</span><span class="sxs-lookup"><span data-stu-id="483c4-105">Return Value</span></span>  
  
|<span data-ttu-id="483c4-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="483c4-106">HRESULT</span></span>|<span data-ttu-id="483c4-107">描述</span><span class="sxs-lookup"><span data-stu-id="483c4-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="483c4-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="483c4-108">S_OK</span></span>|<span data-ttu-id="483c4-109">`Leave`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="483c4-109">`Leave` returned successfully.</span></span>|  
|<span data-ttu-id="483c4-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="483c4-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="483c4-111">公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="483c4-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="483c4-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="483c4-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="483c4-113">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="483c4-113">The call timed out.</span></span>|  
|<span data-ttu-id="483c4-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="483c4-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="483c4-115">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="483c4-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="483c4-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="483c4-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="483c4-117">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="483c4-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="483c4-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="483c4-118">E_FAIL</span></span>|<span data-ttu-id="483c4-119">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="483c4-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="483c4-120">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="483c4-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="483c4-121">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="483c4-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="483c4-122">备注</span><span class="sxs-lookup"><span data-stu-id="483c4-122">Remarks</span></span>  
 <span data-ttu-id="483c4-123">`Leave`允许直接与主机的线程处理实现，而不是使用对应 Win32 通信 CLR`LeaveCriticalSection`函数。</span><span class="sxs-lookup"><span data-stu-id="483c4-123">`Leave` allows the CLR to communicate directly with the host's threading implementation, rather than using the corresponding Win32 `LeaveCriticalSection` function.</span></span> <span data-ttu-id="483c4-124">表示由当前的临界区的所有权的线程`IHostCrst`实例必须调用`Leave`后每次进入该关键部分。</span><span class="sxs-lookup"><span data-stu-id="483c4-124">A thread that takes ownership of the critical section represented by the current `IHostCrst` instance must call `Leave` once for each time it enters that critical section.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="483c4-125">惠?</span><span class="sxs-lookup"><span data-stu-id="483c4-125">Requirements</span></span>  
 <span data-ttu-id="483c4-126">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="483c4-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="483c4-127">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="483c4-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="483c4-128">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="483c4-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="483c4-129">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="483c4-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="483c4-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="483c4-130">See Also</span></span>  
 [<span data-ttu-id="483c4-131">ICLRSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="483c4-131">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="483c4-132">IHostCrst 接口</span><span class="sxs-lookup"><span data-stu-id="483c4-132">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)  
 [<span data-ttu-id="483c4-133">IHostSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="483c4-133">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
