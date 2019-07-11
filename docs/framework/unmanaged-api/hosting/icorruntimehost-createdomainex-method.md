---
title: ICorRuntimeHost::CreateDomainEx 方法
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.CreateDomainEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::CreateDomainEx
helpviewer_keywords:
- ICorRuntimeHost::CreateDomainEx method [.NET Framework hosting]
- CreateDomainEx method [.NET Framework hosting]
ms.assetid: 1bdde382-f8ba-4cc8-94b2-d1ac919c585e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2e51c5cda8eca1737e2daab4cbe94a78433c8608
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67762112"
---
# <a name="icorruntimehostcreatedomainex-method"></a><span data-ttu-id="113c9-102">ICorRuntimeHost::CreateDomainEx 方法</span><span class="sxs-lookup"><span data-stu-id="113c9-102">ICorRuntimeHost::CreateDomainEx Method</span></span>
<span data-ttu-id="113c9-103">创建应用程序域。</span><span class="sxs-lookup"><span data-stu-id="113c9-103">Creates an application domain.</span></span> <span data-ttu-id="113c9-104">调用方会接收类型的接口指针<xref:System._AppDomain>，类型的实例到<xref:System.AppDomain?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="113c9-104">The caller receives an interface pointer, of type <xref:System._AppDomain>, to an instance of type <xref:System.AppDomain?displayProperty=nameWithType>.</span></span> <span data-ttu-id="113c9-105">此方法允许调用方传递一个 IAppDomainSetup 实例，以便配置所返回的其他功能<xref:System._AppDomain>实例。</span><span class="sxs-lookup"><span data-stu-id="113c9-105">This method allows the caller to pass an IAppDomainSetup instance to configure additional features of the returned <xref:System._AppDomain> instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="113c9-106">语法</span><span class="sxs-lookup"><span data-stu-id="113c9-106">Syntax</span></span>  
  
```cpp  
HRESULT CreateDomainEx (  
    [in] LPCWSTR     pwzFriendlyName,  
    [in] IUnknown*   pSetup,  
    [in] IUnknown*   pIdentityArray,  
    [out] IUnknown** pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="113c9-107">参数</span><span class="sxs-lookup"><span data-stu-id="113c9-107">Parameters</span></span>  
 `pwzFriendlyName`  
 <span data-ttu-id="113c9-108">[in]一个可选参数，用于为域提供一个友好名称。</span><span class="sxs-lookup"><span data-stu-id="113c9-108">[in] An optional parameter used to give a friendly name to the domain.</span></span> <span data-ttu-id="113c9-109">可以在调试器中以标识域等用户界面中显示此友好名称。</span><span class="sxs-lookup"><span data-stu-id="113c9-109">This friendly name can be displayed in user interfaces such as debuggers to identify the domain.</span></span>  
  
 `pSetup`  
 <span data-ttu-id="113c9-110">[in]类型的可选接口指针`IAppDomainSetup`，获得通过调用[icorruntimehost:: Createdomainsetup](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainsetup-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="113c9-110">[in] An optional interface pointer of type `IAppDomainSetup`, obtained by a call to the [ICorRuntimeHost::CreateDomainSetup](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainsetup-method.md) method.</span></span>  
  
 `pIdentityArray`  
 <span data-ttu-id="113c9-111">[in]一个指向指针的可选数组`IIdentity`表示映射通过安全策略，以建立一个权限集的证据的实例。</span><span class="sxs-lookup"><span data-stu-id="113c9-111">[in] An optional array of pointers to `IIdentity` instances that represent evidence mapped through security policy to establish a permission set.</span></span> <span data-ttu-id="113c9-112">`IIdentity`对象可以通过调用来获取[CreateEvidence](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createevidence-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="113c9-112">An `IIdentity` object can be obtained by calling the [CreateEvidence](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createevidence-method.md) method.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="113c9-113">[out]类型的接口指针<xref:System._AppDomain>的实例<xref:System.AppDomain?displayProperty=nameWithType>可用于进一步控制域。</span><span class="sxs-lookup"><span data-stu-id="113c9-113">[out] An interface pointer of type <xref:System._AppDomain> to an instance of <xref:System.AppDomain?displayProperty=nameWithType> that can be used to further control the domain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="113c9-114">返回值</span><span class="sxs-lookup"><span data-stu-id="113c9-114">Return Value</span></span>  
  
|<span data-ttu-id="113c9-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="113c9-115">HRESULT</span></span>|<span data-ttu-id="113c9-116">描述</span><span class="sxs-lookup"><span data-stu-id="113c9-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="113c9-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="113c9-117">S_OK</span></span>|<span data-ttu-id="113c9-118">操作成功。</span><span class="sxs-lookup"><span data-stu-id="113c9-118">The operation was successful.</span></span>|  
|<span data-ttu-id="113c9-119">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="113c9-119">S_FALSE</span></span>|<span data-ttu-id="113c9-120">该操作未能完成。</span><span class="sxs-lookup"><span data-stu-id="113c9-120">The operation failed to complete.</span></span>|  
|<span data-ttu-id="113c9-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="113c9-121">E_FAIL</span></span>|<span data-ttu-id="113c9-122">发生了未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="113c9-122">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="113c9-123">如果方法返回 E_FAIL，公共语言运行时 (CLR) 不再可在该过程中使用。</span><span class="sxs-lookup"><span data-stu-id="113c9-123">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="113c9-124">对任何托管 Api 的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="113c9-124">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="113c9-125">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="113c9-125">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="113c9-126">CLR 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="113c9-126">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="113c9-127">备注</span><span class="sxs-lookup"><span data-stu-id="113c9-127">Remarks</span></span>  
 <span data-ttu-id="113c9-128">`CreateDomainEx` 扩展的功能[CreateDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md)通过允许调用方传入`IAppDomainSetup`与用于配置应用程序域的属性值的实例。</span><span class="sxs-lookup"><span data-stu-id="113c9-128">`CreateDomainEx` extends the capabilities of [CreateDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md) by allowing the caller to pass in an `IAppDomainSetup` instance with property values for configuring the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="113c9-129">要求</span><span class="sxs-lookup"><span data-stu-id="113c9-129">Requirements</span></span>  
 <span data-ttu-id="113c9-130">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="113c9-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="113c9-131">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="113c9-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="113c9-132">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="113c9-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="113c9-133">**.NET framework 版本：** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="113c9-133">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="113c9-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="113c9-134">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- <xref:System.IAppDomainSetup?displayProperty=nameWithType>
- [<span data-ttu-id="113c9-135">CreateDomain 方法</span><span class="sxs-lookup"><span data-stu-id="113c9-135">CreateDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md)
- [<span data-ttu-id="113c9-136">ICorRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="113c9-136">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
