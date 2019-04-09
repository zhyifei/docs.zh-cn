---
title: IHostSyncManager::CreateManualEvent 方法
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateManualEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateManualEvent
helpviewer_keywords:
- CreateManualEvent method [.NET Framework hosting]
- IHostSyncManager::CreateManualEvent method [.NET Framework hosting]
ms.assetid: 68661fbd-09cf-46dc-890b-e694f8a3880a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ada9a3131ea3063239ab7897d0096f0accbd0f94
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59137730"
---
# <a name="ihostsyncmanagercreatemanualevent-method"></a><span data-ttu-id="c1155-102">IHostSyncManager::CreateManualEvent 方法</span><span class="sxs-lookup"><span data-stu-id="c1155-102">IHostSyncManager::CreateManualEvent Method</span></span>
<span data-ttu-id="c1155-103">创建手动重置事件对象。</span><span class="sxs-lookup"><span data-stu-id="c1155-103">Creates a manual-reset event object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1155-104">语法</span><span class="sxs-lookup"><span data-stu-id="c1155-104">Syntax</span></span>  
  
```  
HRESULT CreateManualEvent (  
    [in]  BOOL bInitialState,  
    [out] IHostManualEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c1155-105">参数</span><span class="sxs-lookup"><span data-stu-id="c1155-105">Parameters</span></span>  
 `bInitialState`  
 <span data-ttu-id="c1155-106">[in]`true`，则对象是终止状态; 否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="c1155-106">[in] `true`, if the object is signaled; otherwise, `false`.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="c1155-107">[out]指向的地址的指针[IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)实例，或如果无法创建该事件则为 null。</span><span class="sxs-lookup"><span data-stu-id="c1155-107">[out] A pointer to the address of an [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instance, or null if the event could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c1155-108">返回值</span><span class="sxs-lookup"><span data-stu-id="c1155-108">Return Value</span></span>  
  
|<span data-ttu-id="c1155-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c1155-109">HRESULT</span></span>|<span data-ttu-id="c1155-110">描述</span><span class="sxs-lookup"><span data-stu-id="c1155-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c1155-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="c1155-111">S_OK</span></span>|`CreateManualEvent` <span data-ttu-id="c1155-112">已成功返回。</span><span class="sxs-lookup"><span data-stu-id="c1155-112">returned successfully.</span></span>|  
|<span data-ttu-id="c1155-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c1155-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c1155-114">公共语言运行时 (CLR) 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="c1155-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c1155-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c1155-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c1155-116">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="c1155-116">The call timed out.</span></span>|  
|<span data-ttu-id="c1155-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c1155-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c1155-118">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="c1155-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c1155-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c1155-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c1155-120">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="c1155-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c1155-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c1155-121">E_FAIL</span></span>|<span data-ttu-id="c1155-122">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="c1155-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c1155-123">如果某方法返回 E_FAIL，CLR 不再在进程内可用。</span><span class="sxs-lookup"><span data-stu-id="c1155-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c1155-124">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="c1155-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="c1155-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="c1155-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="c1155-126">没有足够的内存是可用于创建请求的事件对象。</span><span class="sxs-lookup"><span data-stu-id="c1155-126">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c1155-127">备注</span><span class="sxs-lookup"><span data-stu-id="c1155-127">Remarks</span></span>  
 `CreateManualEvent` <span data-ttu-id="c1155-128">创建`IHostManualEvent`，需要调用一个手动重置事件对象[ihostmanualevent:: Reset](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-reset-method.md)方法以将其设置为非终止状态。</span><span class="sxs-lookup"><span data-stu-id="c1155-128">creates an `IHostManualEvent`, a manual-reset event object that requires a call to the [IHostManualEvent::Reset](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-reset-method.md) method to set it to a non-signaled state.</span></span> `CreateManualEvent` <span data-ttu-id="c1155-129">镜像 Win32`CreateEvent`的值的函数`true`指定为`bManualReset`参数。</span><span class="sxs-lookup"><span data-stu-id="c1155-129">mirrors the Win32 `CreateEvent` function with a value of `true` specified for the `bManualReset` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c1155-130">要求</span><span class="sxs-lookup"><span data-stu-id="c1155-130">Requirements</span></span>  
 <span data-ttu-id="c1155-131">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c1155-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c1155-132">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c1155-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c1155-133">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="c1155-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="c1155-134">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="c1155-134">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c1155-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="c1155-135">See also</span></span>

- [<span data-ttu-id="c1155-136">ICLRSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="c1155-136">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="c1155-137">IHostManualEvent 接口</span><span class="sxs-lookup"><span data-stu-id="c1155-137">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="c1155-138">IHostSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="c1155-138">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
