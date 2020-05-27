---
title: IHostManualEvent::Wait 方法
ms.date: 03/30/2017
api_name:
- IHostManualEvent.Wait
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostManualEvent::Wait
helpviewer_keywords:
- IHostManualEvent::Wait method [.NET Framework hosting]
- Wait method, IHostManualEvent interface [.NET Framework hosting]
ms.assetid: 1fbb7d8b-8a23-4c2b-8376-1a70cd2d6030
topic_type:
- apiref
ms.openlocfilehash: 6d0276764a07d5bb202d66b653fdf5cb96320c08
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804557"
---
# <a name="ihostmanualeventwait-method"></a><span data-ttu-id="893b6-102">IHostManualEvent::Wait 方法</span><span class="sxs-lookup"><span data-stu-id="893b6-102">IHostManualEvent::Wait Method</span></span>
<span data-ttu-id="893b6-103">导致当前[IHostManualEvent](ihostmanualevent-interface.md)实例等待，直到其拥有或经过指定的时间量。</span><span class="sxs-lookup"><span data-stu-id="893b6-103">Causes the current [IHostManualEvent](ihostmanualevent-interface.md) instance to wait until it is owned, or a specified amount of time elapses.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="893b6-104">语法</span><span class="sxs-lookup"><span data-stu-id="893b6-104">Syntax</span></span>  
  
```cpp  
HRESULT Wait (  
    [in] DWORD dwMilliseconds,  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="893b6-105">参数</span><span class="sxs-lookup"><span data-stu-id="893b6-105">Parameters</span></span>  
 `dwMilliseconds`  
 <span data-ttu-id="893b6-106">中如果当前实例不属于，则返回前等待的毫秒数 `IHostManualEvent` 。</span><span class="sxs-lookup"><span data-stu-id="893b6-106">[in] The number of milliseconds to wait before returning, if the current `IHostManualEvent` instance is not owned.</span></span>  
  
 `option`  
 <span data-ttu-id="893b6-107">中[WAIT_OPTION](wait-option-enumeration.md)值之一，指示当此操作阻止时宿主应执行的操作。</span><span class="sxs-lookup"><span data-stu-id="893b6-107">[in] One of the [WAIT_OPTION](wait-option-enumeration.md) values, indicating the action the host should take if this operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="893b6-108">返回值</span><span class="sxs-lookup"><span data-stu-id="893b6-108">Return Value</span></span>  
  
|<span data-ttu-id="893b6-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="893b6-109">HRESULT</span></span>|<span data-ttu-id="893b6-110">说明</span><span class="sxs-lookup"><span data-stu-id="893b6-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="893b6-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="893b6-111">S_OK</span></span>|<span data-ttu-id="893b6-112">`Wait`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="893b6-112">`Wait` returned successfully.</span></span>|  
|<span data-ttu-id="893b6-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="893b6-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="893b6-114">公共语言运行时（CLR）未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="893b6-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="893b6-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="893b6-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="893b6-116">调用超时。</span><span class="sxs-lookup"><span data-stu-id="893b6-116">The call timed out.</span></span>|  
|<span data-ttu-id="893b6-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="893b6-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="893b6-118">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="893b6-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="893b6-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="893b6-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="893b6-120">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="893b6-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="893b6-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="893b6-121">E_FAIL</span></span>|<span data-ttu-id="893b6-122">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="893b6-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="893b6-123">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="893b6-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="893b6-124">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="893b6-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="893b6-125">HOST_E_DEADLOCK</span><span class="sxs-lookup"><span data-stu-id="893b6-125">HOST_E_DEADLOCK</span></span>|<span data-ttu-id="893b6-126">主机在等待间隔期间检测到死锁，并选择当前 `IHostManualEvent` 实例作为死锁牺牲品。</span><span class="sxs-lookup"><span data-stu-id="893b6-126">The host detected a deadlock during the wait interval, and chose the current `IHostManualEvent` instance as the deadlock victim.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="893b6-127">要求</span><span class="sxs-lookup"><span data-stu-id="893b6-127">Requirements</span></span>  
 <span data-ttu-id="893b6-128">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="893b6-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="893b6-129">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="893b6-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="893b6-130">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="893b6-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="893b6-131">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="893b6-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="893b6-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="893b6-132">See also</span></span>

- [<span data-ttu-id="893b6-133">ICLRSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="893b6-133">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="893b6-134">IHostAutoEvent 接口</span><span class="sxs-lookup"><span data-stu-id="893b6-134">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)
- [<span data-ttu-id="893b6-135">IHostManualEvent 接口</span><span class="sxs-lookup"><span data-stu-id="893b6-135">IHostManualEvent Interface</span></span>](ihostmanualevent-interface.md)
- [<span data-ttu-id="893b6-136">IHostSemaphore 接口</span><span class="sxs-lookup"><span data-stu-id="893b6-136">IHostSemaphore Interface</span></span>](ihostsemaphore-interface.md)
- [<span data-ttu-id="893b6-137">IHostSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="893b6-137">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
