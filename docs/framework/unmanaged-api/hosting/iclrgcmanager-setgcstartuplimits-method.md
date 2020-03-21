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
ms.openlocfilehash: 645b64c8b536029663c350bdcde9a716a715aab3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178087"
---
# <a name="iclrgcmanagersetgcstartuplimits-method"></a><span data-ttu-id="88f0f-102">ICLRGCManager::SetGCStartupLimits 方法</span><span class="sxs-lookup"><span data-stu-id="88f0f-102">ICLRGCManager::SetGCStartupLimits Method</span></span>
<span data-ttu-id="88f0f-103">设置垃圾回收段的大小和垃圾回收系统第 0 代的最大大小。</span><span class="sxs-lookup"><span data-stu-id="88f0f-103">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="88f0f-104">从 .NET 框架 4.5 开始，可以将段大小和最大生成 0 大小设置为`DWORD`大于使用[ICLRGCManager2：：setGC 启动极限Ex](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md)方法的值。</span><span class="sxs-lookup"><span data-stu-id="88f0f-104">Starting with the .NET Framework 4.5, you can set segment size and maximum generation 0 size to values greater than `DWORD` by using the [ICLRGCManager2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88f0f-105">语法</span><span class="sxs-lookup"><span data-stu-id="88f0f-105">Syntax</span></span>  
  
```cpp  
HRESULT SetGCStartupLimits (  
    [in] DWORD SegmentSize,
    [in] DWORD MaxGen0Size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="88f0f-106">parameters</span><span class="sxs-lookup"><span data-stu-id="88f0f-106">Parameters</span></span>  
 `SegmentSize`  
 <span data-ttu-id="88f0f-107">[在]垃圾回收段的指定大小。</span><span class="sxs-lookup"><span data-stu-id="88f0f-107">[in] The specified size of a garbage collection segment.</span></span>  
  
 <span data-ttu-id="88f0f-108">最小段大小为 4 MB。</span><span class="sxs-lookup"><span data-stu-id="88f0f-108">The minimum segment size is 4 MB.</span></span> <span data-ttu-id="88f0f-109">段可以以 1 MB 或更大的增量增加。</span><span class="sxs-lookup"><span data-stu-id="88f0f-109">Segments can be increased in increments of 1 MB or larger.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="88f0f-110">[在]第 0 代的指定最大大小。</span><span class="sxs-lookup"><span data-stu-id="88f0f-110">[in] The specified maximum size for generation 0.</span></span>  
  
 <span data-ttu-id="88f0f-111">最小生成 0 大小为 64 KB。</span><span class="sxs-lookup"><span data-stu-id="88f0f-111">The minimum generation 0 size is 64 KB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="88f0f-112">返回值</span><span class="sxs-lookup"><span data-stu-id="88f0f-112">Return Value</span></span>  
  
|<span data-ttu-id="88f0f-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="88f0f-113">HRESULT</span></span>|<span data-ttu-id="88f0f-114">说明</span><span class="sxs-lookup"><span data-stu-id="88f0f-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="88f0f-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="88f0f-115">S_OK</span></span>|<span data-ttu-id="88f0f-116">`SetGCStartupLimits`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="88f0f-116">`SetGCStartupLimits` returned successfully.</span></span>|  
|<span data-ttu-id="88f0f-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="88f0f-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="88f0f-118">公共语言运行时 （CLR） 尚未加载到进程中，或者 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="88f0f-118">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="88f0f-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="88f0f-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="88f0f-120">呼叫超时。</span><span class="sxs-lookup"><span data-stu-id="88f0f-120">The call timed out.</span></span>|  
|<span data-ttu-id="88f0f-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="88f0f-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="88f0f-122">调用方不拥有锁。</span><span class="sxs-lookup"><span data-stu-id="88f0f-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="88f0f-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="88f0f-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="88f0f-124">当阻塞的线程或光纤等待事件时，事件已被取消。</span><span class="sxs-lookup"><span data-stu-id="88f0f-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="88f0f-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="88f0f-125">E_FAIL</span></span>|<span data-ttu-id="88f0f-126">发生了未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="88f0f-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="88f0f-127">方法返回E_FAIL后，CLR 在进程中不再可用。</span><span class="sxs-lookup"><span data-stu-id="88f0f-127">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="88f0f-128">对托管方法的后续调用返回HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="88f0f-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="88f0f-129">备注</span><span class="sxs-lookup"><span data-stu-id="88f0f-129">Remarks</span></span>  
 <span data-ttu-id="88f0f-130">只能指定一`SetGCStartupLimits`次设置的值。</span><span class="sxs-lookup"><span data-stu-id="88f0f-130">The values that `SetGCStartupLimits` sets can be specified only once.</span></span> <span data-ttu-id="88f0f-131">稍后将忽略对`SetGCStartupLimits`的调用。</span><span class="sxs-lookup"><span data-stu-id="88f0f-131">Later calls to `SetGCStartupLimits` are ignored.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="88f0f-132">要求</span><span class="sxs-lookup"><span data-stu-id="88f0f-132">Requirements</span></span>  
 <span data-ttu-id="88f0f-133">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="88f0f-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="88f0f-134">**标题：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="88f0f-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="88f0f-135">**库：** 作为资源包含在 MSCorEE.dll 中</span><span class="sxs-lookup"><span data-stu-id="88f0f-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="88f0f-136">**.NET 框架版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="88f0f-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88f0f-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="88f0f-137">See also</span></span>

- [<span data-ttu-id="88f0f-138">自动内存管理</span><span class="sxs-lookup"><span data-stu-id="88f0f-138">Automatic Memory Management</span></span>](../../../standard/automatic-memory-management.md)
- [<span data-ttu-id="88f0f-139">垃圾回收</span><span class="sxs-lookup"><span data-stu-id="88f0f-139">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)
- [<span data-ttu-id="88f0f-140">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="88f0f-140">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="88f0f-141">ICLRGCManager 接口</span><span class="sxs-lookup"><span data-stu-id="88f0f-141">ICLRGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)
