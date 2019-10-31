---
title: IHostManualEvent::Set 方法
ms.date: 03/30/2017
api_name:
- IHostManualEvent.Set
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostManualEvent::Set
helpviewer_keywords:
- Set method, IHostManualEvent interface [.NET Framework hosting]
- IHostManualEvent::Set method [.NET Framework hosting]
ms.assetid: e930c174-f71d-4faa-bb59-f0fb3df4d77b
topic_type:
- apiref
ms.openlocfilehash: 1114fc744ac1811585f2c5a94858b75eda00815c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136761"
---
# <a name="ihostmanualeventset-method"></a><span data-ttu-id="97db5-102">IHostManualEvent::Set 方法</span><span class="sxs-lookup"><span data-stu-id="97db5-102">IHostManualEvent::Set Method</span></span>
<span data-ttu-id="97db5-103">将当前的[IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)实例设置为终止状态。</span><span class="sxs-lookup"><span data-stu-id="97db5-103">Sets the current [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instance to a signaled state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97db5-104">语法</span><span class="sxs-lookup"><span data-stu-id="97db5-104">Syntax</span></span>  
  
```cpp  
HRESULT Set ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="97db5-105">返回值</span><span class="sxs-lookup"><span data-stu-id="97db5-105">Return Value</span></span>  
  
|<span data-ttu-id="97db5-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="97db5-106">HRESULT</span></span>|<span data-ttu-id="97db5-107">描述</span><span class="sxs-lookup"><span data-stu-id="97db5-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="97db5-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="97db5-108">S_OK</span></span>|<span data-ttu-id="97db5-109">`Set` 成功返回。</span><span class="sxs-lookup"><span data-stu-id="97db5-109">`Set` returned successfully.</span></span>|  
|<span data-ttu-id="97db5-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="97db5-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="97db5-111">公共语言运行时（CLR）未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="97db5-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="97db5-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="97db5-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="97db5-113">调用超时。</span><span class="sxs-lookup"><span data-stu-id="97db5-113">The call timed out.</span></span>|  
|<span data-ttu-id="97db5-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="97db5-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="97db5-115">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="97db5-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="97db5-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="97db5-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="97db5-117">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="97db5-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="97db5-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="97db5-118">E_FAIL</span></span>|<span data-ttu-id="97db5-119">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="97db5-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="97db5-120">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="97db5-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="97db5-121">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="97db5-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="97db5-122">要求</span><span class="sxs-lookup"><span data-stu-id="97db5-122">Requirements</span></span>  
 <span data-ttu-id="97db5-123">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="97db5-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="97db5-124">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="97db5-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="97db5-125">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="97db5-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="97db5-126">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="97db5-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97db5-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="97db5-127">See also</span></span>

- [<span data-ttu-id="97db5-128">ICLRSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="97db5-128">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="97db5-129">IHostAutoEvent 接口</span><span class="sxs-lookup"><span data-stu-id="97db5-129">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="97db5-130">IHostManualEvent 接口</span><span class="sxs-lookup"><span data-stu-id="97db5-130">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="97db5-131">IHostSemaphore 接口</span><span class="sxs-lookup"><span data-stu-id="97db5-131">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="97db5-132">IHostSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="97db5-132">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
