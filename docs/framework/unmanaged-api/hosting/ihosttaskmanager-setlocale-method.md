---
title: IHostTaskManager::SetLocale 方法
ms.date: 03/30/2017
api_name:
- IHostTaskManager.SetLocale
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::SetLocale
helpviewer_keywords:
- SetLocale method, IHostTaskManager interface [.NET Framework hosting]
- IHostTaskManager::SetLocale method [.NET Framework hosting]
ms.assetid: 747ee407-ee8c-484d-9583-25089236d2d1
topic_type:
- apiref
ms.openlocfilehash: 841827017262b731fd5e6f6bd0b5862fecaf2744
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/26/2020
ms.locfileid: "83841719"
---
# <a name="ihosttaskmanagersetlocale-method"></a><span data-ttu-id="94e15-102">IHostTaskManager::SetLocale 方法</span><span class="sxs-lookup"><span data-stu-id="94e15-102">IHostTaskManager::SetLocale Method</span></span>
<span data-ttu-id="94e15-103">向宿主通知公共语言运行时（CLR）已更改当前正在执行的任务的区域设置或区域性。</span><span class="sxs-lookup"><span data-stu-id="94e15-103">Notifies the host that the common language runtime (CLR) has changed the locale, or culture, on the currently executing task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94e15-104">语法</span><span class="sxs-lookup"><span data-stu-id="94e15-104">Syntax</span></span>  
  
```cpp  
HRESULT SetLocale (  
    [in] LCID lcid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="94e15-105">参数</span><span class="sxs-lookup"><span data-stu-id="94e15-105">Parameters</span></span>  
 `lcid`  
 <span data-ttu-id="94e15-106">中映射到新分配的地理区域和语言的区域设置标识符值。</span><span class="sxs-lookup"><span data-stu-id="94e15-106">[in] The locale identifier value that maps to the newly assigned geographical culture and language.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="94e15-107">返回值</span><span class="sxs-lookup"><span data-stu-id="94e15-107">Return Value</span></span>  
  
|<span data-ttu-id="94e15-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="94e15-108">HRESULT</span></span>|<span data-ttu-id="94e15-109">说明</span><span class="sxs-lookup"><span data-stu-id="94e15-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="94e15-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="94e15-110">S_OK</span></span>|<span data-ttu-id="94e15-111">`SetLocale`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="94e15-111">`SetLocale` returned successfully.</span></span>|  
|<span data-ttu-id="94e15-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="94e15-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="94e15-113">CLR 未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="94e15-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="94e15-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="94e15-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="94e15-115">调用超时。</span><span class="sxs-lookup"><span data-stu-id="94e15-115">The call timed out.</span></span>|  
|<span data-ttu-id="94e15-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="94e15-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="94e15-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="94e15-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="94e15-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="94e15-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="94e15-119">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="94e15-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="94e15-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="94e15-120">E_FAIL</span></span>|<span data-ttu-id="94e15-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="94e15-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="94e15-122">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="94e15-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="94e15-123">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="94e15-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="94e15-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="94e15-124">E_NOTIMPL</span></span>|<span data-ttu-id="94e15-125">宿主不允许托管用户代码修改区域设置。</span><span class="sxs-lookup"><span data-stu-id="94e15-125">The host does not allow managed user code to modify the locale.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="94e15-126">备注</span><span class="sxs-lookup"><span data-stu-id="94e15-126">Remarks</span></span>  
 <span data-ttu-id="94e15-127">`SetLocale`当 <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType> 托管代码更改属性的值时，运行时调用。</span><span class="sxs-lookup"><span data-stu-id="94e15-127">The runtime calls `SetLocale` when the value of the <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType> property is changed by managed code.</span></span> <span data-ttu-id="94e15-128">此方法为主机提供了对区域设置同步所需的任何机制的机会。</span><span class="sxs-lookup"><span data-stu-id="94e15-128">This method provides an opportunity for the host to execute any mechanisms it might have for synchronization of locales.</span></span> <span data-ttu-id="94e15-129">如果主机不允许从托管代码更改区域设置，或未实现同步区域设置的机制，则它应从此方法返回 E_NOTIMPL。</span><span class="sxs-lookup"><span data-stu-id="94e15-129">If a host does not allow the locale to be changed from managed code, or does not implement a mechanism to synchronize locales, it should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="94e15-130">要求</span><span class="sxs-lookup"><span data-stu-id="94e15-130">Requirements</span></span>  
 <span data-ttu-id="94e15-131">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="94e15-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94e15-132">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="94e15-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="94e15-133">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="94e15-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="94e15-134">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94e15-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94e15-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="94e15-135">See also</span></span>

- [<span data-ttu-id="94e15-136">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="94e15-136">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="94e15-137">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="94e15-137">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="94e15-138">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="94e15-138">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="94e15-139">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="94e15-139">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
- [<span data-ttu-id="94e15-140">SetUILocale 方法</span><span class="sxs-lookup"><span data-stu-id="94e15-140">SetUILocale Method</span></span>](ihosttaskmanager-setuilocale-method.md)
