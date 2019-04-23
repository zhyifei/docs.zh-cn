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
ms.openlocfilehash: ca54f779d257314b843838d90ca9996f1eb3237b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59081805"
---
# <a name="icorruntimehostcreateevidence-method"></a><span data-ttu-id="f6b68-102">ICorRuntimeHost::CreateEvidence 方法</span><span class="sxs-lookup"><span data-stu-id="f6b68-102">ICorRuntimeHost::CreateEvidence Method</span></span>
<span data-ttu-id="f6b68-103">获取类型的接口指针<xref:System.Security.Principal.IIdentity?displayProperty=nameWithType>，它允许主机来创建安全证据要传递给[CreateDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md)或[CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="f6b68-103">Gets an interface pointer of type <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType>, which allows the host to create security evidence to pass to the [CreateDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md) or [CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6b68-104">语法</span><span class="sxs-lookup"><span data-stu-id="f6b68-104">Syntax</span></span>  
  
```  
HRESULT CreateEvidence (  
    [out] IUnknown** pEvidence  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f6b68-105">参数</span><span class="sxs-lookup"><span data-stu-id="f6b68-105">Parameters</span></span>  
 `pEvidence`  
 <span data-ttu-id="f6b68-106">[out]指向的接口指针<xref:System.Security.Principal.IIdentity?displayProperty=nameWithType>实例用来创建安全证据。</span><span class="sxs-lookup"><span data-stu-id="f6b68-106">[out] A interface pointer to an <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType> instance used to create security evidence.</span></span> <span data-ttu-id="f6b68-107">此指针被类型化为`IUnknown`，因此通常情况下调用调用方应`QueryInterface`若要获取指向此接口上<xref:System.Security.Principal.IIdentity?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="f6b68-107">This pointer is typed `IUnknown`, so callers should typically call `QueryInterface` on this interface to obtain a pointer to an <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType>.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f6b68-108">返回值</span><span class="sxs-lookup"><span data-stu-id="f6b68-108">Return Value</span></span>  
  
|<span data-ttu-id="f6b68-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f6b68-109">HRESULT</span></span>|<span data-ttu-id="f6b68-110">描述</span><span class="sxs-lookup"><span data-stu-id="f6b68-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f6b68-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="f6b68-111">S_OK</span></span>|<span data-ttu-id="f6b68-112">操作成功。</span><span class="sxs-lookup"><span data-stu-id="f6b68-112">The operation was successful.</span></span>|  
|<span data-ttu-id="f6b68-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="f6b68-113">S_FALSE</span></span>|<span data-ttu-id="f6b68-114">该操作未能完成。</span><span class="sxs-lookup"><span data-stu-id="f6b68-114">The operation failed to complete.</span></span>|  
|<span data-ttu-id="f6b68-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f6b68-115">E_FAIL</span></span>|<span data-ttu-id="f6b68-116">发生了未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="f6b68-116">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="f6b68-117">如果方法返回 E_FAIL，公共语言运行时 (CLR) 不再可在该过程中使用。</span><span class="sxs-lookup"><span data-stu-id="f6b68-117">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="f6b68-118">对任何托管 Api 的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="f6b68-118">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="f6b68-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f6b68-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f6b68-120">CLR 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="f6b68-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f6b68-121">备注</span><span class="sxs-lookup"><span data-stu-id="f6b68-121">Remarks</span></span>  
 <span data-ttu-id="f6b68-122">此方法返回的本机代码中不能填充一个空集合。</span><span class="sxs-lookup"><span data-stu-id="f6b68-122">This method returns an empty collection that cannot be populated from native code.</span></span> <span data-ttu-id="f6b68-123">应使用<xref:System.Security.Policy.Evidence>方法相反。</span><span class="sxs-lookup"><span data-stu-id="f6b68-123">You should use the <xref:System.Security.Policy.Evidence> method instead.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6b68-124">要求</span><span class="sxs-lookup"><span data-stu-id="f6b68-124">Requirements</span></span>  
 <span data-ttu-id="f6b68-125">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f6b68-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f6b68-126">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f6b68-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f6b68-127">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="f6b68-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f6b68-128">**.NET framework 版本：** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="f6b68-128">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6b68-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="f6b68-129">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [<span data-ttu-id="f6b68-130">ICorRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="f6b68-130">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
