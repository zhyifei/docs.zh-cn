---
title: "ICorRuntimeHost::CreateDomain 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorRuntimeHost.CreateDomain
api_location: mscoree.dll
api_type: COM
f1_keywords: ICorRuntimeHost::CreateDomain
helpviewer_keywords:
- CreateDomain method [.NET Framework hosting]
- ICorRuntimeHost::CreateDomain method [.NET Framework hosting]
ms.assetid: b96c5ef3-a9df-4c7c-9952-432d3272cb5c
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0da99f05b09d44338a5f4d695fb2a4114f0e1f30
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icorruntimehostcreatedomain-method"></a><span data-ttu-id="87b46-102">ICorRuntimeHost::CreateDomain 方法</span><span class="sxs-lookup"><span data-stu-id="87b46-102">ICorRuntimeHost::CreateDomain Method</span></span>
<span data-ttu-id="87b46-103">创建应用程序域。</span><span class="sxs-lookup"><span data-stu-id="87b46-103">Creates an application domain.</span></span> <span data-ttu-id="87b46-104">调用方会收到类型的接口指针<xref:System._AppDomain>到类型的实例<xref:System.AppDomain?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="87b46-104">The caller receives an interface pointer of type <xref:System._AppDomain> to an instance of type <xref:System.AppDomain?displayProperty=nameWithType>.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87b46-105">语法</span><span class="sxs-lookup"><span data-stu-id="87b46-105">Syntax</span></span>  
  
```  
HRESULT CreateDomain (  
    [in] LPWSTR    pwzFriendlyName,  
    [in] IUnknown* pIdentityArray,  
    [out] void   **pAppDomain  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="87b46-106">参数</span><span class="sxs-lookup"><span data-stu-id="87b46-106">Parameters</span></span>  
 `pwzFriendlyName`  
 <span data-ttu-id="87b46-107">[in]一个可选参数，用于为域友好名称。</span><span class="sxs-lookup"><span data-stu-id="87b46-107">[in] An optional parameter used to give a friendly name to the domain.</span></span> <span data-ttu-id="87b46-108">此友好名称，可以显示在用户界面，例如调试器以标识域。</span><span class="sxs-lookup"><span data-stu-id="87b46-108">This friendly name can be displayed in user interfaces such as debuggers to identify the domain.</span></span>  
  
 `pIdentityArray`  
 <span data-ttu-id="87b46-109">[in]指向的指针的可选数组`IIdentity`表示映射通过安全策略，以建立权限集的证据的实例。</span><span class="sxs-lookup"><span data-stu-id="87b46-109">[in] An optional array of pointers to `IIdentity` instances that represent evidence mapped through security policy to establish a  permission set.</span></span> <span data-ttu-id="87b46-110">`IIdentity`可以通过调用获取对象[CreateEvidence](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createevidence-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="87b46-110">An `IIdentity` object can be obtained by calling the [CreateEvidence](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createevidence-method.md) method.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="87b46-111">[out]类型的接口指针<xref:System._AppDomain>到实例<xref:System.AppDomain?displayProperty=nameWithType>可以用于进一步控制域。</span><span class="sxs-lookup"><span data-stu-id="87b46-111">[out] An interface pointer of type <xref:System._AppDomain> to an instance of <xref:System.AppDomain?displayProperty=nameWithType> that can be used to further control the domain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="87b46-112">返回值</span><span class="sxs-lookup"><span data-stu-id="87b46-112">Return Value</span></span>  
  
|<span data-ttu-id="87b46-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="87b46-113">HRESULT</span></span>|<span data-ttu-id="87b46-114">描述</span><span class="sxs-lookup"><span data-stu-id="87b46-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="87b46-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="87b46-115">S_OK</span></span>|<span data-ttu-id="87b46-116">该操作成功。</span><span class="sxs-lookup"><span data-stu-id="87b46-116">The operation was successful.</span></span>|  
|<span data-ttu-id="87b46-117">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="87b46-117">S_FALSE</span></span>|<span data-ttu-id="87b46-118">操作无法完成。</span><span class="sxs-lookup"><span data-stu-id="87b46-118">The operation failed to complete.</span></span>|  
|<span data-ttu-id="87b46-119">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="87b46-119">E_FAIL</span></span>|<span data-ttu-id="87b46-120">发生了未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="87b46-120">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="87b46-121">如果某方法返回 E_FAIL，公共语言运行时 (CLR) 不再可用进程中。</span><span class="sxs-lookup"><span data-stu-id="87b46-121">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="87b46-122">对任何托管 Api 的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="87b46-122">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="87b46-123">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="87b46-123">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="87b46-124">CLR 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="87b46-124">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="87b46-125">要求</span><span class="sxs-lookup"><span data-stu-id="87b46-125">Requirements</span></span>  
 <span data-ttu-id="87b46-126">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="87b46-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="87b46-127">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="87b46-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="87b46-128">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="87b46-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="87b46-129">**.NET framework 版本：** 1.0、 1.1</span><span class="sxs-lookup"><span data-stu-id="87b46-129">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87b46-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="87b46-130">See Also</span></span>  
 <xref:System._AppDomain>  
 <xref:System.AppDomain>  
 [<span data-ttu-id="87b46-131">ICorRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="87b46-131">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
