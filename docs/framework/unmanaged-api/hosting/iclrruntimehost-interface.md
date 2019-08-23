---
title: ICLRRuntimeHost 接口
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost
helpviewer_keywords:
- ICLRRuntimeHost interface [.NET Framework hosting]
ms.assetid: cb0c5f65-3791-47bc-b833-2f84f4101ba5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0f159c0b57f2087b608fac8cbc9b9c64ceb063a1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965996"
---
# <a name="iclrruntimehost-interface"></a><span data-ttu-id="d550f-102">ICLRRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="d550f-102">ICLRRuntimeHost Interface</span></span>
<span data-ttu-id="d550f-103">提供与 .NET Framework 版本1中提供的[ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)接口类似的功能, 其中包含以下更改:</span><span class="sxs-lookup"><span data-stu-id="d550f-103">Provides functionality similar to that of the [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) interface provided in the .NET Framework version 1, with the following changes:</span></span>  
  
- <span data-ttu-id="d550f-104">用于设置宿主控件接口的[SetHostControl](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md)方法的添加。</span><span class="sxs-lookup"><span data-stu-id="d550f-104">The addition of the [SetHostControl](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md) method to set the host control interface.</span></span>  
  
- <span data-ttu-id="d550f-105">省略提供`ICorRuntimeHost`的某些方法。</span><span class="sxs-lookup"><span data-stu-id="d550f-105">The omission of some methods provided by `ICorRuntimeHost`.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d550f-106">方法</span><span class="sxs-lookup"><span data-stu-id="d550f-106">Methods</span></span>  
  
|<span data-ttu-id="d550f-107">方法</span><span class="sxs-lookup"><span data-stu-id="d550f-107">Method</span></span>|<span data-ttu-id="d550f-108">描述</span><span class="sxs-lookup"><span data-stu-id="d550f-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d550f-109">ExecuteApplication 方法</span><span class="sxs-lookup"><span data-stu-id="d550f-109">ExecuteApplication Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeapplication-method.md)|<span data-ttu-id="d550f-110">在基于清单的 ClickOnce 部署方案中用于指定要在新域中激活的应用程序。</span><span class="sxs-lookup"><span data-stu-id="d550f-110">Used in manifest-based ClickOnce deployment scenarios to specify the application to be activated in a new domain.</span></span>|  
|[<span data-ttu-id="d550f-111">ExecuteInAppDomain 方法</span><span class="sxs-lookup"><span data-stu-id="d550f-111">ExecuteInAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeinappdomain-method.md)|<span data-ttu-id="d550f-112">指定要<xref:System.AppDomain>在其中执行指定的托管代码的。</span><span class="sxs-lookup"><span data-stu-id="d550f-112">Specifies the <xref:System.AppDomain> in which to execute the specified managed code.</span></span>|  
|[<span data-ttu-id="d550f-113">ExecuteInDefaultAppDomain 方法</span><span class="sxs-lookup"><span data-stu-id="d550f-113">ExecuteInDefaultAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeindefaultappdomain-method.md)|<span data-ttu-id="d550f-114">在指定的程序集中调用指定类型的指定方法。</span><span class="sxs-lookup"><span data-stu-id="d550f-114">Invokes the specified method of the specified type in the specified assembly.</span></span>|  
|[<span data-ttu-id="d550f-115">GetCLRControl 方法</span><span class="sxs-lookup"><span data-stu-id="d550f-115">GetCLRControl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getclrcontrol-method.md)|<span data-ttu-id="d550f-116">获取宿主可用于自定义公共语言运行时 (CLR) 的各个方面的[ICLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)类型的接口指针。</span><span class="sxs-lookup"><span data-stu-id="d550f-116">Gets an interface pointer of type [ICLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) that hosts can use to customize aspects of the common language runtime (CLR).</span></span>|  
|[<span data-ttu-id="d550f-117">GetCurrentAppDomainId 方法</span><span class="sxs-lookup"><span data-stu-id="d550f-117">GetCurrentAppDomainId Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md)|<span data-ttu-id="d550f-118">获取当前正在执行的的<xref:System.AppDomain>数值标识符。</span><span class="sxs-lookup"><span data-stu-id="d550f-118">Gets the numeric identifier of the <xref:System.AppDomain> that is currently executing.</span></span>|  
|[<span data-ttu-id="d550f-119">SetHostControl 方法</span><span class="sxs-lookup"><span data-stu-id="d550f-119">SetHostControl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md)|<span data-ttu-id="d550f-120">设置宿主控件接口。</span><span class="sxs-lookup"><span data-stu-id="d550f-120">Sets the host control interface.</span></span> <span data-ttu-id="d550f-121">`SetHostControl` 调用`Start`之前必须调用。</span><span class="sxs-lookup"><span data-stu-id="d550f-121">You must call `SetHostControl` before calling `Start`.</span></span>|  
|[<span data-ttu-id="d550f-122">Start 方法</span><span class="sxs-lookup"><span data-stu-id="d550f-122">Start Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md)|<span data-ttu-id="d550f-123">将 CLR 初始化为一个进程。</span><span class="sxs-lookup"><span data-stu-id="d550f-123">Initializes the CLR into a process.</span></span>|  
|[<span data-ttu-id="d550f-124">Stop 方法</span><span class="sxs-lookup"><span data-stu-id="d550f-124">Stop Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-stop-method.md)|<span data-ttu-id="d550f-125">停止由运行时执行的代码。</span><span class="sxs-lookup"><span data-stu-id="d550f-125">Stops the execution of code by the runtime.</span></span>|  
|[<span data-ttu-id="d550f-126">UnloadAppDomain 方法</span><span class="sxs-lookup"><span data-stu-id="d550f-126">UnloadAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-unloadappdomain-method.md)|<span data-ttu-id="d550f-127"><xref:System.AppDomain>卸载对应于指定数值标识符的。</span><span class="sxs-lookup"><span data-stu-id="d550f-127">Unloads the <xref:System.AppDomain> that corresponds to the specified numeric identifier.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d550f-128">备注</span><span class="sxs-lookup"><span data-stu-id="d550f-128">Remarks</span></span>  
 <span data-ttu-id="d550f-129">从 .NET Framework 4 开始, 使用[ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)接口获取指向[ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)接口的指针, 然后调用[ICLRRuntimeInfo:: GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md)方法`ICLRRuntimeHost`以获取指向的指针。</span><span class="sxs-lookup"><span data-stu-id="d550f-129">Starting with the .NET Framework 4, use the [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md) interface to get a pointer to the [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface, and then call the [ICLRRuntimeInfo::GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) method to get a pointer to `ICLRRuntimeHost`.</span></span> <span data-ttu-id="d550f-130">在 .NET Framework 的早期版本中, 主机通过调用[CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)或[CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)获取`ICLRRuntimeHost`指向实例的指针。</span><span class="sxs-lookup"><span data-stu-id="d550f-130">In earlier versions of the .NET Framework, the host gets a pointer to an `ICLRRuntimeHost` instance by calling [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) or [CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md).</span></span> <span data-ttu-id="d550f-131">若要提供 .NET Framework 版本2.0 中提供的任何技术的实现, 必须使用`ICLRRuntimeHost` `ICorRuntimeHost`而不是。</span><span class="sxs-lookup"><span data-stu-id="d550f-131">To provide implementations of any of the technologies provided in the .NET Framework version 2.0, you must use `ICLRRuntimeHost` instead of `ICorRuntimeHost`.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="d550f-132">请不要在调用[ExecuteApplication](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeapplication-method.md)方法之前调用[Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md)方法来激活基于清单的应用程序。</span><span class="sxs-lookup"><span data-stu-id="d550f-132">Do not call the [Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) method before calling the [ExecuteApplication](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeapplication-method.md) method to activate a manifest-based application.</span></span> <span data-ttu-id="d550f-133">如果首先调用`ExecuteApplication`方法,方法调用将失败。 `Start`</span><span class="sxs-lookup"><span data-stu-id="d550f-133">If the `Start` method is called first, the `ExecuteApplication` method call will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d550f-134">要求</span><span class="sxs-lookup"><span data-stu-id="d550f-134">Requirements</span></span>  
 <span data-ttu-id="d550f-135">**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d550f-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d550f-136">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d550f-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d550f-137">**类库**作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="d550f-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d550f-138">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d550f-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d550f-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="d550f-139">See also</span></span>

- [<span data-ttu-id="d550f-140">CorBindToCurrentRuntime 函数</span><span class="sxs-lookup"><span data-stu-id="d550f-140">CorBindToCurrentRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)
- [<span data-ttu-id="d550f-141">CorBindToRuntimeEx 函数</span><span class="sxs-lookup"><span data-stu-id="d550f-141">CorBindToRuntimeEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)
- [<span data-ttu-id="d550f-142">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="d550f-142">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="d550f-143">ICorRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="d550f-143">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
- [<span data-ttu-id="d550f-144">承载接口</span><span class="sxs-lookup"><span data-stu-id="d550f-144">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="d550f-145">CLRRuntimeHost 组件类</span><span class="sxs-lookup"><span data-stu-id="d550f-145">CLRRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/clrruntimehost-coclass.md)
