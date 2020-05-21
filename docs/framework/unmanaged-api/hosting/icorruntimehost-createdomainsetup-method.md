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
ms.openlocfilehash: aa1ce70311cd4ef0204c1c31efee8bd7b313c81d
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762326"
---
# <a name="icorruntimehostcreatedomainsetup-method"></a><span data-ttu-id="4028f-102">ICorRuntimeHost::CreateDomainSetup 方法</span><span class="sxs-lookup"><span data-stu-id="4028f-102">ICorRuntimeHost::CreateDomainSetup Method</span></span>
<span data-ttu-id="4028f-103">获取实例的 IAppDomainSetup 类型的接口指针 <xref:System.AppDomainSetup?displayProperty=nameWithType> 。</span><span class="sxs-lookup"><span data-stu-id="4028f-103">Gets an interface pointer of type IAppDomainSetup to an <xref:System.AppDomainSetup?displayProperty=nameWithType> instance.</span></span> <span data-ttu-id="4028f-104">`IAppDomainSetup`提供用于配置应用程序域在创建之前的各个方面的方法。</span><span class="sxs-lookup"><span data-stu-id="4028f-104">`IAppDomainSetup` provides methods to configure aspects of an application domain before it is created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4028f-105">语法</span><span class="sxs-lookup"><span data-stu-id="4028f-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateDomainSetup (  
    [out] IUnknown** pAppDomainSetup  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4028f-106">参数</span><span class="sxs-lookup"><span data-stu-id="4028f-106">Parameters</span></span>  
 `pAppDomainSetup`  
 <span data-ttu-id="4028f-107">弄指向实例的接口指针 <xref:System.AppDomainSetup?displayProperty=nameWithType> 。</span><span class="sxs-lookup"><span data-stu-id="4028f-107">[out] An interface pointer to an <xref:System.AppDomainSetup?displayProperty=nameWithType> instance.</span></span> <span data-ttu-id="4028f-108">此参数的类型为 `IUnknown` ，因此调用方通常应 `QueryInterface` 在此指针上调用，以获取类型的接口指针 `IAppDomainSetup` 。</span><span class="sxs-lookup"><span data-stu-id="4028f-108">This parameter is typed as `IUnknown`, so callers should generally call `QueryInterface` on this pointer to obtain an interface pointer of type `IAppDomainSetup`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4028f-109">返回值</span><span class="sxs-lookup"><span data-stu-id="4028f-109">Return Value</span></span>  
  
|<span data-ttu-id="4028f-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4028f-110">HRESULT</span></span>|<span data-ttu-id="4028f-111">说明</span><span class="sxs-lookup"><span data-stu-id="4028f-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4028f-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="4028f-112">S_OK</span></span>|<span data-ttu-id="4028f-113">操作成功。</span><span class="sxs-lookup"><span data-stu-id="4028f-113">The operation was successful.</span></span>|  
|<span data-ttu-id="4028f-114">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="4028f-114">S_FALSE</span></span>|<span data-ttu-id="4028f-115">操作未能完成。</span><span class="sxs-lookup"><span data-stu-id="4028f-115">The operation failed to complete.</span></span>|  
|<span data-ttu-id="4028f-116">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4028f-116">E_FAIL</span></span>|<span data-ttu-id="4028f-117">发生了未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="4028f-117">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="4028f-118">如果方法返回 E_FAIL，则公共语言运行时（CLR）在该过程中将不再可用。</span><span class="sxs-lookup"><span data-stu-id="4028f-118">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="4028f-119">对任何宿主 Api 的后续调用都会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="4028f-119">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="4028f-120">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4028f-120">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4028f-121">CLR 未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="4028f-121">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4028f-122">注解</span><span class="sxs-lookup"><span data-stu-id="4028f-122">Remarks</span></span>  
 <span data-ttu-id="4028f-123">从此方法返回的指针通常作为参数传递给[CreateDomainEx](icorruntimehost-createdomainex-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="4028f-123">The pointer returned from this method is typically passed as a parameter to the [CreateDomainEx](icorruntimehost-createdomainex-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4028f-124">要求</span><span class="sxs-lookup"><span data-stu-id="4028f-124">Requirements</span></span>  
 <span data-ttu-id="4028f-125">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4028f-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4028f-126">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="4028f-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4028f-127">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="4028f-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4028f-128">**.NET Framework 版本：** 1.0、1。1</span><span class="sxs-lookup"><span data-stu-id="4028f-128">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4028f-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4028f-129">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- <xref:System.AppDomainSetup>
- <xref:System.IAppDomainSetup?displayProperty=nameWithType>
- [<span data-ttu-id="4028f-130">ICorRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="4028f-130">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
