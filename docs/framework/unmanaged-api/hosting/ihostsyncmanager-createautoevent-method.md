---
title: IHostSyncManager::CreateAutoEvent 方法
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateAutoEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateAutoEvent
helpviewer_keywords:
- IHostSyncManager::CreateAutoEvent method [.NET Framework hosting]
- CreateAutoEvent method [.NET Framework hosting]
ms.assetid: 3153643e-cf5c-4b44-8e0e-c2b22cb08208
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fe1b685f50f793f7451187f17adc848ec9d4422f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33440198"
---
# <a name="ihostsyncmanagercreateautoevent-method"></a><span data-ttu-id="cd7d4-102">IHostSyncManager::CreateAutoEvent 方法</span><span class="sxs-lookup"><span data-stu-id="cd7d4-102">IHostSyncManager::CreateAutoEvent Method</span></span>
<span data-ttu-id="cd7d4-103">创建一个自动重置事件对象。</span><span class="sxs-lookup"><span data-stu-id="cd7d4-103">Creates an auto-reset event object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd7d4-104">语法</span><span class="sxs-lookup"><span data-stu-id="cd7d4-104">Syntax</span></span>  
  
```  
HRESULT CreateAutoEvent (  
    [out] IHostAutoEvent **ppEvent  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cd7d4-105">参数</span><span class="sxs-lookup"><span data-stu-id="cd7d4-105">Parameters</span></span>  
 `ppEvent`  
 <span data-ttu-id="cd7d4-106">[out]指向的地址的指针[IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)实现的主机，或者，如果无法创建事件对象的实例。</span><span class="sxs-lookup"><span data-stu-id="cd7d4-106">[out] A pointer to the address of an [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) instance implemented by the host, or null if the event object could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cd7d4-107">返回值</span><span class="sxs-lookup"><span data-stu-id="cd7d4-107">Return Value</span></span>  
  
|<span data-ttu-id="cd7d4-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="cd7d4-108">HRESULT</span></span>|<span data-ttu-id="cd7d4-109">描述</span><span class="sxs-lookup"><span data-stu-id="cd7d4-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="cd7d4-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="cd7d4-110">S_OK</span></span>|<span data-ttu-id="cd7d4-111">`CreateAutoEvent` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="cd7d4-111">`CreateAutoEvent` returned successfully.</span></span>|  
|<span data-ttu-id="cd7d4-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="cd7d4-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="cd7d4-113">公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="cd7d4-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="cd7d4-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="cd7d4-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="cd7d4-115">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="cd7d4-115">The call timed out.</span></span>|  
|<span data-ttu-id="cd7d4-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="cd7d4-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="cd7d4-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="cd7d4-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="cd7d4-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="cd7d4-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="cd7d4-119">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="cd7d4-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="cd7d4-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="cd7d4-120">E_FAIL</span></span>|<span data-ttu-id="cd7d4-121">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="cd7d4-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="cd7d4-122">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="cd7d4-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="cd7d4-123">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="cd7d4-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="cd7d4-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="cd7d4-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="cd7d4-125">没有足够的内存已可用于创建请求的事件对象。</span><span class="sxs-lookup"><span data-stu-id="cd7d4-125">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cd7d4-126">备注</span><span class="sxs-lookup"><span data-stu-id="cd7d4-126">Remarks</span></span>  
 <span data-ttu-id="cd7d4-127">`CreateAutoEvent` 创建其状态自动更改为非终止后正在等待的线程已发布的自动事件对象。</span><span class="sxs-lookup"><span data-stu-id="cd7d4-127">`CreateAutoEvent` creates an auto-event object whose state is automatically changed to non-signaled after the waiting thread has been released.</span></span> <span data-ttu-id="cd7d4-128">此方法将镜像 Win32`CreateEvent`函数中使用的值`false`指定的`bManualReset`参数</span><span class="sxs-lookup"><span data-stu-id="cd7d4-128">This method mirrors the Win32 `CreateEvent` function with a value of `false` specified for the `bManualReset` parameter</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd7d4-129">要求</span><span class="sxs-lookup"><span data-stu-id="cd7d4-129">Requirements</span></span>  
 <span data-ttu-id="cd7d4-130">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="cd7d4-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd7d4-131">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="cd7d4-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cd7d4-132">**库：** 作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="cd7d4-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cd7d4-133">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd7d4-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd7d4-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="cd7d4-134">See Also</span></span>  
 [<span data-ttu-id="cd7d4-135">ICLRSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="cd7d4-135">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="cd7d4-136">IHostAutoEvent 接口</span><span class="sxs-lookup"><span data-stu-id="cd7d4-136">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 [<span data-ttu-id="cd7d4-137">IHostControl 接口</span><span class="sxs-lookup"><span data-stu-id="cd7d4-137">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)  
 [<span data-ttu-id="cd7d4-138">IHostSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="cd7d4-138">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
