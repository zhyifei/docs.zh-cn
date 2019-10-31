---
title: ICorDebugType::EnumerateTypeParameters 方法
ms.date: 03/30/2017
api_name:
- ICorDebugType.EnumerateTypeParameters
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::EnumerateTypeParameters
helpviewer_keywords:
- EnumerateTypeParameters method, ICorDebugType interface [.NET Framework debugging]
- ICorDebugType::EnumerateTypeParameters method [.NET Framework debugging]
ms.assetid: 1ee1f6e6-1bd7-4ebb-83b8-ff9a08ca03de
topic_type:
- apiref
ms.openlocfilehash: 57a82e4ec106fead105cc7f200e7e56026004328
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122384"
---
# <a name="icordebugtypeenumeratetypeparameters-method"></a><span data-ttu-id="d90e7-102">ICorDebugType::EnumerateTypeParameters 方法</span><span class="sxs-lookup"><span data-stu-id="d90e7-102">ICorDebugType::EnumerateTypeParameters Method</span></span>
<span data-ttu-id="d90e7-103">获取一个接口指针，该指针指向包含此 ICorDebugType 引用的类的 <xref:System.Type> 参数的 ICorDebugTypeEnum。</span><span class="sxs-lookup"><span data-stu-id="d90e7-103">Gets an interface pointer to an ICorDebugTypeEnum that contains the <xref:System.Type> parameters of the class referenced by this ICorDebugType.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d90e7-104">语法</span><span class="sxs-lookup"><span data-stu-id="d90e7-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateTypeParameters (  
    [out] ICorDebugTypeEnum   **ppTyParEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d90e7-105">参数</span><span class="sxs-lookup"><span data-stu-id="d90e7-105">Parameters</span></span>  
 `ppTyParEnum`  
 <span data-ttu-id="d90e7-106">弄一个指针，指向包含类型参数的 `ICorDebugTypeEnum` 的地址。</span><span class="sxs-lookup"><span data-stu-id="d90e7-106">[out] A pointer to the address of an `ICorDebugTypeEnum` that contains the parameters of the type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d90e7-107">备注</span><span class="sxs-lookup"><span data-stu-id="d90e7-107">Remarks</span></span>  
 <span data-ttu-id="d90e7-108">如果[ICorDebugType：： GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md)返回的 CorElementType 值为 ELEMENT_TYPE_CLASS、ELEMENT_TYPE_VALUETYPE、ELEMENT_TYPE_ARRAY、ELEMENT_TYPE_SZARRAY、ELEMENT_TYPE_BYREF、ELEMENT_TYPE_PTR 或 ELEMENT_TYPE_FNPTR，则可以使用 `EnumerateTypeParameters`。</span><span class="sxs-lookup"><span data-stu-id="d90e7-108">You can use `EnumerateTypeParameters` if the CorElementType value returned by [ICorDebugType::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) is ELEMENT_TYPE_CLASS, ELEMENT_TYPE_VALUETYPE, ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF, ELEMENT_TYPE_PTR, or ELEMENT_TYPE_FNPTR.</span></span> <span data-ttu-id="d90e7-109">参数的数量及其顺序取决于类型：</span><span class="sxs-lookup"><span data-stu-id="d90e7-109">The number of parameters and their order depends on the type:</span></span>  
  
- <span data-ttu-id="d90e7-110">ELEMENT_TYPE_CLASS 或 ELEMENT_TYPE_VALUETYPE：此方法返回 `ICorDebugTypeEnum` 中包含的类型参数的数量将取决于相应类的形参数量。</span><span class="sxs-lookup"><span data-stu-id="d90e7-110">ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE: The number of type parameters contained in the `ICorDebugTypeEnum` that this method returns, will depend on the number of formal type parameters for the corresponding class.</span></span> <span data-ttu-id="d90e7-111">例如，如果类型为 `class Dict<String,int32>`，则 `EnumerateTypeParameters` 将返回一个 `ICorDebugTypeEnum`，其中包含按顺序表示 `String` 和 `int32` 的对象。</span><span class="sxs-lookup"><span data-stu-id="d90e7-111">For example, if the type is `class Dict<String,int32>`, then `EnumerateTypeParameters` will return an `ICorDebugTypeEnum` that contains objects representing `String` and `int32` in sequence.</span></span>  
  
- <span data-ttu-id="d90e7-112">ELEMENT_TYPE_FNPTR： `ICorDebugTypeEnum` 中包含的类型参数的数目将大于函数接受的参数数量。</span><span class="sxs-lookup"><span data-stu-id="d90e7-112">ELEMENT_TYPE_FNPTR: The number of type parameters contained in the `ICorDebugTypeEnum` will be one greater than the number of arguments accepted by the function.</span></span> <span data-ttu-id="d90e7-113">`ICorDebugTypeEnum` 中包含的第一个类型参数是函数的返回类型，并且后续类型参数是函数的参数。</span><span class="sxs-lookup"><span data-stu-id="d90e7-113">The first type parameter contained in the `ICorDebugTypeEnum` is the return type for the function, and the subsequent type parameters are the function's parameters.</span></span>  
  
- <span data-ttu-id="d90e7-114">ELEMENT_TYPE_ARRAY、ELEMENT_TYPE_SZARRAY、ELEMENT_TYPE_BYREF 或 ELEMENT_TYPE_PTR：将返回一个类型参数。</span><span class="sxs-lookup"><span data-stu-id="d90e7-114">ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF, or ELEMENT_TYPE_PTR: One type parameter will be returned.</span></span> <span data-ttu-id="d90e7-115">例如，如果类型是数组类型（如 `int32[]`），`EnumerateTypeParameters` 将返回一个 `ICorDebugTypeEnum`，其中包含表示 `int32`的对象。</span><span class="sxs-lookup"><span data-stu-id="d90e7-115">For example, if the type is an array type such as `int32[]`,`EnumerateTypeParameters` will return an `ICorDebugTypeEnum` that contains an object representing `int32`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d90e7-116">要求</span><span class="sxs-lookup"><span data-stu-id="d90e7-116">Requirements</span></span>  
 <span data-ttu-id="d90e7-117">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d90e7-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d90e7-118">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d90e7-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d90e7-119">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d90e7-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d90e7-120">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d90e7-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
