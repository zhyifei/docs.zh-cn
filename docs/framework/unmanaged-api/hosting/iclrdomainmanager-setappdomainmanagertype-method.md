---
title: ICLRDomainManager::SetAppDomainManagerType 方法
ms.date: 03/30/2017
api_name:
- ICLRDomainManager.SetAppDomainManagerType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDomainManager::SetAppDomainManagerType
helpviewer_keywords:
- SetAppDomainManagerType method, ICLRDomainManager interface [.NET Framework hosting]
- ICLRDomainManager::SetAppDomainManagerType method [.NET Framework hosting]
ms.assetid: ee91abb0-cb74-41dd-927b-e117fb8ffdf4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6cfef7d929d40996716a02a4db51630827011a68
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59183243"
---
# <a name="iclrdomainmanagersetappdomainmanagertype-method"></a><span data-ttu-id="fa8d8-102">ICLRDomainManager::SetAppDomainManagerType 方法</span><span class="sxs-lookup"><span data-stu-id="fa8d8-102">ICLRDomainManager::SetAppDomainManagerType Method</span></span>
<span data-ttu-id="fa8d8-103">指定的类型，派生自<xref:System.AppDomainManager?displayProperty=nameWithType>的将用来初始化默认应用程序域的应用程序域管理器类。</span><span class="sxs-lookup"><span data-stu-id="fa8d8-103">Specifies the type, derived from the <xref:System.AppDomainManager?displayProperty=nameWithType> class, of the application domain manager that will be used to initialize the default application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa8d8-104">语法</span><span class="sxs-lookup"><span data-stu-id="fa8d8-104">Syntax</span></span>  
  
```  
HRESULT SetAppDomainManagerType(  
    [in] LPCWSTR wszAppDomainManagerAssembly,  
    [in] LPCWSTR wszAppDomainManagerType,  
    [in] EInitializeNewDomainFlags dwInitializeDomainFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fa8d8-105">参数</span><span class="sxs-lookup"><span data-stu-id="fa8d8-105">Parameters</span></span>  
 `wszAppDomainManagerAssembly`  
 <span data-ttu-id="fa8d8-106">[in]包含应用程序域管理器类型、 程序集的显示名称例如："AdMgrExample，版本 = 1.0.0.0，区域性 = 中性，PublicKeyToken = 6856bccf150f00b3"。</span><span class="sxs-lookup"><span data-stu-id="fa8d8-106">[in] The display name of the assembly that contains the application domain manager type; for example: "AdMgrExample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6856bccf150f00b3".</span></span>  
  
 `wszAppDomainManagerType`  
 <span data-ttu-id="fa8d8-107">[in]应用程序域管理器，包括命名空间的类型名称。</span><span class="sxs-lookup"><span data-stu-id="fa8d8-107">[in] The type name of the application domain manager, including the namespace.</span></span>  
  
 `dwInitializeDomainFlags`  
 <span data-ttu-id="fa8d8-108">[in]组合[EInitializeNewDomainFlags](../../../../docs/framework/unmanaged-api/hosting/einitializenewdomainflags-enumeration.md)提供有关应用程序域管理器的信息的枚举值。</span><span class="sxs-lookup"><span data-stu-id="fa8d8-108">[in] A combination of [EInitializeNewDomainFlags](../../../../docs/framework/unmanaged-api/hosting/einitializenewdomainflags-enumeration.md) enumeration values that provide information about the application domain manager.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fa8d8-109">返回值</span><span class="sxs-lookup"><span data-stu-id="fa8d8-109">Return Value</span></span>  
 <span data-ttu-id="fa8d8-110">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="fa8d8-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="fa8d8-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fa8d8-111">HRESULT</span></span>|<span data-ttu-id="fa8d8-112">描述</span><span class="sxs-lookup"><span data-stu-id="fa8d8-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fa8d8-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="fa8d8-113">S_OK</span></span>|<span data-ttu-id="fa8d8-114">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="fa8d8-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="fa8d8-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="fa8d8-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="fa8d8-116">公共语言运行时 (CLR) 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="fa8d8-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fa8d8-117">备注</span><span class="sxs-lookup"><span data-stu-id="fa8d8-117">Remarks</span></span>  
 <span data-ttu-id="fa8d8-118">目前，唯一定义的值为`dwInitializeDomainFlags`是`eInitializeNewDomainFlags_NoSecurityChanges`，它将告诉公共语言运行时 (CLR) 的应用程序域管理器的执行期间将不修改安全设置<xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType>方法。</span><span class="sxs-lookup"><span data-stu-id="fa8d8-118">Currently, the only defined value for `dwInitializeDomainFlags` is `eInitializeNewDomainFlags_NoSecurityChanges`, which tells the common language runtime (CLR) that the application domain manager will not modify security settings during the execution of the <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="fa8d8-119">这样，若要优化的条件性的程序集加载的 CLR <xref:System.Security.AllowPartiallyTrustedCallersAttribute> (APTCA) 特性。</span><span class="sxs-lookup"><span data-stu-id="fa8d8-119">This allows the CLR to optimize the loading of assemblies that have the conditional <xref:System.Security.AllowPartiallyTrustedCallersAttribute> (APTCA) attribute.</span></span> <span data-ttu-id="fa8d8-120">如果此集的程序集的传递闭包很大，这可能导致启动时间得到显著提高。</span><span class="sxs-lookup"><span data-stu-id="fa8d8-120">This can result in a significant improvement in startup time if the transitive closure of this set of assemblies is large.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="fa8d8-121">如果指定了主机`eInitializeNewDomainFlags_NoSecurityChanges`应用程序域管理器中，为<xref:System.InvalidOperationException>如果尝试修改应用程序域的安全，将引发。</span><span class="sxs-lookup"><span data-stu-id="fa8d8-121">If the host specifies `eInitializeNewDomainFlags_NoSecurityChanges` for the application domain manager, an <xref:System.InvalidOperationException> is thrown if any attempt is made to modify the security of the application domain.</span></span>  
  
 <span data-ttu-id="fa8d8-122">调用[iclrcontrol:: Setappdomainmanagertype](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)方法相当于调用`ICLRDomainManager::SetAppDomainManagerType`与`eInitializeNewDomainFlags_None`。</span><span class="sxs-lookup"><span data-stu-id="fa8d8-122">Calling the [ICLRControl::SetAppDomainManagerType](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)method is equivalent to calling `ICLRDomainManager::SetAppDomainManagerType` with `eInitializeNewDomainFlags_None`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa8d8-123">要求</span><span class="sxs-lookup"><span data-stu-id="fa8d8-123">Requirements</span></span>  
 <span data-ttu-id="fa8d8-124">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="fa8d8-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa8d8-125">**标头：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="fa8d8-125">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="fa8d8-126">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="fa8d8-126">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fa8d8-127">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa8d8-127">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa8d8-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="fa8d8-128">See also</span></span>

- [<span data-ttu-id="fa8d8-129">承载</span><span class="sxs-lookup"><span data-stu-id="fa8d8-129">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
- [<span data-ttu-id="fa8d8-130">ICLRDomainManager 接口</span><span class="sxs-lookup"><span data-stu-id="fa8d8-130">ICLRDomainManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-interface.md)
- [<span data-ttu-id="fa8d8-131">EInitializeNewDomainFlags 枚举</span><span class="sxs-lookup"><span data-stu-id="fa8d8-131">EInitializeNewDomainFlags Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/einitializenewdomainflags-enumeration.md)
