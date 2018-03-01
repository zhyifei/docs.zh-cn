---
title: "IHostTask::Start 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IHostTask.Start
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask::Start
helpviewer_keywords:
- IHostTask::Start method [.NET Framework hosting]
- Start method, IHostTask interface [.NET Framework hosting]
ms.assetid: b18742b0-d8c4-401c-ae89-e6eccdaa81d0
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: db43ec56fac86b0040aa4f701940abf0d1c0df07
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ihosttaskstart-method"></a><span data-ttu-id="90a29-102">IHostTask::Start 方法</span><span class="sxs-lookup"><span data-stu-id="90a29-102">IHostTask::Start Method</span></span>
<span data-ttu-id="90a29-103">主机将表示由当前的任务的请求[IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)实例从挂起与代码可以执行的实时状态。</span><span class="sxs-lookup"><span data-stu-id="90a29-103">Requests that the host move the task represented by the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance from a suspended to a live state, in which code can be executed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90a29-104">语法</span><span class="sxs-lookup"><span data-stu-id="90a29-104">Syntax</span></span>  
  
```  
HRESULT Start ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="90a29-105">返回值</span><span class="sxs-lookup"><span data-stu-id="90a29-105">Return Value</span></span>  
  
|<span data-ttu-id="90a29-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="90a29-106">HRESULT</span></span>|<span data-ttu-id="90a29-107">描述</span><span class="sxs-lookup"><span data-stu-id="90a29-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="90a29-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="90a29-108">S_OK</span></span>|<span data-ttu-id="90a29-109">启动返回成功。</span><span class="sxs-lookup"><span data-stu-id="90a29-109">Start returned successfully.</span></span>|  
|<span data-ttu-id="90a29-110">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="90a29-110">E_FAIL</span></span>|<span data-ttu-id="90a29-111">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="90a29-111">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="90a29-112">如果某方法返回 E_FAIL，公共语言运行时 (CLR) 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="90a29-112">When a method returns E_FAIL, the common language runtime (CLR) is no longer usable within the process.</span></span> <span data-ttu-id="90a29-113">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="90a29-113">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="90a29-114">备注</span><span class="sxs-lookup"><span data-stu-id="90a29-114">Remarks</span></span>  
 <span data-ttu-id="90a29-115">`Start`在发生灾难性故障的情况下除外中始终返回 S_OK，HRESULT 值。</span><span class="sxs-lookup"><span data-stu-id="90a29-115">`Start` always returns an HRESULT value of S_OK, except in cases where a catastrophic failure has occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="90a29-116">惠?</span><span class="sxs-lookup"><span data-stu-id="90a29-116">Requirements</span></span>  
 <span data-ttu-id="90a29-117">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="90a29-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90a29-118">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="90a29-118">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="90a29-119">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="90a29-119">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="90a29-120">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="90a29-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90a29-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="90a29-121">See Also</span></span>  
 [<span data-ttu-id="90a29-122">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="90a29-122">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="90a29-123">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="90a29-123">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="90a29-124">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="90a29-124">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="90a29-125">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="90a29-125">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
