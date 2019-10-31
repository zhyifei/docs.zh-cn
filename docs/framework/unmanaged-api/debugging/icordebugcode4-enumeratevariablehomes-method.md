---
title: ICorDebugCode4：： EnumerateVariableHomes 方法
ms.date: 03/30/2017
api_name:
- ICorDebugCode4.EnumerateVariableHomes
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode4::EnumerateVariableHomes
helpviewer_keywords:
- EnumerateVariableHomes method [.NET Framework debugging]
- ICorDebugCode4::EnumerateVariableHomes method [.NET Framework debugging]
ms.assetid: 802c01ff-8b80-4733-b6dd-03ab6ff7fa11
topic_type:
- apiref
ms.openlocfilehash: 850cbd2367dddd9f46375817e271cb8e7183cf64
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121086"
---
# <a name="icordebugcode4enumeratevariablehomes-method"></a><span data-ttu-id="cb7a0-102">ICorDebugCode4：： EnumerateVariableHomes 方法</span><span class="sxs-lookup"><span data-stu-id="cb7a0-102">ICorDebugCode4::EnumerateVariableHomes Method</span></span>
<span data-ttu-id="cb7a0-103">获取函数中局部变量和参数的枚举器。</span><span class="sxs-lookup"><span data-stu-id="cb7a0-103">Gets an enumerator to the local variables and arguments in a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb7a0-104">语法</span><span class="sxs-lookup"><span data-stu-id="cb7a0-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateVariableHomes(  
    [out] ICorDebugVariableHomeEnum **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cb7a0-105">参数</span><span class="sxs-lookup"><span data-stu-id="cb7a0-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="cb7a0-106">指向[ICorDebugVariableHomeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md)接口对象地址的指针，该对象是函数中局部变量和参数的枚举器。</span><span class="sxs-lookup"><span data-stu-id="cb7a0-106">A pointer to the address of an [ICorDebugVariableHomeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md) interface object that is an enumerator for the local variables and arguments in a function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cb7a0-107">备注</span><span class="sxs-lookup"><span data-stu-id="cb7a0-107">Remarks</span></span>  
 <span data-ttu-id="cb7a0-108">[ICorDebugVariableHomeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md)接口对象是从 "ICorDebugEnum" 接口派生的标准枚举器，该枚举器可用于枚举[ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)对象。</span><span class="sxs-lookup"><span data-stu-id="cb7a0-108">The [ICorDebugVariableHomeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md) interface object is a standard enumerator derived from the "ICorDebugEnum" interface that allows you to enumerate [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) objects.</span></span> <span data-ttu-id="cb7a0-109">如果同一槽或参数索引的多个[ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)对象在函数不同的点具有不同的主对象，则该集合可能包含多个这些对象。</span><span class="sxs-lookup"><span data-stu-id="cb7a0-109">The collection may include multiple [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) objects for the same slot or      argument index if they have different homes at different points in the      function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cb7a0-110">要求</span><span class="sxs-lookup"><span data-stu-id="cb7a0-110">Requirements</span></span>  
 <span data-ttu-id="cb7a0-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="cb7a0-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cb7a0-112">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cb7a0-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cb7a0-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cb7a0-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cb7a0-114">**.NET Framework 版本：** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cb7a0-114">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb7a0-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="cb7a0-115">See also</span></span>

- [<span data-ttu-id="cb7a0-116">ICorDebugCode4 接口</span><span class="sxs-lookup"><span data-stu-id="cb7a0-116">ICorDebugCode4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode4-interface.md)
- [<span data-ttu-id="cb7a0-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="cb7a0-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
