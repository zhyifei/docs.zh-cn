---
title: ICorDebugType::GetStaticFieldValue 方法
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetStaticFieldValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetStaticFieldValue
helpviewer_keywords:
- GetStaticFieldValue method, ICorDebugType interface [.NET Framework debugging]
- ICorDebugType::GetStaticFieldValue method [.NET Framework debugging]
ms.assetid: 62eb5d55-53ee-4fb3-8d47-7b6c96808f9e
topic_type:
- apiref
ms.openlocfilehash: 95183701987d3ddec3835a17c5d256c25c2c4c64
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132070"
---
# <a name="icordebugtypegetstaticfieldvalue-method"></a><span data-ttu-id="38608-102">ICorDebugType::GetStaticFieldValue 方法</span><span class="sxs-lookup"><span data-stu-id="38608-102">ICorDebugType::GetStaticFieldValue Method</span></span>
<span data-ttu-id="38608-103">获取一个指向 ICorDebugValue 对象的接口指针，该对象包含指定的堆栈帧中指定字段标记所引用的静态字段的值。</span><span class="sxs-lookup"><span data-stu-id="38608-103">Gets an interface pointer to an ICorDebugValue object that contains the value of the static field referenced by the specified field token in the specified stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38608-104">语法</span><span class="sxs-lookup"><span data-stu-id="38608-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStaticFieldValue (  
    [in]  mdFieldDef        fieldDef,  
    [in]  ICorDebugFrame    *pFrame,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="38608-105">参数</span><span class="sxs-lookup"><span data-stu-id="38608-105">Parameters</span></span>  
 `fieldDef`  
 <span data-ttu-id="38608-106">中指定静态字段的 `mdFieldDef` 标记。</span><span class="sxs-lookup"><span data-stu-id="38608-106">[in] An `mdFieldDef` token that specifies the static field.</span></span>  
  
 `pFrame`  
 <span data-ttu-id="38608-107">中指向表示堆栈帧的 ICorDebugFrame 的指针。</span><span class="sxs-lookup"><span data-stu-id="38608-107">[in] A pointer to an ICorDebugFrame that represents the stack frame.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="38608-108">弄一个指针，指向包含静态字段值的 `ICorDebugValue` 的地址。</span><span class="sxs-lookup"><span data-stu-id="38608-108">[out] A pointer to the address of an `ICorDebugValue` that contains the value of the static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="38608-109">备注</span><span class="sxs-lookup"><span data-stu-id="38608-109">Remarks</span></span>  
 <span data-ttu-id="38608-110">仅当类型为 ELEMENT_TYPE_CLASS 或 ELEMENT_TYPE_VALUETYPE 时，才可以使用 `GetStaticFieldValue` 方法，如[ICorDebugType：： GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md)方法所示。</span><span class="sxs-lookup"><span data-stu-id="38608-110">The `GetStaticFieldValue` method may be used only if the type is ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE, as indicated by the [ICorDebugType::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) method.</span></span>  
  
 <span data-ttu-id="38608-111">对于非泛型类型，`GetStaticFieldValue` 执行的操作与对[ICorDebugType：： GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md)返回的 ICorDebugClass 对象调用[ICorDebugClass：： GetStaticFieldValue](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getstaticfieldvalue-method.md)完全相同。</span><span class="sxs-lookup"><span data-stu-id="38608-111">For non-generic types, the operation performed by `GetStaticFieldValue` is identical to calling [ICorDebugClass::GetStaticFieldValue](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getstaticfieldvalue-method.md) on the ICorDebugClass object that is returned by [ICorDebugType::GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md).</span></span>  
  
 <span data-ttu-id="38608-112">对于泛型类型，静态字段值将与特定实例化相关。</span><span class="sxs-lookup"><span data-stu-id="38608-112">For generic types, a static field value will be relative to a particular instantiation.</span></span> <span data-ttu-id="38608-113">此外，如果静态字段可能是相对于线程、上下文或应用程序域的，则堆栈帧将有助于调试器确定正确的值。</span><span class="sxs-lookup"><span data-stu-id="38608-113">Also, if the static field could possibly be relative to a thread, a context, or an application domain, then the stack frame will help the debugger determine the proper value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="38608-114">备注</span><span class="sxs-lookup"><span data-stu-id="38608-114">Remarks</span></span>  
 <span data-ttu-id="38608-115">仅当对 `ICorDebugType::GetType` 的调用返回 ELEMENT_TYPE_CLASS 或 ELEMENT_TYPE_VALUETYPE 的值时，才能使用 `GetStaticFieldValue`。</span><span class="sxs-lookup"><span data-stu-id="38608-115">`GetStaticFieldValue` can be used only when a call to `ICorDebugType::GetType` returns a value of ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="38608-116">要求</span><span class="sxs-lookup"><span data-stu-id="38608-116">Requirements</span></span>  
 <span data-ttu-id="38608-117">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="38608-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38608-118">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="38608-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="38608-119">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="38608-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="38608-120">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38608-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
