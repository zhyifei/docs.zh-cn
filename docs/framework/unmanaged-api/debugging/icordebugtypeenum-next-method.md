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
ms.openlocfilehash: 83adea3d659eea6d4af9ae364aad18df67e69c03
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396622"
---
# <a name="icordebugtypeenumnext-method"></a><span data-ttu-id="9ca23-102">ICorDebugTypeEnum::Next 方法</span><span class="sxs-lookup"><span data-stu-id="9ca23-102">ICorDebugTypeEnum::Next Method</span></span>
<span data-ttu-id="9ca23-103">从当前位置开始，获取由枚举指定的 "ICorDebugType" 实例的数目 `celt` 。</span><span class="sxs-lookup"><span data-stu-id="9ca23-103">Gets the number of "ICorDebugType" instances specified by `celt` from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ca23-104">语法</span><span class="sxs-lookup"><span data-stu-id="9ca23-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in]  ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugType *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9ca23-105">参数</span><span class="sxs-lookup"><span data-stu-id="9ca23-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="9ca23-106">中`ICorDebugType`要检索的实例数。</span><span class="sxs-lookup"><span data-stu-id="9ca23-106">[in] The number of `ICorDebugType` instances to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="9ca23-107">弄指针的数组，其中每个都指向一个 `ICorDebugType` 对象。</span><span class="sxs-lookup"><span data-stu-id="9ca23-107">[out] An array of pointers, each of which points to an `ICorDebugType` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="9ca23-108">弄一个指针，指向 `ICorDebugType` 实际返回的实例数。</span><span class="sxs-lookup"><span data-stu-id="9ca23-108">[out] Pointer to the number of `ICorDebugType` instances actually returned.</span></span> <span data-ttu-id="9ca23-109">如果为1，则此值可以为 null `celt` 。</span><span class="sxs-lookup"><span data-stu-id="9ca23-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ca23-110">要求</span><span class="sxs-lookup"><span data-stu-id="9ca23-110">Requirements</span></span>  
 <span data-ttu-id="9ca23-111">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9ca23-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ca23-112">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9ca23-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9ca23-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9ca23-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9ca23-114">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ca23-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ca23-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="9ca23-115">See also</span></span>
