---
title: ICorDebugTypeEnum::Next 方法
ms.date: 03/30/2017
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
ms.openlocfilehash: fc205e347fc39fd486d9b8a3fb256a5d29a980a2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73110068"
---
# <a name="icordebugtypeenumnext-method"></a><span data-ttu-id="44549-102">ICorDebugTypeEnum::Next 方法</span><span class="sxs-lookup"><span data-stu-id="44549-102">ICorDebugTypeEnum::Next Method</span></span>
<span data-ttu-id="44549-103">从当前位置开始，获取从枚举 `celt` 指定的 "ICorDebugType" 实例的数目。</span><span class="sxs-lookup"><span data-stu-id="44549-103">Gets the number of "ICorDebugType" instances specified by `celt` from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44549-104">语法</span><span class="sxs-lookup"><span data-stu-id="44549-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in]  ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugType *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="44549-105">参数</span><span class="sxs-lookup"><span data-stu-id="44549-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="44549-106">中要检索的 `ICorDebugType` 实例的数目。</span><span class="sxs-lookup"><span data-stu-id="44549-106">[in] The number of `ICorDebugType` instances to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="44549-107">弄指针的数组，其中每个都指向一个 `ICorDebugType` 对象。</span><span class="sxs-lookup"><span data-stu-id="44549-107">[out] An array of pointers, each of which points to an `ICorDebugType` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="44549-108">弄一个指针，指向实际返回的 `ICorDebugType` 实例的数目。</span><span class="sxs-lookup"><span data-stu-id="44549-108">[out] Pointer to the number of `ICorDebugType` instances actually returned.</span></span> <span data-ttu-id="44549-109">如果 `celt` 为1，则此值可以为 null。</span><span class="sxs-lookup"><span data-stu-id="44549-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="44549-110">要求</span><span class="sxs-lookup"><span data-stu-id="44549-110">Requirements</span></span>  
 <span data-ttu-id="44549-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="44549-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44549-112">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="44549-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="44549-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="44549-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="44549-114">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44549-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44549-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="44549-115">See also</span></span>
