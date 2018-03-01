---
title: "ICorDebugTypeEnum::Next 方法"
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
- ICorDebugTypeEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugTypeEnum::Next
helpviewer_keywords:
- ICorDebugTypeEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugTypeEnum interface [.NET Framework debugging]
ms.assetid: d0fdeba3-c195-4ece-8caf-79b1f40025d2
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 53acf78450e455a4f9778b1e508d79a921e20ae9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugtypeenumnext-method"></a><span data-ttu-id="905b6-102">ICorDebugTypeEnum::Next 方法</span><span class="sxs-lookup"><span data-stu-id="905b6-102">ICorDebugTypeEnum::Next Method</span></span>
<span data-ttu-id="905b6-103">获取由指定的"ICorDebugType"实例数`celt`从枚举中的当前位置开始。</span><span class="sxs-lookup"><span data-stu-id="905b6-103">Gets the number of "ICorDebugType" instances specified by `celt` from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="905b6-104">语法</span><span class="sxs-lookup"><span data-stu-id="905b6-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in]  ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugType *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="905b6-105">参数</span><span class="sxs-lookup"><span data-stu-id="905b6-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="905b6-106">[in]数`ICorDebugType`要检索的实例。</span><span class="sxs-lookup"><span data-stu-id="905b6-106">[in] The number of `ICorDebugType` instances to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="905b6-107">[out]一个指针，其中每个指向数组`ICorDebugType`对象。</span><span class="sxs-lookup"><span data-stu-id="905b6-107">[out] An array of pointers, each of which points to an `ICorDebugType` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="905b6-108">[out]指向数`ICorDebugType`实际返回的实例。</span><span class="sxs-lookup"><span data-stu-id="905b6-108">[out] Pointer to the number of `ICorDebugType` instances actually returned.</span></span> <span data-ttu-id="905b6-109">此值可能为 null 如果`celt`是之一。</span><span class="sxs-lookup"><span data-stu-id="905b6-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="905b6-110">惠?</span><span class="sxs-lookup"><span data-stu-id="905b6-110">Requirements</span></span>  
 <span data-ttu-id="905b6-111">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="905b6-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="905b6-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="905b6-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="905b6-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="905b6-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="905b6-114">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="905b6-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="905b6-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="905b6-115">See Also</span></span>  
 
