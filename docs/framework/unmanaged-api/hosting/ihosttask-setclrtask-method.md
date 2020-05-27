---
title: IHostTask::SetCLRTask 方法
ms.date: 03/30/2017
api_name:
- IHostTask.SetCLRTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask::SetCLRTask
helpviewer_keywords:
- SetCLRTask method [.NET Framework hosting]
- IHostTask::SetCLRTask method [.NET Framework hosting]
ms.assetid: e9d39c80-41a1-49e7-bb5e-ea3433bfb5d7
topic_type:
- apiref
ms.openlocfilehash: b6eac134a4ffb1813cdc6957632ce5fb9b1a5fff
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/26/2020
ms.locfileid: "83842265"
---
# <a name="ihosttasksetclrtask-method"></a><span data-ttu-id="6be68-102">IHostTask::SetCLRTask 方法</span><span class="sxs-lookup"><span data-stu-id="6be68-102">IHostTask::SetCLRTask Method</span></span>
<span data-ttu-id="6be68-103">将 `ICLRTask` 实例与当前[IHostTask](ihosttask-interface.md)实例相关联。</span><span class="sxs-lookup"><span data-stu-id="6be68-103">Associates an `ICLRTask` instance with the current [IHostTask](ihosttask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6be68-104">语法</span><span class="sxs-lookup"><span data-stu-id="6be68-104">Syntax</span></span>  
  
```cpp  
HRESULT SetCLRTask (  
    [in] ICLRTask *pCLRTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6be68-105">参数</span><span class="sxs-lookup"><span data-stu-id="6be68-105">Parameters</span></span>  
 `pCLRTask`  
 <span data-ttu-id="6be68-106">中指向要 `ICLRTask` 与当前实例关联的实例的接口指针 `IHostTask` 。</span><span class="sxs-lookup"><span data-stu-id="6be68-106">[in] An interface pointer to the `ICLRTask` instance to be associated with the current `IHostTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6be68-107">返回值</span><span class="sxs-lookup"><span data-stu-id="6be68-107">Return Value</span></span>  
  
|<span data-ttu-id="6be68-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6be68-108">HRESULT</span></span>|<span data-ttu-id="6be68-109">说明</span><span class="sxs-lookup"><span data-stu-id="6be68-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6be68-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="6be68-110">S_OK</span></span>|<span data-ttu-id="6be68-111">`SetCLRTask`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="6be68-111">`SetCLRTask` returned successfully.</span></span>|  
|<span data-ttu-id="6be68-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6be68-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6be68-113">公共语言运行时（CLR）未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="6be68-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="6be68-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="6be68-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="6be68-115">调用超时。</span><span class="sxs-lookup"><span data-stu-id="6be68-115">The call timed out.</span></span>|  
|<span data-ttu-id="6be68-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="6be68-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="6be68-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="6be68-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="6be68-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="6be68-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="6be68-119">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="6be68-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="6be68-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6be68-120">E_FAIL</span></span>|<span data-ttu-id="6be68-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="6be68-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="6be68-122">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="6be68-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="6be68-123">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="6be68-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6be68-124">备注</span><span class="sxs-lookup"><span data-stu-id="6be68-124">Remarks</span></span>  
 <span data-ttu-id="6be68-125">CLR 调用将 `SetCLRTask` `ICLRTask` 实例与当前实例相关联 `IHostTask` ，该实例是通过调用[IHostTaskManager：： CreateTask](ihosttaskmanager-createtask-method.md)创建的。</span><span class="sxs-lookup"><span data-stu-id="6be68-125">The CLR calls `SetCLRTask` to associate an `ICLRTask` instance with the current `IHostTask` instance, which was created by a call to [IHostTaskManager::CreateTask](ihosttaskmanager-createtask-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6be68-126">要求</span><span class="sxs-lookup"><span data-stu-id="6be68-126">Requirements</span></span>  
 <span data-ttu-id="6be68-127">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6be68-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6be68-128">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="6be68-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6be68-129">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="6be68-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6be68-130">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6be68-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6be68-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6be68-131">See also</span></span>

- [<span data-ttu-id="6be68-132">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="6be68-132">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="6be68-133">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="6be68-133">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="6be68-134">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="6be68-134">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="6be68-135">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="6be68-135">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
