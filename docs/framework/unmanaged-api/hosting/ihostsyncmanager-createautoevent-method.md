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
ms.openlocfilehash: ad704ff1e38d59df9e26d34b6dc62c40522aa728
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67753466"
---
# <a name="ihostsyncmanagercreateautoevent-method"></a><span data-ttu-id="08f05-102">IHostSyncManager::CreateAutoEvent 方法</span><span class="sxs-lookup"><span data-stu-id="08f05-102">IHostSyncManager::CreateAutoEvent Method</span></span>
<span data-ttu-id="08f05-103">创建一个自动重置事件对象。</span><span class="sxs-lookup"><span data-stu-id="08f05-103">Creates an auto-reset event object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08f05-104">语法</span><span class="sxs-lookup"><span data-stu-id="08f05-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateAutoEvent (  
    [out] IHostAutoEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="08f05-105">参数</span><span class="sxs-lookup"><span data-stu-id="08f05-105">Parameters</span></span>  
 `ppEvent`  
 <span data-ttu-id="08f05-106">[out]指向的地址的指针[IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)实现的主机，或者，如果无法创建事件对象的实例。</span><span class="sxs-lookup"><span data-stu-id="08f05-106">[out] A pointer to the address of an [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) instance implemented by the host, or null if the event object could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="08f05-107">返回值</span><span class="sxs-lookup"><span data-stu-id="08f05-107">Return Value</span></span>  
  
|<span data-ttu-id="08f05-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="08f05-108">HRESULT</span></span>|<span data-ttu-id="08f05-109">描述</span><span class="sxs-lookup"><span data-stu-id="08f05-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="08f05-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="08f05-110">S_OK</span></span>|<span data-ttu-id="08f05-111">`CreateAutoEvent` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="08f05-111">`CreateAutoEvent` returned successfully.</span></span>|  
|<span data-ttu-id="08f05-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="08f05-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="08f05-113">公共语言运行时 (CLR) 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="08f05-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="08f05-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="08f05-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="08f05-115">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="08f05-115">The call timed out.</span></span>|  
|<span data-ttu-id="08f05-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="08f05-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="08f05-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="08f05-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="08f05-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="08f05-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="08f05-119">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="08f05-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="08f05-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="08f05-120">E_FAIL</span></span>|<span data-ttu-id="08f05-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="08f05-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="08f05-122">如果某方法返回 E_FAIL，CLR 不再在进程内可用。</span><span class="sxs-lookup"><span data-stu-id="08f05-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="08f05-123">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="08f05-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="08f05-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="08f05-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="08f05-125">没有足够的内存是可用于创建请求的事件对象。</span><span class="sxs-lookup"><span data-stu-id="08f05-125">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="08f05-126">备注</span><span class="sxs-lookup"><span data-stu-id="08f05-126">Remarks</span></span>  
 <span data-ttu-id="08f05-127">`CreateAutoEvent` 创建其状态自动更改为非终止等待线程释放后的自动事件对象。</span><span class="sxs-lookup"><span data-stu-id="08f05-127">`CreateAutoEvent` creates an auto-event object whose state is automatically changed to non-signaled after the waiting thread has been released.</span></span> <span data-ttu-id="08f05-128">此方法将镜像 Win32`CreateEvent`的值的函数`false`指定为`bManualReset`参数</span><span class="sxs-lookup"><span data-stu-id="08f05-128">This method mirrors the Win32 `CreateEvent` function with a value of `false` specified for the `bManualReset` parameter</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08f05-129">要求</span><span class="sxs-lookup"><span data-stu-id="08f05-129">Requirements</span></span>  
 <span data-ttu-id="08f05-130">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="08f05-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08f05-131">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="08f05-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="08f05-132">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="08f05-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="08f05-133">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="08f05-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08f05-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="08f05-134">See also</span></span>

- [<span data-ttu-id="08f05-135">ICLRSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="08f05-135">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="08f05-136">IHostAutoEvent 接口</span><span class="sxs-lookup"><span data-stu-id="08f05-136">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="08f05-137">IHostControl 接口</span><span class="sxs-lookup"><span data-stu-id="08f05-137">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
- [<span data-ttu-id="08f05-138">IHostSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="08f05-138">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
