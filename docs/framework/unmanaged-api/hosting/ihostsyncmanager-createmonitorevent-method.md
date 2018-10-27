---
title: IHostSyncManager::CreateMonitorEvent 方法
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateMonitorEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateMonitorEvent
helpviewer_keywords:
- CreateMonitorEvent method [.NET Framework hosting]
- IHostSyncManager::CreateMonitorEvent method [.NET Framework hosting]
ms.assetid: 524c7fd3-9b5c-46e7-99ba-555fd2fe33f0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b934816073a48936afca119895488ddf2f0e37d2
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2018
ms.locfileid: "50040155"
---
# <a name="ihostsyncmanagercreatemonitorevent-method"></a><span data-ttu-id="72018-102">IHostSyncManager::CreateMonitorEvent 方法</span><span class="sxs-lookup"><span data-stu-id="72018-102">IHostSyncManager::CreateMonitorEvent Method</span></span>
<span data-ttu-id="72018-103">创建一个受监视的自动重置事件对象。</span><span class="sxs-lookup"><span data-stu-id="72018-103">Creates a monitored auto-reset event object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72018-104">语法</span><span class="sxs-lookup"><span data-stu-id="72018-104">Syntax</span></span>  
  
```  
HRESULT CreateMonitorEvent (  
    [in]  SIZE_T cookie,  
    [out] IHostAutoEvent **ppEvent  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="72018-105">参数</span><span class="sxs-lookup"><span data-stu-id="72018-105">Parameters</span></span>  
 `cookie`  
 <span data-ttu-id="72018-106">[in]一个要与事件对象关联的 cookie。</span><span class="sxs-lookup"><span data-stu-id="72018-106">[in] A cookie to associate with the event object.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="72018-107">[out]指向的地址的指针[IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)实例，或如果无法创建事件对象，则为 null。</span><span class="sxs-lookup"><span data-stu-id="72018-107">[out] A pointer to the address of an [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) instance, or null if the event object could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="72018-108">返回值</span><span class="sxs-lookup"><span data-stu-id="72018-108">Return Value</span></span>  
  
|<span data-ttu-id="72018-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="72018-109">HRESULT</span></span>|<span data-ttu-id="72018-110">描述</span><span class="sxs-lookup"><span data-stu-id="72018-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="72018-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="72018-111">S_OK</span></span>|<span data-ttu-id="72018-112">`CreateMonitorEvent` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="72018-112">`CreateMonitorEvent` returned successfully.</span></span>|  
|<span data-ttu-id="72018-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="72018-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="72018-114">公共语言运行时 (CLR) 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="72018-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="72018-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="72018-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="72018-116">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="72018-116">The call timed out.</span></span>|  
|<span data-ttu-id="72018-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="72018-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="72018-118">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="72018-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="72018-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="72018-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="72018-120">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="72018-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="72018-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="72018-121">E_FAIL</span></span>|<span data-ttu-id="72018-122">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="72018-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="72018-123">如果某方法返回 E_FAIL，CLR 不再在进程内可用。</span><span class="sxs-lookup"><span data-stu-id="72018-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="72018-124">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="72018-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="72018-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="72018-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="72018-126">没有足够的内存是可用于创建请求的事件对象。</span><span class="sxs-lookup"><span data-stu-id="72018-126">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="72018-127">备注</span><span class="sxs-lookup"><span data-stu-id="72018-127">Remarks</span></span>  
 <span data-ttu-id="72018-128">`CreateMonitorEvent` 返回`IHostAutoEvent`CLR 用于在其实现的托管<xref:System.Threading.Monitor?displayProperty=nameWithType>类型。</span><span class="sxs-lookup"><span data-stu-id="72018-128">`CreateMonitorEvent` returns an `IHostAutoEvent` that the CLR uses in its implementation of the managed <xref:System.Threading.Monitor?displayProperty=nameWithType> type.</span></span> <span data-ttu-id="72018-129">此方法将镜像 Win32`CreateEvent`函数，值为`false`指定为`bManualReset`参数。</span><span class="sxs-lookup"><span data-stu-id="72018-129">This method mirrors the Win32 `CreateEvent` function, with a value of `false` specified for the `bManualReset` parameter.</span></span>  
  
 <span data-ttu-id="72018-130">主机可以使用 cookie 来确定哪些任务在监视器上等待通过调用[iclrsyncmanager:: Getmonitorowner](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-getmonitorowner-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="72018-130">The host can use the cookie to determine which task is waiting on the monitor by calling the [ICLRSyncManager::GetMonitorOwner](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-getmonitorowner-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72018-131">要求</span><span class="sxs-lookup"><span data-stu-id="72018-131">Requirements</span></span>  
 <span data-ttu-id="72018-132">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="72018-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72018-133">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="72018-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="72018-134">**库：** 作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="72018-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="72018-135">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="72018-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72018-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="72018-136">See Also</span></span>  
 [<span data-ttu-id="72018-137">ICLRSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="72018-137">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="72018-138">IHostAutoEvent 接口</span><span class="sxs-lookup"><span data-stu-id="72018-138">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 [<span data-ttu-id="72018-139">IHostSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="72018-139">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
 <xref:System.Threading.Monitor>
