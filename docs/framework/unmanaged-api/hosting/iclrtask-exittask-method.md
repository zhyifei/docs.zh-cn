---
title: ICLRTask::ExitTask 方法
ms.date: 03/30/2017
api_name:
- ICLRTask.ExitTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::ExitTask
helpviewer_keywords:
- ExitTask method [.NET Framework hosting]
- ICLRTask::ExitTask method [.NET Framework hosting]
ms.assetid: 746c85a6-4b33-4f72-a2e9-379fdf2e96af
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6a55b62c7c71510435b980a4e5938c20628046f4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59075873"
---
# <a name="iclrtaskexittask-method"></a><span data-ttu-id="faf79-102">ICLRTask::ExitTask 方法</span><span class="sxs-lookup"><span data-stu-id="faf79-102">ICLRTask::ExitTask Method</span></span>
<span data-ttu-id="faf79-103">通知任务的当前表示公共语言运行时 (CLR) [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)实例即将结束，并尝试正常关闭任务。</span><span class="sxs-lookup"><span data-stu-id="faf79-103">Notifies the common language runtime (CLR) that the task represented by the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance is ending, and attempts to shut the task down gracefully.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="faf79-104">语法</span><span class="sxs-lookup"><span data-stu-id="faf79-104">Syntax</span></span>  
  
```  
HRESULT ExitTask ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="faf79-105">返回值</span><span class="sxs-lookup"><span data-stu-id="faf79-105">Return Value</span></span>  
  
|<span data-ttu-id="faf79-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="faf79-106">HRESULT</span></span>|<span data-ttu-id="faf79-107">描述</span><span class="sxs-lookup"><span data-stu-id="faf79-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="faf79-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="faf79-108">S_OK</span></span>|`ExitTask` <span data-ttu-id="faf79-109">已成功返回。</span><span class="sxs-lookup"><span data-stu-id="faf79-109">returned successfully.</span></span>|  
|<span data-ttu-id="faf79-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="faf79-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="faf79-111">CLR 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="faf79-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="faf79-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="faf79-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="faf79-113">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="faf79-113">The call timed out.</span></span>|  
|<span data-ttu-id="faf79-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="faf79-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="faf79-115">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="faf79-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="faf79-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="faf79-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="faf79-117">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="faf79-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="faf79-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="faf79-118">E_FAIL</span></span>|<span data-ttu-id="faf79-119">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="faf79-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="faf79-120">如果某方法返回 E_FAIL，CLR 不再在进程内可用。</span><span class="sxs-lookup"><span data-stu-id="faf79-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="faf79-121">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="faf79-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="faf79-122">备注</span><span class="sxs-lookup"><span data-stu-id="faf79-122">Remarks</span></span>  
 `ExitTask` <span data-ttu-id="faf79-123">尝试正常关闭的任务，请在以类似于从非托管的类型库分离线程。</span><span class="sxs-lookup"><span data-stu-id="faf79-123">attempts a clean shutdown of a task, in a manner analogous to detaching a thread from an unmanaged type library.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="faf79-124">要求</span><span class="sxs-lookup"><span data-stu-id="faf79-124">Requirements</span></span>  
 <span data-ttu-id="faf79-125">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="faf79-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="faf79-126">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="faf79-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="faf79-127">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="faf79-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="faf79-128">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="faf79-128">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="faf79-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="faf79-129">See also</span></span>

- [<span data-ttu-id="faf79-130">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="faf79-130">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="faf79-131">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="faf79-131">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="faf79-132">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="faf79-132">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="faf79-133">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="faf79-133">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
