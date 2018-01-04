---
title: "ICorRuntimeHost::CloseEnum 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorRuntimeHost.CloseEnum
api_location: mscoree.dll
api_type: COM
f1_keywords: ICorRuntimeHost::CloseEnum
helpviewer_keywords:
- CloseEnum method, ICorRuntimeHost interface [.NET Framework hosting]
- ICorRuntimeHost::CloseEnum method [.NET Framework hosting]
ms.assetid: f7ce7e8c-0a3e-4587-a180-063e2b85940e
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 677ab3a97b7fcceccd8ceb0943c62df8bc999649
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icorruntimehostcloseenum-method"></a><span data-ttu-id="f258f-102">ICorRuntimeHost::CloseEnum 方法</span><span class="sxs-lookup"><span data-stu-id="f258f-102">ICorRuntimeHost::CloseEnum Method</span></span>
<span data-ttu-id="f258f-103">将域枚举数重置回域列表的开头。</span><span class="sxs-lookup"><span data-stu-id="f258f-103">Resets a domain enumerator back to the beginning of the domain list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f258f-104">语法</span><span class="sxs-lookup"><span data-stu-id="f258f-104">Syntax</span></span>  
  
```  
HRESULT CloseEnum (  
    [in] HCORENUM hEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f258f-105">参数</span><span class="sxs-lookup"><span data-stu-id="f258f-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="f258f-106">[in]枚举数重置。</span><span class="sxs-lookup"><span data-stu-id="f258f-106">[in] The enumerator to reset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f258f-107">返回值</span><span class="sxs-lookup"><span data-stu-id="f258f-107">Return Value</span></span>  
  
|<span data-ttu-id="f258f-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f258f-108">HRESULT</span></span>|<span data-ttu-id="f258f-109">描述</span><span class="sxs-lookup"><span data-stu-id="f258f-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f258f-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="f258f-110">S_OK</span></span>|<span data-ttu-id="f258f-111">该操作成功。</span><span class="sxs-lookup"><span data-stu-id="f258f-111">The operation was successful.</span></span>|  
|<span data-ttu-id="f258f-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="f258f-112">S_FALSE</span></span>|<span data-ttu-id="f258f-113">操作无法完成。</span><span class="sxs-lookup"><span data-stu-id="f258f-113">The operation failed to complete.</span></span>|  
|<span data-ttu-id="f258f-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f258f-114">E_FAIL</span></span>|<span data-ttu-id="f258f-115">发生了未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="f258f-115">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="f258f-116">如果某方法返回 E_FAIL，公共语言运行时 (CLR) 不再可用进程中。</span><span class="sxs-lookup"><span data-stu-id="f258f-116">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="f258f-117">对任何托管 Api 的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="f258f-117">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="f258f-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f258f-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f258f-119">CLR 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="f258f-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f258f-120">惠?</span><span class="sxs-lookup"><span data-stu-id="f258f-120">Requirements</span></span>  
 <span data-ttu-id="f258f-121">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f258f-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f258f-122">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f258f-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f258f-123">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="f258f-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f258f-124">**.NET framework 版本：** 1.0、 1.1</span><span class="sxs-lookup"><span data-stu-id="f258f-124">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f258f-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="f258f-125">See Also</span></span>  
 [<span data-ttu-id="f258f-126">CorBindToRuntimeEx 函数</span><span class="sxs-lookup"><span data-stu-id="f258f-126">CorBindToRuntimeEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)  
 [<span data-ttu-id="f258f-127">ICorRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="f258f-127">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
