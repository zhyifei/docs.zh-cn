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
ms.openlocfilehash: 67fd1a9174b04e42b53f2b866a1dfdd504362aa9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61645612"
---
# <a name="icordebugarrayvalue-interface"></a><span data-ttu-id="1c11d-102">ICorDebugArrayValue 接口</span><span class="sxs-lookup"><span data-stu-id="1c11d-102">ICorDebugArrayValue Interface</span></span>

<span data-ttu-id="1c11d-103">表示一维或多维数组的 ICorDebugHeapValue 子类。</span><span class="sxs-lookup"><span data-stu-id="1c11d-103">A subclass of ICorDebugHeapValue that represents a single-dimensional or multi-dimensional array.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1c11d-104">方法</span><span class="sxs-lookup"><span data-stu-id="1c11d-104">Methods</span></span>  
  
|<span data-ttu-id="1c11d-105">方法</span><span class="sxs-lookup"><span data-stu-id="1c11d-105">Method</span></span>|<span data-ttu-id="1c11d-106">描述</span><span class="sxs-lookup"><span data-stu-id="1c11d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1c11d-107">GetBaseIndicies 方法</span><span class="sxs-lookup"><span data-stu-id="1c11d-107">GetBaseIndicies Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getbaseindicies-method.md)|<span data-ttu-id="1c11d-108">获取数组中的每个维的基索引。</span><span class="sxs-lookup"><span data-stu-id="1c11d-108">Gets the base index of each dimension in the array.</span></span>|  
|[<span data-ttu-id="1c11d-109">GetCount 方法</span><span class="sxs-lookup"><span data-stu-id="1c11d-109">GetCount Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getcount-method.md)|<span data-ttu-id="1c11d-110">获取数组中的元素总数。</span><span class="sxs-lookup"><span data-stu-id="1c11d-110">Gets the total number of elements in the array.</span></span>|  
|[<span data-ttu-id="1c11d-111">GetDimensions 方法</span><span class="sxs-lookup"><span data-stu-id="1c11d-111">GetDimensions Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getdimensions-method.md)|<span data-ttu-id="1c11d-112">获取数组的维数。</span><span class="sxs-lookup"><span data-stu-id="1c11d-112">Gets the dimensions of the array.</span></span>|  
|[<span data-ttu-id="1c11d-113">GetElement 方法</span><span class="sxs-lookup"><span data-stu-id="1c11d-113">GetElement Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getelement-method.md)|<span data-ttu-id="1c11d-114">获取表示给定的数组中元素的值。</span><span class="sxs-lookup"><span data-stu-id="1c11d-114">Gets a value representing the given element in the array.</span></span>|  
|[<span data-ttu-id="1c11d-115">GetElementAtPosition 方法</span><span class="sxs-lookup"><span data-stu-id="1c11d-115">GetElementAtPosition Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getelementatposition-method.md)|<span data-ttu-id="1c11d-116">获取位于给定位置，将数组视为从零开始的一维数组的元素。</span><span class="sxs-lookup"><span data-stu-id="1c11d-116">Gets the element at the given position, treating the array as a zero-based, single-dimensional array.</span></span>|  
|[<span data-ttu-id="1c11d-117">GetElementType 方法</span><span class="sxs-lookup"><span data-stu-id="1c11d-117">GetElementType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getelementtype-method.md)|<span data-ttu-id="1c11d-118">获取数组中元素的简单类型。</span><span class="sxs-lookup"><span data-stu-id="1c11d-118">Gets the simple type of the elements in the array.</span></span>|  
|[<span data-ttu-id="1c11d-119">GetRank 方法</span><span class="sxs-lookup"><span data-stu-id="1c11d-119">GetRank Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getrank-method.md)|<span data-ttu-id="1c11d-120">获取数组中的维度数。</span><span class="sxs-lookup"><span data-stu-id="1c11d-120">Gets the number of dimensions in the array.</span></span>|  
|[<span data-ttu-id="1c11d-121">HasBaseIndicies 方法</span><span class="sxs-lookup"><span data-stu-id="1c11d-121">HasBaseIndicies Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-hasbaseindicies-method.md)|<span data-ttu-id="1c11d-122">确定数组是否具有基索引。</span><span class="sxs-lookup"><span data-stu-id="1c11d-122">Determines whether the array has base indexes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1c11d-123">备注</span><span class="sxs-lookup"><span data-stu-id="1c11d-123">Remarks</span></span>  
 <span data-ttu-id="1c11d-124">`ICorDebugArrayValue` 支持单维度和多维数组。</span><span class="sxs-lookup"><span data-stu-id="1c11d-124">`ICorDebugArrayValue` supports both single-dimensional and multi-dimensional arrays.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1c11d-125">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="1c11d-125">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c11d-126">要求</span><span class="sxs-lookup"><span data-stu-id="1c11d-126">Requirements</span></span>  
 <span data-ttu-id="1c11d-127">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1c11d-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c11d-128">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1c11d-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1c11d-129">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1c11d-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1c11d-130">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c11d-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c11d-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="1c11d-131">See also</span></span>

- [<span data-ttu-id="1c11d-132">调试接口</span><span class="sxs-lookup"><span data-stu-id="1c11d-132">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
