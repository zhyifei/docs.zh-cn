---
title: "ICorDebugType::GetStaticFieldValue 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugType.GetStaticFieldValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugType::GetStaticFieldValue
helpviewer_keywords:
- GetStaticFieldValue method, ICorDebugType interface [.NET Framework debugging]
- ICorDebugType::GetStaticFieldValue method [.NET Framework debugging]
ms.assetid: 62eb5d55-53ee-4fb3-8d47-7b6c96808f9e
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 34a37ef9a28dd0e6325db9bee61146f14d4638a6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugtypegetstaticfieldvalue-method"></a><span data-ttu-id="25f81-102">ICorDebugType::GetStaticFieldValue 方法</span><span class="sxs-lookup"><span data-stu-id="25f81-102">ICorDebugType::GetStaticFieldValue Method</span></span>
<span data-ttu-id="25f81-103">令牌中指定的堆栈帧包含引用的指定字段的静态字段的值的 ICorDebugValue 对象获取的接口指针。</span><span class="sxs-lookup"><span data-stu-id="25f81-103">Gets an interface pointer to an ICorDebugValue object that contains the value of the static field referenced by the specified field token in the specified stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25f81-104">语法</span><span class="sxs-lookup"><span data-stu-id="25f81-104">Syntax</span></span>  
  
```  
HRESULT GetStaticFieldValue (  
    [in]  mdFieldDef        fieldDef,  
    [in]  ICorDebugFrame    *pFrame,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="25f81-105">参数</span><span class="sxs-lookup"><span data-stu-id="25f81-105">Parameters</span></span>  
 `fieldDef`  
 <span data-ttu-id="25f81-106">[in]`mdFieldDef`指定的静态字段的令牌。</span><span class="sxs-lookup"><span data-stu-id="25f81-106">[in] An `mdFieldDef` token that specifies the static field.</span></span>  
  
 `pFrame`  
 <span data-ttu-id="25f81-107">[in]表示堆栈帧 ICorDebugFrame 指向的指针。</span><span class="sxs-lookup"><span data-stu-id="25f81-107">[in] A pointer to an ICorDebugFrame that represents the stack frame.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="25f81-108">[out]指向的地址的指针`ICorDebugValue`包含静态字段的值。</span><span class="sxs-lookup"><span data-stu-id="25f81-108">[out] A pointer to the address of an `ICorDebugValue` that contains the value of the static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="25f81-109">备注</span><span class="sxs-lookup"><span data-stu-id="25f81-109">Remarks</span></span>  
 <span data-ttu-id="25f81-110">`GetStaticFieldValue`方法可能会使用仅当类型为 ELEMENT_TYPE_CLASS 或 ELEMENT_TYPE_VALUETYPE，由[icordebugtype:: Gettype](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="25f81-110">The `GetStaticFieldValue` method may be used only if the type is ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE, as indicated by the [ICorDebugType::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) method.</span></span>  
  
 <span data-ttu-id="25f81-111">对于非泛型类型，该操作由`GetStaticFieldValue`等同于调用[icordebugclass:: Getstaticfieldvalue](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getstaticfieldvalue-method.md)返回 ICorDebugClass 对象上[icordebugtype:: Getclass](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md).</span><span class="sxs-lookup"><span data-stu-id="25f81-111">For non-generic types, the operation performed by `GetStaticFieldValue` is identical to calling [ICorDebugClass::GetStaticFieldValue](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getstaticfieldvalue-method.md) on the ICorDebugClass object that is returned by [ICorDebugType::GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md).</span></span>  
  
 <span data-ttu-id="25f81-112">对于泛型类型，静态字段的值将是相对于特定实例化。</span><span class="sxs-lookup"><span data-stu-id="25f81-112">For generic types, a static field value will be relative to a particular instantiation.</span></span> <span data-ttu-id="25f81-113">此外，如果可能，静态字段可能是相对于某个线程、 非上下文或应用程序域，堆栈帧将帮助调试器确定适当的值。</span><span class="sxs-lookup"><span data-stu-id="25f81-113">Also, if the static field could possibly be relative to a thread, a context, or an application domain, then the stack frame will help the debugger determine the proper value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="25f81-114">备注</span><span class="sxs-lookup"><span data-stu-id="25f81-114">Remarks</span></span>  
 <span data-ttu-id="25f81-115">`GetStaticFieldValue`仅在调用时可以使用`ICorDebugType::GetType`返回 ELEMENT_TYPE_CLASS 或 ELEMENT_TYPE_VALUETYPE 的值。</span><span class="sxs-lookup"><span data-stu-id="25f81-115">`GetStaticFieldValue` can be used only when a call to `ICorDebugType::GetType` returns a value of ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="25f81-116">要求</span><span class="sxs-lookup"><span data-stu-id="25f81-116">Requirements</span></span>  
 <span data-ttu-id="25f81-117">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="25f81-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="25f81-118">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="25f81-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="25f81-119">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="25f81-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="25f81-120">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="25f81-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
