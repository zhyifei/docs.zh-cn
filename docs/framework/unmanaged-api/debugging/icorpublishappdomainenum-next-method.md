---
title: ICorPublishAppDomainEnum::Next 方法
ms.date: 03/30/2017
api_name:
- ICorPublishAppDomainEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishAppDomainEnum::Next
helpviewer_keywords:
- Next method, ICorPublishAppDomainEnum interface [.NET Framework debugging]
- ICorPublishAppDomainEnum::Next method [.NET Framework debugging]
ms.assetid: ad37cd10-0339-4d08-9b0e-4b3428bb4dc3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ac3c6698e4ca127257b7682f1f55acd663375280
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33423723"
---
# <a name="icorpublishappdomainenumnext-method"></a><span data-ttu-id="efea5-102">ICorPublishAppDomainEnum::Next 方法</span><span class="sxs-lookup"><span data-stu-id="efea5-102">ICorPublishAppDomainEnum::Next Method</span></span>
<span data-ttu-id="efea5-103">获取指定的数目的当前存在的应用程序域在过程中，从当前位置开始。</span><span class="sxs-lookup"><span data-stu-id="efea5-103">Gets the specified number of application domains that currently exist in the process, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="efea5-104">语法</span><span class="sxs-lookup"><span data-stu-id="efea5-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]   
        ICorPublishAppDomain **objects,  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="efea5-105">参数</span><span class="sxs-lookup"><span data-stu-id="efea5-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="efea5-106">[in]要检索的元素数。</span><span class="sxs-lookup"><span data-stu-id="efea5-106">[in] The number of elements to be retrieved.</span></span>  
  
 `objects`  
 <span data-ttu-id="efea5-107">[out]检索到的数组的指针[ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)对象，其中每个表示应用程序域。</span><span class="sxs-lookup"><span data-stu-id="efea5-107">[out] A pointer to the array of retrieved [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md) objects, each of which represents an application domain.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="efea5-108">[out]指向指针的实际返回的应用程序域的数量。</span><span class="sxs-lookup"><span data-stu-id="efea5-108">[out] Pointer to the number of application domains actually returned.</span></span> <span data-ttu-id="efea5-109">此值可能为 null 如果`celt`是之一。</span><span class="sxs-lookup"><span data-stu-id="efea5-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="efea5-110">要求</span><span class="sxs-lookup"><span data-stu-id="efea5-110">Requirements</span></span>  
 <span data-ttu-id="efea5-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="efea5-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="efea5-112">**标头：** CorPub.idl、 CorPub.h</span><span class="sxs-lookup"><span data-stu-id="efea5-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="efea5-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="efea5-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="efea5-114">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="efea5-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efea5-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="efea5-115">See Also</span></span>  
 [<span data-ttu-id="efea5-116">ICorPublishAppDomainEnum 接口</span><span class="sxs-lookup"><span data-stu-id="efea5-116">ICorPublishAppDomainEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)
