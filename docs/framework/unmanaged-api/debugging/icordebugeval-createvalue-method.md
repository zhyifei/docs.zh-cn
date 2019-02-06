---
title: ICorDebugEval::CreateValue 方法
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ad40087ca61f1b07c0e0e36e785d89b84132962a
ms.sourcegitcommit: 01ea420eaa4bf76d5fc47673294c8881379b3369
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2019
ms.locfileid: "55759543"
---
# <a name="icordebugevalcreatevalue-method"></a><span data-ttu-id="544ac-102">ICorDebugEval::CreateValue 方法</span><span class="sxs-lookup"><span data-stu-id="544ac-102">ICorDebugEval::CreateValue Method</span></span>
<span data-ttu-id="544ac-103">创建指定类型的值与初始值为零或 null。</span><span class="sxs-lookup"><span data-stu-id="544ac-103">Creates a value of the specified type, with an initial value of zero or null.</span></span>  
  
 <span data-ttu-id="544ac-104">此方法是在.NET Framework 2.0 版中已过时。</span><span class="sxs-lookup"><span data-stu-id="544ac-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="544ac-105">使用[ICorDebugEval2::CreateValueForType](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-createvaluefortype-method.md)相反。</span><span class="sxs-lookup"><span data-stu-id="544ac-105">Use [ICorDebugEval2::CreateValueForType](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-createvaluefortype-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="544ac-106">语法</span><span class="sxs-lookup"><span data-stu-id="544ac-106">Syntax</span></span>  
  
```  
HRESULT CreateValue (  
    [in] CorElementType     elementType,  
    [in] ICorDebugClass     *pElementClass,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="544ac-107">参数</span><span class="sxs-lookup"><span data-stu-id="544ac-107">Parameters</span></span>  
 `elementType`  
 <span data-ttu-id="544ac-108">[in]值为[CorElementType](../../../../docs/framework/unmanaged-api/metadata/corelementtype-enumeration.md)枚举，用于指定值的类型。</span><span class="sxs-lookup"><span data-stu-id="544ac-108">[in] A value of the [CorElementType](../../../../docs/framework/unmanaged-api/metadata/corelementtype-enumeration.md) enumeration that specifies the type of the value.</span></span>  
  
 `pElementClass`  
 <span data-ttu-id="544ac-109">[in]指向[ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md)对象，如果类型不是基元类型指定的值的类。</span><span class="sxs-lookup"><span data-stu-id="544ac-109">[in] Pointer to an [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md) object that specifies the class of the value, if the type is not a primitive type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="544ac-110">[out]表示的值"ICorDebugValue"对象的地址指针。</span><span class="sxs-lookup"><span data-stu-id="544ac-110">[out] Pointer to the address of an "ICorDebugValue" object that represents the value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="544ac-111">备注</span><span class="sxs-lookup"><span data-stu-id="544ac-111">Remarks</span></span>  
 <span data-ttu-id="544ac-112">`CreateValue` 创建`ICorDebugValue`使用函数求值的唯一目的的给定类型的对象。</span><span class="sxs-lookup"><span data-stu-id="544ac-112">`CreateValue` creates an `ICorDebugValue` object of the given type for the sole purpose of using it in a function evaluation.</span></span> <span data-ttu-id="544ac-113">此值对象可以用于将用户常量作为参数传递。</span><span class="sxs-lookup"><span data-stu-id="544ac-113">This value object can be used to pass user constants as parameters.</span></span>  
  
 <span data-ttu-id="544ac-114">如果值的类型是基元类型，其初始值为零或 null。</span><span class="sxs-lookup"><span data-stu-id="544ac-114">If the type of the value is a primitive type, its initial value is zero or null.</span></span> <span data-ttu-id="544ac-115">使用[icordebuggenericvalue:: Setvalue](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-setvalue-method.md)将基元类型的值。</span><span class="sxs-lookup"><span data-stu-id="544ac-115">Use [ICorDebugGenericValue::SetValue](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-setvalue-method.md) to set the value of a primitive type.</span></span>  
  
 <span data-ttu-id="544ac-116">如果的值`elementType`是 ELEMENT_TYPE_CLASS，获取"ICorDebugReferenceValue"(在中返回`ppValue`) 表示空对象引用。</span><span class="sxs-lookup"><span data-stu-id="544ac-116">If the value of `elementType` is ELEMENT_TYPE_CLASS, you get an "ICorDebugReferenceValue" (returned in `ppValue`) representing the null object reference.</span></span> <span data-ttu-id="544ac-117">此对象可用于将 null 传递给函数求值的对象引用参数。</span><span class="sxs-lookup"><span data-stu-id="544ac-117">You can use this object to pass null to a function evaluation that has object reference parameters.</span></span> <span data-ttu-id="544ac-118">不能设置`ICorDebugValue`到任何内容; 它始终保留为 null。</span><span class="sxs-lookup"><span data-stu-id="544ac-118">You cannot set the `ICorDebugValue` to anything; it always remains null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="544ac-119">要求</span><span class="sxs-lookup"><span data-stu-id="544ac-119">Requirements</span></span>  
 <span data-ttu-id="544ac-120">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="544ac-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="544ac-121">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="544ac-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="544ac-122">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="544ac-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="544ac-123">**.NET framework 版本：** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="544ac-123">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="544ac-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="544ac-124">See also</span></span>

- [<span data-ttu-id="544ac-125">CreateValueForType 方法</span><span class="sxs-lookup"><span data-stu-id="544ac-125">CreateValueForType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-createvaluefortype-method.md)
- [<span data-ttu-id="544ac-126">ICorDebugEval 接口</span><span class="sxs-lookup"><span data-stu-id="544ac-126">ICorDebugEval Interface</span></span>](icordebugeval-interface.md)
