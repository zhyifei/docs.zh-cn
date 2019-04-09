---
title: ICLRTask::Abort 方法
ms.date: 03/30/2017
api_name:
- ICLRTask.Abort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::Abort
helpviewer_keywords:
- ICLRTask::Abort method [.NET Framework hosting]
- Abort method, ICLRTask interface [.NET Framework hosting]
ms.assetid: b3594b5f-2e41-4e36-9096-3586276a138c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 57efd4f29ba7e28adf1af03030d7f83eb32c1c2b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59139771"
---
# <a name="iclrtaskabort-method"></a><span data-ttu-id="091a9-102">ICLRTask::Abort 方法</span><span class="sxs-lookup"><span data-stu-id="091a9-102">ICLRTask::Abort Method</span></span>
<span data-ttu-id="091a9-103">请求公共语言运行时 (CLR) 中止任务的当前[ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)实例所表示。</span><span class="sxs-lookup"><span data-stu-id="091a9-103">Requests that the common language runtime (CLR) abort the task that the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="091a9-104">语法</span><span class="sxs-lookup"><span data-stu-id="091a9-104">Syntax</span></span>  
  
```  
HRESULT Abort ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="091a9-105">返回值</span><span class="sxs-lookup"><span data-stu-id="091a9-105">Return Value</span></span>  
  
|<span data-ttu-id="091a9-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="091a9-106">HRESULT</span></span>|<span data-ttu-id="091a9-107">描述</span><span class="sxs-lookup"><span data-stu-id="091a9-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="091a9-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="091a9-108">S_OK</span></span>|`Abort` <span data-ttu-id="091a9-109">已成功返回。</span><span class="sxs-lookup"><span data-stu-id="091a9-109">returned successfully.</span></span>|  
|<span data-ttu-id="091a9-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="091a9-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="091a9-111">CLR 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="091a9-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="091a9-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="091a9-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="091a9-113">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="091a9-113">The call timed out.</span></span>|  
|<span data-ttu-id="091a9-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="091a9-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="091a9-115">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="091a9-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="091a9-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="091a9-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="091a9-117">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="091a9-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="091a9-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="091a9-118">E_FAIL</span></span>|<span data-ttu-id="091a9-119">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="091a9-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="091a9-120">如果某方法返回 E_FAIL，CLR 不再在进程内可用。</span><span class="sxs-lookup"><span data-stu-id="091a9-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="091a9-121">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="091a9-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="091a9-122">备注</span><span class="sxs-lookup"><span data-stu-id="091a9-122">Remarks</span></span>  
 <span data-ttu-id="091a9-123">CLR 将引发<xref:System.Threading.ThreadAbortException>主机时调用`Abort`。</span><span class="sxs-lookup"><span data-stu-id="091a9-123">The CLR raises a <xref:System.Threading.ThreadAbortException> when the host calls `Abort`.</span></span> <span data-ttu-id="091a9-124">它将返回异常信息初始化，而无需等待用户代码，如终结器或异常处理机制，用来执行后立即。</span><span class="sxs-lookup"><span data-stu-id="091a9-124">It returns immediately after the exception information is initialized, without waiting for user code, such as finalizers or exception handling mechanisms, to execute.</span></span> <span data-ttu-id="091a9-125">调用`Abort`因此迅速返回。</span><span class="sxs-lookup"><span data-stu-id="091a9-125">Calls to `Abort` thus return quickly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="091a9-126">要求</span><span class="sxs-lookup"><span data-stu-id="091a9-126">Requirements</span></span>  
 <span data-ttu-id="091a9-127">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="091a9-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="091a9-128">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="091a9-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="091a9-129">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="091a9-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="091a9-130">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="091a9-130">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="091a9-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="091a9-131">See also</span></span>

- [<span data-ttu-id="091a9-132">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="091a9-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="091a9-133">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="091a9-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="091a9-134">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="091a9-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="091a9-135">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="091a9-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
