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
ms.openlocfilehash: b9c91a982a5f3d28b43a301f961601485639bb91
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59180623"
---
# <a name="ihostsyncmanagercreateautoevent-method"></a><span data-ttu-id="c8019-102">IHostSyncManager::CreateAutoEvent 方法</span><span class="sxs-lookup"><span data-stu-id="c8019-102">IHostSyncManager::CreateAutoEvent Method</span></span>
<span data-ttu-id="c8019-103">创建一个自动重置事件对象。</span><span class="sxs-lookup"><span data-stu-id="c8019-103">Creates an auto-reset event object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8019-104">语法</span><span class="sxs-lookup"><span data-stu-id="c8019-104">Syntax</span></span>  
  
```  
HRESULT CreateAutoEvent (  
    [out] IHostAutoEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c8019-105">参数</span><span class="sxs-lookup"><span data-stu-id="c8019-105">Parameters</span></span>  
 `ppEvent`  
 <span data-ttu-id="c8019-106">[out]指向的地址的指针[IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)实现的主机，或者，如果无法创建事件对象的实例。</span><span class="sxs-lookup"><span data-stu-id="c8019-106">[out] A pointer to the address of an [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) instance implemented by the host, or null if the event object could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c8019-107">返回值</span><span class="sxs-lookup"><span data-stu-id="c8019-107">Return Value</span></span>  
  
|<span data-ttu-id="c8019-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c8019-108">HRESULT</span></span>|<span data-ttu-id="c8019-109">描述</span><span class="sxs-lookup"><span data-stu-id="c8019-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c8019-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="c8019-110">S_OK</span></span>|`CreateAutoEvent` <span data-ttu-id="c8019-111">已成功返回。</span><span class="sxs-lookup"><span data-stu-id="c8019-111">returned successfully.</span></span>|  
|<span data-ttu-id="c8019-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c8019-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c8019-113">公共语言运行时 (CLR) 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="c8019-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c8019-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c8019-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c8019-115">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="c8019-115">The call timed out.</span></span>|  
|<span data-ttu-id="c8019-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c8019-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c8019-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="c8019-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c8019-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c8019-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c8019-119">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="c8019-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c8019-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c8019-120">E_FAIL</span></span>|<span data-ttu-id="c8019-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="c8019-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c8019-122">如果某方法返回 E_FAIL，CLR 不再在进程内可用。</span><span class="sxs-lookup"><span data-stu-id="c8019-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c8019-123">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="c8019-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="c8019-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="c8019-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="c8019-125">没有足够的内存是可用于创建请求的事件对象。</span><span class="sxs-lookup"><span data-stu-id="c8019-125">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c8019-126">备注</span><span class="sxs-lookup"><span data-stu-id="c8019-126">Remarks</span></span>  
 `CreateAutoEvent` <span data-ttu-id="c8019-127">创建其状态自动更改为非终止等待线程释放后的自动事件对象。</span><span class="sxs-lookup"><span data-stu-id="c8019-127">creates an auto-event object whose state is automatically changed to non-signaled after the waiting thread has been released.</span></span> <span data-ttu-id="c8019-128">此方法将镜像 Win32`CreateEvent`的值的函数`false`指定为`bManualReset`参数</span><span class="sxs-lookup"><span data-stu-id="c8019-128">This method mirrors the Win32 `CreateEvent` function with a value of `false` specified for the `bManualReset` parameter</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8019-129">要求</span><span class="sxs-lookup"><span data-stu-id="c8019-129">Requirements</span></span>  
 <span data-ttu-id="c8019-130">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c8019-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8019-131">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c8019-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c8019-132">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="c8019-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="c8019-133">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="c8019-133">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c8019-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="c8019-134">See also</span></span>

- [<span data-ttu-id="c8019-135">ICLRSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="c8019-135">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="c8019-136">IHostAutoEvent 接口</span><span class="sxs-lookup"><span data-stu-id="c8019-136">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="c8019-137">IHostControl 接口</span><span class="sxs-lookup"><span data-stu-id="c8019-137">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
- [<span data-ttu-id="c8019-138">IHostSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="c8019-138">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
