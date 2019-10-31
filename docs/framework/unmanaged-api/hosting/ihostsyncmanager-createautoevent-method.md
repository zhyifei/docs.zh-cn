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
ms.openlocfilehash: b3778e12dd96d4f4653633252e13469601c4879d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139436"
---
# <a name="ihostsyncmanagercreateautoevent-method"></a><span data-ttu-id="c9210-102">IHostSyncManager::CreateAutoEvent 方法</span><span class="sxs-lookup"><span data-stu-id="c9210-102">IHostSyncManager::CreateAutoEvent Method</span></span>
<span data-ttu-id="c9210-103">创建自动重置事件对象。</span><span class="sxs-lookup"><span data-stu-id="c9210-103">Creates an auto-reset event object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9210-104">语法</span><span class="sxs-lookup"><span data-stu-id="c9210-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateAutoEvent (  
    [out] IHostAutoEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c9210-105">参数</span><span class="sxs-lookup"><span data-stu-id="c9210-105">Parameters</span></span>  
 `ppEvent`  
 <span data-ttu-id="c9210-106">弄指向由主机实现的[IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)实例的地址的指针; 如果无法创建事件对象，则为 null。</span><span class="sxs-lookup"><span data-stu-id="c9210-106">[out] A pointer to the address of an [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) instance implemented by the host, or null if the event object could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c9210-107">返回值</span><span class="sxs-lookup"><span data-stu-id="c9210-107">Return Value</span></span>  
  
|<span data-ttu-id="c9210-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c9210-108">HRESULT</span></span>|<span data-ttu-id="c9210-109">描述</span><span class="sxs-lookup"><span data-stu-id="c9210-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c9210-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="c9210-110">S_OK</span></span>|<span data-ttu-id="c9210-111">`CreateAutoEvent` 成功返回。</span><span class="sxs-lookup"><span data-stu-id="c9210-111">`CreateAutoEvent` returned successfully.</span></span>|  
|<span data-ttu-id="c9210-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c9210-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c9210-113">公共语言运行时（CLR）未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="c9210-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c9210-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c9210-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c9210-115">调用超时。</span><span class="sxs-lookup"><span data-stu-id="c9210-115">The call timed out.</span></span>|  
|<span data-ttu-id="c9210-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c9210-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c9210-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="c9210-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c9210-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c9210-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c9210-119">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="c9210-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c9210-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c9210-120">E_FAIL</span></span>|<span data-ttu-id="c9210-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="c9210-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c9210-122">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="c9210-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c9210-123">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="c9210-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="c9210-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="c9210-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="c9210-125">没有足够的内存可用于创建请求的事件对象。</span><span class="sxs-lookup"><span data-stu-id="c9210-125">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c9210-126">备注</span><span class="sxs-lookup"><span data-stu-id="c9210-126">Remarks</span></span>  
 <span data-ttu-id="c9210-127">`CreateAutoEvent` 创建一个自动事件对象，其状态将在释放等待线程后自动更改为非终止状态。</span><span class="sxs-lookup"><span data-stu-id="c9210-127">`CreateAutoEvent` creates an auto-event object whose state is automatically changed to non-signaled after the waiting thread has been released.</span></span> <span data-ttu-id="c9210-128">此方法使用为 `bManualReset` 参数指定的 `false` 值来镜像 Win32 `CreateEvent` 函数</span><span class="sxs-lookup"><span data-stu-id="c9210-128">This method mirrors the Win32 `CreateEvent` function with a value of `false` specified for the `bManualReset` parameter</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c9210-129">要求</span><span class="sxs-lookup"><span data-stu-id="c9210-129">Requirements</span></span>  
 <span data-ttu-id="c9210-130">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c9210-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c9210-131">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="c9210-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c9210-132">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="c9210-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c9210-133">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c9210-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9210-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="c9210-134">See also</span></span>

- [<span data-ttu-id="c9210-135">ICLRSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="c9210-135">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="c9210-136">IHostAutoEvent 接口</span><span class="sxs-lookup"><span data-stu-id="c9210-136">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="c9210-137">IHostControl 接口</span><span class="sxs-lookup"><span data-stu-id="c9210-137">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
- [<span data-ttu-id="c9210-138">IHostSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="c9210-138">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
