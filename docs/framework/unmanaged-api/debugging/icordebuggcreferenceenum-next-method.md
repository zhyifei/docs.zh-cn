---
title: ICorDebugGCReferenceEnum::Next 方法
ms.date: 03/30/2017
api_name:
- ICorDebugGCReferenceEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGCReferenceEnum::Next
helpviewer_keywords:
- Next method, ICorDebugGCReferenceEnum interface [.NET Framework debugging]
- ICorDebugGCReferenceEnum::Next method [.NET Framework debugging]
ms.assetid: 91b1345c-a94f-4ef8-9696-3823d06c6d05
topic_type:
- apiref
ms.openlocfilehash: d87f414e9dfd05a519b60efc7ecdd5328a6dd86f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178870"
---
# <a name="icordebuggcreferenceenumnext-method"></a><span data-ttu-id="212cb-102">ICorDebugGCReferenceEnum::Next 方法</span><span class="sxs-lookup"><span data-stu-id="212cb-102">ICorDebugGCReferenceEnum::Next Method</span></span>
<span data-ttu-id="212cb-103">获取指定数量的[COR_GC_REFERENCE](cor-gc-reference-structure.md)实例，这些实例包含有关将垃圾回收的对象的信息。</span><span class="sxs-lookup"><span data-stu-id="212cb-103">Gets the specified number of [COR_GC_REFERENCE](cor-gc-reference-structure.md) instances that contain information about objects that will be garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="212cb-104">语法</span><span class="sxs-lookup"><span data-stu-id="212cb-104">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_GC_REFERENCE roots[],
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="212cb-105">parameters</span><span class="sxs-lookup"><span data-stu-id="212cb-105">Parameters</span></span>  
 <span data-ttu-id="212cb-106">celt</span><span class="sxs-lookup"><span data-stu-id="212cb-106">celt</span></span>  
 <span data-ttu-id="212cb-107">[在]要检索的根数。</span><span class="sxs-lookup"><span data-stu-id="212cb-107">[in] The number of roots to be retrieved.</span></span>  
  
 <span data-ttu-id="212cb-108">根</span><span class="sxs-lookup"><span data-stu-id="212cb-108">roots</span></span>  
 <span data-ttu-id="212cb-109">[出]指针数组，每个指针都指向表示要垃圾回收的对象的根[COR_GC_REFERENCE](cor-gc-reference-structure.md)对象。</span><span class="sxs-lookup"><span data-stu-id="212cb-109">[out] An array of pointers, each of which points to a [COR_GC_REFERENCE](cor-gc-reference-structure.md) object that represents the root of an object to be garbage-collected.</span></span>  
  
 <span data-ttu-id="212cb-110">pceltFetched</span><span class="sxs-lookup"><span data-stu-id="212cb-110">pceltFetched</span></span>  
 <span data-ttu-id="212cb-111">[出]指向中实际返回的对象数[COR_GC_REFERENCE](cor-gc-reference-structure.md)的指针`roots`。</span><span class="sxs-lookup"><span data-stu-id="212cb-111">[out] A pointer to the number of [COR_GC_REFERENCE](cor-gc-reference-structure.md) objects actually returned in `roots`.</span></span> <span data-ttu-id="212cb-112">如果 `celt` 为 1，此值可能为 `null`。</span><span class="sxs-lookup"><span data-stu-id="212cb-112">This value may be `null` if `celt` is 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="212cb-113">备注</span><span class="sxs-lookup"><span data-stu-id="212cb-113">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="212cb-114">要求</span><span class="sxs-lookup"><span data-stu-id="212cb-114">Requirements</span></span>  
 <span data-ttu-id="212cb-115">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="212cb-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="212cb-116">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="212cb-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="212cb-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="212cb-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="212cb-118">**.NET 框架版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="212cb-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="212cb-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="212cb-119">See also</span></span>

- [<span data-ttu-id="212cb-120">ICorDebugGCReferenceEnum 接口</span><span class="sxs-lookup"><span data-stu-id="212cb-120">ICorDebugGCReferenceEnum Interface</span></span>](icordebuggcreferenceenum-interface.md)
- [<span data-ttu-id="212cb-121">调试接口</span><span class="sxs-lookup"><span data-stu-id="212cb-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
