---
title: "IHostCrst::TryEnter 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostCrst.TryEnter
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostCrst::TryEnter
helpviewer_keywords:
- IHostCrst::TryEnter method [.NET Framework hosting]
- TryEnter method [.NET Framework hosting]
ms.assetid: a922fa98-beab-4f09-a342-cc94fc65687f
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c6b622666c3bda806c77329d0d0a10726b4838c6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ihostcrsttryenter-method"></a><span data-ttu-id="459b3-102">IHostCrst::TryEnter 方法</span><span class="sxs-lookup"><span data-stu-id="459b3-102">IHostCrst::TryEnter Method</span></span>
<span data-ttu-id="459b3-103">尝试进入表示由当前的临界区[IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)实例。</span><span class="sxs-lookup"><span data-stu-id="459b3-103">Attempts to enter the critical section represented by the current [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="459b3-104">语法</span><span class="sxs-lookup"><span data-stu-id="459b3-104">Syntax</span></span>  
  
```  
HRESULT TryEnter (  
    [in]  DWORD  option,  
    [out] BOOL   *pbSucceeded  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="459b3-105">参数</span><span class="sxs-lookup"><span data-stu-id="459b3-105">Parameters</span></span>  
 `option`  
 <span data-ttu-id="459b3-106">[in]之一[WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md)值，指示主机时应采取什么操作的操作块。</span><span class="sxs-lookup"><span data-stu-id="459b3-106">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) values, indicating what action the host should take if the operation blocks.</span></span>  
  
 `pbSucceeded`  
 <span data-ttu-id="459b3-107">[out]`true`临界区可输入; 否则为如果`false`。</span><span class="sxs-lookup"><span data-stu-id="459b3-107">[out] `true` if the critical section can be entered; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="459b3-108">返回值</span><span class="sxs-lookup"><span data-stu-id="459b3-108">Return Value</span></span>  
  
|<span data-ttu-id="459b3-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="459b3-109">HRESULT</span></span>|<span data-ttu-id="459b3-110">描述</span><span class="sxs-lookup"><span data-stu-id="459b3-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="459b3-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="459b3-111">S_OK</span></span>|<span data-ttu-id="459b3-112">`TryEnter`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="459b3-112">`TryEnter` returned successfully.</span></span>|  
|<span data-ttu-id="459b3-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="459b3-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="459b3-114">公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="459b3-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="459b3-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="459b3-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="459b3-116">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="459b3-116">The call timed out.</span></span>|  
|<span data-ttu-id="459b3-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="459b3-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="459b3-118">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="459b3-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="459b3-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="459b3-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="459b3-120">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="459b3-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="459b3-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="459b3-121">E_FAIL</span></span>|<span data-ttu-id="459b3-122">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="459b3-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="459b3-123">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="459b3-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="459b3-124">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="459b3-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="459b3-125">备注</span><span class="sxs-lookup"><span data-stu-id="459b3-125">Remarks</span></span>  
 <span data-ttu-id="459b3-126">`TryEnter`将立即返回，该值指示调用线程是否进入临界区。</span><span class="sxs-lookup"><span data-stu-id="459b3-126">`TryEnter` returns immediately and indicates whether the calling thread entered the critical section.</span></span> <span data-ttu-id="459b3-127">此方法将镜像 Wind32`TryEnterCriticalSection`函数。</span><span class="sxs-lookup"><span data-stu-id="459b3-127">This method mirrors the Wind32 `TryEnterCriticalSection` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="459b3-128">要求</span><span class="sxs-lookup"><span data-stu-id="459b3-128">Requirements</span></span>  
 <span data-ttu-id="459b3-129">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="459b3-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="459b3-130">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="459b3-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="459b3-131">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="459b3-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="459b3-132">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="459b3-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="459b3-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="459b3-133">See Also</span></span>  
 [<span data-ttu-id="459b3-134">ICLRSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="459b3-134">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="459b3-135">IHostCrst 接口</span><span class="sxs-lookup"><span data-stu-id="459b3-135">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)  
 [<span data-ttu-id="459b3-136">IHostSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="459b3-136">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
