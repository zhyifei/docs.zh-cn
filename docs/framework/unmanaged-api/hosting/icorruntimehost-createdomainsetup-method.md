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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 88f5de9882f8a029769d0ccbdac21aec541582a4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61937067"
---
# <a name="icorruntimehostcreatedomainsetup-method"></a><span data-ttu-id="87770-102">ICorRuntimeHost::CreateDomainSetup 方法</span><span class="sxs-lookup"><span data-stu-id="87770-102">ICorRuntimeHost::CreateDomainSetup Method</span></span>
<span data-ttu-id="87770-103">获取的接口指针类型到 IAppDomainSetup<xref:System.AppDomainSetup?displayProperty=nameWithType>实例。</span><span class="sxs-lookup"><span data-stu-id="87770-103">Gets an interface pointer of type IAppDomainSetup to an <xref:System.AppDomainSetup?displayProperty=nameWithType> instance.</span></span> <span data-ttu-id="87770-104">`IAppDomainSetup` 提供方法来配置方面的应用程序域，然后创建它。</span><span class="sxs-lookup"><span data-stu-id="87770-104">`IAppDomainSetup` provides methods to configure aspects of an application domain before it is created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87770-105">语法</span><span class="sxs-lookup"><span data-stu-id="87770-105">Syntax</span></span>  
  
```  
HRESULT CreateDomainSetup (  
    [out] IUnknown** pAppDomainSetup  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="87770-106">参数</span><span class="sxs-lookup"><span data-stu-id="87770-106">Parameters</span></span>  
 `pAppDomainSetup`  
 <span data-ttu-id="87770-107">[out]接口指针<xref:System.AppDomainSetup?displayProperty=nameWithType>实例。</span><span class="sxs-lookup"><span data-stu-id="87770-107">[out] An interface pointer to an <xref:System.AppDomainSetup?displayProperty=nameWithType> instance.</span></span> <span data-ttu-id="87770-108">此参数被类型化为`IUnknown`，因此调用方通常应调用`QueryInterface`this 指针获取类型的接口指针上`IAppDomainSetup`。</span><span class="sxs-lookup"><span data-stu-id="87770-108">This parameter is typed as `IUnknown`, so callers should generally call `QueryInterface` on this pointer to obtain an interface pointer of type `IAppDomainSetup`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="87770-109">返回值</span><span class="sxs-lookup"><span data-stu-id="87770-109">Return Value</span></span>  
  
|<span data-ttu-id="87770-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="87770-110">HRESULT</span></span>|<span data-ttu-id="87770-111">描述</span><span class="sxs-lookup"><span data-stu-id="87770-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="87770-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="87770-112">S_OK</span></span>|<span data-ttu-id="87770-113">操作成功。</span><span class="sxs-lookup"><span data-stu-id="87770-113">The operation was successful.</span></span>|  
|<span data-ttu-id="87770-114">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="87770-114">S_FALSE</span></span>|<span data-ttu-id="87770-115">该操作未能完成。</span><span class="sxs-lookup"><span data-stu-id="87770-115">The operation failed to complete.</span></span>|  
|<span data-ttu-id="87770-116">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="87770-116">E_FAIL</span></span>|<span data-ttu-id="87770-117">发生了未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="87770-117">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="87770-118">如果方法返回 E_FAIL，公共语言运行时 (CLR) 不再可在该过程中使用。</span><span class="sxs-lookup"><span data-stu-id="87770-118">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="87770-119">对任何托管 Api 的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="87770-119">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="87770-120">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="87770-120">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="87770-121">CLR 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="87770-121">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="87770-122">备注</span><span class="sxs-lookup"><span data-stu-id="87770-122">Remarks</span></span>  
 <span data-ttu-id="87770-123">此方法返回的指针通常作为参数传递[CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="87770-123">The pointer returned from this method is typically passed as a parameter to the [CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="87770-124">要求</span><span class="sxs-lookup"><span data-stu-id="87770-124">Requirements</span></span>  
 <span data-ttu-id="87770-125">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="87770-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="87770-126">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="87770-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="87770-127">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="87770-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="87770-128">**.NET framework 版本：** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="87770-128">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87770-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="87770-129">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- <xref:System.AppDomainSetup>
- <xref:System.IAppDomainSetup?displayProperty=nameWithType>
- [<span data-ttu-id="87770-130">ICorRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="87770-130">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
