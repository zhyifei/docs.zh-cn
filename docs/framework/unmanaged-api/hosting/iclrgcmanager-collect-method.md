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
ms.openlocfilehash: aa906e314c408b7653e611b07d7ad21d4519b715
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616978"
---
# <a name="iclrgcmanagercollect-method"></a><span data-ttu-id="7e90d-102">ICLRGCManager::Collect 方法</span><span class="sxs-lookup"><span data-stu-id="7e90d-102">ICLRGCManager::Collect Method</span></span>
<span data-ttu-id="7e90d-103">强制执行指定代的垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="7e90d-103">Forces a garbage collection for the specified generation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e90d-104">语法</span><span class="sxs-lookup"><span data-stu-id="7e90d-104">Syntax</span></span>  
  
```cpp  
HRESULT Collect (  
    [in] LONG Generation  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7e90d-105">参数</span><span class="sxs-lookup"><span data-stu-id="7e90d-105">Parameters</span></span>  
 `Generation`  
 <span data-ttu-id="7e90d-106">中要收集的代。</span><span class="sxs-lookup"><span data-stu-id="7e90d-106">[in] The generation to collect.</span></span> <span data-ttu-id="7e90d-107">如果值为-1，则强制收集所有代。</span><span class="sxs-lookup"><span data-stu-id="7e90d-107">A value of -1 forces a collection of all generations.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7e90d-108">返回值</span><span class="sxs-lookup"><span data-stu-id="7e90d-108">Return Value</span></span>  
  
|<span data-ttu-id="7e90d-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7e90d-109">HRESULT</span></span>|<span data-ttu-id="7e90d-110">说明</span><span class="sxs-lookup"><span data-stu-id="7e90d-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7e90d-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="7e90d-111">S_OK</span></span>|<span data-ttu-id="7e90d-112">`Collect`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="7e90d-112">`Collect` returned successfully.</span></span>|  
|<span data-ttu-id="7e90d-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7e90d-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7e90d-114">公共语言运行时（CLR）未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="7e90d-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7e90d-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7e90d-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7e90d-116">调用超时。</span><span class="sxs-lookup"><span data-stu-id="7e90d-116">The call timed out.</span></span>|  
|<span data-ttu-id="7e90d-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7e90d-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7e90d-118">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="7e90d-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7e90d-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7e90d-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7e90d-120">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="7e90d-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7e90d-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7e90d-121">E_FAIL</span></span>|<span data-ttu-id="7e90d-122">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="7e90d-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7e90d-123">方法返回 E_FAIL 后，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="7e90d-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7e90d-124">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="7e90d-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7e90d-125">备注</span><span class="sxs-lookup"><span data-stu-id="7e90d-125">Remarks</span></span>  
 <span data-ttu-id="7e90d-126">`Collect`方法强制 CLR 的垃圾回收器执行集合，而不考虑其当前状态。</span><span class="sxs-lookup"><span data-stu-id="7e90d-126">The `Collect` method forces the CLR's garbage collector to perform a collection regardless of its current state.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7e90d-127">要求</span><span class="sxs-lookup"><span data-stu-id="7e90d-127">Requirements</span></span>  
 <span data-ttu-id="7e90d-128">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7e90d-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7e90d-129">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="7e90d-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7e90d-130">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="7e90d-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7e90d-131">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7e90d-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e90d-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7e90d-132">See also</span></span>

- [<span data-ttu-id="7e90d-133">自动内存管理</span><span class="sxs-lookup"><span data-stu-id="7e90d-133">Automatic Memory Management</span></span>](../../../standard/automatic-memory-management.md)
- [<span data-ttu-id="7e90d-134">垃圾回收</span><span class="sxs-lookup"><span data-stu-id="7e90d-134">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)
- [<span data-ttu-id="7e90d-135">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="7e90d-135">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="7e90d-136">ICLRGCManager 接口</span><span class="sxs-lookup"><span data-stu-id="7e90d-136">ICLRGCManager Interface</span></span>](iclrgcmanager-interface.md)
- [<span data-ttu-id="7e90d-137">CLR 承载接口</span><span class="sxs-lookup"><span data-stu-id="7e90d-137">CLR Hosting Interfaces</span></span>](clr-hosting-interfaces.md)
- [<span data-ttu-id="7e90d-138">承载接口</span><span class="sxs-lookup"><span data-stu-id="7e90d-138">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="7e90d-139">承载</span><span class="sxs-lookup"><span data-stu-id="7e90d-139">Hosting</span></span>](index.md)
