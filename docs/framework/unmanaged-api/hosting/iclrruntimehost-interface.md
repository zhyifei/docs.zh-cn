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
ms.openlocfilehash: 95dd084520d1e93803a91f0c4d01214ed0d3744d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33436236"
---
# <a name="iclrruntimehost-interface"></a><span data-ttu-id="0669c-102">ICLRRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="0669c-102">ICLRRuntimeHost Interface</span></span>
<span data-ttu-id="0669c-103">提供的功能类似于[ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)在.NET Framework 版本 1 包含以下更改提供的接口：</span><span class="sxs-lookup"><span data-stu-id="0669c-103">Provides functionality similar to that of the [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) interface provided in the .NET Framework version 1, with the following changes:</span></span>  
  
-   <span data-ttu-id="0669c-104">添加[SetHostControl](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md)方法以设置主机控件接口。</span><span class="sxs-lookup"><span data-stu-id="0669c-104">The addition of the [SetHostControl](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md) method to set the host control interface.</span></span>  
  
-   <span data-ttu-id="0669c-105">提供一些方法省略`ICorRuntimeHost`。</span><span class="sxs-lookup"><span data-stu-id="0669c-105">The omission of some methods provided by `ICorRuntimeHost`.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0669c-106">方法</span><span class="sxs-lookup"><span data-stu-id="0669c-106">Methods</span></span>  
  
|<span data-ttu-id="0669c-107">方法</span><span class="sxs-lookup"><span data-stu-id="0669c-107">Method</span></span>|<span data-ttu-id="0669c-108">描述</span><span class="sxs-lookup"><span data-stu-id="0669c-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0669c-109">ExecuteApplication 方法</span><span class="sxs-lookup"><span data-stu-id="0669c-109">ExecuteApplication Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeapplication-method.md)|<span data-ttu-id="0669c-110">在基于清单的 ClickOnce 部署方案中用于指定要在新域中激活的应用程序。</span><span class="sxs-lookup"><span data-stu-id="0669c-110">Used in manifest-based ClickOnce deployment scenarios to specify the application to be activated in a new domain.</span></span>|  
|[<span data-ttu-id="0669c-111">ExecuteInAppDomain 方法</span><span class="sxs-lookup"><span data-stu-id="0669c-111">ExecuteInAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeinappdomain-method.md)|<span data-ttu-id="0669c-112">指定<xref:System.AppDomain>在其中执行指定的托管的代码。</span><span class="sxs-lookup"><span data-stu-id="0669c-112">Specifies the <xref:System.AppDomain> in which to execute the specified managed code.</span></span>|  
|[<span data-ttu-id="0669c-113">ExecuteInDefaultAppDomain 方法</span><span class="sxs-lookup"><span data-stu-id="0669c-113">ExecuteInDefaultAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeindefaultappdomain-method.md)|<span data-ttu-id="0669c-114">调用中指定的程序集的指定类型的指定的方法。</span><span class="sxs-lookup"><span data-stu-id="0669c-114">Invokes the specified method of the specified type in the specified assembly.</span></span>|  
|[<span data-ttu-id="0669c-115">GetCLRControl 方法</span><span class="sxs-lookup"><span data-stu-id="0669c-115">GetCLRControl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getclrcontrol-method.md)|<span data-ttu-id="0669c-116">获取类型的接口指针[ICLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)主机可用于自定义的公共语言运行时 (CLR) 方面。</span><span class="sxs-lookup"><span data-stu-id="0669c-116">Gets an interface pointer of type [ICLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) that hosts can use to customize aspects of the common language runtime (CLR).</span></span>|  
|[<span data-ttu-id="0669c-117">GetCurrentAppDomainId 方法</span><span class="sxs-lookup"><span data-stu-id="0669c-117">GetCurrentAppDomainId Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md)|<span data-ttu-id="0669c-118">获取的数字标识符<xref:System.AppDomain>，当前正在执行。</span><span class="sxs-lookup"><span data-stu-id="0669c-118">Gets the numeric identifier of the <xref:System.AppDomain> that is currently executing.</span></span>|  
|[<span data-ttu-id="0669c-119">SetHostControl 方法</span><span class="sxs-lookup"><span data-stu-id="0669c-119">SetHostControl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md)|<span data-ttu-id="0669c-120">设置主机控件接口。</span><span class="sxs-lookup"><span data-stu-id="0669c-120">Sets the host control interface.</span></span> <span data-ttu-id="0669c-121">必须调用`SetHostControl`之前调用`Start`。</span><span class="sxs-lookup"><span data-stu-id="0669c-121">You must call `SetHostControl` before calling `Start`.</span></span>|  
|[<span data-ttu-id="0669c-122">Start 方法</span><span class="sxs-lookup"><span data-stu-id="0669c-122">Start Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md)|<span data-ttu-id="0669c-123">初始化到进程中 CLR。</span><span class="sxs-lookup"><span data-stu-id="0669c-123">Initializes the CLR into a process.</span></span>|  
|[<span data-ttu-id="0669c-124">Stop 方法</span><span class="sxs-lookup"><span data-stu-id="0669c-124">Stop Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-stop-method.md)|<span data-ttu-id="0669c-125">由运行时停止执行的代码。</span><span class="sxs-lookup"><span data-stu-id="0669c-125">Stops the execution of code by the runtime.</span></span>|  
|[<span data-ttu-id="0669c-126">UnloadAppDomain 方法</span><span class="sxs-lookup"><span data-stu-id="0669c-126">UnloadAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-unloadappdomain-method.md)|<span data-ttu-id="0669c-127">卸载<xref:System.AppDomain>对应于指定的数字标识符。</span><span class="sxs-lookup"><span data-stu-id="0669c-127">Unloads the <xref:System.AppDomain> that corresponds to the specified numeric identifier.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0669c-128">备注</span><span class="sxs-lookup"><span data-stu-id="0669c-128">Remarks</span></span>  
 <span data-ttu-id="0669c-129">从开始[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]，使用[ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)接口以获取指向[ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)接口，，然后调用[iclrruntimeinfo:: Getinterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md)方法以获取指向`ICLRRuntimeHost`。</span><span class="sxs-lookup"><span data-stu-id="0669c-129">Starting with the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], use the [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md) interface to get a pointer to the [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface, and then call the [ICLRRuntimeInfo::GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) method to get a pointer to `ICLRRuntimeHost`.</span></span> <span data-ttu-id="0669c-130">在.NET framework 的早期版本，主机获取指向的指针`ICLRRuntimeHost`实例通过调用[CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)或[CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)。</span><span class="sxs-lookup"><span data-stu-id="0669c-130">In earlier versions of the .NET Framework, the host gets a pointer to an `ICLRRuntimeHost` instance by calling [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) or [CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md).</span></span> <span data-ttu-id="0669c-131">若要提供的任何.NET Framework 2.0 版中提供的技术实现，你必须使用`ICLRRuntimeHost`而不是`ICorRuntimeHost`。</span><span class="sxs-lookup"><span data-stu-id="0669c-131">To provide implementations of any of the technologies provided in the .NET Framework version 2.0, you must use `ICLRRuntimeHost` instead of `ICorRuntimeHost`.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="0669c-132">不要调用[启动](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md)方法之前调用[ExecuteApplication](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeapplication-method.md)激活基于清单的应用程序的方法。</span><span class="sxs-lookup"><span data-stu-id="0669c-132">Do not call the [Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) method before calling the [ExecuteApplication](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeapplication-method.md) method to activate a manifest-based application.</span></span> <span data-ttu-id="0669c-133">如果`Start`首先，调用方法`ExecuteApplication`方法调用将失败。</span><span class="sxs-lookup"><span data-stu-id="0669c-133">If the `Start` method is called first, the `ExecuteApplication` method call will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0669c-134">要求</span><span class="sxs-lookup"><span data-stu-id="0669c-134">Requirements</span></span>  
 <span data-ttu-id="0669c-135">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0669c-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0669c-136">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0669c-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0669c-137">**库：** 作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="0669c-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0669c-138">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0669c-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0669c-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="0669c-139">See Also</span></span>  
 [<span data-ttu-id="0669c-140">CorBindToCurrentRuntime 函数</span><span class="sxs-lookup"><span data-stu-id="0669c-140">CorBindToCurrentRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)  
 [<span data-ttu-id="0669c-141">CorBindToRuntimeEx 函数</span><span class="sxs-lookup"><span data-stu-id="0669c-141">CorBindToRuntimeEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)  
 [<span data-ttu-id="0669c-142">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="0669c-142">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="0669c-143">ICorRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="0669c-143">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)  
 [<span data-ttu-id="0669c-144">承载接口</span><span class="sxs-lookup"><span data-stu-id="0669c-144">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="0669c-145">CLRRuntimeHost 组件类</span><span class="sxs-lookup"><span data-stu-id="0669c-145">CLRRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/clrruntimehost-coclass.md)
