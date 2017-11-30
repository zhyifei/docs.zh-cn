---
title: "ICorRuntimeHost::NextDomain 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorRuntimeHost.NextDomain
api_location: mscoree.dll
api_type: COM
f1_keywords: ICorRuntimeHost::NextDomain
helpviewer_keywords:
- ICorRuntimeHost::NextDomain method [.NET Framework hosting]
- NextDomain method [.NET Framework hosting]
ms.assetid: fe07a05b-f6d6-44b5-ab01-b9a6eb15c350
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: de7d90ed55cf27aa0b1679b5e55d9f28902b6aeb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icorruntimehostnextdomain-method"></a><span data-ttu-id="b4113-102">ICorRuntimeHost::NextDomain 方法</span><span class="sxs-lookup"><span data-stu-id="b4113-102">ICorRuntimeHost::NextDomain Method</span></span>
<span data-ttu-id="b4113-103">枚举中的下一个域中获取的接口指针。</span><span class="sxs-lookup"><span data-stu-id="b4113-103">Gets an interface pointer to the next domain in the enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4113-104">语法</span><span class="sxs-lookup"><span data-stu-id="b4113-104">Syntax</span></span>  
  
```  
HRESULT NextDomain (  
    [in] HCORENUM hEnum,  
    [out] void** pAppDomain  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b4113-105">参数</span><span class="sxs-lookup"><span data-stu-id="b4113-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="b4113-106">[in]枚举器已通过调用[EnumDomains](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-enumdomains-method.md)。</span><span class="sxs-lookup"><span data-stu-id="b4113-106">[in] The enumerator that was obtained through a call to [EnumDomains](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-enumdomains-method.md).</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="b4113-107">[out]接口指针<xref:System._AppDomain?displayProperty=nameWithType>表示下一个域中的枚举或为 null，如果没有更多域存在的类型。</span><span class="sxs-lookup"><span data-stu-id="b4113-107">[out] An interface pointer to the <xref:System._AppDomain?displayProperty=nameWithType> type that represents the next domain in the enumeration, or null, if no more domains exist.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b4113-108">返回值</span><span class="sxs-lookup"><span data-stu-id="b4113-108">Return Value</span></span>  
  
|<span data-ttu-id="b4113-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b4113-109">HRESULT</span></span>|<span data-ttu-id="b4113-110">描述</span><span class="sxs-lookup"><span data-stu-id="b4113-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b4113-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="b4113-111">S_OK</span></span>|<span data-ttu-id="b4113-112">该操作成功。</span><span class="sxs-lookup"><span data-stu-id="b4113-112">The operation was successful.</span></span>|  
|<span data-ttu-id="b4113-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="b4113-113">S_FALSE</span></span>|<span data-ttu-id="b4113-114">操作无法完成，或在枚举中的没有更多域。</span><span class="sxs-lookup"><span data-stu-id="b4113-114">The operation failed to complete, or there are no more domains in the enumeration.</span></span>|  
|<span data-ttu-id="b4113-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b4113-115">E_FAIL</span></span>|<span data-ttu-id="b4113-116">发生了未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="b4113-116">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="b4113-117">如果某方法返回 E_FAIL，公共语言运行时 (CLR) 不再可用进程中。</span><span class="sxs-lookup"><span data-stu-id="b4113-117">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="b4113-118">对任何托管 Api 的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="b4113-118">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="b4113-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b4113-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b4113-120">CLR 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="b4113-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b4113-121">要求</span><span class="sxs-lookup"><span data-stu-id="b4113-121">Requirements</span></span>  
 <span data-ttu-id="b4113-122">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b4113-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4113-123">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b4113-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b4113-124">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="b4113-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b4113-125">**.NET framework 版本：** 1.0、 1.1</span><span class="sxs-lookup"><span data-stu-id="b4113-125">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4113-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b4113-126">See Also</span></span>  
 <xref:System._AppDomain>  
 <xref:System.AppDomain>  
 [<span data-ttu-id="b4113-127">ICorRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="b4113-127">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
