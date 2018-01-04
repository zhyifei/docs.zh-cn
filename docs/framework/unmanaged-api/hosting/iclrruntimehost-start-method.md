---
title: "ICLRRuntimeHost::Start 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeHost.Start
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRRuntimeHost::Start
helpviewer_keywords:
- ICLRRuntimeHost::Start method [.NET Framework hosting]
- Start method, ICLRRuntimeHost interface [.NET Framework hosting]
ms.assetid: c0a6dce5-0a8d-42e8-808b-6ca14df9d289
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a9705e4449da3b485bef7e7250ca08473d51387b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iclrruntimehoststart-method"></a><span data-ttu-id="de7a4-102">ICLRRuntimeHost::Start 方法</span><span class="sxs-lookup"><span data-stu-id="de7a4-102">ICLRRuntimeHost::Start Method</span></span>
<span data-ttu-id="de7a4-103">到另一进程初始化公共语言运行时 (CLR)。</span><span class="sxs-lookup"><span data-stu-id="de7a4-103">Initializes the common language runtime (CLR) into a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de7a4-104">语法</span><span class="sxs-lookup"><span data-stu-id="de7a4-104">Syntax</span></span>  
  
```  
HRESULT Start();  
```  
  
## <a name="return-value"></a><span data-ttu-id="de7a4-105">返回值</span><span class="sxs-lookup"><span data-stu-id="de7a4-105">Return Value</span></span>  
  
|<span data-ttu-id="de7a4-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="de7a4-106">HRESULT</span></span>|<span data-ttu-id="de7a4-107">描述</span><span class="sxs-lookup"><span data-stu-id="de7a4-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="de7a4-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="de7a4-108">S_OK</span></span>|<span data-ttu-id="de7a4-109">`Start`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="de7a4-109">`Start` returned successfully.</span></span>|  
|<span data-ttu-id="de7a4-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="de7a4-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="de7a4-111">CLR 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="de7a4-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="de7a4-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="de7a4-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="de7a4-113">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="de7a4-113">The call timed out.</span></span>|  
|<span data-ttu-id="de7a4-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="de7a4-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="de7a4-115">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="de7a4-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="de7a4-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="de7a4-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="de7a4-117">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="de7a4-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="de7a4-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="de7a4-118">E_FAIL</span></span>|<span data-ttu-id="de7a4-119">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="de7a4-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="de7a4-120">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="de7a4-120">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="de7a4-121">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="de7a4-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="de7a4-122">备注</span><span class="sxs-lookup"><span data-stu-id="de7a4-122">Remarks</span></span>  
 <span data-ttu-id="de7a4-123">在许多情况下它不需要调用`Start`，因为运行时将运行托管的代码的第一个请求时自动初始化自身。</span><span class="sxs-lookup"><span data-stu-id="de7a4-123">In many scenarios it is not necessary to call `Start`, because the runtime will initialize itself automatically upon the first request to run managed code.</span></span> <span data-ttu-id="de7a4-124">但是，你可以使用`Start`指定完全时运行时应已初始化。</span><span class="sxs-lookup"><span data-stu-id="de7a4-124">You can, however, use `Start` to specify exactly when the runtime should be initialized.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="de7a4-125">惠?</span><span class="sxs-lookup"><span data-stu-id="de7a4-125">Requirements</span></span>  
 <span data-ttu-id="de7a4-126">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="de7a4-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de7a4-127">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="de7a4-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="de7a4-128">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="de7a4-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="de7a4-129">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="de7a4-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de7a4-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="de7a4-130">See Also</span></span>  
 <xref:System.AppDomain>  
 [<span data-ttu-id="de7a4-131">ICLRRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="de7a4-131">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
