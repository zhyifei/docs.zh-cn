---
title: ICorDebugEval2::NewParameterizedArray 方法
ms.date: 03/30/2017
api_name:
- ICorDebugEval2.NewParameterizedArray
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::NewParameterizedArray
helpviewer_keywords:
- ICorDebugEval2::NewParameterizedArray method [.NET Framework debugging]
- NewParameterizedArray method [.NET Framework debugging]
ms.assetid: 45efb8ba-c4de-4109-945f-e734d376b43c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8c639204fa207774b0e362f1ba8fe71937494ae2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61988972"
---
# <a name="icordebugeval2newparameterizedarray-method"></a><span data-ttu-id="ba040-102">ICorDebugEval2::NewParameterizedArray 方法</span><span class="sxs-lookup"><span data-stu-id="ba040-102">ICorDebugEval2::NewParameterizedArray Method</span></span>
<span data-ttu-id="ba040-103">分配的指定的元素类型和维度的一个新数组。</span><span class="sxs-lookup"><span data-stu-id="ba040-103">Allocates a new array of the specified element type and dimensions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba040-104">语法</span><span class="sxs-lookup"><span data-stu-id="ba040-104">Syntax</span></span>  
  
```  
HRESULT NewParameterizedArray(  
    [in] ICorDebugType          *pElementType,  
    [in] ULONG32                rank,  
    [in, size_is(rank)] ULONG32 dims[],  
    [in, size_is(rank)] ULONG32 lowBounds[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ba040-105">参数</span><span class="sxs-lookup"><span data-stu-id="ba040-105">Parameters</span></span>  
 `pElementType`  
 <span data-ttu-id="ba040-106">[in]指向一个 ICorDebugType 对象，表示存储在数组中元素的类型的指针。</span><span class="sxs-lookup"><span data-stu-id="ba040-106">[in] A pointer to an ICorDebugType object that represents the type of element stored in the array.</span></span>  
  
 `rank`  
 <span data-ttu-id="ba040-107">[in]数组的维度数。</span><span class="sxs-lookup"><span data-stu-id="ba040-107">[in] The number of dimensions of the array.</span></span> <span data-ttu-id="ba040-108">在.NET Framework 2.0 版中，此值必须为 1。</span><span class="sxs-lookup"><span data-stu-id="ba040-108">In the .NET Framework version 2.0, this value must be 1.</span></span>  
  
 `dims`  
 <span data-ttu-id="ba040-109">[in]以字节为单位，每个维度的数组大小。</span><span class="sxs-lookup"><span data-stu-id="ba040-109">[in] The size, in bytes, of each dimension of the array.</span></span>  
  
 `lowBounds`  
 <span data-ttu-id="ba040-110">[in] 可选。</span><span class="sxs-lookup"><span data-stu-id="ba040-110">[in] Optional.</span></span> <span data-ttu-id="ba040-111">数组的每个维度的下限。</span><span class="sxs-lookup"><span data-stu-id="ba040-111">The lower bound of each dimension of the array.</span></span> <span data-ttu-id="ba040-112">如果省略此值，下限为零则假定为每个维度。</span><span class="sxs-lookup"><span data-stu-id="ba040-112">If this value is omitted, a lower bound of zero is assumed for each dimension.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ba040-113">备注</span><span class="sxs-lookup"><span data-stu-id="ba040-113">Remarks</span></span>  
 <span data-ttu-id="ba040-114">数组的元素可能是泛型类型的实例。</span><span class="sxs-lookup"><span data-stu-id="ba040-114">The elements of the array may be instances of a generic type.</span></span> <span data-ttu-id="ba040-115">始终在线程当前运行的应用程序域中创建数组。</span><span class="sxs-lookup"><span data-stu-id="ba040-115">The array is always created in the application domain in which the thread is currently running.</span></span> <span data-ttu-id="ba040-116">在.NET Framework 2.0 中，值`rank`必须为 1。</span><span class="sxs-lookup"><span data-stu-id="ba040-116">In the .NET Framework 2.0, the value of `rank` must be 1.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ba040-117">要求</span><span class="sxs-lookup"><span data-stu-id="ba040-117">Requirements</span></span>  
 <span data-ttu-id="ba040-118">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ba040-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ba040-119">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ba040-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ba040-120">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ba040-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ba040-121">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ba040-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
