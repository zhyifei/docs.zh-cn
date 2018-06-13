---
title: IGCHost::Collect 方法
ms.date: 03/30/2017
api_name:
- IGCHost.Collect
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- Collect
helpviewer_keywords:
- Collect method, IGCHost interface [.NET Framework hosting]
- IGCHost::Collect method [.NET Framework hosting]
ms.assetid: fc7d9448-3186-494d-9f0d-ea39717e9a82
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bce005a677dcb74c176a6dddfb2726f6b1fd0e8a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33436902"
---
# <a name="igchostcollect-method"></a><span data-ttu-id="4d6f3-102">IGCHost::Collect 方法</span><span class="sxs-lookup"><span data-stu-id="4d6f3-102">IGCHost::Collect Method</span></span>
<span data-ttu-id="4d6f3-103">强制回收进行回收对给定的代，而无论当前的垃圾回收的状态。</span><span class="sxs-lookup"><span data-stu-id="4d6f3-103">Forces a collection to occur for the given generation, regardless of the state of the current garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d6f3-104">语法</span><span class="sxs-lookup"><span data-stu-id="4d6f3-104">Syntax</span></span>  
  
```  
HRESULT Collect (  
    [in] LONG Generation  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4d6f3-105">参数</span><span class="sxs-lookup"><span data-stu-id="4d6f3-105">Parameters</span></span>  
 `Generation`  
 <span data-ttu-id="4d6f3-106">[in]要对其执行垃圾回收生成。</span><span class="sxs-lookup"><span data-stu-id="4d6f3-106">[in] The generation on which to perform the garbage collection.</span></span> <span data-ttu-id="4d6f3-107">值-1 指示所有代上将都进行垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="4d6f3-107">A value of -1 indicates that all generations will undergo a garbage collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4d6f3-108">要求</span><span class="sxs-lookup"><span data-stu-id="4d6f3-108">Requirements</span></span>  
 <span data-ttu-id="4d6f3-109">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4d6f3-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4d6f3-110">**标头：** GCHost.idl、 GCHost.h</span><span class="sxs-lookup"><span data-stu-id="4d6f3-110">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="4d6f3-111">**库：** 作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="4d6f3-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4d6f3-112">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4d6f3-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d6f3-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="4d6f3-113">See Also</span></span>  
 [<span data-ttu-id="4d6f3-114">IGCHost 接口</span><span class="sxs-lookup"><span data-stu-id="4d6f3-114">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
