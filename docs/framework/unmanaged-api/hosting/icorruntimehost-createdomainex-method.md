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
ms.openlocfilehash: 4e5856fbcda83c1dd30559c6f59f63495faea78d
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762339"
---
# <a name="icorruntimehostcreatedomainex-method"></a><span data-ttu-id="f099c-102">ICorRuntimeHost::CreateDomainEx 方法</span><span class="sxs-lookup"><span data-stu-id="f099c-102">ICorRuntimeHost::CreateDomainEx Method</span></span>
<span data-ttu-id="f099c-103">创建应用程序域。</span><span class="sxs-lookup"><span data-stu-id="f099c-103">Creates an application domain.</span></span> <span data-ttu-id="f099c-104">调用方将类型的接口指针接收 <xref:System._AppDomain> 到类型的实例 <xref:System.AppDomain?displayProperty=nameWithType> 。</span><span class="sxs-lookup"><span data-stu-id="f099c-104">The caller receives an interface pointer, of type <xref:System._AppDomain>, to an instance of type <xref:System.AppDomain?displayProperty=nameWithType>.</span></span> <span data-ttu-id="f099c-105">此方法允许调用方传递 IAppDomainSetup 实例，以配置返回的实例的附加功能 <xref:System._AppDomain> 。</span><span class="sxs-lookup"><span data-stu-id="f099c-105">This method allows the caller to pass an IAppDomainSetup instance to configure additional features of the returned <xref:System._AppDomain> instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f099c-106">语法</span><span class="sxs-lookup"><span data-stu-id="f099c-106">Syntax</span></span>  
  
```cpp  
HRESULT CreateDomainEx (  
    [in] LPCWSTR     pwzFriendlyName,  
    [in] IUnknown*   pSetup,  
    [in] IUnknown*   pIdentityArray,  
    [out] IUnknown** pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f099c-107">参数</span><span class="sxs-lookup"><span data-stu-id="f099c-107">Parameters</span></span>  
 `pwzFriendlyName`  
 <span data-ttu-id="f099c-108">中用于给域指定友好名称的可选参数。</span><span class="sxs-lookup"><span data-stu-id="f099c-108">[in] An optional parameter used to give a friendly name to the domain.</span></span> <span data-ttu-id="f099c-109">此友好名称可在用户界面（例如调试器）中显示，以标识域。</span><span class="sxs-lookup"><span data-stu-id="f099c-109">This friendly name can be displayed in user interfaces such as debuggers to identify the domain.</span></span>  
  
 `pSetup`  
 <span data-ttu-id="f099c-110">中类型的可选接口指针 `IAppDomainSetup` ，由对[ICorRuntimeHost：： CreateDomainSetup](icorruntimehost-createdomainsetup-method.md)方法的调用获得。</span><span class="sxs-lookup"><span data-stu-id="f099c-110">[in] An optional interface pointer of type `IAppDomainSetup`, obtained by a call to the [ICorRuntimeHost::CreateDomainSetup](icorruntimehost-createdomainsetup-method.md) method.</span></span>  
  
 `pIdentityArray`  
 <span data-ttu-id="f099c-111">中指向实例的可选指针数组， `IIdentity` 这些实例表示通过安全策略映射以建立权限集的证据。</span><span class="sxs-lookup"><span data-stu-id="f099c-111">[in] An optional array of pointers to `IIdentity` instances that represent evidence mapped through security policy to establish a permission set.</span></span> <span data-ttu-id="f099c-112">`IIdentity`可以通过调用[CreateEvidence](icorruntimehost-createevidence-method.md)方法来获取对象。</span><span class="sxs-lookup"><span data-stu-id="f099c-112">An `IIdentity` object can be obtained by calling the [CreateEvidence](icorruntimehost-createevidence-method.md) method.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="f099c-113">弄类型为的接口指针 <xref:System._AppDomain> <xref:System.AppDomain?displayProperty=nameWithType> ，可用于进一步控制域。</span><span class="sxs-lookup"><span data-stu-id="f099c-113">[out] An interface pointer of type <xref:System._AppDomain> to an instance of <xref:System.AppDomain?displayProperty=nameWithType> that can be used to further control the domain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f099c-114">返回值</span><span class="sxs-lookup"><span data-stu-id="f099c-114">Return Value</span></span>  
  
|<span data-ttu-id="f099c-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f099c-115">HRESULT</span></span>|<span data-ttu-id="f099c-116">说明</span><span class="sxs-lookup"><span data-stu-id="f099c-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f099c-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="f099c-117">S_OK</span></span>|<span data-ttu-id="f099c-118">操作成功。</span><span class="sxs-lookup"><span data-stu-id="f099c-118">The operation was successful.</span></span>|  
|<span data-ttu-id="f099c-119">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="f099c-119">S_FALSE</span></span>|<span data-ttu-id="f099c-120">操作未能完成。</span><span class="sxs-lookup"><span data-stu-id="f099c-120">The operation failed to complete.</span></span>|  
|<span data-ttu-id="f099c-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f099c-121">E_FAIL</span></span>|<span data-ttu-id="f099c-122">发生了未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="f099c-122">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="f099c-123">如果方法返回 E_FAIL，则公共语言运行时（CLR）在该过程中将不再可用。</span><span class="sxs-lookup"><span data-stu-id="f099c-123">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="f099c-124">对任何宿主 Api 的后续调用都会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="f099c-124">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="f099c-125">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f099c-125">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f099c-126">CLR 未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="f099c-126">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f099c-127">注解</span><span class="sxs-lookup"><span data-stu-id="f099c-127">Remarks</span></span>  
 <span data-ttu-id="f099c-128">`CreateDomainEx`通过允许调用方[CreateDomain](icorruntimehost-createdomain-method.md)传入 `IAppDomainSetup` 具有属性值的实例来配置应用程序域，从而扩展了 CreateDomain 的功能。</span><span class="sxs-lookup"><span data-stu-id="f099c-128">`CreateDomainEx` extends the capabilities of [CreateDomain](icorruntimehost-createdomain-method.md) by allowing the caller to pass in an `IAppDomainSetup` instance with property values for configuring the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f099c-129">要求</span><span class="sxs-lookup"><span data-stu-id="f099c-129">Requirements</span></span>  
 <span data-ttu-id="f099c-130">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f099c-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f099c-131">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="f099c-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f099c-132">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="f099c-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f099c-133">**.NET Framework 版本：** 1.0、1。1</span><span class="sxs-lookup"><span data-stu-id="f099c-133">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f099c-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f099c-134">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- <xref:System.IAppDomainSetup?displayProperty=nameWithType>
- [<span data-ttu-id="f099c-135">CreateDomain 方法</span><span class="sxs-lookup"><span data-stu-id="f099c-135">CreateDomain Method</span></span>](icorruntimehost-createdomain-method.md)
- [<span data-ttu-id="f099c-136">ICorRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="f099c-136">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
