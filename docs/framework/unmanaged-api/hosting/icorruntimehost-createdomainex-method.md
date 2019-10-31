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
ms.openlocfilehash: a3a2d1827774ddedc00eb849f64256e3f425b3fa
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127713"
---
# <a name="icorruntimehostcreatedomainex-method"></a><span data-ttu-id="775cc-102">ICorRuntimeHost::CreateDomainEx 方法</span><span class="sxs-lookup"><span data-stu-id="775cc-102">ICorRuntimeHost::CreateDomainEx Method</span></span>
<span data-ttu-id="775cc-103">创建应用程序域。</span><span class="sxs-lookup"><span data-stu-id="775cc-103">Creates an application domain.</span></span> <span data-ttu-id="775cc-104">调用方将 <xref:System._AppDomain>类型的接口指针接收到 <xref:System.AppDomain?displayProperty=nameWithType>类型的实例。</span><span class="sxs-lookup"><span data-stu-id="775cc-104">The caller receives an interface pointer, of type <xref:System._AppDomain>, to an instance of type <xref:System.AppDomain?displayProperty=nameWithType>.</span></span> <span data-ttu-id="775cc-105">此方法允许调用方传递 IAppDomainSetup 实例，以配置返回的 <xref:System._AppDomain> 实例的附加功能。</span><span class="sxs-lookup"><span data-stu-id="775cc-105">This method allows the caller to pass an IAppDomainSetup instance to configure additional features of the returned <xref:System._AppDomain> instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="775cc-106">语法</span><span class="sxs-lookup"><span data-stu-id="775cc-106">Syntax</span></span>  
  
```cpp  
HRESULT CreateDomainEx (  
    [in] LPCWSTR     pwzFriendlyName,  
    [in] IUnknown*   pSetup,  
    [in] IUnknown*   pIdentityArray,  
    [out] IUnknown** pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="775cc-107">参数</span><span class="sxs-lookup"><span data-stu-id="775cc-107">Parameters</span></span>  
 `pwzFriendlyName`  
 <span data-ttu-id="775cc-108">中用于给域指定友好名称的可选参数。</span><span class="sxs-lookup"><span data-stu-id="775cc-108">[in] An optional parameter used to give a friendly name to the domain.</span></span> <span data-ttu-id="775cc-109">此友好名称可在用户界面（例如调试器）中显示，以标识域。</span><span class="sxs-lookup"><span data-stu-id="775cc-109">This friendly name can be displayed in user interfaces such as debuggers to identify the domain.</span></span>  
  
 `pSetup`  
 <span data-ttu-id="775cc-110">中`IAppDomainSetup`类型的可选接口指针，通过调用[ICorRuntimeHost：： CreateDomainSetup](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainsetup-method.md)方法获取。</span><span class="sxs-lookup"><span data-stu-id="775cc-110">[in] An optional interface pointer of type `IAppDomainSetup`, obtained by a call to the [ICorRuntimeHost::CreateDomainSetup](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainsetup-method.md) method.</span></span>  
  
 `pIdentityArray`  
 <span data-ttu-id="775cc-111">中指向 `IIdentity` 实例的可选指针数组，这些实例表示通过安全策略映射以建立权限集的证据。</span><span class="sxs-lookup"><span data-stu-id="775cc-111">[in] An optional array of pointers to `IIdentity` instances that represent evidence mapped through security policy to establish a permission set.</span></span> <span data-ttu-id="775cc-112">可以通过调用[CreateEvidence](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createevidence-method.md)方法来获取 `IIdentity` 的对象。</span><span class="sxs-lookup"><span data-stu-id="775cc-112">An `IIdentity` object can be obtained by calling the [CreateEvidence](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createevidence-method.md) method.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="775cc-113">弄类型的接口指针 <xref:System._AppDomain> 到可用于进一步控制域的 <xref:System.AppDomain?displayProperty=nameWithType> 的实例。</span><span class="sxs-lookup"><span data-stu-id="775cc-113">[out] An interface pointer of type <xref:System._AppDomain> to an instance of <xref:System.AppDomain?displayProperty=nameWithType> that can be used to further control the domain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="775cc-114">返回值</span><span class="sxs-lookup"><span data-stu-id="775cc-114">Return Value</span></span>  
  
|<span data-ttu-id="775cc-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="775cc-115">HRESULT</span></span>|<span data-ttu-id="775cc-116">描述</span><span class="sxs-lookup"><span data-stu-id="775cc-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="775cc-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="775cc-117">S_OK</span></span>|<span data-ttu-id="775cc-118">操作成功。</span><span class="sxs-lookup"><span data-stu-id="775cc-118">The operation was successful.</span></span>|  
|<span data-ttu-id="775cc-119">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="775cc-119">S_FALSE</span></span>|<span data-ttu-id="775cc-120">操作未能完成。</span><span class="sxs-lookup"><span data-stu-id="775cc-120">The operation failed to complete.</span></span>|  
|<span data-ttu-id="775cc-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="775cc-121">E_FAIL</span></span>|<span data-ttu-id="775cc-122">发生了未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="775cc-122">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="775cc-123">如果某个方法返回 E_FAIL，则公共语言运行时（CLR）在该过程中将不再可用。</span><span class="sxs-lookup"><span data-stu-id="775cc-123">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="775cc-124">对任何托管 Api 的后续调用都将返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="775cc-124">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="775cc-125">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="775cc-125">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="775cc-126">CLR 未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="775cc-126">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="775cc-127">备注</span><span class="sxs-lookup"><span data-stu-id="775cc-127">Remarks</span></span>  
 <span data-ttu-id="775cc-128">`CreateDomainEx` 通过允许调用方传入具有属性值的 `IAppDomainSetup` 实例来扩展[CreateDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md)的功能，以便配置应用程序域。</span><span class="sxs-lookup"><span data-stu-id="775cc-128">`CreateDomainEx` extends the capabilities of [CreateDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md) by allowing the caller to pass in an `IAppDomainSetup` instance with property values for configuring the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="775cc-129">要求</span><span class="sxs-lookup"><span data-stu-id="775cc-129">Requirements</span></span>  
 <span data-ttu-id="775cc-130">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="775cc-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="775cc-131">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="775cc-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="775cc-132">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="775cc-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="775cc-133">**.NET Framework 版本：** 1.0、1。1</span><span class="sxs-lookup"><span data-stu-id="775cc-133">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="775cc-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="775cc-134">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- <xref:System.IAppDomainSetup?displayProperty=nameWithType>
- [<span data-ttu-id="775cc-135">CreateDomain 方法</span><span class="sxs-lookup"><span data-stu-id="775cc-135">CreateDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md)
- [<span data-ttu-id="775cc-136">ICorRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="775cc-136">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
