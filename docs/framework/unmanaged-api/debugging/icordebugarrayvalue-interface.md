---
title: ICorDebugArrayValue 接口
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue interface
helpviewer_keywords:
- ICorDebugArrayValue interface [.NET Framework debugging]
ms.assetid: dc437751-7093-44e2-bfdc-191d9ce3c192
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 99bd3e9ae1faec1b71933681fadf4816b4789c98
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69952208"
---
# <a name="icordebugarrayvalue-interface"></a><span data-ttu-id="1a103-102">ICorDebugArrayValue 接口</span><span class="sxs-lookup"><span data-stu-id="1a103-102">ICorDebugArrayValue Interface</span></span>

<span data-ttu-id="1a103-103">表示一维或多维数组的 ICorDebugHeapValue 的子类。</span><span class="sxs-lookup"><span data-stu-id="1a103-103">A subclass of ICorDebugHeapValue that represents a single-dimensional or multi-dimensional array.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1a103-104">方法</span><span class="sxs-lookup"><span data-stu-id="1a103-104">Methods</span></span>  
  
|<span data-ttu-id="1a103-105">方法</span><span class="sxs-lookup"><span data-stu-id="1a103-105">Method</span></span>|<span data-ttu-id="1a103-106">描述</span><span class="sxs-lookup"><span data-stu-id="1a103-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1a103-107">GetBaseIndicies 方法</span><span class="sxs-lookup"><span data-stu-id="1a103-107">GetBaseIndicies Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getbaseindicies-method.md)|<span data-ttu-id="1a103-108">获取数组中每个维的基索引。</span><span class="sxs-lookup"><span data-stu-id="1a103-108">Gets the base index of each dimension in the array.</span></span>|  
|[<span data-ttu-id="1a103-109">GetCount 方法</span><span class="sxs-lookup"><span data-stu-id="1a103-109">GetCount Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getcount-method.md)|<span data-ttu-id="1a103-110">获取数组中的元素总数。</span><span class="sxs-lookup"><span data-stu-id="1a103-110">Gets the total number of elements in the array.</span></span>|  
|[<span data-ttu-id="1a103-111">GetDimensions 方法</span><span class="sxs-lookup"><span data-stu-id="1a103-111">GetDimensions Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getdimensions-method.md)|<span data-ttu-id="1a103-112">获取数组的尺寸。</span><span class="sxs-lookup"><span data-stu-id="1a103-112">Gets the dimensions of the array.</span></span>|  
|[<span data-ttu-id="1a103-113">GetElement 方法</span><span class="sxs-lookup"><span data-stu-id="1a103-113">GetElement Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getelement-method.md)|<span data-ttu-id="1a103-114">获取一个值, 该值表示数组中的给定元素。</span><span class="sxs-lookup"><span data-stu-id="1a103-114">Gets a value representing the given element in the array.</span></span>|  
|[<span data-ttu-id="1a103-115">GetElementAtPosition 方法</span><span class="sxs-lookup"><span data-stu-id="1a103-115">GetElementAtPosition Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getelementatposition-method.md)|<span data-ttu-id="1a103-116">获取位于给定位置的元素, 并将该数组视为从零开始的一维数组。</span><span class="sxs-lookup"><span data-stu-id="1a103-116">Gets the element at the given position, treating the array as a zero-based, single-dimensional array.</span></span>|  
|[<span data-ttu-id="1a103-117">GetElementType 方法</span><span class="sxs-lookup"><span data-stu-id="1a103-117">GetElementType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getelementtype-method.md)|<span data-ttu-id="1a103-118">获取数组中元素的简单类型。</span><span class="sxs-lookup"><span data-stu-id="1a103-118">Gets the simple type of the elements in the array.</span></span>|  
|[<span data-ttu-id="1a103-119">GetRank 方法</span><span class="sxs-lookup"><span data-stu-id="1a103-119">GetRank Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getrank-method.md)|<span data-ttu-id="1a103-120">获取数组中的维度数。</span><span class="sxs-lookup"><span data-stu-id="1a103-120">Gets the number of dimensions in the array.</span></span>|  
|[<span data-ttu-id="1a103-121">HasBaseIndicies 方法</span><span class="sxs-lookup"><span data-stu-id="1a103-121">HasBaseIndicies Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-hasbaseindicies-method.md)|<span data-ttu-id="1a103-122">确定数组是否具有基索引。</span><span class="sxs-lookup"><span data-stu-id="1a103-122">Determines whether the array has base indexes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1a103-123">备注</span><span class="sxs-lookup"><span data-stu-id="1a103-123">Remarks</span></span>  
 <span data-ttu-id="1a103-124">`ICorDebugArrayValue`支持一维数组和多维数组。</span><span class="sxs-lookup"><span data-stu-id="1a103-124">`ICorDebugArrayValue` supports both single-dimensional and multi-dimensional arrays.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1a103-125">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="1a103-125">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1a103-126">要求</span><span class="sxs-lookup"><span data-stu-id="1a103-126">Requirements</span></span>  
 <span data-ttu-id="1a103-127">**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1a103-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1a103-128">**标头：** Cordebug.idl, Cordebug.idl</span><span class="sxs-lookup"><span data-stu-id="1a103-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1a103-129">**类库**CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1a103-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1a103-130">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1a103-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a103-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="1a103-131">See also</span></span>

- [<span data-ttu-id="1a103-132">调试接口</span><span class="sxs-lookup"><span data-stu-id="1a103-132">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
