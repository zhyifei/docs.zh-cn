---
title: ICorRuntimeHost::CreateEvidence 方法
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.CreateEvidence
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::CreateEvidence
helpviewer_keywords:
- CreateEvidence method [.NET Framework hosting]
- ICorRuntimeHost::CreateEvidence method [.NET Framework hosting]
ms.assetid: e235ea80-b84c-4442-a4c3-fc96c25a8eb9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a06d57348cfbdfb8bb57580a48e54e298e27e166
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33438189"
---
# <a name="icorruntimehostcreateevidence-method"></a><span data-ttu-id="67733-102">ICorRuntimeHost::CreateEvidence 方法</span><span class="sxs-lookup"><span data-stu-id="67733-102">ICorRuntimeHost::CreateEvidence Method</span></span>
<span data-ttu-id="67733-103">获取类型的接口指针<xref:System.Security.Principal.IIdentity?displayProperty=nameWithType>，这样，主机可以在创建安全证据要传递给[CreateDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md)或[CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="67733-103">Gets an interface pointer of type <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType>, which allows the host to create security evidence to pass to the [CreateDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md) or [CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67733-104">语法</span><span class="sxs-lookup"><span data-stu-id="67733-104">Syntax</span></span>  
  
```  
HRESULT CreateEvidence (  
    [out] IUnknown** pEvidence  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="67733-105">参数</span><span class="sxs-lookup"><span data-stu-id="67733-105">Parameters</span></span>  
 `pEvidence`  
 <span data-ttu-id="67733-106">[out]接口指针<xref:System.Security.Principal.IIdentity?displayProperty=nameWithType>用于创建安全证据的实例。</span><span class="sxs-lookup"><span data-stu-id="67733-106">[out] A interface pointer to an <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType> instance used to create security evidence.</span></span> <span data-ttu-id="67733-107">此指针被类型化为`IUnknown`，因此通常应调用的调用方`QueryInterface`用于获取指向此接口上<xref:System.Security.Principal.IIdentity?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="67733-107">This pointer is typed `IUnknown`, so callers should typically call `QueryInterface` on this interface to obtain a pointer to an <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType>.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="67733-108">返回值</span><span class="sxs-lookup"><span data-stu-id="67733-108">Return Value</span></span>  
  
|<span data-ttu-id="67733-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="67733-109">HRESULT</span></span>|<span data-ttu-id="67733-110">描述</span><span class="sxs-lookup"><span data-stu-id="67733-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="67733-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="67733-111">S_OK</span></span>|<span data-ttu-id="67733-112">该操作成功。</span><span class="sxs-lookup"><span data-stu-id="67733-112">The operation was successful.</span></span>|  
|<span data-ttu-id="67733-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="67733-113">S_FALSE</span></span>|<span data-ttu-id="67733-114">操作无法完成。</span><span class="sxs-lookup"><span data-stu-id="67733-114">The operation failed to complete.</span></span>|  
|<span data-ttu-id="67733-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="67733-115">E_FAIL</span></span>|<span data-ttu-id="67733-116">发生了未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="67733-116">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="67733-117">如果某方法返回 E_FAIL，公共语言运行时 (CLR) 不再可用进程中。</span><span class="sxs-lookup"><span data-stu-id="67733-117">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="67733-118">对任何托管 Api 的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="67733-118">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="67733-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="67733-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="67733-120">CLR 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="67733-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="67733-121">备注</span><span class="sxs-lookup"><span data-stu-id="67733-121">Remarks</span></span>  
 <span data-ttu-id="67733-122">此方法返回从本机代码，将无法填充的空集合。</span><span class="sxs-lookup"><span data-stu-id="67733-122">This method returns an empty collection that cannot be populated from native code.</span></span> <span data-ttu-id="67733-123">应使用<xref:System.Security.Policy.Evidence>方法相反。</span><span class="sxs-lookup"><span data-stu-id="67733-123">You should use the <xref:System.Security.Policy.Evidence> method instead.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67733-124">要求</span><span class="sxs-lookup"><span data-stu-id="67733-124">Requirements</span></span>  
 <span data-ttu-id="67733-125">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="67733-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67733-126">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="67733-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="67733-127">**库：** 作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="67733-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="67733-128">**.NET framework 版本：** 1.0、 1.1</span><span class="sxs-lookup"><span data-stu-id="67733-128">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67733-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="67733-129">See Also</span></span>  
 <xref:System._AppDomain>  
 <xref:System.AppDomain>  
 [<span data-ttu-id="67733-130">ICorRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="67733-130">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
