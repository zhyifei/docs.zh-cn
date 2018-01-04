---
title: "ICLRGCManager2::SetGCStartupLimitsEx 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRGCManager2.SetGCStartupLimitsEx
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRGCManager2::SetCLRGCStartupLimitsEx
helpviewer_keywords:
- ICLRGCManager2::SetGCStartupLimitsEx method [.NET Framework hosting]
- SetGCStartupLimitsEx method, ICLRGCManager2 interface [.NET Framework hosting]
ms.assetid: 6c3a08a9-5d65-48d4-8bbf-2a86ed7d356a
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 371d6d32b3f9f5da0411234438972a8d2df4cc3b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iclrgcmanager2setgcstartuplimitsex-method"></a><span data-ttu-id="d48e0-102">ICLRGCManager2::SetGCStartupLimitsEx 方法</span><span class="sxs-lookup"><span data-stu-id="d48e0-102">ICLRGCManager2::SetGCStartupLimitsEx Method</span></span>
<span data-ttu-id="d48e0-103">设置的垃圾回收段的大小和第 0 代垃圾回收系统的最大大小。</span><span class="sxs-lookup"><span data-stu-id="d48e0-103">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d48e0-104">语法</span><span class="sxs-lookup"><span data-stu-id="d48e0-104">Syntax</span></span>  
  
```  
HRESULT SetGCStartupLimitsEx (  
    [in] SIZE_T SegmentSize,   
    [in] SIZE_T MaxGen0Size  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d48e0-105">参数</span><span class="sxs-lookup"><span data-stu-id="d48e0-105">Parameters</span></span>  
 `SegmentSize`  
 <span data-ttu-id="d48e0-106">[in]垃圾回收段指定的大小。</span><span class="sxs-lookup"><span data-stu-id="d48e0-106">[in] The specified size of a garbage collection segment.</span></span>  
  
 <span data-ttu-id="d48e0-107">最小的段大小为 4 MB。</span><span class="sxs-lookup"><span data-stu-id="d48e0-107">The minimum segment size is 4 MB.</span></span> <span data-ttu-id="d48e0-108">段可以增加增量为 1 MB 或更大。</span><span class="sxs-lookup"><span data-stu-id="d48e0-108">Segments can be increased in increments of 1 MB or larger.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="d48e0-109">[in]第 0 代指定最大大小。</span><span class="sxs-lookup"><span data-stu-id="d48e0-109">[in] The specified maximum size for generation 0.</span></span>  
  
 <span data-ttu-id="d48e0-110">最小的第 0 代大小为 64 KB。</span><span class="sxs-lookup"><span data-stu-id="d48e0-110">The minimum generation 0 size is 64 KB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d48e0-111">返回值</span><span class="sxs-lookup"><span data-stu-id="d48e0-111">Return Value</span></span>  
  
|<span data-ttu-id="d48e0-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d48e0-112">HRESULT</span></span>|<span data-ttu-id="d48e0-113">描述</span><span class="sxs-lookup"><span data-stu-id="d48e0-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d48e0-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="d48e0-114">S_OK</span></span>|<span data-ttu-id="d48e0-115">`SetGCStartupLimitsEx`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="d48e0-115">`SetGCStartupLimitsEx` returned successfully.</span></span>|  
|<span data-ttu-id="d48e0-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d48e0-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d48e0-117">公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="d48e0-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d48e0-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d48e0-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d48e0-119">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="d48e0-119">The call timed out.</span></span>|  
|<span data-ttu-id="d48e0-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d48e0-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d48e0-121">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="d48e0-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d48e0-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d48e0-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d48e0-123">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="d48e0-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d48e0-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d48e0-124">E_FAIL</span></span>|<span data-ttu-id="d48e0-125">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="d48e0-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d48e0-126">方法返回 E_FAIL 后，CLR 不再进程内中使用。</span><span class="sxs-lookup"><span data-stu-id="d48e0-126">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d48e0-127">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="d48e0-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d48e0-128">备注</span><span class="sxs-lookup"><span data-stu-id="d48e0-128">Remarks</span></span>  
 <span data-ttu-id="d48e0-129">值的`SetGCStartupLimitsEx`仅之前启动主机时，可以指定集。</span><span class="sxs-lookup"><span data-stu-id="d48e0-129">The values that `SetGCStartupLimitsEx` sets can be specified only before the host is started.</span></span> <span data-ttu-id="d48e0-130">更高版本调用`SetGCStartupLimitsEx`将被忽略。</span><span class="sxs-lookup"><span data-stu-id="d48e0-130">Later calls to `SetGCStartupLimitsEx` are ignored.</span></span>  
  
 <span data-ttu-id="d48e0-131">若要设置而不会影响另两个参数中，你不想要更改的参数指定 0 （零）。</span><span class="sxs-lookup"><span data-stu-id="d48e0-131">To set either parameter without affecting the other, specify 0 (zero) for the parameter you don't want to change.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d48e0-132">惠?</span><span class="sxs-lookup"><span data-stu-id="d48e0-132">Requirements</span></span>  
 <span data-ttu-id="d48e0-133">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d48e0-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d48e0-134">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d48e0-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d48e0-135">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="d48e0-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d48e0-136">**.NET framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d48e0-136">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d48e0-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="d48e0-137">See Also</span></span>  
 [<span data-ttu-id="d48e0-138">自动内存管理</span><span class="sxs-lookup"><span data-stu-id="d48e0-138">Automatic Memory Management</span></span>](../../../../docs/standard/automatic-memory-management.md)  
 [<span data-ttu-id="d48e0-139">垃圾回收</span><span class="sxs-lookup"><span data-stu-id="d48e0-139">Garbage Collection</span></span>](../../../../docs/standard/garbage-collection/index.md)  
 [<span data-ttu-id="d48e0-140">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="d48e0-140">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="d48e0-141">ICLRGCManager2 接口</span><span class="sxs-lookup"><span data-stu-id="d48e0-141">ICLRGCManager2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md)
