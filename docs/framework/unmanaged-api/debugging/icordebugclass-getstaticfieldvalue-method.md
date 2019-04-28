---
title: ICorDebugClass::GetStaticFieldValue 方法
ms.date: 03/30/2017
api_name:
- ICorDebugClass.GetStaticFieldValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass::GetStaticFieldValue
helpviewer_keywords:
- GetStaticFieldValue method, ICorDebugClass interface [.NET Framework debugging]
- ICorDebugClass::GetStaticFieldValue method [.NET Framework debugging]
ms.assetid: 56e718b4-fabd-418b-a5b3-3cc33c745683
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6b67f5ec233679461f61715d7562b47c2a195fb8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61750846"
---
# <a name="icordebugclassgetstaticfieldvalue-method"></a><span data-ttu-id="21734-102">ICorDebugClass::GetStaticFieldValue 方法</span><span class="sxs-lookup"><span data-stu-id="21734-102">ICorDebugClass::GetStaticFieldValue Method</span></span>
<span data-ttu-id="21734-103">获取指定的静态字段的值。</span><span class="sxs-lookup"><span data-stu-id="21734-103">Gets the value of the specified static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21734-104">语法</span><span class="sxs-lookup"><span data-stu-id="21734-104">Syntax</span></span>  
  
```  
HRESULT GetStaticFieldValue (  
    [in]  mdFieldDef         fieldDef,  
    [in]  ICorDebugFrame     *pFrame,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="21734-105">参数</span><span class="sxs-lookup"><span data-stu-id="21734-105">Parameters</span></span>  
 `fieldDef`  
 <span data-ttu-id="21734-106">[in]字段`Def`引用要检索的字段的令牌。</span><span class="sxs-lookup"><span data-stu-id="21734-106">[in] A field `Def` token that references the field to be retrieved.</span></span>  
  
 `pFrame`  
 <span data-ttu-id="21734-107">[in]指向一个 ICorDebugFrame 对象，表示要用来区分线程、 上下文或应用程序域静态对象的帧的指针。</span><span class="sxs-lookup"><span data-stu-id="21734-107">[in] A pointer to an ICorDebugFrame object that represents the frame to be used to disambiguate among thread, context, or application domain statics.</span></span>  
  
 <span data-ttu-id="21734-108">如果静态字段是相对于一个线程、 上下文或应用程序域，则框架将确定适当的值。</span><span class="sxs-lookup"><span data-stu-id="21734-108">If the static field is relative to a thread, a context, or an application domain, the frame will determine the proper value.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="21734-109">[out]指向一个 ICorDebugValue 对象，表示静态字段的值的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="21734-109">[out] A pointer to the address of an ICorDebugValue object that represents the value of the static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="21734-110">备注</span><span class="sxs-lookup"><span data-stu-id="21734-110">Remarks</span></span>  
 <span data-ttu-id="21734-111">对于参数化类型的静态字段的值是相对于特定的实例化。</span><span class="sxs-lookup"><span data-stu-id="21734-111">For parameterized types, the value of a static field is relative to the particular instantiation.</span></span> <span data-ttu-id="21734-112">因此，如果类构造函数参数的类型，则<xref:System.Type>，调用[icordebugtype:: Getstaticfieldvalue](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getstaticfieldvalue-method.md)而不是`ICorDebugClass::GetStaticFieldValue`。</span><span class="sxs-lookup"><span data-stu-id="21734-112">Therefore, if the class constructor takes parameters of type <xref:System.Type>, call [ICorDebugType::GetStaticFieldValue](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getstaticfieldvalue-method.md) instead of `ICorDebugClass::GetStaticFieldValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="21734-113">要求</span><span class="sxs-lookup"><span data-stu-id="21734-113">Requirements</span></span>  
 <span data-ttu-id="21734-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="21734-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="21734-115">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="21734-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="21734-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="21734-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="21734-117">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="21734-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
