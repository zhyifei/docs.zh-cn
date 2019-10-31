---
title: IHostCrst::Leave 方法
ms.date: 03/30/2017
api_name:
- IHostCrst.Leave
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostCrst::Leave
helpviewer_keywords:
- IHostCrst::Leave method [.NET Framework hosting]
- Leave method [.NET Framework hosting]
ms.assetid: dfc51d9e-b36d-4dba-9ea1-4f63fa0601ae
topic_type:
- apiref
ms.openlocfilehash: 050af068579d84b984ed83377d0c201e281bd154
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130537"
---
# <a name="ihostcrstleave-method"></a><span data-ttu-id="e4aad-102">IHostCrst::Leave 方法</span><span class="sxs-lookup"><span data-stu-id="e4aad-102">IHostCrst::Leave Method</span></span>
<span data-ttu-id="e4aad-103">保留[IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)的当前实例所表示的临界区。</span><span class="sxs-lookup"><span data-stu-id="e4aad-103">Leaves the critical section that is represented by the current instance of [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4aad-104">语法</span><span class="sxs-lookup"><span data-stu-id="e4aad-104">Syntax</span></span>  
  
```cpp  
HRESULT Leave ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="e4aad-105">返回值</span><span class="sxs-lookup"><span data-stu-id="e4aad-105">Return Value</span></span>  
  
|<span data-ttu-id="e4aad-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e4aad-106">HRESULT</span></span>|<span data-ttu-id="e4aad-107">描述</span><span class="sxs-lookup"><span data-stu-id="e4aad-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e4aad-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="e4aad-108">S_OK</span></span>|<span data-ttu-id="e4aad-109">`Leave` 成功返回。</span><span class="sxs-lookup"><span data-stu-id="e4aad-109">`Leave` returned successfully.</span></span>|  
|<span data-ttu-id="e4aad-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e4aad-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e4aad-111">公共语言运行时（CLR）未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="e4aad-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e4aad-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e4aad-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e4aad-113">调用超时。</span><span class="sxs-lookup"><span data-stu-id="e4aad-113">The call timed out.</span></span>|  
|<span data-ttu-id="e4aad-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e4aad-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e4aad-115">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="e4aad-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e4aad-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e4aad-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e4aad-117">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="e4aad-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e4aad-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e4aad-118">E_FAIL</span></span>|<span data-ttu-id="e4aad-119">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="e4aad-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e4aad-120">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="e4aad-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e4aad-121">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="e4aad-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e4aad-122">备注</span><span class="sxs-lookup"><span data-stu-id="e4aad-122">Remarks</span></span>  
 <span data-ttu-id="e4aad-123">`Leave` 允许 CLR 与宿主的线程实现直接通信，而不是使用相应的 Win32 `LeaveCriticalSection` 函数。</span><span class="sxs-lookup"><span data-stu-id="e4aad-123">`Leave` allows the CLR to communicate directly with the host's threading implementation, rather than using the corresponding Win32 `LeaveCriticalSection` function.</span></span> <span data-ttu-id="e4aad-124">获取由当前 `IHostCrst` 实例表示的临界区所有权的线程必须在每次进入该关键部分时调用一次 `Leave`。</span><span class="sxs-lookup"><span data-stu-id="e4aad-124">A thread that takes ownership of the critical section represented by the current `IHostCrst` instance must call `Leave` once for each time it enters that critical section.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e4aad-125">要求</span><span class="sxs-lookup"><span data-stu-id="e4aad-125">Requirements</span></span>  
 <span data-ttu-id="e4aad-126">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e4aad-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e4aad-127">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="e4aad-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e4aad-128">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="e4aad-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e4aad-129">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e4aad-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4aad-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="e4aad-130">See also</span></span>

- [<span data-ttu-id="e4aad-131">ICLRSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="e4aad-131">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="e4aad-132">IHostCrst 接口</span><span class="sxs-lookup"><span data-stu-id="e4aad-132">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)
- [<span data-ttu-id="e4aad-133">IHostSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="e4aad-133">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
