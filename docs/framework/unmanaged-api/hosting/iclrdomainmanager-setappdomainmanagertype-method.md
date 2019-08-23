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
ms.openlocfilehash: 9b142f1a05036eddf44c69d8b7da95091dc8f445
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963095"
---
# <a name="iclrdomainmanagersetappdomainmanagertype-method"></a><span data-ttu-id="77df4-102">ICLRDomainManager::SetAppDomainManagerType 方法</span><span class="sxs-lookup"><span data-stu-id="77df4-102">ICLRDomainManager::SetAppDomainManagerType Method</span></span>
<span data-ttu-id="77df4-103">指定从<xref:System.AppDomainManager?displayProperty=nameWithType>类派生的、将用于初始化默认应用程序域的应用程序域管理器的类型。</span><span class="sxs-lookup"><span data-stu-id="77df4-103">Specifies the type, derived from the <xref:System.AppDomainManager?displayProperty=nameWithType> class, of the application domain manager that will be used to initialize the default application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77df4-104">语法</span><span class="sxs-lookup"><span data-stu-id="77df4-104">Syntax</span></span>  
  
```cpp  
HRESULT SetAppDomainManagerType(  
    [in] LPCWSTR wszAppDomainManagerAssembly,  
    [in] LPCWSTR wszAppDomainManagerType,  
    [in] EInitializeNewDomainFlags dwInitializeDomainFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="77df4-105">参数</span><span class="sxs-lookup"><span data-stu-id="77df4-105">Parameters</span></span>  
 `wszAppDomainManagerAssembly`  
 <span data-ttu-id="77df4-106">中包含应用程序域管理器类型的程序集的显示名称;例如:"AdMgrExample, Version = 1.0.0.0, Culture = 中立, PublicKeyToken = 6856bccf150f00b3"。</span><span class="sxs-lookup"><span data-stu-id="77df4-106">[in] The display name of the assembly that contains the application domain manager type; for example: "AdMgrExample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6856bccf150f00b3".</span></span>  
  
 `wszAppDomainManagerType`  
 <span data-ttu-id="77df4-107">中应用程序域管理器的类型名称, 包括命名空间。</span><span class="sxs-lookup"><span data-stu-id="77df4-107">[in] The type name of the application domain manager, including the namespace.</span></span>  
  
 `dwInitializeDomainFlags`  
 <span data-ttu-id="77df4-108">中[EInitializeNewDomainFlags](../../../../docs/framework/unmanaged-api/hosting/einitializenewdomainflags-enumeration.md)枚举值的组合, 提供有关应用程序域管理器的信息。</span><span class="sxs-lookup"><span data-stu-id="77df4-108">[in] A combination of [EInitializeNewDomainFlags](../../../../docs/framework/unmanaged-api/hosting/einitializenewdomainflags-enumeration.md) enumeration values that provide information about the application domain manager.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="77df4-109">返回值</span><span class="sxs-lookup"><span data-stu-id="77df4-109">Return Value</span></span>  
 <span data-ttu-id="77df4-110">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="77df4-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="77df4-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="77df4-111">HRESULT</span></span>|<span data-ttu-id="77df4-112">描述</span><span class="sxs-lookup"><span data-stu-id="77df4-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="77df4-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="77df4-113">S_OK</span></span>|<span data-ttu-id="77df4-114">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="77df4-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="77df4-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="77df4-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="77df4-116">公共语言运行时 (CLR) 未加载到进程中, 或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="77df4-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="77df4-117">备注</span><span class="sxs-lookup"><span data-stu-id="77df4-117">Remarks</span></span>  
 <span data-ttu-id="77df4-118">目前, 的唯一定义的值`dwInitializeDomainFlags`为`eInitializeNewDomainFlags_NoSecurityChanges`, 它指示公共语言运行时 (CLR), 应用程序域管理器在执行<xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType>方法期间将不会修改安全设置。</span><span class="sxs-lookup"><span data-stu-id="77df4-118">Currently, the only defined value for `dwInitializeDomainFlags` is `eInitializeNewDomainFlags_NoSecurityChanges`, which tells the common language runtime (CLR) that the application domain manager will not modify security settings during the execution of the <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="77df4-119">这样, CLR 就可以优化具有条件<xref:System.Security.AllowPartiallyTrustedCallersAttribute> (APTCA) 属性的程序集的加载。</span><span class="sxs-lookup"><span data-stu-id="77df4-119">This allows the CLR to optimize the loading of assemblies that have the conditional <xref:System.Security.AllowPartiallyTrustedCallersAttribute> (APTCA) attribute.</span></span> <span data-ttu-id="77df4-120">如果这组程序集的可传递闭包很大, 则这可能会显著提高启动时间。</span><span class="sxs-lookup"><span data-stu-id="77df4-120">This can result in a significant improvement in startup time if the transitive closure of this set of assemblies is large.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="77df4-121">如果主机为应用`eInitializeNewDomainFlags_NoSecurityChanges`程序域管理器指定了<xref:System.InvalidOperationException> , 则如果尝试修改应用程序域的安全性, 则会引发。</span><span class="sxs-lookup"><span data-stu-id="77df4-121">If the host specifies `eInitializeNewDomainFlags_NoSecurityChanges` for the application domain manager, an <xref:System.InvalidOperationException> is thrown if any attempt is made to modify the security of the application domain.</span></span>  
  
 <span data-ttu-id="77df4-122">调用[ICLRControl:: SetAppDomainManagerType](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)方法等效于调用`ICLRDomainManager::SetAppDomainManagerType`。 `eInitializeNewDomainFlags_None`</span><span class="sxs-lookup"><span data-stu-id="77df4-122">Calling the [ICLRControl::SetAppDomainManagerType](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)method is equivalent to calling `ICLRDomainManager::SetAppDomainManagerType` with `eInitializeNewDomainFlags_None`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="77df4-123">要求</span><span class="sxs-lookup"><span data-stu-id="77df4-123">Requirements</span></span>  
 <span data-ttu-id="77df4-124">**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="77df4-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="77df4-125">**标头：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="77df4-125">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="77df4-126">**类库**作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="77df4-126">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="77df4-127">**.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="77df4-127">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77df4-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="77df4-128">See also</span></span>

- [<span data-ttu-id="77df4-129">承载</span><span class="sxs-lookup"><span data-stu-id="77df4-129">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
- [<span data-ttu-id="77df4-130">ICLRDomainManager 接口</span><span class="sxs-lookup"><span data-stu-id="77df4-130">ICLRDomainManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-interface.md)
- [<span data-ttu-id="77df4-131">EInitializeNewDomainFlags 枚举</span><span class="sxs-lookup"><span data-stu-id="77df4-131">EInitializeNewDomainFlags Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/einitializenewdomainflags-enumeration.md)
