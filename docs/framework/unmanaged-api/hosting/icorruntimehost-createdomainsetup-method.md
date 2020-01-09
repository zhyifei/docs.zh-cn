---
title: ICorRuntimeHost::CreateDomainSetup 方法
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.CreateDomainSetup
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::CreateDomainSetup
helpviewer_keywords:
- CreateDomainSetup method [.NET Framework hosting]
- ICorRuntimeHost::CreateDomainSetup method [.NET Framework hosting]
ms.assetid: c21dab60-fb65-47d9-8a94-7fd47ca53b48
topic_type:
- apiref
ms.openlocfilehash: 217874e625604613e67170a118a7bc3616e02c4d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139644"
---
# <a name="icorruntimehostcreatedomainsetup-method"></a><span data-ttu-id="ae201-102">ICorRuntimeHost::CreateDomainSetup 方法</span><span class="sxs-lookup"><span data-stu-id="ae201-102">ICorRuntimeHost::CreateDomainSetup Method</span></span>
<span data-ttu-id="ae201-103">获取 <xref:System.AppDomainSetup?displayProperty=nameWithType> 实例的 IAppDomainSetup 类型的接口指针。</span><span class="sxs-lookup"><span data-stu-id="ae201-103">Gets an interface pointer of type IAppDomainSetup to an <xref:System.AppDomainSetup?displayProperty=nameWithType> instance.</span></span> <span data-ttu-id="ae201-104">`IAppDomainSetup` 提供在创建应用程序域之前配置这些方面的方法。</span><span class="sxs-lookup"><span data-stu-id="ae201-104">`IAppDomainSetup` provides methods to configure aspects of an application domain before it is created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae201-105">语法</span><span class="sxs-lookup"><span data-stu-id="ae201-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateDomainSetup (  
    [out] IUnknown** pAppDomainSetup  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ae201-106">参数</span><span class="sxs-lookup"><span data-stu-id="ae201-106">Parameters</span></span>  
 `pAppDomainSetup`  
 <span data-ttu-id="ae201-107">弄指向 <xref:System.AppDomainSetup?displayProperty=nameWithType> 实例的接口指针。</span><span class="sxs-lookup"><span data-stu-id="ae201-107">[out] An interface pointer to an <xref:System.AppDomainSetup?displayProperty=nameWithType> instance.</span></span> <span data-ttu-id="ae201-108">此参数被类型化为 `IUnknown`，因此调用方通常应调用此指针 `QueryInterface` 以获取 `IAppDomainSetup`类型的接口指针。</span><span class="sxs-lookup"><span data-stu-id="ae201-108">This parameter is typed as `IUnknown`, so callers should generally call `QueryInterface` on this pointer to obtain an interface pointer of type `IAppDomainSetup`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ae201-109">返回值</span><span class="sxs-lookup"><span data-stu-id="ae201-109">Return Value</span></span>  
  
|<span data-ttu-id="ae201-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ae201-110">HRESULT</span></span>|<span data-ttu-id="ae201-111">描述</span><span class="sxs-lookup"><span data-stu-id="ae201-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ae201-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="ae201-112">S_OK</span></span>|<span data-ttu-id="ae201-113">操作成功。</span><span class="sxs-lookup"><span data-stu-id="ae201-113">The operation was successful.</span></span>|  
|<span data-ttu-id="ae201-114">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="ae201-114">S_FALSE</span></span>|<span data-ttu-id="ae201-115">操作未能完成。</span><span class="sxs-lookup"><span data-stu-id="ae201-115">The operation failed to complete.</span></span>|  
|<span data-ttu-id="ae201-116">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ae201-116">E_FAIL</span></span>|<span data-ttu-id="ae201-117">发生了未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="ae201-117">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="ae201-118">如果某个方法返回 E_FAIL，则公共语言运行时（CLR）在该过程中将不再可用。</span><span class="sxs-lookup"><span data-stu-id="ae201-118">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="ae201-119">对任何托管 Api 的后续调用都将返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="ae201-119">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="ae201-120">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ae201-120">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ae201-121">CLR 未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="ae201-121">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ae201-122">备注</span><span class="sxs-lookup"><span data-stu-id="ae201-122">Remarks</span></span>  
 <span data-ttu-id="ae201-123">从此方法返回的指针通常作为参数传递给[CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="ae201-123">The pointer returned from this method is typically passed as a parameter to the [CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae201-124">要求</span><span class="sxs-lookup"><span data-stu-id="ae201-124">Requirements</span></span>  
 <span data-ttu-id="ae201-125">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ae201-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae201-126">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="ae201-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ae201-127">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="ae201-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ae201-128">**.NET Framework 版本：** 1.0、1.1</span><span class="sxs-lookup"><span data-stu-id="ae201-128">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae201-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="ae201-129">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- <xref:System.AppDomainSetup>
- <xref:System.IAppDomainSetup?displayProperty=nameWithType>
- [<span data-ttu-id="ae201-130">ICorRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="ae201-130">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
