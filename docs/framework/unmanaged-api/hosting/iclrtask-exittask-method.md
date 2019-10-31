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
ms.openlocfilehash: 3f6ccf2eb25e96e0f94c558fb642b153ae3472c1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124896"
---
# <a name="iclrtaskexittask-method"></a><span data-ttu-id="67a91-102">ICLRTask::ExitTask 方法</span><span class="sxs-lookup"><span data-stu-id="67a91-102">ICLRTask::ExitTask Method</span></span>
<span data-ttu-id="67a91-103">通知公共语言运行时（CLR）当前[ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)实例表示的任务正在结束，并尝试正常关闭任务。</span><span class="sxs-lookup"><span data-stu-id="67a91-103">Notifies the common language runtime (CLR) that the task represented by the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance is ending, and attempts to shut the task down gracefully.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67a91-104">语法</span><span class="sxs-lookup"><span data-stu-id="67a91-104">Syntax</span></span>  
  
```cpp  
HRESULT ExitTask ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="67a91-105">返回值</span><span class="sxs-lookup"><span data-stu-id="67a91-105">Return Value</span></span>  
  
|<span data-ttu-id="67a91-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="67a91-106">HRESULT</span></span>|<span data-ttu-id="67a91-107">描述</span><span class="sxs-lookup"><span data-stu-id="67a91-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="67a91-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="67a91-108">S_OK</span></span>|<span data-ttu-id="67a91-109">`ExitTask` 成功返回。</span><span class="sxs-lookup"><span data-stu-id="67a91-109">`ExitTask` returned successfully.</span></span>|  
|<span data-ttu-id="67a91-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="67a91-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="67a91-111">CLR 未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="67a91-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="67a91-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="67a91-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="67a91-113">调用超时。</span><span class="sxs-lookup"><span data-stu-id="67a91-113">The call timed out.</span></span>|  
|<span data-ttu-id="67a91-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="67a91-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="67a91-115">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="67a91-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="67a91-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="67a91-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="67a91-117">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="67a91-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="67a91-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="67a91-118">E_FAIL</span></span>|<span data-ttu-id="67a91-119">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="67a91-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="67a91-120">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="67a91-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="67a91-121">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="67a91-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="67a91-122">备注</span><span class="sxs-lookup"><span data-stu-id="67a91-122">Remarks</span></span>  
 <span data-ttu-id="67a91-123">`ExitTask` 尝试完全关闭任务，其方式类似于从非托管类型库分离线程。</span><span class="sxs-lookup"><span data-stu-id="67a91-123">`ExitTask` attempts a clean shutdown of a task, in a manner analogous to detaching a thread from an unmanaged type library.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67a91-124">要求</span><span class="sxs-lookup"><span data-stu-id="67a91-124">Requirements</span></span>  
 <span data-ttu-id="67a91-125">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="67a91-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67a91-126">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="67a91-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="67a91-127">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="67a91-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="67a91-128">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67a91-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67a91-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="67a91-129">See also</span></span>

- [<span data-ttu-id="67a91-130">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="67a91-130">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="67a91-131">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="67a91-131">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="67a91-132">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="67a91-132">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="67a91-133">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="67a91-133">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
