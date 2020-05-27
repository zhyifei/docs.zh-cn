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
ms.openlocfilehash: 049a0ae6d860c7c431d08af8ba4539656b8e5592
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804576"
---
# <a name="ihostmanualeventreset-method"></a><span data-ttu-id="d1247-102">IHostManualEvent::Reset 方法</span><span class="sxs-lookup"><span data-stu-id="d1247-102">IHostManualEvent::Reset Method</span></span>
<span data-ttu-id="d1247-103">将当前[IHostManualEvent](ihostmanualevent-interface.md)实例重置为非终止状态。</span><span class="sxs-lookup"><span data-stu-id="d1247-103">Resets the current [IHostManualEvent](ihostmanualevent-interface.md) instance to a non-signaled state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1247-104">语法</span><span class="sxs-lookup"><span data-stu-id="d1247-104">Syntax</span></span>  
  
```cpp  
HRESULT Reset ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="d1247-105">返回值</span><span class="sxs-lookup"><span data-stu-id="d1247-105">Return Value</span></span>  
  
|<span data-ttu-id="d1247-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d1247-106">HRESULT</span></span>|<span data-ttu-id="d1247-107">说明</span><span class="sxs-lookup"><span data-stu-id="d1247-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d1247-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="d1247-108">S_OK</span></span>|<span data-ttu-id="d1247-109">`Reset`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="d1247-109">`Reset` returned successfully.</span></span>|  
|<span data-ttu-id="d1247-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d1247-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d1247-111">公共语言运行时（CLR）未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="d1247-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d1247-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d1247-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d1247-113">调用超时。</span><span class="sxs-lookup"><span data-stu-id="d1247-113">The call timed out.</span></span>|  
|<span data-ttu-id="d1247-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d1247-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d1247-115">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="d1247-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d1247-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d1247-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d1247-117">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="d1247-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d1247-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d1247-118">E_FAIL</span></span>|<span data-ttu-id="d1247-119">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="d1247-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d1247-120">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="d1247-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d1247-121">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="d1247-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d1247-122">要求</span><span class="sxs-lookup"><span data-stu-id="d1247-122">Requirements</span></span>  
 <span data-ttu-id="d1247-123">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d1247-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d1247-124">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="d1247-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d1247-125">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="d1247-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d1247-126">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d1247-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1247-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d1247-127">See also</span></span>

- [<span data-ttu-id="d1247-128">ICLRSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="d1247-128">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="d1247-129">IHostAutoEvent 接口</span><span class="sxs-lookup"><span data-stu-id="d1247-129">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)
- [<span data-ttu-id="d1247-130">IHostManualEvent 接口</span><span class="sxs-lookup"><span data-stu-id="d1247-130">IHostManualEvent Interface</span></span>](ihostmanualevent-interface.md)
- [<span data-ttu-id="d1247-131">IHostSemaphore 接口</span><span class="sxs-lookup"><span data-stu-id="d1247-131">IHostSemaphore Interface</span></span>](ihostsemaphore-interface.md)
- [<span data-ttu-id="d1247-132">IHostSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="d1247-132">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
