---
title: IHostAutoEvent::Set 方法
ms.date: 03/30/2017
api_name:
- IHostAutoEvent.Set
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAutoEvent::Set
helpviewer_keywords:
- Set method, IHostAutoEvent interface [.NET Framework hosting]
- IHostAutoEvent::Set method [.NET Framework hosting]
ms.assetid: 46becf3e-bc0e-4338-85c0-9ab0df76a1d0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b7994757a127686967d9863a574d0e1f8425ca86
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54521213"
---
# <a name="ihostautoeventset-method"></a><span data-ttu-id="476f3-102">IHostAutoEvent::Set 方法</span><span class="sxs-lookup"><span data-stu-id="476f3-102">IHostAutoEvent::Set Method</span></span>
<span data-ttu-id="476f3-103">设置当前[IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)到已发出信号状态的实例。</span><span class="sxs-lookup"><span data-stu-id="476f3-103">Sets the current [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) instance to a signaled state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="476f3-104">语法</span><span class="sxs-lookup"><span data-stu-id="476f3-104">Syntax</span></span>  
  
```  
HRESULT Set ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="476f3-105">返回值</span><span class="sxs-lookup"><span data-stu-id="476f3-105">Return Value</span></span>  
  
|<span data-ttu-id="476f3-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="476f3-106">HRESULT</span></span>|<span data-ttu-id="476f3-107">描述</span><span class="sxs-lookup"><span data-stu-id="476f3-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="476f3-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="476f3-108">S_OK</span></span>|<span data-ttu-id="476f3-109">`Set` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="476f3-109">`Set` returned successfully.</span></span>|  
|<span data-ttu-id="476f3-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="476f3-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="476f3-111">公共语言运行时 (CLR) 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="476f3-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="476f3-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="476f3-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="476f3-113">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="476f3-113">The call timed out.</span></span>|  
|<span data-ttu-id="476f3-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="476f3-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="476f3-115">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="476f3-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="476f3-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="476f3-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="476f3-117">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="476f3-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="476f3-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="476f3-118">E_FAIL</span></span>|<span data-ttu-id="476f3-119">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="476f3-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="476f3-120">如果某方法返回 E_FAIL，CLR 不再在进程内可用。</span><span class="sxs-lookup"><span data-stu-id="476f3-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="476f3-121">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="476f3-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="476f3-122">要求</span><span class="sxs-lookup"><span data-stu-id="476f3-122">Requirements</span></span>  
 <span data-ttu-id="476f3-123">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="476f3-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="476f3-124">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="476f3-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="476f3-125">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="476f3-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="476f3-126">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="476f3-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="476f3-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="476f3-127">See also</span></span>
- [<span data-ttu-id="476f3-128">ICLRSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="476f3-128">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="476f3-129">IHostAutoEvent 接口</span><span class="sxs-lookup"><span data-stu-id="476f3-129">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="476f3-130">IHostManualEvent 接口</span><span class="sxs-lookup"><span data-stu-id="476f3-130">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="476f3-131">IHostSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="476f3-131">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
