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
ms.openlocfilehash: 4d3c3c0c5634653d14577de9a1334048d75216b9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33405621"
---
# <a name="icordebugclassgetstaticfieldvalue-method"></a><span data-ttu-id="0fcc1-102">ICorDebugClass::GetStaticFieldValue 方法</span><span class="sxs-lookup"><span data-stu-id="0fcc1-102">ICorDebugClass::GetStaticFieldValue Method</span></span>
<span data-ttu-id="0fcc1-103">获取指定的静态字段的值。</span><span class="sxs-lookup"><span data-stu-id="0fcc1-103">Gets the value of the specified static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0fcc1-104">语法</span><span class="sxs-lookup"><span data-stu-id="0fcc1-104">Syntax</span></span>  
  
```  
HRESULT GetStaticFieldValue (  
    [in]  mdFieldDef         fieldDef,  
    [in]  ICorDebugFrame     *pFrame,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0fcc1-105">参数</span><span class="sxs-lookup"><span data-stu-id="0fcc1-105">Parameters</span></span>  
 `fieldDef`  
 <span data-ttu-id="0fcc1-106">[in]字段`Def`引用字段要检索的令牌。</span><span class="sxs-lookup"><span data-stu-id="0fcc1-106">[in] A field `Def` token that references the field to be retrieved.</span></span>  
  
 `pFrame`  
 <span data-ttu-id="0fcc1-107">[in]指向一个 ICorDebugFrame 对象，表示要用于消除线程、 上下文或应用程序域的静态对象之间的歧义的帧的指针。</span><span class="sxs-lookup"><span data-stu-id="0fcc1-107">[in] A pointer to an ICorDebugFrame object that represents the frame to be used to disambiguate among thread, context, or application domain statics.</span></span>  
  
 <span data-ttu-id="0fcc1-108">如果静态字段为相对于某个线程、 非上下文或应用程序域，则帧将确定适当的值。</span><span class="sxs-lookup"><span data-stu-id="0fcc1-108">If the static field is relative to a thread, a context, or an application domain, the frame will determine the proper value.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="0fcc1-109">[out]指向一个 ICorDebugValue 对象，表示的静态字段的值的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="0fcc1-109">[out] A pointer to the address of an ICorDebugValue object that represents the value of the static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0fcc1-110">备注</span><span class="sxs-lookup"><span data-stu-id="0fcc1-110">Remarks</span></span>  
 <span data-ttu-id="0fcc1-111">对于参数化类型的静态字段的值是相对于特定的实例化。</span><span class="sxs-lookup"><span data-stu-id="0fcc1-111">For parameterized types, the value of a static field is relative to the particular instantiation.</span></span> <span data-ttu-id="0fcc1-112">因此，如果类构造函数采用的类型参数的<xref:System.Type>，调用[icordebugtype:: Getstaticfieldvalue](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getstaticfieldvalue-method.md)而不是`ICorDebugClass::GetStaticFieldValue`。</span><span class="sxs-lookup"><span data-stu-id="0fcc1-112">Therefore, if the class constructor takes parameters of type <xref:System.Type>, call [ICorDebugType::GetStaticFieldValue](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getstaticfieldvalue-method.md) instead of `ICorDebugClass::GetStaticFieldValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0fcc1-113">要求</span><span class="sxs-lookup"><span data-stu-id="0fcc1-113">Requirements</span></span>  
 <span data-ttu-id="0fcc1-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0fcc1-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0fcc1-115">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0fcc1-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0fcc1-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0fcc1-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0fcc1-117">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0fcc1-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
