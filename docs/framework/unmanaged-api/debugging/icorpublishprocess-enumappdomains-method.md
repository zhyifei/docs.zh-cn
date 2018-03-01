---
title: "ICorPublishProcess::EnumAppDomains 方法"
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
- ICorPublishProcess.EnumAppDomains
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess::EnumAppDomains
helpviewer_keywords:
- EnumAppDomains method [.NET Framework debugging]
- ICorPublishProcess::EnumAppDomains method [.NET Framework debugging]
ms.assetid: 7da621fc-e7d0-4c00-9439-5c93619d7414
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 938c022788d5ed9f0e28f794432017748dc096e8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icorpublishprocessenumappdomains-method"></a><span data-ttu-id="40e76-102">ICorPublishProcess::EnumAppDomains 方法</span><span class="sxs-lookup"><span data-stu-id="40e76-102">ICorPublishProcess::EnumAppDomains Method</span></span>
<span data-ttu-id="40e76-103">对于应用程序域引用的过程中获取一个枚举器[ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)。</span><span class="sxs-lookup"><span data-stu-id="40e76-103">Gets an enumerator for the application domains in the process that is referenced by this [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40e76-104">语法</span><span class="sxs-lookup"><span data-stu-id="40e76-104">Syntax</span></span>  
  
```  
HRESULT EnumAppDomains (  
    [out] ICorPublishAppDomainEnum   **ppEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="40e76-105">参数</span><span class="sxs-lookup"><span data-stu-id="40e76-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="40e76-106">[out]指向的地址的指针[ICorPublishAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)允许通过此过程中应用程序域的集合的迭代的实例。</span><span class="sxs-lookup"><span data-stu-id="40e76-106">[out] A pointer to the address of an [ICorPublishAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md) instance that allows iteration through the collection of application domains in this process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="40e76-107">备注</span><span class="sxs-lookup"><span data-stu-id="40e76-107">Remarks</span></span>  
 <span data-ttu-id="40e76-108">应用程序域的列表基于的应用程序域中存在的快照时`EnumAppDomains`调用方法。</span><span class="sxs-lookup"><span data-stu-id="40e76-108">The list of application domains is based on a snapshot of the application domains that exist when the `EnumAppDomains` method is called.</span></span> <span data-ttu-id="40e76-109">可能会多次调用此方法，以创建新的最新列表。</span><span class="sxs-lookup"><span data-stu-id="40e76-109">This method may be called more than once to create a new up-to-date list.</span></span> <span data-ttu-id="40e76-110">此方法的后续调用不会影响现有列表。</span><span class="sxs-lookup"><span data-stu-id="40e76-110">Existing lists will not be affected by subsequent calls of this method.</span></span>  
  
 <span data-ttu-id="40e76-111">如果进程已终止，`EnumAppDomains`将失败，并 CORDBG_E_PROCESS_TERMINATED 的 HRESULT 值。</span><span class="sxs-lookup"><span data-stu-id="40e76-111">If the process has been terminated, `EnumAppDomains` will fail with an HRESULT value of CORDBG_E_PROCESS_TERMINATED.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="40e76-112">惠?</span><span class="sxs-lookup"><span data-stu-id="40e76-112">Requirements</span></span>  
 <span data-ttu-id="40e76-113">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="40e76-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40e76-114">**标头：** CorPub.idl、 CorPub.h</span><span class="sxs-lookup"><span data-stu-id="40e76-114">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="40e76-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="40e76-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="40e76-116">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40e76-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40e76-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="40e76-117">See Also</span></span>  
 [<span data-ttu-id="40e76-118">ICorPublishProcess 接口</span><span class="sxs-lookup"><span data-stu-id="40e76-118">ICorPublishProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)
