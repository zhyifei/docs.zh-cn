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
ms.openlocfilehash: 9d589bfc3093d03d87acb47ade0fc6c972bcd335
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976104"
---
# <a name="icordebugeval2newparameterizedarray-method"></a><span data-ttu-id="6e4f3-102">ICorDebugEval2::NewParameterizedArray 方法</span><span class="sxs-lookup"><span data-stu-id="6e4f3-102">ICorDebugEval2::NewParameterizedArray Method</span></span>
<span data-ttu-id="6e4f3-103">分配指定元素类型和维度的新数组。</span><span class="sxs-lookup"><span data-stu-id="6e4f3-103">Allocates a new array of the specified element type and dimensions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e4f3-104">语法</span><span class="sxs-lookup"><span data-stu-id="6e4f3-104">Syntax</span></span>  
  
```cpp  
HRESULT NewParameterizedArray(  
    [in] ICorDebugType          *pElementType,  
    [in] ULONG32                rank,  
    [in, size_is(rank)] ULONG32 dims[],  
    [in, size_is(rank)] ULONG32 lowBounds[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6e4f3-105">参数</span><span class="sxs-lookup"><span data-stu-id="6e4f3-105">Parameters</span></span>  
 `pElementType`  
 <span data-ttu-id="6e4f3-106">中指向 ICorDebugType 对象的指针，该对象表示存储在数组中的元素的类型。</span><span class="sxs-lookup"><span data-stu-id="6e4f3-106">[in] A pointer to an ICorDebugType object that represents the type of element stored in the array.</span></span>  
  
 `rank`  
 <span data-ttu-id="6e4f3-107">中数组的维数。</span><span class="sxs-lookup"><span data-stu-id="6e4f3-107">[in] The number of dimensions of the array.</span></span> <span data-ttu-id="6e4f3-108">在 .NET Framework 版本2.0 中，此值必须为1。</span><span class="sxs-lookup"><span data-stu-id="6e4f3-108">In the .NET Framework version 2.0, this value must be 1.</span></span>  
  
 `dims`  
 <span data-ttu-id="6e4f3-109">中数组每个维度的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="6e4f3-109">[in] The size, in bytes, of each dimension of the array.</span></span>  
  
 `lowBounds`  
 <span data-ttu-id="6e4f3-110">[in] 可选。</span><span class="sxs-lookup"><span data-stu-id="6e4f3-110">[in] Optional.</span></span> <span data-ttu-id="6e4f3-111">数组的每个维度的下限。</span><span class="sxs-lookup"><span data-stu-id="6e4f3-111">The lower bound of each dimension of the array.</span></span> <span data-ttu-id="6e4f3-112">如果省略此值，则假定每个维度的下限为零。</span><span class="sxs-lookup"><span data-stu-id="6e4f3-112">If this value is omitted, a lower bound of zero is assumed for each dimension.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6e4f3-113">备注</span><span class="sxs-lookup"><span data-stu-id="6e4f3-113">Remarks</span></span>  
 <span data-ttu-id="6e4f3-114">数组的元素可以是泛型类型的实例。</span><span class="sxs-lookup"><span data-stu-id="6e4f3-114">The elements of the array may be instances of a generic type.</span></span> <span data-ttu-id="6e4f3-115">始终在当前运行线程的应用程序域中创建数组。</span><span class="sxs-lookup"><span data-stu-id="6e4f3-115">The array is always created in the application domain in which the thread is currently running.</span></span> <span data-ttu-id="6e4f3-116">在 .NET Framework 2.0 中，的`rank`值必须为1。</span><span class="sxs-lookup"><span data-stu-id="6e4f3-116">In the .NET Framework 2.0, the value of `rank` must be 1.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e4f3-117">要求</span><span class="sxs-lookup"><span data-stu-id="6e4f3-117">Requirements</span></span>  
 <span data-ttu-id="6e4f3-118">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6e4f3-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6e4f3-119">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6e4f3-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6e4f3-120">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6e4f3-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6e4f3-121">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6e4f3-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
