---
title: ICLRGCManager2::SetGCStartupLimitsEx 方法
ms.date: 03/30/2017
api_name:
- ICLRGCManager2.SetGCStartupLimitsEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRGCManager2::SetCLRGCStartupLimitsEx
helpviewer_keywords:
- ICLRGCManager2::SetGCStartupLimitsEx method [.NET Framework hosting]
- SetGCStartupLimitsEx method, ICLRGCManager2 interface [.NET Framework hosting]
ms.assetid: 6c3a08a9-5d65-48d4-8bbf-2a86ed7d356a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0d881c71d4725e1a73d743aa098aecc053182947
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918610"
---
# <a name="iclrgcmanager2setgcstartuplimitsex-method"></a><span data-ttu-id="30e8d-102">ICLRGCManager2::SetGCStartupLimitsEx 方法</span><span class="sxs-lookup"><span data-stu-id="30e8d-102">ICLRGCManager2::SetGCStartupLimitsEx Method</span></span>
<span data-ttu-id="30e8d-103">设置垃圾回收段的大小以及垃圾回收系统的第0代的最大大小。</span><span class="sxs-lookup"><span data-stu-id="30e8d-103">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30e8d-104">语法</span><span class="sxs-lookup"><span data-stu-id="30e8d-104">Syntax</span></span>  
  
```cpp  
HRESULT SetGCStartupLimitsEx (  
    [in] SIZE_T SegmentSize,   
    [in] SIZE_T MaxGen0Size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="30e8d-105">参数</span><span class="sxs-lookup"><span data-stu-id="30e8d-105">Parameters</span></span>  
 `SegmentSize`  
 <span data-ttu-id="30e8d-106">中垃圾收集段的指定大小。</span><span class="sxs-lookup"><span data-stu-id="30e8d-106">[in] The specified size of a garbage collection segment.</span></span>  
  
 <span data-ttu-id="30e8d-107">最小段大小为 4 MB。</span><span class="sxs-lookup"><span data-stu-id="30e8d-107">The minimum segment size is 4 MB.</span></span> <span data-ttu-id="30e8d-108">段可以增加 1 MB 或更大的增量。</span><span class="sxs-lookup"><span data-stu-id="30e8d-108">Segments can be increased in increments of 1 MB or larger.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="30e8d-109">中第0代的指定最大大小。</span><span class="sxs-lookup"><span data-stu-id="30e8d-109">[in] The specified maximum size for generation 0.</span></span>  
  
 <span data-ttu-id="30e8d-110">最小第0代大小为 64 KB。</span><span class="sxs-lookup"><span data-stu-id="30e8d-110">The minimum generation 0 size is 64 KB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="30e8d-111">返回值</span><span class="sxs-lookup"><span data-stu-id="30e8d-111">Return Value</span></span>  
  
|<span data-ttu-id="30e8d-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="30e8d-112">HRESULT</span></span>|<span data-ttu-id="30e8d-113">描述</span><span class="sxs-lookup"><span data-stu-id="30e8d-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="30e8d-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="30e8d-114">S_OK</span></span>|<span data-ttu-id="30e8d-115">`SetGCStartupLimitsEx`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="30e8d-115">`SetGCStartupLimitsEx` returned successfully.</span></span>|  
|<span data-ttu-id="30e8d-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="30e8d-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="30e8d-117">公共语言运行时 (CLR) 未加载到进程中, 或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="30e8d-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="30e8d-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="30e8d-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="30e8d-119">调用超时。</span><span class="sxs-lookup"><span data-stu-id="30e8d-119">The call timed out.</span></span>|  
|<span data-ttu-id="30e8d-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="30e8d-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="30e8d-121">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="30e8d-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="30e8d-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="30e8d-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="30e8d-123">已阻止的线程或纤程正在等待某个事件时, 该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="30e8d-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="30e8d-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="30e8d-124">E_FAIL</span></span>|<span data-ttu-id="30e8d-125">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="30e8d-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="30e8d-126">方法返回 E_FAIL 后, CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="30e8d-126">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="30e8d-127">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="30e8d-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="30e8d-128">备注</span><span class="sxs-lookup"><span data-stu-id="30e8d-128">Remarks</span></span>  
 <span data-ttu-id="30e8d-129">只能在启动`SetGCStartupLimitsEx`主机之前指定设置的值。</span><span class="sxs-lookup"><span data-stu-id="30e8d-129">The values that `SetGCStartupLimitsEx` sets can be specified only before the host is started.</span></span> <span data-ttu-id="30e8d-130">`SetGCStartupLimitsEx`将忽略以后对的调用。</span><span class="sxs-lookup"><span data-stu-id="30e8d-130">Later calls to `SetGCStartupLimitsEx` are ignored.</span></span>  
  
 <span data-ttu-id="30e8d-131">若要设置任一参数而不影响其他参数, 请为不想更改的参数指定 0 (零)。</span><span class="sxs-lookup"><span data-stu-id="30e8d-131">To set either parameter without affecting the other, specify 0 (zero) for the parameter you don't want to change.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30e8d-132">要求</span><span class="sxs-lookup"><span data-stu-id="30e8d-132">Requirements</span></span>  
 <span data-ttu-id="30e8d-133">**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="30e8d-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30e8d-134">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="30e8d-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="30e8d-135">**类库**作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="30e8d-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="30e8d-136">**.NET Framework 版本：** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30e8d-136">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30e8d-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="30e8d-137">See also</span></span>

- [<span data-ttu-id="30e8d-138">自动内存管理</span><span class="sxs-lookup"><span data-stu-id="30e8d-138">Automatic Memory Management</span></span>](../../../standard/automatic-memory-management.md)
- [<span data-ttu-id="30e8d-139">垃圾回收</span><span class="sxs-lookup"><span data-stu-id="30e8d-139">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)
- [<span data-ttu-id="30e8d-140">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="30e8d-140">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="30e8d-141">ICLRGCManager2 接口</span><span class="sxs-lookup"><span data-stu-id="30e8d-141">ICLRGCManager2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md)
