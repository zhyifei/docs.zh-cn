---
title: ICorRuntimeHost 接口
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost
helpviewer_keywords:
- ICorRuntimeHost interface [.NET Framework hosting]
ms.assetid: 4369533d-7834-4497-bc37-bfea0ad737b1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ecf6bff10e98ab7f008cfd176f59687f34d89553
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/05/2018
ms.locfileid: "43784771"
---
# <a name="icorruntimehost-interface"></a><span data-ttu-id="80936-102">ICorRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="80936-102">ICorRuntimeHost Interface</span></span>
<span data-ttu-id="80936-103">提供了使宿主能够启动和停止公共语言运行时 (CLR) 明确，若要创建和配置应用程序域，若要访问默认域，并要枚举的进程中运行的所有域的方法。</span><span class="sxs-lookup"><span data-stu-id="80936-103">Provides methods that enable the host to start and stop the common language runtime (CLR) explicitly, to create and configure application domains, to access the default domain, and to enumerate all domains running in the process.</span></span>  
  
 <span data-ttu-id="80936-104">在.NET Framework 2.0 版中，此接口被取代[ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)。</span><span class="sxs-lookup"><span data-stu-id="80936-104">In the .NET Framework version 2.0, this interface is superceded by [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="80936-105">方法</span><span class="sxs-lookup"><span data-stu-id="80936-105">Methods</span></span>  
  
|<span data-ttu-id="80936-106">方法</span><span class="sxs-lookup"><span data-stu-id="80936-106">Method</span></span>|<span data-ttu-id="80936-107">描述</span><span class="sxs-lookup"><span data-stu-id="80936-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="80936-108">CloseEnum 方法</span><span class="sxs-lookup"><span data-stu-id="80936-108">CloseEnum Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-closeenum-method.md)|<span data-ttu-id="80936-109">将域枚举数重置回域列表的开头。</span><span class="sxs-lookup"><span data-stu-id="80936-109">Resets a domain enumerator back to the beginning of the domain list.</span></span>|  
|[<span data-ttu-id="80936-110">CreateDomain 方法</span><span class="sxs-lookup"><span data-stu-id="80936-110">CreateDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md)|<span data-ttu-id="80936-111">创建应用程序域。</span><span class="sxs-lookup"><span data-stu-id="80936-111">Creates an application domain.</span></span> <span data-ttu-id="80936-112">调用方会接收类型的接口指针<xref:System._AppDomain>类型的实例到<xref:System.AppDomain?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="80936-112">The caller receives an interface pointer of type <xref:System._AppDomain> to an instance of type <xref:System.AppDomain?displayProperty=nameWithType>.</span></span>|  
|[<span data-ttu-id="80936-113">CreateDomainEx 方法</span><span class="sxs-lookup"><span data-stu-id="80936-113">CreateDomainEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md)|<span data-ttu-id="80936-114">创建应用程序域。</span><span class="sxs-lookup"><span data-stu-id="80936-114">Creates an application domain.</span></span> <span data-ttu-id="80936-115">此方法允许调用方传递一个 IAppDomainSetup 实例，以便配置所返回的其他功能<xref:System._AppDomain>实例。</span><span class="sxs-lookup"><span data-stu-id="80936-115">This method allows the caller to pass an IAppDomainSetup instance to configure additional features of the returned <xref:System._AppDomain> instance.</span></span>|  
|[<span data-ttu-id="80936-116">CreateDomainSetup 方法</span><span class="sxs-lookup"><span data-stu-id="80936-116">CreateDomainSetup Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainsetup-method.md)|<span data-ttu-id="80936-117">获取类型的接口指针`IAppDomainSetup`到<xref:System.AppDomainSetup>实例。</span><span class="sxs-lookup"><span data-stu-id="80936-117">Gets an interface pointer of type `IAppDomainSetup` to an <xref:System.AppDomainSetup> instance.</span></span> <span data-ttu-id="80936-118">`IAppDomainSetup` 提供方法来配置方面的应用程序域，然后创建它。</span><span class="sxs-lookup"><span data-stu-id="80936-118">`IAppDomainSetup` provides methods to configure aspects of an application domain before it is created.</span></span>|  
|[<span data-ttu-id="80936-119">CreateEvidence 方法</span><span class="sxs-lookup"><span data-stu-id="80936-119">CreateEvidence Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createevidence-method.md)|<span data-ttu-id="80936-120">获取类型的接口指针<xref:System.Security.Principal.IIdentity>，它允许主机来创建安全证据要传递给[CreateDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md)或[CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md)。</span><span class="sxs-lookup"><span data-stu-id="80936-120">Gets an interface pointer of type <xref:System.Security.Principal.IIdentity>, which allows the host to create security evidence to pass to [CreateDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md) or [CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md).</span></span>|  
|[<span data-ttu-id="80936-121">CreateLogicalThreadState 方法</span><span class="sxs-lookup"><span data-stu-id="80936-121">CreateLogicalThreadState Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createlogicalthreadstate-method.md)|<span data-ttu-id="80936-122">请勿使用。</span><span class="sxs-lookup"><span data-stu-id="80936-122">Do not use.</span></span>|  
|[<span data-ttu-id="80936-123">CurrentDomain 方法</span><span class="sxs-lookup"><span data-stu-id="80936-123">CurrentDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-currentdomain-method.md)|<span data-ttu-id="80936-124">获取类型的接口指针<xref:System._AppDomain>，表示当前线程上加载的域。</span><span class="sxs-lookup"><span data-stu-id="80936-124">Gets an interface pointer of type <xref:System._AppDomain> that represents the domain loaded on the current thread.</span></span>|  
|[<span data-ttu-id="80936-125">DeleteLogicalThreadState 方法</span><span class="sxs-lookup"><span data-stu-id="80936-125">DeleteLogicalThreadState Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-deletelogicalthreadstate-method.md)|<span data-ttu-id="80936-126">请勿使用。</span><span class="sxs-lookup"><span data-stu-id="80936-126">Do not use.</span></span>|  
|[<span data-ttu-id="80936-127">EnumDomains 方法</span><span class="sxs-lookup"><span data-stu-id="80936-127">EnumDomains Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-enumdomains-method.md)|<span data-ttu-id="80936-128">域当前进程中获取一个枚举器。</span><span class="sxs-lookup"><span data-stu-id="80936-128">Gets an enumerator for the domains in the current process.</span></span>|  
|[<span data-ttu-id="80936-129">GetConfiguration 方法</span><span class="sxs-lookup"><span data-stu-id="80936-129">GetConfiguration Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-getconfiguration-method.md)|<span data-ttu-id="80936-130">获取允许指定的 CLR 回调配置主机的对象。</span><span class="sxs-lookup"><span data-stu-id="80936-130">Gets an object that allows the host to specify the callback configuration of the CLR.</span></span>|  
|[<span data-ttu-id="80936-131">GetDefaultDomain 方法</span><span class="sxs-lookup"><span data-stu-id="80936-131">GetDefaultDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-getdefaultdomain-method.md)|<span data-ttu-id="80936-132">获取类型的接口指针<xref:System._AppDomain>，表示当前进程的默认域。</span><span class="sxs-lookup"><span data-stu-id="80936-132">Gets an interface pointer of type <xref:System._AppDomain> that represents the default domain for the current process.</span></span>|  
|[<span data-ttu-id="80936-133">LocksHeldByLogicalThread 方法</span><span class="sxs-lookup"><span data-stu-id="80936-133">LocksHeldByLogicalThread Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-locksheldbylogicalthread-method.md)|<span data-ttu-id="80936-134">请勿使用。</span><span class="sxs-lookup"><span data-stu-id="80936-134">Do not use.</span></span>|  
|[<span data-ttu-id="80936-135">MapFile 方法</span><span class="sxs-lookup"><span data-stu-id="80936-135">MapFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-mapfile-method.md)|<span data-ttu-id="80936-136">将指定的文件映射到内存中。</span><span class="sxs-lookup"><span data-stu-id="80936-136">Maps the specified file into memory.</span></span> <span data-ttu-id="80936-137">此方法已过时。</span><span class="sxs-lookup"><span data-stu-id="80936-137">This method is obsolete.</span></span>|  
|[<span data-ttu-id="80936-138">NextDomain 方法</span><span class="sxs-lookup"><span data-stu-id="80936-138">NextDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-nextdomain-method.md)|<span data-ttu-id="80936-139">获取到下一个域中枚举的接口指针。</span><span class="sxs-lookup"><span data-stu-id="80936-139">Gets an interface pointer to the next domain in the enumeration.</span></span>|  
|[<span data-ttu-id="80936-140">Start 方法</span><span class="sxs-lookup"><span data-stu-id="80936-140">Start Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-start-method.md)|<span data-ttu-id="80936-141">启动 CLR。</span><span class="sxs-lookup"><span data-stu-id="80936-141">Starts the CLR.</span></span>|  
|[<span data-ttu-id="80936-142">Stop 方法</span><span class="sxs-lookup"><span data-stu-id="80936-142">Stop Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-stop-method.md)|<span data-ttu-id="80936-143">停止执行当前进程的运行时中的代码。</span><span class="sxs-lookup"><span data-stu-id="80936-143">Stops the execution of code in the runtime for the current process.</span></span>|  
|[<span data-ttu-id="80936-144">SwitchInLogicalThreadState 方法</span><span class="sxs-lookup"><span data-stu-id="80936-144">SwitchInLogicalThreadState Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-switchinlogicalthreadstate-method.md)|<span data-ttu-id="80936-145">请勿使用。</span><span class="sxs-lookup"><span data-stu-id="80936-145">Do not use.</span></span>|  
|[<span data-ttu-id="80936-146">SwitchOutLogicalThreadState 方法</span><span class="sxs-lookup"><span data-stu-id="80936-146">SwitchOutLogicalThreadState Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-switchoutlogicalthreadstate-method.md)|<span data-ttu-id="80936-147">请勿使用。</span><span class="sxs-lookup"><span data-stu-id="80936-147">Do not use.</span></span>|  
|[<span data-ttu-id="80936-148">UnloadDomain 方法</span><span class="sxs-lookup"><span data-stu-id="80936-148">UnloadDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-unloaddomain-method.md)|<span data-ttu-id="80936-149">卸载当前的过程中指定的应用程序域。</span><span class="sxs-lookup"><span data-stu-id="80936-149">Unloads the specified application domain from the current process.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="80936-150">要求</span><span class="sxs-lookup"><span data-stu-id="80936-150">Requirements</span></span>  
 <span data-ttu-id="80936-151">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="80936-151">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="80936-152">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="80936-152">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="80936-153">**库：** 作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="80936-153">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="80936-154">**.NET framework 版本：** 1.0、 1.1</span><span class="sxs-lookup"><span data-stu-id="80936-154">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80936-155">请参阅</span><span class="sxs-lookup"><span data-stu-id="80936-155">See Also</span></span>  
 <xref:System.AppDomain>  
 [<span data-ttu-id="80936-156">承载</span><span class="sxs-lookup"><span data-stu-id="80936-156">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)  
 [<span data-ttu-id="80936-157">ICLRRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="80936-157">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)  
 [<span data-ttu-id="80936-158">运行时主机</span><span class="sxs-lookup"><span data-stu-id="80936-158">Runtime Hosts</span></span>](https://msdn.microsoft.com/library/99d9246a-b994-4fe5-985c-8588d1d59998)  
 [<span data-ttu-id="80936-159">承载接口</span><span class="sxs-lookup"><span data-stu-id="80936-159">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="80936-160">CorRuntimeHost 组件类</span><span class="sxs-lookup"><span data-stu-id="80936-160">CorRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
