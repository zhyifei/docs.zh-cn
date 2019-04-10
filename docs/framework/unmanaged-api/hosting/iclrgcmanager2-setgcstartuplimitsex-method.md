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
ms.openlocfilehash: 6cba7b4a34835eb2f394aa71be8b907973cb1cd6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59204713"
---
# <a name="iclrgcmanager2setgcstartuplimitsex-method"></a><span data-ttu-id="86779-102">ICLRGCManager2::SetGCStartupLimitsEx 方法</span><span class="sxs-lookup"><span data-stu-id="86779-102">ICLRGCManager2::SetGCStartupLimitsEx Method</span></span>
<span data-ttu-id="86779-103">设置垃圾回收段的大小和第 0 代垃圾回收系统的最大大小。</span><span class="sxs-lookup"><span data-stu-id="86779-103">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86779-104">语法</span><span class="sxs-lookup"><span data-stu-id="86779-104">Syntax</span></span>  
  
```  
HRESULT SetGCStartupLimitsEx (  
    [in] SIZE_T SegmentSize,   
    [in] SIZE_T MaxGen0Size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="86779-105">参数</span><span class="sxs-lookup"><span data-stu-id="86779-105">Parameters</span></span>  
 `SegmentSize`  
 <span data-ttu-id="86779-106">[in]垃圾回收段指定的大小。</span><span class="sxs-lookup"><span data-stu-id="86779-106">[in] The specified size of a garbage collection segment.</span></span>  
  
 <span data-ttu-id="86779-107">最小的段大小为 4 MB。</span><span class="sxs-lookup"><span data-stu-id="86779-107">The minimum segment size is 4 MB.</span></span> <span data-ttu-id="86779-108">段可以增加增量为 1 MB 或更大。</span><span class="sxs-lookup"><span data-stu-id="86779-108">Segments can be increased in increments of 1 MB or larger.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="86779-109">[in]第 0 代为指定的最大大小。</span><span class="sxs-lookup"><span data-stu-id="86779-109">[in] The specified maximum size for generation 0.</span></span>  
  
 <span data-ttu-id="86779-110">最小的第 0 代大小为 64 KB。</span><span class="sxs-lookup"><span data-stu-id="86779-110">The minimum generation 0 size is 64 KB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="86779-111">返回值</span><span class="sxs-lookup"><span data-stu-id="86779-111">Return Value</span></span>  
  
|<span data-ttu-id="86779-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="86779-112">HRESULT</span></span>|<span data-ttu-id="86779-113">描述</span><span class="sxs-lookup"><span data-stu-id="86779-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="86779-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="86779-114">S_OK</span></span>|`SetGCStartupLimitsEx` <span data-ttu-id="86779-115">已成功返回。</span><span class="sxs-lookup"><span data-stu-id="86779-115">returned successfully.</span></span>|  
|<span data-ttu-id="86779-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="86779-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="86779-117">公共语言运行时 (CLR) 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="86779-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="86779-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="86779-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="86779-119">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="86779-119">The call timed out.</span></span>|  
|<span data-ttu-id="86779-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="86779-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="86779-121">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="86779-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="86779-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="86779-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="86779-123">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="86779-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="86779-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="86779-124">E_FAIL</span></span>|<span data-ttu-id="86779-125">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="86779-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="86779-126">方法返回 E_FAIL 后，CLR 不再在进程中使用。</span><span class="sxs-lookup"><span data-stu-id="86779-126">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="86779-127">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="86779-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="86779-128">备注</span><span class="sxs-lookup"><span data-stu-id="86779-128">Remarks</span></span>  
 <span data-ttu-id="86779-129">值的`SetGCStartupLimitsEx`只能在启动主机之前，可以指定集。</span><span class="sxs-lookup"><span data-stu-id="86779-129">The values that `SetGCStartupLimitsEx` sets can be specified only before the host is started.</span></span> <span data-ttu-id="86779-130">更高版本调用`SetGCStartupLimitsEx`将被忽略。</span><span class="sxs-lookup"><span data-stu-id="86779-130">Later calls to `SetGCStartupLimitsEx` are ignored.</span></span>  
  
 <span data-ttu-id="86779-131">若要设置而不会影响另两个参数中，你不想要更改的参数指定 0 （零）。</span><span class="sxs-lookup"><span data-stu-id="86779-131">To set either parameter without affecting the other, specify 0 (zero) for the parameter you don't want to change.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="86779-132">要求</span><span class="sxs-lookup"><span data-stu-id="86779-132">Requirements</span></span>  
 <span data-ttu-id="86779-133">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="86779-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="86779-134">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="86779-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="86779-135">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="86779-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="86779-136">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="86779-136">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="86779-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="86779-137">See also</span></span>

- [<span data-ttu-id="86779-138">自动内存管理</span><span class="sxs-lookup"><span data-stu-id="86779-138">Automatic Memory Management</span></span>](../../../../docs/standard/automatic-memory-management.md)
- [<span data-ttu-id="86779-139">垃圾回收</span><span class="sxs-lookup"><span data-stu-id="86779-139">Garbage Collection</span></span>](../../../../docs/standard/garbage-collection/index.md)
- [<span data-ttu-id="86779-140">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="86779-140">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="86779-141">ICLRGCManager2 接口</span><span class="sxs-lookup"><span data-stu-id="86779-141">ICLRGCManager2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md)
