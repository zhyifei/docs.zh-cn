---
title: ICLRGCManager::Collect 方法
ms.date: 03/30/2017
api_name:
- ICLRGCManager.Collect
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRGCManager::Collect
helpviewer_keywords:
- ICLRGCManager::Collect method [.NET Framework hosting]
- Collect method, ICLRGCManager interface [.NET Framework hosting]
ms.assetid: 0c6cbbea-c27c-4695-bda3-17c1910d8ddb
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6b9c3899c4319c623bc991d0775945f0a4dc09e6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33434750"
---
# <a name="iclrgcmanagercollect-method"></a><span data-ttu-id="e6c99-102">ICLRGCManager::Collect 方法</span><span class="sxs-lookup"><span data-stu-id="e6c99-102">ICLRGCManager::Collect Method</span></span>
<span data-ttu-id="e6c99-103">强制指定代的垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="e6c99-103">Forces a garbage collection for the specified generation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6c99-104">语法</span><span class="sxs-lookup"><span data-stu-id="e6c99-104">Syntax</span></span>  
  
```  
HRESULT Collect (  
    [in] LONG Generation  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e6c99-105">参数</span><span class="sxs-lookup"><span data-stu-id="e6c99-105">Parameters</span></span>  
 `Generation`  
 <span data-ttu-id="e6c99-106">[in]若要收集生成。</span><span class="sxs-lookup"><span data-stu-id="e6c99-106">[in] The generation to collect.</span></span> <span data-ttu-id="e6c99-107">值-1 强制对所有代回收。</span><span class="sxs-lookup"><span data-stu-id="e6c99-107">A value of -1 forces a collection of all generations.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e6c99-108">返回值</span><span class="sxs-lookup"><span data-stu-id="e6c99-108">Return Value</span></span>  
  
|<span data-ttu-id="e6c99-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e6c99-109">HRESULT</span></span>|<span data-ttu-id="e6c99-110">描述</span><span class="sxs-lookup"><span data-stu-id="e6c99-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e6c99-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="e6c99-111">S_OK</span></span>|<span data-ttu-id="e6c99-112">`Collect` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="e6c99-112">`Collect` returned successfully.</span></span>|  
|<span data-ttu-id="e6c99-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e6c99-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e6c99-114">公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="e6c99-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e6c99-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e6c99-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e6c99-116">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="e6c99-116">The call timed out.</span></span>|  
|<span data-ttu-id="e6c99-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e6c99-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e6c99-118">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="e6c99-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e6c99-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e6c99-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e6c99-120">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="e6c99-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e6c99-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e6c99-121">E_FAIL</span></span>|<span data-ttu-id="e6c99-122">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="e6c99-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e6c99-123">方法返回 E_FAIL 后，CLR 不再进程内中使用。</span><span class="sxs-lookup"><span data-stu-id="e6c99-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e6c99-124">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="e6c99-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e6c99-125">备注</span><span class="sxs-lookup"><span data-stu-id="e6c99-125">Remarks</span></span>  
 <span data-ttu-id="e6c99-126">`Collect`方法强制 CLR 垃圾回收器执行而不考虑其当前状态的集合。</span><span class="sxs-lookup"><span data-stu-id="e6c99-126">The `Collect` method forces the CLR's garbage collector to perform a collection regardless of its current state.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e6c99-127">要求</span><span class="sxs-lookup"><span data-stu-id="e6c99-127">Requirements</span></span>  
 <span data-ttu-id="e6c99-128">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e6c99-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6c99-129">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e6c99-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e6c99-130">**库：** 作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="e6c99-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e6c99-131">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6c99-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6c99-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="e6c99-132">See Also</span></span>  
 [<span data-ttu-id="e6c99-133">自动内存管理</span><span class="sxs-lookup"><span data-stu-id="e6c99-133">Automatic Memory Management</span></span>](../../../../docs/standard/automatic-memory-management.md)  
 [<span data-ttu-id="e6c99-134">垃圾回收</span><span class="sxs-lookup"><span data-stu-id="e6c99-134">Garbage Collection</span></span>](../../../../docs/standard/garbage-collection/index.md)  
 [<span data-ttu-id="e6c99-135">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="e6c99-135">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="e6c99-136">ICLRGCManager 接口</span><span class="sxs-lookup"><span data-stu-id="e6c99-136">ICLRGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)  
 [<span data-ttu-id="e6c99-137">CLR Hosting 接口</span><span class="sxs-lookup"><span data-stu-id="e6c99-137">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)  
 [<span data-ttu-id="e6c99-138">承载接口</span><span class="sxs-lookup"><span data-stu-id="e6c99-138">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="e6c99-139">承载</span><span class="sxs-lookup"><span data-stu-id="e6c99-139">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
