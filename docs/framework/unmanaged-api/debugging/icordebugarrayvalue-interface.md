---
title: "ICorDebugArrayValue 接口 1"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugArrayValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugArrayValue interface
helpviewer_keywords: ICorDebugArrayValue interface [.NET Framework debugging]
ms.assetid: dc437751-7093-44e2-bfdc-191d9ce3c192
topic_type: apiref
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 35169f0dd2ca71400d3aebddf9d5e2ae6b72be07
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugarrayvalue-interface1"></a><span data-ttu-id="133b0-102">ICorDebugArrayValue 接口 1</span><span class="sxs-lookup"><span data-stu-id="133b0-102">ICorDebugArrayValue Interface1</span></span>
<span data-ttu-id="133b0-103">ICorDebugHeapValue 表示一维或多维数组的一个子类。</span><span class="sxs-lookup"><span data-stu-id="133b0-103">A subclass of ICorDebugHeapValue that represents a single-dimensional or multi-dimensional array.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="133b0-104">方法</span><span class="sxs-lookup"><span data-stu-id="133b0-104">Methods</span></span>  
  
|<span data-ttu-id="133b0-105">方法</span><span class="sxs-lookup"><span data-stu-id="133b0-105">Method</span></span>|<span data-ttu-id="133b0-106">描述</span><span class="sxs-lookup"><span data-stu-id="133b0-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="133b0-107">GetBaseIndicies 方法</span><span class="sxs-lookup"><span data-stu-id="133b0-107">GetBaseIndicies Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getbaseindicies-method.md)|<span data-ttu-id="133b0-108">获取数组中的每个维度的基的索引。</span><span class="sxs-lookup"><span data-stu-id="133b0-108">Gets the base index of each dimension in the array.</span></span>|  
|[<span data-ttu-id="133b0-109">GetCount 方法</span><span class="sxs-lookup"><span data-stu-id="133b0-109">GetCount Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getcount-method.md)|<span data-ttu-id="133b0-110">获取数组中的元素总数。</span><span class="sxs-lookup"><span data-stu-id="133b0-110">Gets the total number of elements in the array.</span></span>|  
|[<span data-ttu-id="133b0-111">GetDimensions 方法</span><span class="sxs-lookup"><span data-stu-id="133b0-111">GetDimensions Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getdimensions-method.md)|<span data-ttu-id="133b0-112">获取数组的维数。</span><span class="sxs-lookup"><span data-stu-id="133b0-112">Gets the dimensions of the array.</span></span>|  
|[<span data-ttu-id="133b0-113">GetElement 方法</span><span class="sxs-lookup"><span data-stu-id="133b0-113">GetElement Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getelement-method.md)|<span data-ttu-id="133b0-114">获取表示给定的数组中元素的值。</span><span class="sxs-lookup"><span data-stu-id="133b0-114">Gets a value representing the given element in the array.</span></span>|  
|[<span data-ttu-id="133b0-115">GetElementAtPosition 方法</span><span class="sxs-lookup"><span data-stu-id="133b0-115">GetElementAtPosition Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getelementatposition-method.md)|<span data-ttu-id="133b0-116">获取位于给定位置，将数组视为的从零开始的一维数组的元素。</span><span class="sxs-lookup"><span data-stu-id="133b0-116">Gets the element at the given position, treating the array as a zero-based, single-dimensional array.</span></span>|  
|[<span data-ttu-id="133b0-117">GetElementType 方法</span><span class="sxs-lookup"><span data-stu-id="133b0-117">GetElementType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getelementtype-method.md)|<span data-ttu-id="133b0-118">获取数组中元素的简单类型。</span><span class="sxs-lookup"><span data-stu-id="133b0-118">Gets the simple type of the elements in the array.</span></span>|  
|[<span data-ttu-id="133b0-119">GetRank 方法</span><span class="sxs-lookup"><span data-stu-id="133b0-119">GetRank Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getrank-method.md)|<span data-ttu-id="133b0-120">获取数组中的维度数。</span><span class="sxs-lookup"><span data-stu-id="133b0-120">Gets the number of dimensions in the array.</span></span>|  
|[<span data-ttu-id="133b0-121">HasBaseIndicies 方法</span><span class="sxs-lookup"><span data-stu-id="133b0-121">HasBaseIndicies Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-hasbaseindicies-method.md)|<span data-ttu-id="133b0-122">确定数组是否具有基的索引。</span><span class="sxs-lookup"><span data-stu-id="133b0-122">Determines whether the array has base indexes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="133b0-123">备注</span><span class="sxs-lookup"><span data-stu-id="133b0-123">Remarks</span></span>  
 <span data-ttu-id="133b0-124">`ICorDebugArrayValue`支持的一维和多维数组。</span><span class="sxs-lookup"><span data-stu-id="133b0-124">`ICorDebugArrayValue` supports both single-dimensional and multi-dimensional arrays.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="133b0-125">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="133b0-125">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="133b0-126">惠?</span><span class="sxs-lookup"><span data-stu-id="133b0-126">Requirements</span></span>  
 <span data-ttu-id="133b0-127">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="133b0-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="133b0-128">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="133b0-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="133b0-129">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="133b0-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="133b0-130">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="133b0-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="133b0-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="133b0-131">See Also</span></span>  
 [<span data-ttu-id="133b0-132">调试接口</span><span class="sxs-lookup"><span data-stu-id="133b0-132">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
