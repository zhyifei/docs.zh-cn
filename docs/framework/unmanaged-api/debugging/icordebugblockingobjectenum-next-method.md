---
title: ICorDebugBlockingObjectEnum::Next 方法
ms.date: 03/30/2017
api_name:
- ICorDebugBlockingObjectEnum.Next Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBlockingObjectEnum::Next
helpviewer_keywords:
- Next method, ICorDebugBlockingObjectEnum interface [.NET Framework debugging]
- ICorDebugBlockingObjectEnum::Next method [.NET Framework debugging]
ms.assetid: 0121753f-ebea-48d0-aeb2-ed7fda76dc60
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b4336978825fbf7844b3ceaf179954f28660f08c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33409402"
---
# <a name="icordebugblockingobjectenumnext-method"></a><span data-ttu-id="a2578-102">ICorDebugBlockingObjectEnum::Next 方法</span><span class="sxs-lookup"><span data-stu-id="a2578-102">ICorDebugBlockingObjectEnum::Next Method</span></span>
<span data-ttu-id="a2578-103">获取指定的数目的[CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md)枚举，从当前位置开始中的对象。</span><span class="sxs-lookup"><span data-stu-id="a2578-103">Gets the specified number of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) objects from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2578-104">语法</span><span class="sxs-lookup"><span data-stu-id="a2578-104">Syntax</span></span>  
  
```  
HRESULT Next([in] ULONG  celt,  
             [out, size_is(celt), length_is(*pceltFetched)]  
                           CorDebugBlockingObject values[],  
             [out] ULONG *pceltFetched;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a2578-105">参数</span><span class="sxs-lookup"><span data-stu-id="a2578-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="a2578-106">[in]要检索的对象数。</span><span class="sxs-lookup"><span data-stu-id="a2578-106">[in] The number of objects to retrieve.</span></span>  
  
 `values`  
 <span data-ttu-id="a2578-107">[out]指向的指针的数组[CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md)对象。</span><span class="sxs-lookup"><span data-stu-id="a2578-107">[out] An array of pointers to [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) objects.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="a2578-108">[out]指向所检索到的对象数的指针。</span><span class="sxs-lookup"><span data-stu-id="a2578-108">[out] A pointer to the number of objects that were retrieved.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a2578-109">返回值</span><span class="sxs-lookup"><span data-stu-id="a2578-109">Return Value</span></span>  
 <span data-ttu-id="a2578-110">此方法会返回以下特定的 HRESULT。</span><span class="sxs-lookup"><span data-stu-id="a2578-110">This method returns the following specific HRESULTs.</span></span>  
  
|<span data-ttu-id="a2578-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a2578-111">HRESULT</span></span>|<span data-ttu-id="a2578-112">描述</span><span class="sxs-lookup"><span data-stu-id="a2578-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a2578-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="a2578-113">S_OK</span></span>|<span data-ttu-id="a2578-114">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="a2578-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="a2578-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="a2578-115">S_FALSE</span></span>|<span data-ttu-id="a2578-116">`pceltFetched` 不等于 `celt`。</span><span class="sxs-lookup"><span data-stu-id="a2578-116">`pceltFetched` does not equal `celt`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a2578-117">备注</span><span class="sxs-lookup"><span data-stu-id="a2578-117">Remarks</span></span>  
 <span data-ttu-id="a2578-118">此方法的功能类似的典型的 COM 枚举器。</span><span class="sxs-lookup"><span data-stu-id="a2578-118">This method functions like a typical COM enumerator.</span></span>  
  
 <span data-ttu-id="a2578-119">至少必须为输入的数组值的大小`celt`。</span><span class="sxs-lookup"><span data-stu-id="a2578-119">The input array values must be at least of size `celt`.</span></span> <span data-ttu-id="a2578-120">数组中将填充是下一步`celt`值在枚举中或使用所有剩余的值，如果少于`celt`保持。</span><span class="sxs-lookup"><span data-stu-id="a2578-120">The array will be filled with either the next `celt` values in the enumeration or with all remaining values if fewer than `celt` remain.</span></span> <span data-ttu-id="a2578-121">此方法返回时，`pceltFetched`中检索到的值数目中将填充。</span><span class="sxs-lookup"><span data-stu-id="a2578-121">When this method returns, `pceltFetched` will be filled with the number of values that were retrieved.</span></span> <span data-ttu-id="a2578-122">如果`values`包含无效的指针或指向的缓冲区，则小于`celt`，或者如果`pceltFetched`是无效的指针，结果不可确定。</span><span class="sxs-lookup"><span data-stu-id="a2578-122">If `values` contains invalid pointers or points to a buffer that is smaller than `celt`, or if `pceltFetched` is an invalid pointer, the result is undefined.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a2578-123">尽管[CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md)结构不需要释放，在其内部的"ICorDebugValue"接口确实需要释放。</span><span class="sxs-lookup"><span data-stu-id="a2578-123">Although the [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structure does not need to be released, the "ICorDebugValue" interface inside of it does need to be released.</span></span>  
  
-  
  
## <a name="requirements"></a><span data-ttu-id="a2578-124">要求</span><span class="sxs-lookup"><span data-stu-id="a2578-124">Requirements</span></span>  
 <span data-ttu-id="a2578-125">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a2578-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a2578-126">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a2578-126">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a2578-127">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a2578-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a2578-128">**.NET framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a2578-128">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2578-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="a2578-129">See Also</span></span>  
 [<span data-ttu-id="a2578-130">ICorDebugDataTarget 接口</span><span class="sxs-lookup"><span data-stu-id="a2578-130">ICorDebugDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)  
 [<span data-ttu-id="a2578-131">调试接口</span><span class="sxs-lookup"><span data-stu-id="a2578-131">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="a2578-132">调试</span><span class="sxs-lookup"><span data-stu-id="a2578-132">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
