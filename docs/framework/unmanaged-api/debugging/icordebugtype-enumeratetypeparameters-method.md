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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 12b002aaad65fd5f2a1207700c8de2ca8dd60eec
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugtypeenumeratetypeparameters-method"></a><span data-ttu-id="c60a2-102">ICorDebugType::EnumerateTypeParameters 方法</span><span class="sxs-lookup"><span data-stu-id="c60a2-102">ICorDebugType::EnumerateTypeParameters Method</span></span>
<span data-ttu-id="c60a2-103">获取的接口指针指向包含 ICorDebugTypeEnum<xref:System.Type>参数的此 ICorDebugType 所引用的类。</span><span class="sxs-lookup"><span data-stu-id="c60a2-103">Gets an interface pointer to an ICorDebugTypeEnum that contains the <xref:System.Type> parameters of the class referenced by this ICorDebugType.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c60a2-104">语法</span><span class="sxs-lookup"><span data-stu-id="c60a2-104">Syntax</span></span>  
  
```  
HRESULT EnumerateTypeParameters (  
    [out] ICorDebugTypeEnum   **ppTyParEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c60a2-105">参数</span><span class="sxs-lookup"><span data-stu-id="c60a2-105">Parameters</span></span>  
 `ppTyParEnum`  
 <span data-ttu-id="c60a2-106">[out]指向的地址的指针`ICorDebugTypeEnum`包含类型的参数。</span><span class="sxs-lookup"><span data-stu-id="c60a2-106">[out] A pointer to the address of an `ICorDebugTypeEnum` that contains the parameters of the type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c60a2-107">备注</span><span class="sxs-lookup"><span data-stu-id="c60a2-107">Remarks</span></span>  
 <span data-ttu-id="c60a2-108">你可以使用`EnumerateTypeParameters`如果返回 CorElementType 值[icordebugtype:: Gettype](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) ELEMENT_TYPE_CLASS、 ELEMENT_TYPE_VALUETYPE、 ELEMENT_TYPE_ARRAY、 ELEMENT_TYPE_SZARRAY、 ELEMENT_TYPE_BYREF、 ELEMENT_TYPE_PTR 或 ELEMENT_TYPE_FNPTR。</span><span class="sxs-lookup"><span data-stu-id="c60a2-108">You can use `EnumerateTypeParameters` if the CorElementType value returned by [ICorDebugType::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) is ELEMENT_TYPE_CLASS, ELEMENT_TYPE_VALUETYPE, ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF, ELEMENT_TYPE_PTR, or ELEMENT_TYPE_FNPTR.</span></span> <span data-ttu-id="c60a2-109">参数和它们的顺序的数量取决于的类型：</span><span class="sxs-lookup"><span data-stu-id="c60a2-109">The number of parameters and their order depends on the type:</span></span>  
  
-   <span data-ttu-id="c60a2-110">ELEMENT_TYPE_CLASS 或 ELEMENT_TYPE_VALUETYPE： 中包含的类型参数的数目`ICorDebugTypeEnum`，此方法返回时，将取决于相应的类的形参类型参数的数目。</span><span class="sxs-lookup"><span data-stu-id="c60a2-110">ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE: The number of type parameters contained in the `ICorDebugTypeEnum` that this method returns, will depend on the number of formal type parameters for the corresponding class.</span></span> <span data-ttu-id="c60a2-111">例如，如果类型为`class Dict<String,int32>`，然后`EnumerateTypeParameters`将返回`ICorDebugTypeEnum`，其中包含表示的对象`String`和`int32`序列中。</span><span class="sxs-lookup"><span data-stu-id="c60a2-111">For example, if the type is `class Dict<String,int32>`, then `EnumerateTypeParameters` will return an `ICorDebugTypeEnum` that contains objects representing `String` and `int32` in sequence.</span></span>  
  
-   <span data-ttu-id="c60a2-112">ELEMENT_TYPE_FNPTR: 中包含的类型参数数目`ICorDebugTypeEnum`将是一个大于函数接受参数的数目。</span><span class="sxs-lookup"><span data-stu-id="c60a2-112">ELEMENT_TYPE_FNPTR: The number of type parameters contained in the `ICorDebugTypeEnum` will be one greater than the number of arguments accepted by the function.</span></span> <span data-ttu-id="c60a2-113">中包含的第一个类型参数`ICorDebugTypeEnum`是该函数的返回类型和后面的类型参数是函数的参数。</span><span class="sxs-lookup"><span data-stu-id="c60a2-113">The first type parameter contained in the `ICorDebugTypeEnum` is the return type for the function, and the subsequent type parameters are the function's parameters.</span></span>  
  
-   <span data-ttu-id="c60a2-114">ELEMENT_TYPE_ARRAY、 ELEMENT_TYPE_SZARRAY、 ELEMENT_TYPE_BYREF 或 ELEMENT_TYPE_PTR： 将返回一个类型参数。</span><span class="sxs-lookup"><span data-stu-id="c60a2-114">ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF, or ELEMENT_TYPE_PTR: One type parameter will be returned.</span></span> <span data-ttu-id="c60a2-115">例如，如果类型是数组类型，如`int32[]`，`EnumerateTypeParameters`将返回`ICorDebugTypeEnum`包含对象，表示`int32`。</span><span class="sxs-lookup"><span data-stu-id="c60a2-115">For example, if the type is an array type such as `int32[]`,`EnumerateTypeParameters` will return an `ICorDebugTypeEnum` that contains an object representing `int32`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c60a2-116">要求</span><span class="sxs-lookup"><span data-stu-id="c60a2-116">Requirements</span></span>  
 <span data-ttu-id="c60a2-117">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c60a2-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c60a2-118">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c60a2-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c60a2-119">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c60a2-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c60a2-120">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c60a2-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
