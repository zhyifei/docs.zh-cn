---
title: "ICorDebugObjectEnum::Next 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugObjectEnum.Next
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugObjectEnum::Next
helpviewer_keywords:
- Next method, ICorDebugObjectEnum interface [.NET Framework debugging]
- ICorDebugObjectEnum::Next method [.NET Framework debugging]
ms.assetid: 10093e3d-26b6-4ad7-8ef3-bbf66243fc02
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c8edc9273710a843b4e99568097646825fc52a09
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugobjectenumnext-method"></a><span data-ttu-id="507ac-102">ICorDebugObjectEnum::Next 方法</span><span class="sxs-lookup"><span data-stu-id="507ac-102">ICorDebugObjectEnum::Next Method</span></span>
<span data-ttu-id="507ac-103">从当前位置开始在枚举中获取指定数目的对象的相对虚拟地址 (Rva)。</span><span class="sxs-lookup"><span data-stu-id="507ac-103">Gets the relative virtual addresses (RVAs) of the specified number of objects from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="507ac-104">语法</span><span class="sxs-lookup"><span data-stu-id="507ac-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]    
        CORDB_ADDRESS objects[],  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="507ac-105">参数</span><span class="sxs-lookup"><span data-stu-id="507ac-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="507ac-106">[in] 要检索的对象数。</span><span class="sxs-lookup"><span data-stu-id="507ac-106">[in] The number of objects to be retrieved.</span></span>  
  
 `objects`  
 <span data-ttu-id="507ac-107">[out]一个指针数组，其中每个指向 CORDB_ADDRESS 对象。</span><span class="sxs-lookup"><span data-stu-id="507ac-107">[out] An array of pointers, each of which points to a CORDB_ADDRESS object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="507ac-108">[out]对实际返回的对象的数量的指针。</span><span class="sxs-lookup"><span data-stu-id="507ac-108">[out] Pointer to the number of objects actually returned.</span></span> <span data-ttu-id="507ac-109">此值可能为 null 如果`celt`是之一。</span><span class="sxs-lookup"><span data-stu-id="507ac-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="507ac-110">惠?</span><span class="sxs-lookup"><span data-stu-id="507ac-110">Requirements</span></span>  
 <span data-ttu-id="507ac-111">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="507ac-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="507ac-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="507ac-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="507ac-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="507ac-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="507ac-114">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="507ac-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="507ac-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="507ac-115">See Also</span></span>  
 
