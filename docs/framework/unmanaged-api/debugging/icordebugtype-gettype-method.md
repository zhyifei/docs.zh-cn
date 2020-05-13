---
title: ICorDebugType::GetType 方法
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetType
helpviewer_keywords:
- ICorDebugType::GetType method [.NET Framework debugging]
- GetType method, ICorDebugType interface [.NET Framework debugging]
ms.assetid: d6e64534-4d47-4ad0-a340-7590e07e2b4a
topic_type:
- apiref
ms.openlocfilehash: ac42c6254182ea775377a448a54d527b234c97dc
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379925"
---
# <a name="icordebugtypegettype-method"></a><span data-ttu-id="b8769-102">ICorDebugType::GetType 方法</span><span class="sxs-lookup"><span data-stu-id="b8769-102">ICorDebugType::GetType Method</span></span>
<span data-ttu-id="b8769-103">获取一个 CorElementType 值，该值描述此 ICorDebugType 表示的公共语言运行时（CLR）的本机类型 <xref:System.Type> 。</span><span class="sxs-lookup"><span data-stu-id="b8769-103">Gets a CorElementType value that describes the native type of the common language runtime (CLR) <xref:System.Type> represented by this ICorDebugType.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8769-104">语法</span><span class="sxs-lookup"><span data-stu-id="b8769-104">Syntax</span></span>  
  
```cpp  
HRESULT GetType (  
    [out] CorElementType   *ty  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b8769-105">参数</span><span class="sxs-lookup"><span data-stu-id="b8769-105">Parameters</span></span>  
 `ty`  
 <span data-ttu-id="b8769-106">弄一个指针，指向 `CorElementType` 枚举的值，该值指示 <xref:System.Type> 此表示的 CLR `ICorDebugType` 。</span><span class="sxs-lookup"><span data-stu-id="b8769-106">[out] A pointer to a value of the `CorElementType` enumeration that indicates the CLR <xref:System.Type> that this `ICorDebugType` represents.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b8769-107">备注</span><span class="sxs-lookup"><span data-stu-id="b8769-107">Remarks</span></span>  
 <span data-ttu-id="b8769-108">如果的值 `ty` 为 ELEMENT_TYPE_CLASS 或 ELEMENT_TYPE_VALUETYPE，则可以调用[ICorDebugType：： GetClass](icordebugtype-getclass-method.md)方法来获取泛型类型的非实例化类型; 否则，不会调用 `ICorDebugType::GetClass` 。</span><span class="sxs-lookup"><span data-stu-id="b8769-108">If the value of `ty` is either ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE, the [ICorDebugType::GetClass](icordebugtype-getclass-method.md) method may be called to get the uninstantiated type for a generic type; otherwise, do not call `ICorDebugType::GetClass`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b8769-109">要求</span><span class="sxs-lookup"><span data-stu-id="b8769-109">Requirements</span></span>  
 <span data-ttu-id="b8769-110">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b8769-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b8769-111">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b8769-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b8769-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b8769-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b8769-113">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b8769-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
