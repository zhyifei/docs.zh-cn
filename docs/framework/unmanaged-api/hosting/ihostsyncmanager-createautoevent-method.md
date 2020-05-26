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
ms.openlocfilehash: ba221beaa0edce49e75f75edddaee72e1beb9747
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/22/2020
ms.locfileid: "83803504"
---
# <a name="ihostsyncmanagercreateautoevent-method"></a><span data-ttu-id="9049c-102">IHostSyncManager::CreateAutoEvent 方法</span><span class="sxs-lookup"><span data-stu-id="9049c-102">IHostSyncManager::CreateAutoEvent Method</span></span>
<span data-ttu-id="9049c-103">创建自动重置事件对象。</span><span class="sxs-lookup"><span data-stu-id="9049c-103">Creates an auto-reset event object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9049c-104">语法</span><span class="sxs-lookup"><span data-stu-id="9049c-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateAutoEvent (  
    [out] IHostAutoEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9049c-105">参数</span><span class="sxs-lookup"><span data-stu-id="9049c-105">Parameters</span></span>  
 `ppEvent`  
 <span data-ttu-id="9049c-106">弄指向由主机实现的[IHostAutoEvent](ihostautoevent-interface.md)实例的地址的指针; 如果无法创建事件对象，则为 null。</span><span class="sxs-lookup"><span data-stu-id="9049c-106">[out] A pointer to the address of an [IHostAutoEvent](ihostautoevent-interface.md) instance implemented by the host, or null if the event object could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9049c-107">返回值</span><span class="sxs-lookup"><span data-stu-id="9049c-107">Return Value</span></span>  
  
|<span data-ttu-id="9049c-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9049c-108">HRESULT</span></span>|<span data-ttu-id="9049c-109">说明</span><span class="sxs-lookup"><span data-stu-id="9049c-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9049c-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="9049c-110">S_OK</span></span>|<span data-ttu-id="9049c-111">`CreateAutoEvent`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="9049c-111">`CreateAutoEvent` returned successfully.</span></span>|  
|<span data-ttu-id="9049c-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9049c-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9049c-113">公共语言运行时（CLR）未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="9049c-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9049c-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9049c-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9049c-115">调用超时。</span><span class="sxs-lookup"><span data-stu-id="9049c-115">The call timed out.</span></span>|  
|<span data-ttu-id="9049c-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9049c-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9049c-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="9049c-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9049c-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9049c-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9049c-119">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="9049c-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9049c-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9049c-120">E_FAIL</span></span>|<span data-ttu-id="9049c-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="9049c-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9049c-122">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="9049c-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9049c-123">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="9049c-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="9049c-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="9049c-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="9049c-125">没有足够的内存可用于创建请求的事件对象。</span><span class="sxs-lookup"><span data-stu-id="9049c-125">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9049c-126">备注</span><span class="sxs-lookup"><span data-stu-id="9049c-126">Remarks</span></span>  
 <span data-ttu-id="9049c-127">`CreateAutoEvent`创建自动事件对象，其状态将在释放等待线程后自动更改为非终止状态。</span><span class="sxs-lookup"><span data-stu-id="9049c-127">`CreateAutoEvent` creates an auto-event object whose state is automatically changed to non-signaled after the waiting thread has been released.</span></span> <span data-ttu-id="9049c-128">此方法 `CreateEvent` 使用 `false` 为参数指定的值镜像 Win32 函数 `bManualReset`</span><span class="sxs-lookup"><span data-stu-id="9049c-128">This method mirrors the Win32 `CreateEvent` function with a value of `false` specified for the `bManualReset` parameter</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9049c-129">要求</span><span class="sxs-lookup"><span data-stu-id="9049c-129">Requirements</span></span>  
 <span data-ttu-id="9049c-130">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9049c-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9049c-131">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="9049c-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9049c-132">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="9049c-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9049c-133">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9049c-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9049c-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9049c-134">See also</span></span>

- [<span data-ttu-id="9049c-135">ICLRSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="9049c-135">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="9049c-136">IHostAutoEvent 接口</span><span class="sxs-lookup"><span data-stu-id="9049c-136">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)
- [<span data-ttu-id="9049c-137">IHostControl 接口</span><span class="sxs-lookup"><span data-stu-id="9049c-137">IHostControl Interface</span></span>](ihostcontrol-interface.md)
- [<span data-ttu-id="9049c-138">IHostSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="9049c-138">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
