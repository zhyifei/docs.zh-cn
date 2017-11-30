---
title: "IActionOnCLREvent::OnEvent 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IActionOnCLREvent.OnEvent
api_location: mscoree.dll
api_type: COM
f1_keywords: IActionOnCLREvent::OnEvent
helpviewer_keywords:
- OnEvent method [.NET Framework hosting]
- IActionOnCLREvent::OnEvent method [.NET Framework hosting]
ms.assetid: 0970f10c-4304-4c12-91c0-83e51455afb4
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b2f609969ccf67f07701d20578225f1618293968
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="iactiononclreventonevent-method"></a><span data-ttu-id="7c8d4-102">IActionOnCLREvent::OnEvent 方法</span><span class="sxs-lookup"><span data-stu-id="7c8d4-102">IActionOnCLREvent::OnEvent Method</span></span>
<span data-ttu-id="7c8d4-103">对已通过调用注册的事件执行回调[iclroneventmanager:: Registeractiononevent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="7c8d4-103">Performs callbacks on events that have been registered by using a call to the [ICLROnEventManager::RegisterActionOnEvent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c8d4-104">语法</span><span class="sxs-lookup"><span data-stu-id="7c8d4-104">Syntax</span></span>  
  
```  
HRESULT OnEvent (  
    [in] EClrEvent event,  
    [in] PVOID     data  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7c8d4-105">参数</span><span class="sxs-lookup"><span data-stu-id="7c8d4-105">Parameters</span></span>  
 `event`  
 <span data-ttu-id="7c8d4-106">[in]之一[EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)值，该值指示事件的类型。</span><span class="sxs-lookup"><span data-stu-id="7c8d4-106">[in] One of the [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) values, which indicates the type of event.</span></span>  
  
 `data`  
 <span data-ttu-id="7c8d4-107">[in]指向包含有关的详细信息的对象的指针`event`。</span><span class="sxs-lookup"><span data-stu-id="7c8d4-107">[in] A pointer to an object that contains details about `event`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7c8d4-108">返回值</span><span class="sxs-lookup"><span data-stu-id="7c8d4-108">Return Value</span></span>  
  
|<span data-ttu-id="7c8d4-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7c8d4-109">HRESULT</span></span>|<span data-ttu-id="7c8d4-110">描述</span><span class="sxs-lookup"><span data-stu-id="7c8d4-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7c8d4-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="7c8d4-111">S_OK</span></span>|<span data-ttu-id="7c8d4-112">`OnEvent`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="7c8d4-112">`OnEvent` returned successfully.</span></span>|  
|<span data-ttu-id="7c8d4-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7c8d4-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7c8d4-114">公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="7c8d4-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7c8d4-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7c8d4-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7c8d4-116">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="7c8d4-116">The call timed out.</span></span>|  
|<span data-ttu-id="7c8d4-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7c8d4-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7c8d4-118">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="7c8d4-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7c8d4-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7c8d4-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7c8d4-120">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="7c8d4-120">An event was cancelled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7c8d4-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7c8d4-121">E_FAIL</span></span>|<span data-ttu-id="7c8d4-122">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="7c8d4-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7c8d4-123">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="7c8d4-123">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7c8d4-124">对任何托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="7c8d4-124">Subsequent calls to any hosting method return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7c8d4-125">备注</span><span class="sxs-lookup"><span data-stu-id="7c8d4-125">Remarks</span></span>  
 <span data-ttu-id="7c8d4-126">`data`参数是指向未指定类型的对象的指针。</span><span class="sxs-lookup"><span data-stu-id="7c8d4-126">The `data` parameter is a pointer to an object of unspecified type.</span></span> <span data-ttu-id="7c8d4-127">如果`event`参数是`Event_DomainUnload`，`data`是的数值标识符<xref:System.AppDomain>，已被卸载。</span><span class="sxs-lookup"><span data-stu-id="7c8d4-127">If the `event` parameter is `Event_DomainUnload`, `data` is the numeric identifier for the <xref:System.AppDomain> that was unloaded.</span></span> <span data-ttu-id="7c8d4-128">主机可以采取相应的操作使用此标识符作为键。</span><span class="sxs-lookup"><span data-stu-id="7c8d4-128">The host can take appropriate action using this identifier as a key.</span></span>  
  
 <span data-ttu-id="7c8d4-129">如果`event`是`Event_MDAFired`，`data`是一个指向[MDAInfo](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md)实例，其中包含的消息输出从托管调试助手 (MDA)。</span><span class="sxs-lookup"><span data-stu-id="7c8d4-129">If `event` is `Event_MDAFired`, `data` is a pointer to an [MDAInfo](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md) instance that contains the message output from a Managed Debugging Assistant (MDA).</span></span> <span data-ttu-id="7c8d4-130">Mda 是调试后，生成有关难以否则捕获的事件的 XML 消息来帮助开发人员的 CLR 的功能。</span><span class="sxs-lookup"><span data-stu-id="7c8d4-130">MDAs are a feature of the CLR that help developers with debugging, by generating XML messages about events that are otherwise difficult to trap.</span></span> <span data-ttu-id="7c8d4-131">此类消息可能在调试托管和非托管代码之间的转换中特别有用。</span><span class="sxs-lookup"><span data-stu-id="7c8d4-131">Such messages can be especially useful in debugging transitions between managed and unmanaged code.</span></span> <span data-ttu-id="7c8d4-132">有关详细信息，请参阅[使用托管调试助手诊断错误](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)。</span><span class="sxs-lookup"><span data-stu-id="7c8d4-132">For more information, see [Diagnosing Errors with Managed Debugging Assistants](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c8d4-133">要求</span><span class="sxs-lookup"><span data-stu-id="7c8d4-133">Requirements</span></span>  
 <span data-ttu-id="7c8d4-134">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7c8d4-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c8d4-135">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7c8d4-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7c8d4-136">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="7c8d4-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7c8d4-137">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c8d4-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c8d4-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7c8d4-138">See Also</span></span>  
 [<span data-ttu-id="7c8d4-139">使用托管调试助手诊断错误</span><span class="sxs-lookup"><span data-stu-id="7c8d4-139">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [<span data-ttu-id="7c8d4-140">EClrEvent 枚举</span><span class="sxs-lookup"><span data-stu-id="7c8d4-140">EClrEvent Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)  
 [<span data-ttu-id="7c8d4-141">IActionOnCLREvent 接口</span><span class="sxs-lookup"><span data-stu-id="7c8d4-141">IActionOnCLREvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)  
 [<span data-ttu-id="7c8d4-142">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="7c8d4-142">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="7c8d4-143">ICLROnEventManager 接口</span><span class="sxs-lookup"><span data-stu-id="7c8d4-143">ICLROnEventManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)  
 [<span data-ttu-id="7c8d4-144">MDAInfo 结构</span><span class="sxs-lookup"><span data-stu-id="7c8d4-144">MDAInfo Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md)
