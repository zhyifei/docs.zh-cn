---
title: ICLRGCManager::SetGCStartupLimits 方法
ms.date: 03/30/2017
api_name:
- ICLRGCManager.SetGCStartupLimits
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRGCManager::SetGCStartupLimits
helpviewer_keywords:
- SetGCStartupLimits method, ICLRGCManager interface [.NET Framework hosting]
- ICLRGCManager::SetGCStartupLimits method [.NET Framework hosting]
ms.assetid: 1c8d9959-95b5-4131-be4a-556d97774014
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 29311f00f5ac4b61380b57cdd9fda07ec7de1b23
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966204"
---
# <a name="iclrgcmanagersetgcstartuplimits-method"></a><span data-ttu-id="5a33e-102">ICLRGCManager::SetGCStartupLimits 方法</span><span class="sxs-lookup"><span data-stu-id="5a33e-102">ICLRGCManager::SetGCStartupLimits Method</span></span>
<span data-ttu-id="5a33e-103">设置垃圾回收段的大小以及垃圾回收系统的第0代的最大大小。</span><span class="sxs-lookup"><span data-stu-id="5a33e-103">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="5a33e-104">从 .NET Framework 4.5 开始, 可以使用[ICLRGCManager2:: SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md)方法将段大小和最大第 0 `DWORD`代大小设置为大于的值。</span><span class="sxs-lookup"><span data-stu-id="5a33e-104">Starting with the .NET Framework 4.5, you can set segment size and maximum generation 0 size to values greater than `DWORD` by using the [ICLRGCManager2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a33e-105">语法</span><span class="sxs-lookup"><span data-stu-id="5a33e-105">Syntax</span></span>  
  
```cpp  
HRESULT SetGCStartupLimits (  
    [in] DWORD SegmentSize,   
    [in] DWORD MaxGen0Size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5a33e-106">参数</span><span class="sxs-lookup"><span data-stu-id="5a33e-106">Parameters</span></span>  
 `SegmentSize`  
 <span data-ttu-id="5a33e-107">中垃圾收集段的指定大小。</span><span class="sxs-lookup"><span data-stu-id="5a33e-107">[in] The specified size of a garbage collection segment.</span></span>  
  
 <span data-ttu-id="5a33e-108">最小段大小为 4 MB。</span><span class="sxs-lookup"><span data-stu-id="5a33e-108">The minimum segment size is 4 MB.</span></span> <span data-ttu-id="5a33e-109">段可以增加 1 MB 或更大的增量。</span><span class="sxs-lookup"><span data-stu-id="5a33e-109">Segments can be increased in increments of 1 MB or larger.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="5a33e-110">中第0代的指定最大大小。</span><span class="sxs-lookup"><span data-stu-id="5a33e-110">[in] The specified maximum size for generation 0.</span></span>  
  
 <span data-ttu-id="5a33e-111">最小第0代大小为 64 KB。</span><span class="sxs-lookup"><span data-stu-id="5a33e-111">The minimum generation 0 size is 64 KB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5a33e-112">返回值</span><span class="sxs-lookup"><span data-stu-id="5a33e-112">Return Value</span></span>  
  
|<span data-ttu-id="5a33e-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5a33e-113">HRESULT</span></span>|<span data-ttu-id="5a33e-114">描述</span><span class="sxs-lookup"><span data-stu-id="5a33e-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5a33e-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="5a33e-115">S_OK</span></span>|<span data-ttu-id="5a33e-116">`SetGCStartupLimits`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="5a33e-116">`SetGCStartupLimits` returned successfully.</span></span>|  
|<span data-ttu-id="5a33e-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5a33e-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5a33e-118">公共语言运行时 (CLR) 未加载到进程中, 或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="5a33e-118">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5a33e-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5a33e-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5a33e-120">调用超时。</span><span class="sxs-lookup"><span data-stu-id="5a33e-120">The call timed out.</span></span>|  
|<span data-ttu-id="5a33e-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5a33e-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5a33e-122">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="5a33e-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5a33e-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5a33e-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5a33e-124">已阻止的线程或纤程正在等待某个事件时, 该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="5a33e-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5a33e-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5a33e-125">E_FAIL</span></span>|<span data-ttu-id="5a33e-126">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="5a33e-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5a33e-127">方法返回 E_FAIL 后, CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="5a33e-127">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5a33e-128">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="5a33e-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5a33e-129">备注</span><span class="sxs-lookup"><span data-stu-id="5a33e-129">Remarks</span></span>  
 <span data-ttu-id="5a33e-130">`SetGCStartupLimits`设置的值只能指定一次。</span><span class="sxs-lookup"><span data-stu-id="5a33e-130">The values that `SetGCStartupLimits` sets can be specified only once.</span></span> <span data-ttu-id="5a33e-131">`SetGCStartupLimits`将忽略以后对的调用。</span><span class="sxs-lookup"><span data-stu-id="5a33e-131">Later calls to `SetGCStartupLimits` are ignored.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a33e-132">要求</span><span class="sxs-lookup"><span data-stu-id="5a33e-132">Requirements</span></span>  
 <span data-ttu-id="5a33e-133">**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5a33e-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a33e-134">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5a33e-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5a33e-135">**类库**作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="5a33e-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5a33e-136">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a33e-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a33e-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="5a33e-137">See also</span></span>

- [<span data-ttu-id="5a33e-138">自动内存管理</span><span class="sxs-lookup"><span data-stu-id="5a33e-138">Automatic Memory Management</span></span>](../../../standard/automatic-memory-management.md)
- [<span data-ttu-id="5a33e-139">垃圾回收</span><span class="sxs-lookup"><span data-stu-id="5a33e-139">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)
- [<span data-ttu-id="5a33e-140">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="5a33e-140">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="5a33e-141">ICLRGCManager 接口</span><span class="sxs-lookup"><span data-stu-id="5a33e-141">ICLRGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)
