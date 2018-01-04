---
title: "ICLRPolicyManager::SetUnhandledExceptionPolicy 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRPolicyManager.SetUnhandledExceptionPolicy
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRPolicyManager::SetUnhandledExceptionPolicy
helpviewer_keywords:
- ICLRPolicyManager::SetUnhandledExceptionPolicy method [.NET Framework hosting]
- SetUnhandledExceptionPolicy method [.NET Framework hosting]
ms.assetid: 5268480e-280a-4931-b7a3-dc3ffdf7f78f
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9ad287fedbc06768dd683c254292e0c28760d59a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iclrpolicymanagersetunhandledexceptionpolicy-method"></a><span data-ttu-id="65464-102">ICLRPolicyManager::SetUnhandledExceptionPolicy 方法</span><span class="sxs-lookup"><span data-stu-id="65464-102">ICLRPolicyManager::SetUnhandledExceptionPolicy Method</span></span>
<span data-ttu-id="65464-103">发生未处理的异常时，请指定公共语言运行时 (CLR) 的行为。</span><span class="sxs-lookup"><span data-stu-id="65464-103">Specifies the behavior of the common language runtime (CLR) when an unhandled exception occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65464-104">语法</span><span class="sxs-lookup"><span data-stu-id="65464-104">Syntax</span></span>  
  
```  
HRESULT SetUnhandledExceptionPolicy (  
    [in] EClrUnhandledExceptionPolicy policy  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="65464-105">参数</span><span class="sxs-lookup"><span data-stu-id="65464-105">Parameters</span></span>  
 `policy`  
 <span data-ttu-id="65464-106">[in]之一[EClrUnhandledException](../../../../docs/framework/unmanaged-api/hosting/eclrunhandledexception-enumeration.md) ，该值指示是否通过 CLR 或主机设置行为的值。</span><span class="sxs-lookup"><span data-stu-id="65464-106">[in] One of the [EClrUnhandledException](../../../../docs/framework/unmanaged-api/hosting/eclrunhandledexception-enumeration.md) values, indicating whether the behavior is set by the CLR or the host.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="65464-107">返回值</span><span class="sxs-lookup"><span data-stu-id="65464-107">Return Value</span></span>  
  
|<span data-ttu-id="65464-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="65464-108">HRESULT</span></span>|<span data-ttu-id="65464-109">描述</span><span class="sxs-lookup"><span data-stu-id="65464-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="65464-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="65464-110">S_OK</span></span>|<span data-ttu-id="65464-111">`SetUnhandledExceptionPolicy`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="65464-111">`SetUnhandledExceptionPolicy` returned successfully.</span></span>|  
|<span data-ttu-id="65464-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="65464-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="65464-113">CLR 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="65464-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="65464-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="65464-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="65464-115">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="65464-115">The call timed out.</span></span>|  
|<span data-ttu-id="65464-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="65464-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="65464-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="65464-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="65464-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="65464-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="65464-119">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="65464-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="65464-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="65464-120">E_FAIL</span></span>|<span data-ttu-id="65464-121">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="65464-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="65464-122">方法返回 E_FAIL 后，CLR 不再进程内中使用。</span><span class="sxs-lookup"><span data-stu-id="65464-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="65464-123">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="65464-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="65464-124">备注</span><span class="sxs-lookup"><span data-stu-id="65464-124">Remarks</span></span>  
 <span data-ttu-id="65464-125">默认情况下，CLR 的最后一个处理程序所有未经处理的异常，并且其默认行为是关闭进程。</span><span class="sxs-lookup"><span data-stu-id="65464-125">By default, the CLR is the final handler for all unhandled exceptions, and its default behavior is to tear down the process.</span></span> <span data-ttu-id="65464-126">主机可以更改此行为，通过设置`policy`eHostDeterminedPolicy 的值。</span><span class="sxs-lookup"><span data-stu-id="65464-126">The host can change this behavior by setting the `policy` value to eHostDeterminedPolicy.</span></span> <span data-ttu-id="65464-127">此值允许宿主实现其自己的默认行为，与早期版本的 CLR。</span><span class="sxs-lookup"><span data-stu-id="65464-127">This value allows the host to implement its own default behavior, as with earlier versions of the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="65464-128">惠?</span><span class="sxs-lookup"><span data-stu-id="65464-128">Requirements</span></span>  
 <span data-ttu-id="65464-129">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="65464-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="65464-130">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="65464-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="65464-131">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="65464-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="65464-132">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="65464-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65464-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="65464-133">See Also</span></span>  
 [<span data-ttu-id="65464-134">EClrUnhandledException 枚举</span><span class="sxs-lookup"><span data-stu-id="65464-134">EClrUnhandledException Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrunhandledexception-enumeration.md)  
 [<span data-ttu-id="65464-135">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="65464-135">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="65464-136">ICLRPolicyManager 接口</span><span class="sxs-lookup"><span data-stu-id="65464-136">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 [<span data-ttu-id="65464-137">IHostPolicyManager 接口</span><span class="sxs-lookup"><span data-stu-id="65464-137">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
