---
title: ICorDebugEval::NewArray 方法
ms.date: 03/30/2017
api_name:
- ICorDebugEval.NewArray
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::NewArray
helpviewer_keywords:
- NewArray method [.NET Framework debugging]
- ICorDebugEval::NewArray method [.NET Framework debugging]
ms.assetid: cc79a67d-5368-434d-a943-209db90491b9
topic_type:
- apiref
ms.openlocfilehash: 13ac5379992f4e768b09a03d31591143ba9bf627
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788723"
---
# <a name="icordebugevalnewarray-method"></a><span data-ttu-id="46576-102">ICorDebugEval::NewArray 方法</span><span class="sxs-lookup"><span data-stu-id="46576-102">ICorDebugEval::NewArray Method</span></span>
<span data-ttu-id="46576-103">分配指定元素类型和维度的新数组。</span><span class="sxs-lookup"><span data-stu-id="46576-103">Allocates a new array of the specified element type and dimensions.</span></span>  
  
 <span data-ttu-id="46576-104">此方法在 .NET Framework 版本2.0 中已过时。</span><span class="sxs-lookup"><span data-stu-id="46576-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="46576-105">改[为使用 ICorDebugEval2：： NewParameterizedArray](icordebugeval2-newparameterizedarray-method.md) 。</span><span class="sxs-lookup"><span data-stu-id="46576-105">Use [ICorDebugEval2::NewParameterizedArray](icordebugeval2-newparameterizedarray-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46576-106">语法</span><span class="sxs-lookup"><span data-stu-id="46576-106">Syntax</span></span>  
  
```cpp  
HRESULT NewArray (  
    [in] CorElementType     elementType,  
    [in] ICorDebugClass     *pElementClass,  
    [in] ULONG32            rank,  
    [in, size_is(rank)] ULONG32 dims[],  
    [in, size_is(rank)] ULONG32 lowBounds[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="46576-107">参数</span><span class="sxs-lookup"><span data-stu-id="46576-107">Parameters</span></span>  
 `elementType`  
 <span data-ttu-id="46576-108">中CorElementType 枚举的一个值，该值指定数组的元素类型。</span><span class="sxs-lookup"><span data-stu-id="46576-108">[in] A value of the CorElementType enumeration that specifies the element type of the array.</span></span>  
  
 `pElementClass`  
 <span data-ttu-id="46576-109">中指向 ICorDebugClass 对象的指针，该对象指定元素的类。</span><span class="sxs-lookup"><span data-stu-id="46576-109">[in] A pointer to a ICorDebugClass object that specifies the class of the element.</span></span> <span data-ttu-id="46576-110">如果元素类型为基元类型，则此值可以为 null。</span><span class="sxs-lookup"><span data-stu-id="46576-110">This value may be null if the element type is a primitive type.</span></span>  
  
 `rank`  
 <span data-ttu-id="46576-111">中数组的维数。</span><span class="sxs-lookup"><span data-stu-id="46576-111">[in] The number of dimensions of the array.</span></span> <span data-ttu-id="46576-112">在 .NET Framework 2.0 中，此值必须为1。</span><span class="sxs-lookup"><span data-stu-id="46576-112">In the .NET Framework 2.0, this value must be 1.</span></span>  
  
 `dims`  
 <span data-ttu-id="46576-113">中数组每个维度的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="46576-113">[in] The size, in bytes, of each dimension of the array.</span></span>  
  
 `lowBounds`  
 <span data-ttu-id="46576-114">[in] 可选。</span><span class="sxs-lookup"><span data-stu-id="46576-114">[in] Optional.</span></span> <span data-ttu-id="46576-115">数组的每个维度的下限。</span><span class="sxs-lookup"><span data-stu-id="46576-115">The lower bound of each dimension of the array.</span></span> <span data-ttu-id="46576-116">如果省略此值，则假定每个维度的下限为零。</span><span class="sxs-lookup"><span data-stu-id="46576-116">If this value is omitted, a lower bound of zero is assumed for each dimension.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="46576-117">备注</span><span class="sxs-lookup"><span data-stu-id="46576-117">Remarks</span></span>  
 <span data-ttu-id="46576-118">始终在当前执行线程的应用程序域中创建数组。</span><span class="sxs-lookup"><span data-stu-id="46576-118">The array is always created in the application domain in which the thread is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="46576-119">需求</span><span class="sxs-lookup"><span data-stu-id="46576-119">Requirements</span></span>  
 <span data-ttu-id="46576-120">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="46576-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="46576-121">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="46576-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="46576-122">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="46576-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="46576-123">**.NET Framework 版本：** 1.1、1.0</span><span class="sxs-lookup"><span data-stu-id="46576-123">**.NET Framework Versions:** 1.1, 1.0</span></span>
