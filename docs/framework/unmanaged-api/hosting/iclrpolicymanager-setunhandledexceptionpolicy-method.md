---
title: ICLRPolicyManager::SetUnhandledExceptionPolicy 方法
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager.SetUnhandledExceptionPolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager::SetUnhandledExceptionPolicy
helpviewer_keywords:
- ICLRPolicyManager::SetUnhandledExceptionPolicy method [.NET Framework hosting]
- SetUnhandledExceptionPolicy method [.NET Framework hosting]
ms.assetid: 5268480e-280a-4931-b7a3-dc3ffdf7f78f
topic_type:
- apiref
ms.openlocfilehash: 7b6a4be94e526e7b464b336d221eff936808635a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120575"
---
# <a name="iclrpolicymanagersetunhandledexceptionpolicy-method"></a><span data-ttu-id="09fe0-102">ICLRPolicyManager::SetUnhandledExceptionPolicy 方法</span><span class="sxs-lookup"><span data-stu-id="09fe0-102">ICLRPolicyManager::SetUnhandledExceptionPolicy Method</span></span>
<span data-ttu-id="09fe0-103">指定在发生未经处理的异常时公共语言运行时（CLR）的行为。</span><span class="sxs-lookup"><span data-stu-id="09fe0-103">Specifies the behavior of the common language runtime (CLR) when an unhandled exception occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09fe0-104">语法</span><span class="sxs-lookup"><span data-stu-id="09fe0-104">Syntax</span></span>  
  
```cpp  
HRESULT SetUnhandledExceptionPolicy (  
    [in] EClrUnhandledExceptionPolicy policy  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="09fe0-105">参数</span><span class="sxs-lookup"><span data-stu-id="09fe0-105">Parameters</span></span>  
 `policy`  
 <span data-ttu-id="09fe0-106">中[EClrUnhandledException](../../../../docs/framework/unmanaged-api/hosting/eclrunhandledexception-enumeration.md)值之一，指示行为是由 CLR 还是宿主设置。</span><span class="sxs-lookup"><span data-stu-id="09fe0-106">[in] One of the [EClrUnhandledException](../../../../docs/framework/unmanaged-api/hosting/eclrunhandledexception-enumeration.md) values, indicating whether the behavior is set by the CLR or the host.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="09fe0-107">返回值</span><span class="sxs-lookup"><span data-stu-id="09fe0-107">Return Value</span></span>  
  
|<span data-ttu-id="09fe0-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="09fe0-108">HRESULT</span></span>|<span data-ttu-id="09fe0-109">描述</span><span class="sxs-lookup"><span data-stu-id="09fe0-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="09fe0-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="09fe0-110">S_OK</span></span>|<span data-ttu-id="09fe0-111">`SetUnhandledExceptionPolicy` 成功返回。</span><span class="sxs-lookup"><span data-stu-id="09fe0-111">`SetUnhandledExceptionPolicy` returned successfully.</span></span>|  
|<span data-ttu-id="09fe0-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="09fe0-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="09fe0-113">CLR 未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="09fe0-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="09fe0-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="09fe0-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="09fe0-115">调用超时。</span><span class="sxs-lookup"><span data-stu-id="09fe0-115">The call timed out.</span></span>|  
|<span data-ttu-id="09fe0-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="09fe0-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="09fe0-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="09fe0-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="09fe0-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="09fe0-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="09fe0-119">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="09fe0-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="09fe0-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="09fe0-120">E_FAIL</span></span>|<span data-ttu-id="09fe0-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="09fe0-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="09fe0-122">方法返回 E_FAIL 后，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="09fe0-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="09fe0-123">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="09fe0-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="09fe0-124">备注</span><span class="sxs-lookup"><span data-stu-id="09fe0-124">Remarks</span></span>  
 <span data-ttu-id="09fe0-125">默认情况下，CLR 是所有未经处理的异常的最终处理程序，其默认行为是销毁进程。</span><span class="sxs-lookup"><span data-stu-id="09fe0-125">By default, the CLR is the final handler for all unhandled exceptions, and its default behavior is to tear down the process.</span></span> <span data-ttu-id="09fe0-126">宿主可以通过将 `policy` 值设置为 eHostDeterminedPolicy 来更改此行为。</span><span class="sxs-lookup"><span data-stu-id="09fe0-126">The host can change this behavior by setting the `policy` value to eHostDeterminedPolicy.</span></span> <span data-ttu-id="09fe0-127">与早期版本的 CLR 一样，此值允许主机实现其自己的默认行为。</span><span class="sxs-lookup"><span data-stu-id="09fe0-127">This value allows the host to implement its own default behavior, as with earlier versions of the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="09fe0-128">要求</span><span class="sxs-lookup"><span data-stu-id="09fe0-128">Requirements</span></span>  
 <span data-ttu-id="09fe0-129">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="09fe0-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09fe0-130">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="09fe0-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="09fe0-131">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="09fe0-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="09fe0-132">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="09fe0-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09fe0-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="09fe0-133">See also</span></span>

- [<span data-ttu-id="09fe0-134">EClrUnhandledException 枚举</span><span class="sxs-lookup"><span data-stu-id="09fe0-134">EClrUnhandledException Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrunhandledexception-enumeration.md)
- [<span data-ttu-id="09fe0-135">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="09fe0-135">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="09fe0-136">ICLRPolicyManager 接口</span><span class="sxs-lookup"><span data-stu-id="09fe0-136">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="09fe0-137">IHostPolicyManager 接口</span><span class="sxs-lookup"><span data-stu-id="09fe0-137">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
