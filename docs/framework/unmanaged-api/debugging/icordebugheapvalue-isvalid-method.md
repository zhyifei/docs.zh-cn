---
title: ICorDebugHeapValue::IsValid 方法
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue.IsValid
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue::IsValid
helpviewer_keywords:
- IsValid method [.NET Framework debugging]
- ICorDebugHeapValue::IsValid method [.NET Framework debugging]
ms.assetid: 68e20e62-203d-46d8-bb91-8d3c61cfacc3
topic_type:
- apiref
ms.openlocfilehash: 7edf0065fa7eb39dada167a682f2b634a438f1f3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138403"
---
# <a name="icordebugheapvalueisvalid-method"></a><span data-ttu-id="9c093-102">ICorDebugHeapValue::IsValid 方法</span><span class="sxs-lookup"><span data-stu-id="9c093-102">ICorDebugHeapValue::IsValid Method</span></span>
<span data-ttu-id="9c093-103">获取一个值，该值指示此 ICorDebugHeapValue 表示的对象是否有效。</span><span class="sxs-lookup"><span data-stu-id="9c093-103">Gets a value that indicates whether the object represented by this ICorDebugHeapValue is valid.</span></span>  
  
 <span data-ttu-id="9c093-104">此方法在 .NET Framework 版本2.0 中已弃用。</span><span class="sxs-lookup"><span data-stu-id="9c093-104">This method has been deprecated in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c093-105">语法</span><span class="sxs-lookup"><span data-stu-id="9c093-105">Syntax</span></span>  
  
```cpp  
HRESULT IsValid (  
    [out] BOOL    *pbValid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9c093-106">参数</span><span class="sxs-lookup"><span data-stu-id="9c093-106">Parameters</span></span>  
 `pbValid`  
 <span data-ttu-id="9c093-107">弄一个指向布尔值的指针，该布尔值指示堆上的此值是否有效。</span><span class="sxs-lookup"><span data-stu-id="9c093-107">[out] A pointer to a Boolean value that indicates whether this value on the heap is valid.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9c093-108">备注</span><span class="sxs-lookup"><span data-stu-id="9c093-108">Remarks</span></span>  
 <span data-ttu-id="9c093-109">如果它已被垃圾回收器回收，则该值无效。</span><span class="sxs-lookup"><span data-stu-id="9c093-109">The value is invalid if it has been reclaimed by the garbage collector.</span></span>  
  
 <span data-ttu-id="9c093-110">此方法已被否决。</span><span class="sxs-lookup"><span data-stu-id="9c093-110">This method has been deprecated.</span></span> <span data-ttu-id="9c093-111">在 .NET Framework 2.0 中，在调用[ICorDebugController：： Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md)之前，所有值都有效，此时值无效。</span><span class="sxs-lookup"><span data-stu-id="9c093-111">In the .NET Framework 2.0, all values are valid until [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) is called, at which time the values are invalidated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9c093-112">要求</span><span class="sxs-lookup"><span data-stu-id="9c093-112">Requirements</span></span>  
 <span data-ttu-id="9c093-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9c093-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9c093-114">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9c093-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9c093-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9c093-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9c093-116">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9c093-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
