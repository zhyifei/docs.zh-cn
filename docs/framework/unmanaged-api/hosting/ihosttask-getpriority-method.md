---
title: IHostTask::GetPriority 方法
ms.date: 03/30/2017
api_name:
- IHostTask.GetPriority
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask::GetPriority
helpviewer_keywords:
- GetPriority method [.NET Framework hosting]
- IHostTask::GetPriority method [.NET Framework hosting]
ms.assetid: 4b463cd6-77c1-4f9a-8518-346ad8fc4b70
topic_type:
- apiref
ms.openlocfilehash: 6c33fa6d2e6cb09f013c5334461e61235db549f7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121420"
---
# <a name="ihosttaskgetpriority-method"></a><span data-ttu-id="18d22-102">IHostTask::GetPriority 方法</span><span class="sxs-lookup"><span data-stu-id="18d22-102">IHostTask::GetPriority Method</span></span>
<span data-ttu-id="18d22-103">获取当前[IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)实例所表示的任务的线程优先级别。</span><span class="sxs-lookup"><span data-stu-id="18d22-103">Gets the thread priority level of the task represented by the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18d22-104">语法</span><span class="sxs-lookup"><span data-stu-id="18d22-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPriority (  
    [out] int *pPriority  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="18d22-105">参数</span><span class="sxs-lookup"><span data-stu-id="18d22-105">Parameters</span></span>  
 `pPriority`  
 <span data-ttu-id="18d22-106">弄指向一个整数的指针，该整数指示当前 `IHostTask` 实例所表示的任务的线程优先级别。</span><span class="sxs-lookup"><span data-stu-id="18d22-106">[out] A pointer to an integer that indicates the thread priority level of the task represented by the current `IHostTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="18d22-107">返回值</span><span class="sxs-lookup"><span data-stu-id="18d22-107">Return Value</span></span>  
  
|<span data-ttu-id="18d22-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="18d22-108">HRESULT</span></span>|<span data-ttu-id="18d22-109">描述</span><span class="sxs-lookup"><span data-stu-id="18d22-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="18d22-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="18d22-110">S_OK</span></span>|<span data-ttu-id="18d22-111">`GetPriority` 成功返回。</span><span class="sxs-lookup"><span data-stu-id="18d22-111">`GetPriority` returned successfully.</span></span>|  
|<span data-ttu-id="18d22-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="18d22-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="18d22-113">公共语言运行时（CLR）未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="18d22-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="18d22-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="18d22-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="18d22-115">调用超时。</span><span class="sxs-lookup"><span data-stu-id="18d22-115">The call timed out.</span></span>|  
|<span data-ttu-id="18d22-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="18d22-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="18d22-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="18d22-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="18d22-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="18d22-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="18d22-119">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="18d22-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="18d22-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="18d22-120">E_FAIL</span></span>|<span data-ttu-id="18d22-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="18d22-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="18d22-122">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="18d22-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="18d22-123">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="18d22-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="18d22-124">备注</span><span class="sxs-lookup"><span data-stu-id="18d22-124">Remarks</span></span>  
 <span data-ttu-id="18d22-125">线程优先级别值由 Win32 `SetThreadPriority` 函数定义。</span><span class="sxs-lookup"><span data-stu-id="18d22-125">Thread priority level values are defined by the Win32 `SetThreadPriority` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="18d22-126">要求</span><span class="sxs-lookup"><span data-stu-id="18d22-126">Requirements</span></span>  
 <span data-ttu-id="18d22-127">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="18d22-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="18d22-128">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="18d22-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="18d22-129">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="18d22-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="18d22-130">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="18d22-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18d22-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="18d22-131">See also</span></span>

- [<span data-ttu-id="18d22-132">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="18d22-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="18d22-133">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="18d22-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="18d22-134">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="18d22-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="18d22-135">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="18d22-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
