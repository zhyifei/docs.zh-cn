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
ms.openlocfilehash: 37bf5abf66b613d8432af84c7d73aff60e9127cb
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791272"
---
# <a name="icordebugtypegetstaticfieldvalue-method"></a><span data-ttu-id="e7103-102">ICorDebugType::GetStaticFieldValue 方法</span><span class="sxs-lookup"><span data-stu-id="e7103-102">ICorDebugType::GetStaticFieldValue Method</span></span>
<span data-ttu-id="e7103-103">获取一个指向 ICorDebugValue 对象的接口指针，该对象包含指定的堆栈帧中指定字段标记所引用的静态字段的值。</span><span class="sxs-lookup"><span data-stu-id="e7103-103">Gets an interface pointer to an ICorDebugValue object that contains the value of the static field referenced by the specified field token in the specified stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7103-104">语法</span><span class="sxs-lookup"><span data-stu-id="e7103-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStaticFieldValue (  
    [in]  mdFieldDef        fieldDef,  
    [in]  ICorDebugFrame    *pFrame,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e7103-105">参数</span><span class="sxs-lookup"><span data-stu-id="e7103-105">Parameters</span></span>  
 `fieldDef`  
 <span data-ttu-id="e7103-106">中指定静态字段的 `mdFieldDef` 标记。</span><span class="sxs-lookup"><span data-stu-id="e7103-106">[in] An `mdFieldDef` token that specifies the static field.</span></span>  
  
 `pFrame`  
 <span data-ttu-id="e7103-107">中指向表示堆栈帧的 ICorDebugFrame 的指针。</span><span class="sxs-lookup"><span data-stu-id="e7103-107">[in] A pointer to an ICorDebugFrame that represents the stack frame.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="e7103-108">弄一个指针，指向包含静态字段值的 `ICorDebugValue` 的地址。</span><span class="sxs-lookup"><span data-stu-id="e7103-108">[out] A pointer to the address of an `ICorDebugValue` that contains the value of the static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e7103-109">备注</span><span class="sxs-lookup"><span data-stu-id="e7103-109">Remarks</span></span>  
 <span data-ttu-id="e7103-110">仅当类型 ELEMENT_TYPE_CLASS 或 ELEMENT_TYPE_VALUETYPE 时，才能使用 `GetStaticFieldValue` 方法，如[ICorDebugType：： GetType](icordebugtype-gettype-method.md)方法所示。</span><span class="sxs-lookup"><span data-stu-id="e7103-110">The `GetStaticFieldValue` method may be used only if the type is ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE, as indicated by the [ICorDebugType::GetType](icordebugtype-gettype-method.md) method.</span></span>  
  
 <span data-ttu-id="e7103-111">对于非泛型类型，`GetStaticFieldValue` 执行的操作与对[ICorDebugType：： GetClass](icordebugtype-getclass-method.md)返回的 ICorDebugClass 对象调用[ICorDebugClass：： GetStaticFieldValue](icordebugclass-getstaticfieldvalue-method.md)完全相同。</span><span class="sxs-lookup"><span data-stu-id="e7103-111">For non-generic types, the operation performed by `GetStaticFieldValue` is identical to calling [ICorDebugClass::GetStaticFieldValue](icordebugclass-getstaticfieldvalue-method.md) on the ICorDebugClass object that is returned by [ICorDebugType::GetClass](icordebugtype-getclass-method.md).</span></span>  
  
 <span data-ttu-id="e7103-112">对于泛型类型，静态字段值将与特定实例化相关。</span><span class="sxs-lookup"><span data-stu-id="e7103-112">For generic types, a static field value will be relative to a particular instantiation.</span></span> <span data-ttu-id="e7103-113">此外，如果静态字段可能是相对于线程、上下文或应用程序域的，则堆栈帧将有助于调试器确定正确的值。</span><span class="sxs-lookup"><span data-stu-id="e7103-113">Also, if the static field could possibly be relative to a thread, a context, or an application domain, then the stack frame will help the debugger determine the proper value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e7103-114">备注</span><span class="sxs-lookup"><span data-stu-id="e7103-114">Remarks</span></span>  
 <span data-ttu-id="e7103-115">仅当对 `ICorDebugType::GetType` 的调用返回 ELEMENT_TYPE_CLASS 或 ELEMENT_TYPE_VALUETYPE 值时，才能使用 `GetStaticFieldValue`。</span><span class="sxs-lookup"><span data-stu-id="e7103-115">`GetStaticFieldValue` can be used only when a call to `ICorDebugType::GetType` returns a value of ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7103-116">需求</span><span class="sxs-lookup"><span data-stu-id="e7103-116">Requirements</span></span>  
 <span data-ttu-id="e7103-117">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e7103-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e7103-118">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e7103-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e7103-119">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e7103-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e7103-120">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e7103-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
