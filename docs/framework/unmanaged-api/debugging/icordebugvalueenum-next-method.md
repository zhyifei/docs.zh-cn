---
title: ICorDebugValueEnum::Next 方法
ms.date: 03/30/2017
api_name:
- ICorDebugValueEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValueEnum::Next
helpviewer_keywords:
- ICorDebugValueEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugValueEnum interface [.NET Framework debugging]
ms.assetid: f5ef94dd-dfee-49d3-a398-b110f8906dd8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2ae09b4f1cd069edf81be583c7c4226717736094
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67764271"
---
# <a name="icordebugvalueenumnext-method"></a><span data-ttu-id="5f6ce-102">ICorDebugValueEnum::Next 方法</span><span class="sxs-lookup"><span data-stu-id="5f6ce-102">ICorDebugValueEnum::Next Method</span></span>
<span data-ttu-id="5f6ce-103">从当前位置开始枚举中获取指定的数量的"ICorDebugValue"实例。</span><span class="sxs-lookup"><span data-stu-id="5f6ce-103">Gets the specified number of "ICorDebugValue" instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f6ce-104">语法</span><span class="sxs-lookup"><span data-stu-id="5f6ce-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in]  ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugValue *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5f6ce-105">参数</span><span class="sxs-lookup"><span data-stu-id="5f6ce-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="5f6ce-106">[in]数`ICorDebugValue`要检索的实例。</span><span class="sxs-lookup"><span data-stu-id="5f6ce-106">[in] The number of `ICorDebugValue` instances to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="5f6ce-107">[out]一个指针，其中每个指向数组`ICorDebugValue`对象。</span><span class="sxs-lookup"><span data-stu-id="5f6ce-107">[out] An array of pointers, each of which points to an `ICorDebugValue` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="5f6ce-108">[out]指向数`ICorDebugValue`实际返回的实例。</span><span class="sxs-lookup"><span data-stu-id="5f6ce-108">[out] Pointer to the number of `ICorDebugValue` instances actually returned.</span></span> <span data-ttu-id="5f6ce-109">此值可能为 null 如果`celt`是其中一个。</span><span class="sxs-lookup"><span data-stu-id="5f6ce-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f6ce-110">要求</span><span class="sxs-lookup"><span data-stu-id="5f6ce-110">Requirements</span></span>  
 <span data-ttu-id="5f6ce-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5f6ce-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f6ce-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5f6ce-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5f6ce-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5f6ce-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5f6ce-114">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f6ce-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f6ce-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="5f6ce-115">See also</span></span>
