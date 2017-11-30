---
title: "ICLRDomainManager::SetAppDomainManagerType 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDomainManager.SetAppDomainManagerType
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRDomainManager::SetAppDomainManagerType
helpviewer_keywords:
- SetAppDomainManagerType method, ICLRDomainManager interface [.NET Framework hosting]
- ICLRDomainManager::SetAppDomainManagerType method [.NET Framework hosting]
ms.assetid: ee91abb0-cb74-41dd-927b-e117fb8ffdf4
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 17c99d21155d8f985ea455e171067855edcafedc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="iclrdomainmanagersetappdomainmanagertype-method"></a><span data-ttu-id="9c85a-102">ICLRDomainManager::SetAppDomainManagerType 方法</span><span class="sxs-lookup"><span data-stu-id="9c85a-102">ICLRDomainManager::SetAppDomainManagerType Method</span></span>
<span data-ttu-id="9c85a-103">指定的类型，派生自<xref:System.AppDomainManager?displayProperty=nameWithType>类，用于初始化默认应用程序域的应用程序域管理器。</span><span class="sxs-lookup"><span data-stu-id="9c85a-103">Specifies the type, derived from the <xref:System.AppDomainManager?displayProperty=nameWithType> class, of the application domain manager that will be used to initialize the default application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c85a-104">语法</span><span class="sxs-lookup"><span data-stu-id="9c85a-104">Syntax</span></span>  
  
```  
HRESULT SetAppDomainManagerType(  
    [in] LPCWSTR wszAppDomainManagerAssembly,  
    [in] LPCWSTR wszAppDomainManagerType,  
    [in] EInitializeNewDomainFlags dwInitializeDomainFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9c85a-105">参数</span><span class="sxs-lookup"><span data-stu-id="9c85a-105">Parameters</span></span>  
 `wszAppDomainManagerAssembly`  
 <span data-ttu-id="9c85a-106">[in]包含应用程序域管理器类型; 程序集的显示名称例如:"AdMgrExample，Version = 1.0.0.0，Culture = neutral，PublicKeyToken = 6856bccf150f00b3"。</span><span class="sxs-lookup"><span data-stu-id="9c85a-106">[in] The display name of the assembly that contains the application domain manager type; for example: "AdMgrExample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6856bccf150f00b3".</span></span>  
  
 `wszAppDomainManagerType`  
 <span data-ttu-id="9c85a-107">[in]应用程序域管理器，包括命名空间的类型名称。</span><span class="sxs-lookup"><span data-stu-id="9c85a-107">[in] The type name of the application domain manager, including the namespace.</span></span>  
  
 `dwInitializeDomainFlags`  
 <span data-ttu-id="9c85a-108">[in]组合[EInitializeNewDomainFlags](../../../../docs/framework/unmanaged-api/hosting/einitializenewdomainflags-enumeration.md)提供有关应用程序域管理器的信息的枚举值。</span><span class="sxs-lookup"><span data-stu-id="9c85a-108">[in] A combination of [EInitializeNewDomainFlags](../../../../docs/framework/unmanaged-api/hosting/einitializenewdomainflags-enumeration.md) enumeration values that provide information about the application domain manager.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9c85a-109">返回值</span><span class="sxs-lookup"><span data-stu-id="9c85a-109">Return Value</span></span>  
 <span data-ttu-id="9c85a-110">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="9c85a-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="9c85a-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9c85a-111">HRESULT</span></span>|<span data-ttu-id="9c85a-112">描述</span><span class="sxs-lookup"><span data-stu-id="9c85a-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9c85a-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="9c85a-113">S_OK</span></span>|<span data-ttu-id="9c85a-114">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="9c85a-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="9c85a-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9c85a-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9c85a-116">公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="9c85a-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9c85a-117">备注</span><span class="sxs-lookup"><span data-stu-id="9c85a-117">Remarks</span></span>  
 <span data-ttu-id="9c85a-118">目前，唯一定义的值为`dwInitializeDomainFlags`是`eInitializeNewDomainFlags_NoSecurityChanges`，它指示公共语言运行时 (CLR) 的应用程序域管理器执行期间将不修改安全设置<xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType>方法。</span><span class="sxs-lookup"><span data-stu-id="9c85a-118">Currently, the only defined value for `dwInitializeDomainFlags` is `eInitializeNewDomainFlags_NoSecurityChanges`, which tells the common language runtime (CLR) that the application domain manager will not modify security settings during the execution of the <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="9c85a-119">这允许以优化的有条件的程序集加载的 CLR <xref:System.Security.AllowPartiallyTrustedCallersAttribute> (APTCA) 特性。</span><span class="sxs-lookup"><span data-stu-id="9c85a-119">This allows the CLR to optimize the loading of assemblies that have the conditional <xref:System.Security.AllowPartiallyTrustedCallersAttribute> (APTCA) attribute.</span></span> <span data-ttu-id="9c85a-120">如果此集的程序集的传递闭包很大，这可能导致在启动时间的重大进步。</span><span class="sxs-lookup"><span data-stu-id="9c85a-120">This can result in a significant improvement in startup time if the transitive closure of this set of assemblies is large.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="9c85a-121">如果主机指定`eInitializeNewDomainFlags_NoSecurityChanges`对于应用程序域管理器，<xref:System.InvalidOperationException>如果尝试修改的应用程序域的安全，则引发。</span><span class="sxs-lookup"><span data-stu-id="9c85a-121">If the host specifies `eInitializeNewDomainFlags_NoSecurityChanges` for the application domain manager, an <xref:System.InvalidOperationException> is thrown if any attempt is made to modify the security of the application domain.</span></span>  
  
 <span data-ttu-id="9c85a-122">调用[iclrcontrol:: Setappdomainmanagertype](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)方法等效于调用`ICLRDomainManager::SetAppDomainManagerType`与`eInitializeNewDomainFlags_None`。</span><span class="sxs-lookup"><span data-stu-id="9c85a-122">Calling the [ICLRControl::SetAppDomainManagerType](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)method is equivalent to calling `ICLRDomainManager::SetAppDomainManagerType` with `eInitializeNewDomainFlags_None`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9c85a-123">要求</span><span class="sxs-lookup"><span data-stu-id="9c85a-123">Requirements</span></span>  
 <span data-ttu-id="9c85a-124">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9c85a-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9c85a-125">**标头：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="9c85a-125">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="9c85a-126">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="9c85a-126">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9c85a-127">**.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9c85a-127">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c85a-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9c85a-128">See Also</span></span>  
 [<span data-ttu-id="9c85a-129">承载</span><span class="sxs-lookup"><span data-stu-id="9c85a-129">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)  
 [<span data-ttu-id="9c85a-130">ICLRDomainManager 接口</span><span class="sxs-lookup"><span data-stu-id="9c85a-130">ICLRDomainManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-interface.md)  
 [<span data-ttu-id="9c85a-131">EInitializeNewDomainFlags 枚举</span><span class="sxs-lookup"><span data-stu-id="9c85a-131">EInitializeNewDomainFlags Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/einitializenewdomainflags-enumeration.md)
