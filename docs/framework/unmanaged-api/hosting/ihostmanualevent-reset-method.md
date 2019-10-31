---
title: IHostManualEvent::Reset 方法
ms.date: 03/30/2017
api_name:
- IHostManualEvent.Reset
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostManualEvent::Reset
helpviewer_keywords:
- Reset method, IHostManualEvent interface [.NET Framework hosting]
- IHostManualEvent::Reset method [.NET Framework hosting]
ms.assetid: 0d101168-b5e3-49ce-90c7-85cf2db83c4c
topic_type:
- apiref
ms.openlocfilehash: 464093291648d7c5c1f2001fbaef85fcd5d592de
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136805"
---
# <a name="ihostmanualeventreset-method"></a><span data-ttu-id="c5202-102">IHostManualEvent::Reset 方法</span><span class="sxs-lookup"><span data-stu-id="c5202-102">IHostManualEvent::Reset Method</span></span>
<span data-ttu-id="c5202-103">将当前[IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)实例重置为非终止状态。</span><span class="sxs-lookup"><span data-stu-id="c5202-103">Resets the current [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instance to a non-signaled state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5202-104">语法</span><span class="sxs-lookup"><span data-stu-id="c5202-104">Syntax</span></span>  
  
```cpp  
HRESULT Reset ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="c5202-105">返回值</span><span class="sxs-lookup"><span data-stu-id="c5202-105">Return Value</span></span>  
  
|<span data-ttu-id="c5202-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c5202-106">HRESULT</span></span>|<span data-ttu-id="c5202-107">描述</span><span class="sxs-lookup"><span data-stu-id="c5202-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c5202-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="c5202-108">S_OK</span></span>|<span data-ttu-id="c5202-109">`Reset` 成功返回。</span><span class="sxs-lookup"><span data-stu-id="c5202-109">`Reset` returned successfully.</span></span>|  
|<span data-ttu-id="c5202-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c5202-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c5202-111">公共语言运行时（CLR）未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="c5202-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c5202-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c5202-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c5202-113">调用超时。</span><span class="sxs-lookup"><span data-stu-id="c5202-113">The call timed out.</span></span>|  
|<span data-ttu-id="c5202-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c5202-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c5202-115">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="c5202-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c5202-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c5202-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c5202-117">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="c5202-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c5202-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c5202-118">E_FAIL</span></span>|<span data-ttu-id="c5202-119">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="c5202-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c5202-120">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="c5202-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c5202-121">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="c5202-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c5202-122">要求</span><span class="sxs-lookup"><span data-stu-id="c5202-122">Requirements</span></span>  
 <span data-ttu-id="c5202-123">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c5202-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c5202-124">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="c5202-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c5202-125">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="c5202-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c5202-126">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c5202-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5202-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="c5202-127">See also</span></span>

- [<span data-ttu-id="c5202-128">ICLRSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="c5202-128">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="c5202-129">IHostAutoEvent 接口</span><span class="sxs-lookup"><span data-stu-id="c5202-129">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="c5202-130">IHostManualEvent 接口</span><span class="sxs-lookup"><span data-stu-id="c5202-130">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="c5202-131">IHostSemaphore 接口</span><span class="sxs-lookup"><span data-stu-id="c5202-131">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="c5202-132">IHostSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="c5202-132">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
