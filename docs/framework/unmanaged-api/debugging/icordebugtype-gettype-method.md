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
ms.openlocfilehash: 25ffbf73fbefbb3c584450283c3080dfc11ee598
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791245"
---
# <a name="icordebugtypegettype-method"></a><span data-ttu-id="56bb4-102">ICorDebugType::GetType 方法</span><span class="sxs-lookup"><span data-stu-id="56bb4-102">ICorDebugType::GetType Method</span></span>
<span data-ttu-id="56bb4-103">获取一个 CorElementType 值，该值描述此 ICorDebugType 表示的公共语言运行时（CLR） <xref:System.Type> 的本机类型。</span><span class="sxs-lookup"><span data-stu-id="56bb4-103">Gets a CorElementType value that describes the native type of the common language runtime (CLR) <xref:System.Type> represented by this ICorDebugType.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56bb4-104">语法</span><span class="sxs-lookup"><span data-stu-id="56bb4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetType (  
    [out] CorElementType   *ty  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="56bb4-105">参数</span><span class="sxs-lookup"><span data-stu-id="56bb4-105">Parameters</span></span>  
 `ty`  
 <span data-ttu-id="56bb4-106">弄一个指针，指向 `CorElementType` 枚举的值，该值指示此 `ICorDebugType` 表示的 CLR <xref:System.Type>。</span><span class="sxs-lookup"><span data-stu-id="56bb4-106">[out] A pointer to a value of the `CorElementType` enumeration that indicates the CLR <xref:System.Type> that this `ICorDebugType` represents.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="56bb4-107">备注</span><span class="sxs-lookup"><span data-stu-id="56bb4-107">Remarks</span></span>  
 <span data-ttu-id="56bb4-108">如果 `ty` 的值 ELEMENT_TYPE_CLASS 或 ELEMENT_TYPE_VALUETYPE，则可以调用[ICorDebugType：： GetClass](icordebugtype-getclass-method.md)方法来获取泛型类型的实例化类型;否则，请不要调用 `ICorDebugType::GetClass`。</span><span class="sxs-lookup"><span data-stu-id="56bb4-108">If the value of `ty` is either ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE, the [ICorDebugType::GetClass](icordebugtype-getclass-method.md) method may be called to get the uninstantiated type for a generic type; otherwise, do not call `ICorDebugType::GetClass`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="56bb4-109">需求</span><span class="sxs-lookup"><span data-stu-id="56bb4-109">Requirements</span></span>  
 <span data-ttu-id="56bb4-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="56bb4-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="56bb4-111">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="56bb4-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="56bb4-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="56bb4-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="56bb4-113">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="56bb4-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
