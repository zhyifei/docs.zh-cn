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
ms.openlocfilehash: 9885149a71147db6eef13958b8ef825caa1d6ec6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176378"
---
# <a name="iclrgcmanager2setgcstartuplimitsex-method"></a><span data-ttu-id="ddac2-102">ICLRGCManager2::SetGCStartupLimitsEx 方法</span><span class="sxs-lookup"><span data-stu-id="ddac2-102">ICLRGCManager2::SetGCStartupLimitsEx Method</span></span>
<span data-ttu-id="ddac2-103">设置垃圾回收段的大小和垃圾回收系统第 0 代的最大大小。</span><span class="sxs-lookup"><span data-stu-id="ddac2-103">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ddac2-104">语法</span><span class="sxs-lookup"><span data-stu-id="ddac2-104">Syntax</span></span>  
  
```cpp  
HRESULT SetGCStartupLimitsEx (  
    [in] SIZE_T SegmentSize,
    [in] SIZE_T MaxGen0Size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ddac2-105">parameters</span><span class="sxs-lookup"><span data-stu-id="ddac2-105">Parameters</span></span>  
 `SegmentSize`  
 <span data-ttu-id="ddac2-106">[在]垃圾回收段的指定大小。</span><span class="sxs-lookup"><span data-stu-id="ddac2-106">[in] The specified size of a garbage collection segment.</span></span>  
  
 <span data-ttu-id="ddac2-107">最小段大小为 4 MB。</span><span class="sxs-lookup"><span data-stu-id="ddac2-107">The minimum segment size is 4 MB.</span></span> <span data-ttu-id="ddac2-108">段可以以 1 MB 或更大的增量增加。</span><span class="sxs-lookup"><span data-stu-id="ddac2-108">Segments can be increased in increments of 1 MB or larger.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="ddac2-109">[在]第 0 代的指定最大大小。</span><span class="sxs-lookup"><span data-stu-id="ddac2-109">[in] The specified maximum size for generation 0.</span></span>  
  
 <span data-ttu-id="ddac2-110">最小生成 0 大小为 64 KB。</span><span class="sxs-lookup"><span data-stu-id="ddac2-110">The minimum generation 0 size is 64 KB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ddac2-111">返回值</span><span class="sxs-lookup"><span data-stu-id="ddac2-111">Return Value</span></span>  
  
|<span data-ttu-id="ddac2-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ddac2-112">HRESULT</span></span>|<span data-ttu-id="ddac2-113">说明</span><span class="sxs-lookup"><span data-stu-id="ddac2-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ddac2-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="ddac2-114">S_OK</span></span>|<span data-ttu-id="ddac2-115">`SetGCStartupLimitsEx`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="ddac2-115">`SetGCStartupLimitsEx` returned successfully.</span></span>|  
|<span data-ttu-id="ddac2-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ddac2-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ddac2-117">公共语言运行时 （CLR） 尚未加载到进程中，或者 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="ddac2-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ddac2-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ddac2-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ddac2-119">呼叫超时。</span><span class="sxs-lookup"><span data-stu-id="ddac2-119">The call timed out.</span></span>|  
|<span data-ttu-id="ddac2-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ddac2-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ddac2-121">调用方不拥有锁。</span><span class="sxs-lookup"><span data-stu-id="ddac2-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ddac2-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ddac2-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ddac2-123">当阻塞的线程或光纤等待事件时，事件已被取消。</span><span class="sxs-lookup"><span data-stu-id="ddac2-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ddac2-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ddac2-124">E_FAIL</span></span>|<span data-ttu-id="ddac2-125">发生了未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="ddac2-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ddac2-126">方法返回E_FAIL后，CLR 在进程中不再可用。</span><span class="sxs-lookup"><span data-stu-id="ddac2-126">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ddac2-127">对托管方法的后续调用返回HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="ddac2-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ddac2-128">备注</span><span class="sxs-lookup"><span data-stu-id="ddac2-128">Remarks</span></span>  
 <span data-ttu-id="ddac2-129">只能在启动主机`SetGCStartupLimitsEx`之前指定设置的值。</span><span class="sxs-lookup"><span data-stu-id="ddac2-129">The values that `SetGCStartupLimitsEx` sets can be specified only before the host is started.</span></span> <span data-ttu-id="ddac2-130">稍后将忽略对`SetGCStartupLimitsEx`的调用。</span><span class="sxs-lookup"><span data-stu-id="ddac2-130">Later calls to `SetGCStartupLimitsEx` are ignored.</span></span>  
  
 <span data-ttu-id="ddac2-131">要设置任一参数而不影响另一个参数，请为不想更改的参数指定 0（零）。</span><span class="sxs-lookup"><span data-stu-id="ddac2-131">To set either parameter without affecting the other, specify 0 (zero) for the parameter you don't want to change.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ddac2-132">要求</span><span class="sxs-lookup"><span data-stu-id="ddac2-132">Requirements</span></span>  
 <span data-ttu-id="ddac2-133">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ddac2-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ddac2-134">**标题：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ddac2-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ddac2-135">**库：** 作为资源包含在 MSCorEE.dll 中</span><span class="sxs-lookup"><span data-stu-id="ddac2-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ddac2-136">**.NET 框架版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ddac2-136">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ddac2-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ddac2-137">See also</span></span>

- [<span data-ttu-id="ddac2-138">自动内存管理</span><span class="sxs-lookup"><span data-stu-id="ddac2-138">Automatic Memory Management</span></span>](../../../standard/automatic-memory-management.md)
- [<span data-ttu-id="ddac2-139">垃圾回收</span><span class="sxs-lookup"><span data-stu-id="ddac2-139">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)
- [<span data-ttu-id="ddac2-140">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="ddac2-140">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="ddac2-141">ICLRGCManager2 接口</span><span class="sxs-lookup"><span data-stu-id="ddac2-141">ICLRGCManager2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md)
