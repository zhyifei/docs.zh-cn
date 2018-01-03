---
title: "ICorDebugEval::NewArray 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugEval.NewArray
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugEval::NewArray
helpviewer_keywords:
- NewArray method [.NET Framework debugging]
- ICorDebugEval::NewArray method [.NET Framework debugging]
ms.assetid: cc79a67d-5368-434d-a943-209db90491b9
topic_type: apiref
caps.latest.revision: "19"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f9116c2ee7edbc39d203728909ce37e963c896fc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugevalnewarray-method"></a><span data-ttu-id="d7c50-102">ICorDebugEval::NewArray 方法</span><span class="sxs-lookup"><span data-stu-id="d7c50-102">ICorDebugEval::NewArray Method</span></span>
<span data-ttu-id="d7c50-103">分配的指定的元素类型和维度的一个新数组。</span><span class="sxs-lookup"><span data-stu-id="d7c50-103">Allocates a new array of the specified element type and dimensions.</span></span>  
  
 <span data-ttu-id="d7c50-104">此方法是.NET Framework 2.0 版中过时。</span><span class="sxs-lookup"><span data-stu-id="d7c50-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="d7c50-105">使用[icordebugeval2:: Newparameterizedarray](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedarray-method.md)相反。</span><span class="sxs-lookup"><span data-stu-id="d7c50-105">Use [ICorDebugEval2::NewParameterizedArray](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedarray-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7c50-106">语法</span><span class="sxs-lookup"><span data-stu-id="d7c50-106">Syntax</span></span>  
  
```  
HRESULT NewArray (  
    [in] CorElementType     elementType,  
    [in] ICorDebugClass     *pElementClass,  
    [in] ULONG32            rank,  
    [in, size_is(rank)] ULONG32 dims[],  
    [in, size_is(rank)] ULONG32 lowBounds[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d7c50-107">参数</span><span class="sxs-lookup"><span data-stu-id="d7c50-107">Parameters</span></span>  
 `elementType`  
 <span data-ttu-id="d7c50-108">[in]CorElementType 枚举，指定数组的元素类型的值。</span><span class="sxs-lookup"><span data-stu-id="d7c50-108">[in] A value of the CorElementType enumeration that specifies the element type of the array.</span></span>  
  
 `pElementClass`  
 <span data-ttu-id="d7c50-109">[in]指向一个指定元素的类的 ICorDebugClass 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="d7c50-109">[in] A pointer to a ICorDebugClass object that specifies the class of the element.</span></span> <span data-ttu-id="d7c50-110">此值可能为 null 的基元类型的元素类型时。</span><span class="sxs-lookup"><span data-stu-id="d7c50-110">This value may be null if the element type is a primitive type.</span></span>  
  
 `rank`  
 <span data-ttu-id="d7c50-111">[in]数组的维度数。</span><span class="sxs-lookup"><span data-stu-id="d7c50-111">[in] The number of dimensions of the array.</span></span> <span data-ttu-id="d7c50-112">在.NET Framework 2.0 中，此值必须为 1。</span><span class="sxs-lookup"><span data-stu-id="d7c50-112">In the .NET Framework 2.0, this value must be 1.</span></span>  
  
 `dims`  
 <span data-ttu-id="d7c50-113">[in]以字节为单位，每个维度的数组大小。</span><span class="sxs-lookup"><span data-stu-id="d7c50-113">[in] The size, in bytes, of each dimension of the array.</span></span>  
  
 `lowBounds`  
 <span data-ttu-id="d7c50-114">[in] 可选。</span><span class="sxs-lookup"><span data-stu-id="d7c50-114">[in] Optional.</span></span> <span data-ttu-id="d7c50-115">数组的每个维度的下限。</span><span class="sxs-lookup"><span data-stu-id="d7c50-115">The lower bound of each dimension of the array.</span></span> <span data-ttu-id="d7c50-116">如果省略此值，每个维度假设下限为零。</span><span class="sxs-lookup"><span data-stu-id="d7c50-116">If this value is omitted, a lower bound of zero is assumed for each dimension.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d7c50-117">备注</span><span class="sxs-lookup"><span data-stu-id="d7c50-117">Remarks</span></span>  
 <span data-ttu-id="d7c50-118">始终在线程当前执行的应用程序域中创建数组。</span><span class="sxs-lookup"><span data-stu-id="d7c50-118">The array is always created in the application domain in which the thread is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7c50-119">惠?</span><span class="sxs-lookup"><span data-stu-id="d7c50-119">Requirements</span></span>  
 <span data-ttu-id="d7c50-120">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d7c50-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7c50-121">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d7c50-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d7c50-122">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d7c50-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d7c50-123">**.NET framework 版本：** 1.1、 1.0</span><span class="sxs-lookup"><span data-stu-id="d7c50-123">**.NET Framework Versions:** 1.1, 1.0</span></span>
