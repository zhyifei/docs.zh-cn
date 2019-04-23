---
title: IHostTask::Alert 方法
ms.date: 03/30/2017
api_name:
- IHostTask.Alert
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask::Alert
helpviewer_keywords:
- IHostTask::Alert method [.NET Framework hosting]
- Alert method, IHostTask interface [.NET Framework hosting]
ms.assetid: 5245d4b5-b6c3-48df-9cb9-8caf059f43fb
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c153e6ae8558eeab2efa99765405fb7c84632b01
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59110027"
---
# <a name="ihosttaskalert-method"></a><span data-ttu-id="48ea8-102">IHostTask::Alert 方法</span><span class="sxs-lookup"><span data-stu-id="48ea8-102">IHostTask::Alert Method</span></span>
<span data-ttu-id="48ea8-103">请求主机唤醒表示由当前的任务[IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)的实例，因此，任务可以中止。</span><span class="sxs-lookup"><span data-stu-id="48ea8-103">Requests that the host wake the task represented by the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance, so the task can be aborted.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48ea8-104">语法</span><span class="sxs-lookup"><span data-stu-id="48ea8-104">Syntax</span></span>  
  
```  
HRESULT Alert ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="48ea8-105">返回值</span><span class="sxs-lookup"><span data-stu-id="48ea8-105">Return Value</span></span>  
  
|<span data-ttu-id="48ea8-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="48ea8-106">HRESULT</span></span>|<span data-ttu-id="48ea8-107">描述</span><span class="sxs-lookup"><span data-stu-id="48ea8-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="48ea8-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="48ea8-108">S_OK</span></span>|<span data-ttu-id="48ea8-109">该方法成功返回。</span><span class="sxs-lookup"><span data-stu-id="48ea8-109">The method returned successfully.</span></span>|  
|<span data-ttu-id="48ea8-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="48ea8-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="48ea8-111">公共语言运行时 (CLR) 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="48ea8-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="48ea8-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="48ea8-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="48ea8-113">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="48ea8-113">The call timed out.</span></span>|  
|<span data-ttu-id="48ea8-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="48ea8-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="48ea8-115">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="48ea8-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="48ea8-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="48ea8-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="48ea8-117">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="48ea8-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="48ea8-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="48ea8-118">E_FAIL</span></span>|<span data-ttu-id="48ea8-119">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="48ea8-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="48ea8-120">如果某方法返回 E_FAIL，CLR 不再在进程内可用。</span><span class="sxs-lookup"><span data-stu-id="48ea8-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="48ea8-121">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="48ea8-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="48ea8-122">备注</span><span class="sxs-lookup"><span data-stu-id="48ea8-122">Remarks</span></span>  
 <span data-ttu-id="48ea8-123">CLR 调用`Alert`方法时<xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>从用户代码调用时，或者当<xref:System.AppDomain>与当前关联<xref:System.Threading.Thread>关闭。</span><span class="sxs-lookup"><span data-stu-id="48ea8-123">The CLR calls the `Alert` method when <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> is called from user code, or when the <xref:System.AppDomain> associated with the current <xref:System.Threading.Thread> shuts down.</span></span> <span data-ttu-id="48ea8-124">主机必须立即返回，因为调用以异步方式。</span><span class="sxs-lookup"><span data-stu-id="48ea8-124">The host must return immediately, because the call is made asynchronously.</span></span> <span data-ttu-id="48ea8-125">如果主机不能立即警报任务，它必须唤醒的下次进入在其中可以收到警报的状态。</span><span class="sxs-lookup"><span data-stu-id="48ea8-125">If the host cannot alert the task immediately, it must wake up the next time it enters a state in which it can be alerted.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="48ea8-126">`Alert` 影响运行时已传递到这些任务[WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md)等方法对值 WAIT_ALERTABLE[加入](../../../../docs/framework/unmanaged-api/hosting/ihosttask-join-method.md)。</span><span class="sxs-lookup"><span data-stu-id="48ea8-126">`Alert` affects only those tasks to which the runtime has passed a [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) value of WAIT_ALERTABLE to methods such as [Join](../../../../docs/framework/unmanaged-api/hosting/ihosttask-join-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48ea8-127">要求</span><span class="sxs-lookup"><span data-stu-id="48ea8-127">Requirements</span></span>  
 <span data-ttu-id="48ea8-128">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="48ea8-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48ea8-129">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="48ea8-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="48ea8-130">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="48ea8-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="48ea8-131">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48ea8-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48ea8-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="48ea8-132">See also</span></span>

- [<span data-ttu-id="48ea8-133">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="48ea8-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="48ea8-134">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="48ea8-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="48ea8-135">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="48ea8-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="48ea8-136">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="48ea8-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
