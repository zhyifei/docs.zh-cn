---
title: "ICorRuntimeHost::CurrentDomain 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorRuntimeHost.CurrentDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::CurrentDomain
helpviewer_keywords:
- ICorRuntimeHost::CreateDomain method [.NET Framework hosting]
- CurrentDomain method [.NET Framework hosting]
ms.assetid: dd2afb38-675b-4c3c-a9f3-8ab3b133eb02
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1ac437d924b6f5b290db117260701b554e29b6e7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icorruntimehostcurrentdomain-method"></a><span data-ttu-id="360d3-102">ICorRuntimeHost::CurrentDomain 方法</span><span class="sxs-lookup"><span data-stu-id="360d3-102">ICorRuntimeHost::CurrentDomain Method</span></span>
<span data-ttu-id="360d3-103">获取类型的接口指针<xref:System.AppDomain?displayProperty=nameWithType>表示加载到当前线程上的域。</span><span class="sxs-lookup"><span data-stu-id="360d3-103">Gets an interface pointer of type <xref:System.AppDomain?displayProperty=nameWithType> that represents the domain loaded on the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="360d3-104">语法</span><span class="sxs-lookup"><span data-stu-id="360d3-104">Syntax</span></span>  
  
```  
HRESULT CurrentDomain (  
    [out] IUnknown** pAppDomain  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="360d3-105">参数</span><span class="sxs-lookup"><span data-stu-id="360d3-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="360d3-106">[out]类型的指针<xref:System.AppDomain?displayProperty=nameWithType>表示线程的当前应用程序域。</span><span class="sxs-lookup"><span data-stu-id="360d3-106">[out] A pointer of type <xref:System.AppDomain?displayProperty=nameWithType> that represents the thread's current application domain.</span></span> <span data-ttu-id="360d3-107">此指针被类型化为`IUnknown`，因此通常应调用的调用方`QueryInterface`获取类型的指针<xref:System._AppDomain>。</span><span class="sxs-lookup"><span data-stu-id="360d3-107">This pointer is typed `IUnknown`, so callers should generally call `QueryInterface` to obtain a pointer of type <xref:System._AppDomain>.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="360d3-108">返回值</span><span class="sxs-lookup"><span data-stu-id="360d3-108">Return Value</span></span>  
  
|<span data-ttu-id="360d3-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="360d3-109">HRESULT</span></span>|<span data-ttu-id="360d3-110">描述</span><span class="sxs-lookup"><span data-stu-id="360d3-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="360d3-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="360d3-111">S_OK</span></span>|<span data-ttu-id="360d3-112">该操作成功。</span><span class="sxs-lookup"><span data-stu-id="360d3-112">The operation was successful.</span></span>|  
|<span data-ttu-id="360d3-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="360d3-113">S_FALSE</span></span>|<span data-ttu-id="360d3-114">操作无法完成。</span><span class="sxs-lookup"><span data-stu-id="360d3-114">The operation failed to complete.</span></span>|  
|<span data-ttu-id="360d3-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="360d3-115">E_FAIL</span></span>|<span data-ttu-id="360d3-116">发生了未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="360d3-116">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="360d3-117">如果某方法返回 E_FAIL，公共语言运行时 (CLR) 不再可用进程中。</span><span class="sxs-lookup"><span data-stu-id="360d3-117">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="360d3-118">对任何托管 Api 的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="360d3-118">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="360d3-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="360d3-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="360d3-120">CLR 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="360d3-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="360d3-121">惠?</span><span class="sxs-lookup"><span data-stu-id="360d3-121">Requirements</span></span>  
 <span data-ttu-id="360d3-122">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="360d3-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="360d3-123">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="360d3-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="360d3-124">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="360d3-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="360d3-125">**.NET framework 版本：** 1.0、 1.1</span><span class="sxs-lookup"><span data-stu-id="360d3-125">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="360d3-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="360d3-126">See Also</span></span>  
 <xref:System._AppDomain>  
 <xref:System.AppDomain>  
 [<span data-ttu-id="360d3-127">ICorRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="360d3-127">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
