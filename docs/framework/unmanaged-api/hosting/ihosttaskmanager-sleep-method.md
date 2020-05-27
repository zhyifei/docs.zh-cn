---
title: IHostTaskManager::Sleep 方法
ms.date: 03/30/2017
api_name:
- IHostTaskManager.Sleep
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::Sleep
helpviewer_keywords:
- IHostTaskManager::Sleep method [.NET Framework hosting]
- Sleep method, IHostTaskManager interface [.NET Framework hosting]
ms.assetid: f67d25f3-9199-4c5f-b1e8-1c819243cfd5
topic_type:
- apiref
ms.openlocfilehash: bb12547155383bb410f592018232ca6f688bab8a
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/26/2020
ms.locfileid: "83841901"
---
# <a name="ihosttaskmanagersleep-method"></a><span data-ttu-id="bd870-102">IHostTaskManager::Sleep 方法</span><span class="sxs-lookup"><span data-stu-id="bd870-102">IHostTaskManager::Sleep Method</span></span>
<span data-ttu-id="bd870-103">通知宿主当前任务将要进入睡眠状态。</span><span class="sxs-lookup"><span data-stu-id="bd870-103">Notifies the host that the current task is going to sleep.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd870-104">语法</span><span class="sxs-lookup"><span data-stu-id="bd870-104">Syntax</span></span>  
  
```cpp  
HRESULT Sleep (  
    [in] DWORD dwMilliseconds,  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bd870-105">参数</span><span class="sxs-lookup"><span data-stu-id="bd870-105">Parameters</span></span>  
 `dwMilliseconds`  
 <span data-ttu-id="bd870-106">中线程将进入睡眠状态的时间间隔（以毫秒为单位）。</span><span class="sxs-lookup"><span data-stu-id="bd870-106">[in] The time interval, in milliseconds, that the thread will sleep.</span></span>  
  
 `option`  
 <span data-ttu-id="bd870-107">中[WAIT_OPTION](wait-option-enumeration.md)枚举值之一，指示当此操作阻止时宿主应执行的操作。</span><span class="sxs-lookup"><span data-stu-id="bd870-107">[in] One of the [WAIT_OPTION](wait-option-enumeration.md) enumeration values, indicating what action the host should take if this action blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bd870-108">返回值</span><span class="sxs-lookup"><span data-stu-id="bd870-108">Return Value</span></span>  
  
|<span data-ttu-id="bd870-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="bd870-109">HRESULT</span></span>|<span data-ttu-id="bd870-110">说明</span><span class="sxs-lookup"><span data-stu-id="bd870-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="bd870-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="bd870-111">S_OK</span></span>|<span data-ttu-id="bd870-112">`Sleep`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="bd870-112">`Sleep` returned successfully.</span></span>|  
|<span data-ttu-id="bd870-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="bd870-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="bd870-114">公共语言运行时（CLR）未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="bd870-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="bd870-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="bd870-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="bd870-116">调用超时。</span><span class="sxs-lookup"><span data-stu-id="bd870-116">The call timed out.</span></span>|  
|<span data-ttu-id="bd870-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="bd870-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="bd870-118">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="bd870-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="bd870-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="bd870-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="bd870-120">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="bd870-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="bd870-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="bd870-121">E_FAIL</span></span>|<span data-ttu-id="bd870-122">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="bd870-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="bd870-123">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="bd870-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="bd870-124">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="bd870-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bd870-125">备注</span><span class="sxs-lookup"><span data-stu-id="bd870-125">Remarks</span></span>  
 <span data-ttu-id="bd870-126">在 `IHostTaskManager::Sleep` <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> 从用户代码调用时，CLR 通常会调用。</span><span class="sxs-lookup"><span data-stu-id="bd870-126">The CLR typically calls `IHostTaskManager::Sleep` when <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> is called from user code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bd870-127">要求</span><span class="sxs-lookup"><span data-stu-id="bd870-127">Requirements</span></span>  
 <span data-ttu-id="bd870-128">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="bd870-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bd870-129">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="bd870-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bd870-130">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="bd870-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bd870-131">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bd870-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd870-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bd870-132">See also</span></span>

- [<span data-ttu-id="bd870-133">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="bd870-133">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="bd870-134">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="bd870-134">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="bd870-135">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="bd870-135">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="bd870-136">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="bd870-136">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
