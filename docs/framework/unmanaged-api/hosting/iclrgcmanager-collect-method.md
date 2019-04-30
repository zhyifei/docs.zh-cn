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
ms.openlocfilehash: 1746527a2667676dfeab89e72874204460bcd33c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61984719"
---
# <a name="iclrgcmanagercollect-method"></a><span data-ttu-id="54d83-102">ICLRGCManager::Collect 方法</span><span class="sxs-lookup"><span data-stu-id="54d83-102">ICLRGCManager::Collect Method</span></span>
<span data-ttu-id="54d83-103">强制对指定代进行垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="54d83-103">Forces a garbage collection for the specified generation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54d83-104">语法</span><span class="sxs-lookup"><span data-stu-id="54d83-104">Syntax</span></span>  
  
```  
HRESULT Collect (  
    [in] LONG Generation  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="54d83-105">参数</span><span class="sxs-lookup"><span data-stu-id="54d83-105">Parameters</span></span>  
 `Generation`  
 <span data-ttu-id="54d83-106">[in]若要收集的生成。</span><span class="sxs-lookup"><span data-stu-id="54d83-106">[in] The generation to collect.</span></span> <span data-ttu-id="54d83-107">值为-1 强制所有生成的集合。</span><span class="sxs-lookup"><span data-stu-id="54d83-107">A value of -1 forces a collection of all generations.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="54d83-108">返回值</span><span class="sxs-lookup"><span data-stu-id="54d83-108">Return Value</span></span>  
  
|<span data-ttu-id="54d83-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="54d83-109">HRESULT</span></span>|<span data-ttu-id="54d83-110">描述</span><span class="sxs-lookup"><span data-stu-id="54d83-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="54d83-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="54d83-111">S_OK</span></span>|<span data-ttu-id="54d83-112">`Collect` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="54d83-112">`Collect` returned successfully.</span></span>|  
|<span data-ttu-id="54d83-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="54d83-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="54d83-114">公共语言运行时 (CLR) 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="54d83-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="54d83-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="54d83-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="54d83-116">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="54d83-116">The call timed out.</span></span>|  
|<span data-ttu-id="54d83-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="54d83-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="54d83-118">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="54d83-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="54d83-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="54d83-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="54d83-120">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="54d83-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="54d83-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="54d83-121">E_FAIL</span></span>|<span data-ttu-id="54d83-122">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="54d83-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="54d83-123">方法返回 E_FAIL 后，CLR 不再在进程中使用。</span><span class="sxs-lookup"><span data-stu-id="54d83-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="54d83-124">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="54d83-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="54d83-125">备注</span><span class="sxs-lookup"><span data-stu-id="54d83-125">Remarks</span></span>  
 <span data-ttu-id="54d83-126">`Collect`方法强制 CLR 的垃圾回收器执行而不考虑其当前状态的集合。</span><span class="sxs-lookup"><span data-stu-id="54d83-126">The `Collect` method forces the CLR's garbage collector to perform a collection regardless of its current state.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="54d83-127">要求</span><span class="sxs-lookup"><span data-stu-id="54d83-127">Requirements</span></span>  
 <span data-ttu-id="54d83-128">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="54d83-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="54d83-129">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="54d83-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="54d83-130">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="54d83-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="54d83-131">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="54d83-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54d83-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="54d83-132">See also</span></span>

- [<span data-ttu-id="54d83-133">自动内存管理</span><span class="sxs-lookup"><span data-stu-id="54d83-133">Automatic Memory Management</span></span>](../../../../docs/standard/automatic-memory-management.md)
- [<span data-ttu-id="54d83-134">垃圾回收</span><span class="sxs-lookup"><span data-stu-id="54d83-134">Garbage Collection</span></span>](../../../../docs/standard/garbage-collection/index.md)
- [<span data-ttu-id="54d83-135">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="54d83-135">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="54d83-136">ICLRGCManager 接口</span><span class="sxs-lookup"><span data-stu-id="54d83-136">ICLRGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)
- [<span data-ttu-id="54d83-137">CLR Hosting 接口</span><span class="sxs-lookup"><span data-stu-id="54d83-137">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)
- [<span data-ttu-id="54d83-138">承载接口</span><span class="sxs-lookup"><span data-stu-id="54d83-138">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="54d83-139">承载</span><span class="sxs-lookup"><span data-stu-id="54d83-139">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
