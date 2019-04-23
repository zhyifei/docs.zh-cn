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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9f988084310b920907bb7f212e7d40ca0d1c91db
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59197511"
---
# <a name="iclrpolicymanagersetunhandledexceptionpolicy-method"></a><span data-ttu-id="e605d-102">ICLRPolicyManager::SetUnhandledExceptionPolicy 方法</span><span class="sxs-lookup"><span data-stu-id="e605d-102">ICLRPolicyManager::SetUnhandledExceptionPolicy Method</span></span>
<span data-ttu-id="e605d-103">发生未处理的异常时，请指定公共语言运行时 (CLR) 的行为。</span><span class="sxs-lookup"><span data-stu-id="e605d-103">Specifies the behavior of the common language runtime (CLR) when an unhandled exception occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e605d-104">语法</span><span class="sxs-lookup"><span data-stu-id="e605d-104">Syntax</span></span>  
  
```  
HRESULT SetUnhandledExceptionPolicy (  
    [in] EClrUnhandledExceptionPolicy policy  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e605d-105">参数</span><span class="sxs-lookup"><span data-stu-id="e605d-105">Parameters</span></span>  
 `policy`  
 <span data-ttu-id="e605d-106">[in]之一[EClrUnhandledException](../../../../docs/framework/unmanaged-api/hosting/eclrunhandledexception-enumeration.md)值，该值指示是否由 CLR 或主机设置行为。</span><span class="sxs-lookup"><span data-stu-id="e605d-106">[in] One of the [EClrUnhandledException](../../../../docs/framework/unmanaged-api/hosting/eclrunhandledexception-enumeration.md) values, indicating whether the behavior is set by the CLR or the host.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e605d-107">返回值</span><span class="sxs-lookup"><span data-stu-id="e605d-107">Return Value</span></span>  
  
|<span data-ttu-id="e605d-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e605d-108">HRESULT</span></span>|<span data-ttu-id="e605d-109">描述</span><span class="sxs-lookup"><span data-stu-id="e605d-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e605d-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="e605d-110">S_OK</span></span>|<span data-ttu-id="e605d-111">`SetUnhandledExceptionPolicy` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="e605d-111">`SetUnhandledExceptionPolicy` returned successfully.</span></span>|  
|<span data-ttu-id="e605d-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e605d-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e605d-113">CLR 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="e605d-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e605d-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e605d-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e605d-115">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="e605d-115">The call timed out.</span></span>|  
|<span data-ttu-id="e605d-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e605d-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e605d-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="e605d-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e605d-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e605d-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e605d-119">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="e605d-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e605d-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e605d-120">E_FAIL</span></span>|<span data-ttu-id="e605d-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="e605d-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e605d-122">方法返回 E_FAIL 后，CLR 不再在进程中使用。</span><span class="sxs-lookup"><span data-stu-id="e605d-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e605d-123">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="e605d-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e605d-124">备注</span><span class="sxs-lookup"><span data-stu-id="e605d-124">Remarks</span></span>  
 <span data-ttu-id="e605d-125">默认情况下，CLR 是所有未经处理的异常的最后一个处理程序，其默认行为是关闭进程。</span><span class="sxs-lookup"><span data-stu-id="e605d-125">By default, the CLR is the final handler for all unhandled exceptions, and its default behavior is to tear down the process.</span></span> <span data-ttu-id="e605d-126">主机可以通过设置更改此行为`policy`eHostDeterminedPolicy 的值。</span><span class="sxs-lookup"><span data-stu-id="e605d-126">The host can change this behavior by setting the `policy` value to eHostDeterminedPolicy.</span></span> <span data-ttu-id="e605d-127">此值允许主机以实现其自己的默认行为，就像 CLR 的早期版本一样。</span><span class="sxs-lookup"><span data-stu-id="e605d-127">This value allows the host to implement its own default behavior, as with earlier versions of the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e605d-128">要求</span><span class="sxs-lookup"><span data-stu-id="e605d-128">Requirements</span></span>  
 <span data-ttu-id="e605d-129">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e605d-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e605d-130">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e605d-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e605d-131">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="e605d-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e605d-132">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e605d-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e605d-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="e605d-133">See also</span></span>

- [<span data-ttu-id="e605d-134">EClrUnhandledException 枚举</span><span class="sxs-lookup"><span data-stu-id="e605d-134">EClrUnhandledException Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrunhandledexception-enumeration.md)
- [<span data-ttu-id="e605d-135">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="e605d-135">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="e605d-136">ICLRPolicyManager 接口</span><span class="sxs-lookup"><span data-stu-id="e605d-136">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="e605d-137">IHostPolicyManager 接口</span><span class="sxs-lookup"><span data-stu-id="e605d-137">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
