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
ms.openlocfilehash: f7426585045c7ae81377ec9bfca9d397d6f734cb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73192022"
---
# <a name="ihostsyncmanagercreatemonitorevent-method"></a><span data-ttu-id="6ea3a-102">IHostSyncManager::CreateMonitorEvent 方法</span><span class="sxs-lookup"><span data-stu-id="6ea3a-102">IHostSyncManager::CreateMonitorEvent Method</span></span>
<span data-ttu-id="6ea3a-103">创建监视的自动重置事件对象。</span><span class="sxs-lookup"><span data-stu-id="6ea3a-103">Creates a monitored auto-reset event object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ea3a-104">语法</span><span class="sxs-lookup"><span data-stu-id="6ea3a-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateMonitorEvent (  
    [in]  SIZE_T cookie,  
    [out] IHostAutoEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6ea3a-105">参数</span><span class="sxs-lookup"><span data-stu-id="6ea3a-105">Parameters</span></span>  
 `cookie`  
 <span data-ttu-id="6ea3a-106">中要与事件对象关联的 cookie。</span><span class="sxs-lookup"><span data-stu-id="6ea3a-106">[in] A cookie to associate with the event object.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="6ea3a-107">弄指向[IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)实例的地址的指针; 如果无法创建事件对象，则为 null。</span><span class="sxs-lookup"><span data-stu-id="6ea3a-107">[out] A pointer to the address of an [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) instance, or null if the event object could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6ea3a-108">返回值</span><span class="sxs-lookup"><span data-stu-id="6ea3a-108">Return Value</span></span>  
  
|<span data-ttu-id="6ea3a-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6ea3a-109">HRESULT</span></span>|<span data-ttu-id="6ea3a-110">描述</span><span class="sxs-lookup"><span data-stu-id="6ea3a-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6ea3a-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="6ea3a-111">S_OK</span></span>|<span data-ttu-id="6ea3a-112">`CreateMonitorEvent` 成功返回。</span><span class="sxs-lookup"><span data-stu-id="6ea3a-112">`CreateMonitorEvent` returned successfully.</span></span>|  
|<span data-ttu-id="6ea3a-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6ea3a-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6ea3a-114">公共语言运行时（CLR）未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="6ea3a-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="6ea3a-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="6ea3a-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="6ea3a-116">调用超时。</span><span class="sxs-lookup"><span data-stu-id="6ea3a-116">The call timed out.</span></span>|  
|<span data-ttu-id="6ea3a-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="6ea3a-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="6ea3a-118">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="6ea3a-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="6ea3a-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="6ea3a-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="6ea3a-120">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="6ea3a-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="6ea3a-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6ea3a-121">E_FAIL</span></span>|<span data-ttu-id="6ea3a-122">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="6ea3a-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="6ea3a-123">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="6ea3a-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="6ea3a-124">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="6ea3a-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="6ea3a-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="6ea3a-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="6ea3a-126">没有足够的内存可用于创建请求的事件对象。</span><span class="sxs-lookup"><span data-stu-id="6ea3a-126">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6ea3a-127">备注</span><span class="sxs-lookup"><span data-stu-id="6ea3a-127">Remarks</span></span>  
 <span data-ttu-id="6ea3a-128">`CreateMonitorEvent` 返回 CLR 在其托管 <xref:System.Threading.Monitor?displayProperty=nameWithType> 类型实现中使用的 `IHostAutoEvent`。</span><span class="sxs-lookup"><span data-stu-id="6ea3a-128">`CreateMonitorEvent` returns an `IHostAutoEvent` that the CLR uses in its implementation of the managed <xref:System.Threading.Monitor?displayProperty=nameWithType> type.</span></span> <span data-ttu-id="6ea3a-129">此方法会镜像 Win32 `CreateEvent` 函数，并为 `bManualReset` 参数指定 `false` 值。</span><span class="sxs-lookup"><span data-stu-id="6ea3a-129">This method mirrors the Win32 `CreateEvent` function, with a value of `false` specified for the `bManualReset` parameter.</span></span>  
  
 <span data-ttu-id="6ea3a-130">主机可以通过调用[ICLRSyncManager：： GetMonitorOwner](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-getmonitorowner-method.md)方法来使用 cookie 来确定在监视器上正在等待的任务。</span><span class="sxs-lookup"><span data-stu-id="6ea3a-130">The host can use the cookie to determine which task is waiting on the monitor by calling the [ICLRSyncManager::GetMonitorOwner](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-getmonitorowner-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6ea3a-131">要求</span><span class="sxs-lookup"><span data-stu-id="6ea3a-131">Requirements</span></span>  
 <span data-ttu-id="6ea3a-132">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6ea3a-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ea3a-133">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="6ea3a-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6ea3a-134">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="6ea3a-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6ea3a-135">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6ea3a-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ea3a-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="6ea3a-136">See also</span></span>

- [<span data-ttu-id="6ea3a-137">ICLRSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="6ea3a-137">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="6ea3a-138">IHostAutoEvent 接口</span><span class="sxs-lookup"><span data-stu-id="6ea3a-138">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="6ea3a-139">IHostSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="6ea3a-139">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
- <xref:System.Threading.Monitor>
