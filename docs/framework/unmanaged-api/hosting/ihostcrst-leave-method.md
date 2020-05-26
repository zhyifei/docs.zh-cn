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
ms.openlocfilehash: 08af77c3a158b97cd698dbaeebdc7cdf1b9acfc3
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804895"
---
# <a name="ihostcrstleave-method"></a><span data-ttu-id="fdfa3-102">IHostCrst::Leave 方法</span><span class="sxs-lookup"><span data-stu-id="fdfa3-102">IHostCrst::Leave Method</span></span>
<span data-ttu-id="fdfa3-103">保留[IHostCrst](ihostcrst-interface.md)的当前实例所表示的临界区。</span><span class="sxs-lookup"><span data-stu-id="fdfa3-103">Leaves the critical section that is represented by the current instance of [IHostCrst](ihostcrst-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fdfa3-104">语法</span><span class="sxs-lookup"><span data-stu-id="fdfa3-104">Syntax</span></span>  
  
```cpp  
HRESULT Leave ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="fdfa3-105">返回值</span><span class="sxs-lookup"><span data-stu-id="fdfa3-105">Return Value</span></span>  
  
|<span data-ttu-id="fdfa3-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fdfa3-106">HRESULT</span></span>|<span data-ttu-id="fdfa3-107">说明</span><span class="sxs-lookup"><span data-stu-id="fdfa3-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fdfa3-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="fdfa3-108">S_OK</span></span>|<span data-ttu-id="fdfa3-109">`Leave`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="fdfa3-109">`Leave` returned successfully.</span></span>|  
|<span data-ttu-id="fdfa3-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="fdfa3-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="fdfa3-111">公共语言运行时（CLR）未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="fdfa3-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="fdfa3-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="fdfa3-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="fdfa3-113">调用超时。</span><span class="sxs-lookup"><span data-stu-id="fdfa3-113">The call timed out.</span></span>|  
|<span data-ttu-id="fdfa3-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="fdfa3-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="fdfa3-115">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="fdfa3-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="fdfa3-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="fdfa3-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="fdfa3-117">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="fdfa3-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="fdfa3-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="fdfa3-118">E_FAIL</span></span>|<span data-ttu-id="fdfa3-119">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="fdfa3-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="fdfa3-120">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="fdfa3-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="fdfa3-121">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="fdfa3-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fdfa3-122">备注</span><span class="sxs-lookup"><span data-stu-id="fdfa3-122">Remarks</span></span>  
 <span data-ttu-id="fdfa3-123">`Leave`允许 CLR 与宿主的线程实现直接通信，而不是使用相应的 Win32 `LeaveCriticalSection` 函数。</span><span class="sxs-lookup"><span data-stu-id="fdfa3-123">`Leave` allows the CLR to communicate directly with the host's threading implementation, rather than using the corresponding Win32 `LeaveCriticalSection` function.</span></span> <span data-ttu-id="fdfa3-124">获取由当前实例表示的临界区所有权的线程必须在 `IHostCrst` `Leave` 每次进入该临界部分时调用一次。</span><span class="sxs-lookup"><span data-stu-id="fdfa3-124">A thread that takes ownership of the critical section represented by the current `IHostCrst` instance must call `Leave` once for each time it enters that critical section.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fdfa3-125">要求</span><span class="sxs-lookup"><span data-stu-id="fdfa3-125">Requirements</span></span>  
 <span data-ttu-id="fdfa3-126">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="fdfa3-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fdfa3-127">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="fdfa3-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fdfa3-128">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="fdfa3-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fdfa3-129">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fdfa3-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdfa3-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fdfa3-130">See also</span></span>

- [<span data-ttu-id="fdfa3-131">ICLRSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="fdfa3-131">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="fdfa3-132">IHostCrst 接口</span><span class="sxs-lookup"><span data-stu-id="fdfa3-132">IHostCrst Interface</span></span>](ihostcrst-interface.md)
- [<span data-ttu-id="fdfa3-133">IHostSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="fdfa3-133">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
