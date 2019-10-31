---
title: IHostTask::Start 方法
ms.date: 03/30/2017
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
ms.openlocfilehash: fe93a3bab267ccca941974b734c86329ad0f4d03
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121340"
---
# <a name="ihosttaskstart-method"></a><span data-ttu-id="9d9f8-102">IHostTask::Start 方法</span><span class="sxs-lookup"><span data-stu-id="9d9f8-102">IHostTask::Start Method</span></span>
<span data-ttu-id="9d9f8-103">请求宿主将当前[IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)实例表示的任务从挂起状态移动到实时状态，在此状态下可以执行代码。</span><span class="sxs-lookup"><span data-stu-id="9d9f8-103">Requests that the host move the task represented by the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance from a suspended to a live state, in which code can be executed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d9f8-104">语法</span><span class="sxs-lookup"><span data-stu-id="9d9f8-104">Syntax</span></span>  
  
```cpp  
HRESULT Start ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="9d9f8-105">返回值</span><span class="sxs-lookup"><span data-stu-id="9d9f8-105">Return Value</span></span>  
  
|<span data-ttu-id="9d9f8-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9d9f8-106">HRESULT</span></span>|<span data-ttu-id="9d9f8-107">描述</span><span class="sxs-lookup"><span data-stu-id="9d9f8-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9d9f8-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="9d9f8-108">S_OK</span></span>|<span data-ttu-id="9d9f8-109">已成功启动。</span><span class="sxs-lookup"><span data-stu-id="9d9f8-109">Start returned successfully.</span></span>|  
|<span data-ttu-id="9d9f8-110">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9d9f8-110">E_FAIL</span></span>|<span data-ttu-id="9d9f8-111">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="9d9f8-111">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9d9f8-112">当方法返回 E_FAIL 时，公共语言运行时（CLR）在该过程中将不再可用。</span><span class="sxs-lookup"><span data-stu-id="9d9f8-112">When a method returns E_FAIL, the common language runtime (CLR) is no longer usable within the process.</span></span> <span data-ttu-id="9d9f8-113">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="9d9f8-113">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9d9f8-114">备注</span><span class="sxs-lookup"><span data-stu-id="9d9f8-114">Remarks</span></span>  
 <span data-ttu-id="9d9f8-115">`Start` 总是返回的 HRESULT 值为 S_OK，但发生灾难性故障的情况除外。</span><span class="sxs-lookup"><span data-stu-id="9d9f8-115">`Start` always returns an HRESULT value of S_OK, except in cases where a catastrophic failure has occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9d9f8-116">要求</span><span class="sxs-lookup"><span data-stu-id="9d9f8-116">Requirements</span></span>  
 <span data-ttu-id="9d9f8-117">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9d9f8-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9d9f8-118">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="9d9f8-118">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9d9f8-119">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="9d9f8-119">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9d9f8-120">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9d9f8-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d9f8-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="9d9f8-121">See also</span></span>

- [<span data-ttu-id="9d9f8-122">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="9d9f8-122">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="9d9f8-123">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="9d9f8-123">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="9d9f8-124">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="9d9f8-124">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="9d9f8-125">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="9d9f8-125">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
