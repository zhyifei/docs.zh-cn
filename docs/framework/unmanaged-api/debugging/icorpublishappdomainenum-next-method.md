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
ms.openlocfilehash: c14d364320c82f061ef606a402563dacfce28139
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59186233"
---
# <a name="icorpublishappdomainenumnext-method"></a><span data-ttu-id="b718d-102">ICorPublishAppDomainEnum::Next 方法</span><span class="sxs-lookup"><span data-stu-id="b718d-102">ICorPublishAppDomainEnum::Next Method</span></span>
<span data-ttu-id="b718d-103">在过程中，从当前位置开始获取指定的当前存在的应用程序域数。</span><span class="sxs-lookup"><span data-stu-id="b718d-103">Gets the specified number of application domains that currently exist in the process, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b718d-104">语法</span><span class="sxs-lookup"><span data-stu-id="b718d-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]   
        ICorPublishAppDomain **objects,  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b718d-105">参数</span><span class="sxs-lookup"><span data-stu-id="b718d-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="b718d-106">[in]要检索的元素数。</span><span class="sxs-lookup"><span data-stu-id="b718d-106">[in] The number of elements to be retrieved.</span></span>  
  
 `objects`  
 <span data-ttu-id="b718d-107">[out]检索到的数组的指针[ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)对象，其中每个表示应用程序域。</span><span class="sxs-lookup"><span data-stu-id="b718d-107">[out] A pointer to the array of retrieved [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md) objects, each of which represents an application domain.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="b718d-108">[out]指向实际返回的应用程序域数。</span><span class="sxs-lookup"><span data-stu-id="b718d-108">[out] Pointer to the number of application domains actually returned.</span></span> <span data-ttu-id="b718d-109">此值可能为 null 如果`celt`是其中一个。</span><span class="sxs-lookup"><span data-stu-id="b718d-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b718d-110">要求</span><span class="sxs-lookup"><span data-stu-id="b718d-110">Requirements</span></span>  
 <span data-ttu-id="b718d-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b718d-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b718d-112">**标头：** CorPub.idl CorPub.h</span><span class="sxs-lookup"><span data-stu-id="b718d-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="b718d-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b718d-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b718d-114">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b718d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b718d-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="b718d-115">See also</span></span>

- [<span data-ttu-id="b718d-116">ICorPublishAppDomainEnum 接口</span><span class="sxs-lookup"><span data-stu-id="b718d-116">ICorPublishAppDomainEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)
