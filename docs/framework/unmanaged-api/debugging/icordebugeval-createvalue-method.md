---
title: "ICorDebugEval::CreateValue 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugEval.CreateValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::CreateValue
helpviewer_keywords:
- ICorDebugEval::CreateValue method [.NET Framework debugging]
- CreateValue method [.NET Framework debugging]
ms.assetid: 9a1c0b47-6f10-4fcb-844a-4ab2d7990140
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 64d55a951795cc5efc1bfc624dbe07575be153aa
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugevalcreatevalue-method"></a><span data-ttu-id="e002a-102">ICorDebugEval::CreateValue 方法</span><span class="sxs-lookup"><span data-stu-id="e002a-102">ICorDebugEval::CreateValue Method</span></span>
<span data-ttu-id="e002a-103">其初始值为零或 null 创建指定类型的值。</span><span class="sxs-lookup"><span data-stu-id="e002a-103">Creates a value of the specified type, with an initial value of zero or null.</span></span>  
  
 <span data-ttu-id="e002a-104">此方法是.NET Framework 2.0 版中过时。</span><span class="sxs-lookup"><span data-stu-id="e002a-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="e002a-105">使用[icordebugeval2:: Createvaluefortype](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-createvaluefortype-method.md)相反。</span><span class="sxs-lookup"><span data-stu-id="e002a-105">Use [ICorDebugEval2::CreateValueForType](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-createvaluefortype-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e002a-106">语法</span><span class="sxs-lookup"><span data-stu-id="e002a-106">Syntax</span></span>  
  
```  
HRESULT CreateValue (  
    [in] CorElementType     elementType,  
    [in] ICorDebugClass     *pElementClass,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e002a-107">参数</span><span class="sxs-lookup"><span data-stu-id="e002a-107">Parameters</span></span>  
 `elementType`  
 <span data-ttu-id="e002a-108">[in]值为[CorElementType](../../../../docs/framework/unmanaged-api/metadata/corelementtype-enumeration.md)指定值的类型的枚举。</span><span class="sxs-lookup"><span data-stu-id="e002a-108">[in] A value of the [CorElementType](../../../../docs/framework/unmanaged-api/metadata/corelementtype-enumeration.md) enumeration that specifies the type of the value.</span></span>  
  
 `pElementClass`  
 <span data-ttu-id="e002a-109">[in]指向[ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md)指定的值的类，如果类型不是基元类型的对象。</span><span class="sxs-lookup"><span data-stu-id="e002a-109">[in] Pointer to an [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md) object that specifies the class of the value, if the type is not a primitive type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="e002a-110">[out]一个表示值的"ICorDebugValue"对象的地址指针。</span><span class="sxs-lookup"><span data-stu-id="e002a-110">[out] Pointer to the address of an "ICorDebugValue" object that represents the value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e002a-111">备注</span><span class="sxs-lookup"><span data-stu-id="e002a-111">Remarks</span></span>  
 <span data-ttu-id="e002a-112">`CreateValue`创建`ICorDebugValue`使用函数求值的唯一目的是给定类型的对象。</span><span class="sxs-lookup"><span data-stu-id="e002a-112">`CreateValue` creates an `ICorDebugValue` object of the given type for the sole purpose of using it in a function evaluation.</span></span> <span data-ttu-id="e002a-113">此值对象可以用于将用户常量作为参数传递。</span><span class="sxs-lookup"><span data-stu-id="e002a-113">This value object can be used to pass user constants as parameters.</span></span>  
  
 <span data-ttu-id="e002a-114">如果值的类型为基元类型，其初始值为零或 null。</span><span class="sxs-lookup"><span data-stu-id="e002a-114">If the type of the value is a primitive type, its initial value is zero or null.</span></span> <span data-ttu-id="e002a-115">使用[icordebuggenericvalue:: Setvalue](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-setvalue-method.md)设置基元类型的值。</span><span class="sxs-lookup"><span data-stu-id="e002a-115">Use [ICorDebugGenericValue::SetValue](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-setvalue-method.md) to set the value of a primitive type.</span></span>  
  
 <span data-ttu-id="e002a-116">如果值`elementType`是 ELEMENT_TYPE_CLASS，获取"ICorDebugReferenceValue"(在返回`ppValue`) 表示空对象引用。</span><span class="sxs-lookup"><span data-stu-id="e002a-116">If the value of `elementType` is ELEMENT_TYPE_CLASS, you get an "ICorDebugReferenceValue" (returned in `ppValue`) representing the null object reference.</span></span> <span data-ttu-id="e002a-117">此对象可用于向函数求值的对象引用参数传递 null。</span><span class="sxs-lookup"><span data-stu-id="e002a-117">You can use this object to pass null to a function evaluation that has object reference parameters.</span></span> <span data-ttu-id="e002a-118">无法设置`ICorDebugValue`任何内容; 它始终仍是 null。</span><span class="sxs-lookup"><span data-stu-id="e002a-118">You cannot set the `ICorDebugValue` to anything; it always remains null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e002a-119">惠?</span><span class="sxs-lookup"><span data-stu-id="e002a-119">Requirements</span></span>  
 <span data-ttu-id="e002a-120">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e002a-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e002a-121">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e002a-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e002a-122">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e002a-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e002a-123">**.NET framework 版本：** 1.1、 1.0</span><span class="sxs-lookup"><span data-stu-id="e002a-123">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e002a-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="e002a-124">See Also</span></span>  
    
 [<span data-ttu-id="e002a-125">CreateValueForType 方法</span><span class="sxs-lookup"><span data-stu-id="e002a-125">CreateValueForType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-createvaluefortype-method.md)  
 <span data-ttu-id="e002a-126">ICorDebugValue</span><span class="sxs-lookup"><span data-stu-id="e002a-126">ICorDebugValue</span></span>
