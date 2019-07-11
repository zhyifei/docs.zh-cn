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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3ca3b86e90dcb76c1fece44cf2c5ed68e073d8e7
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67757219"
---
# <a name="icordebugheapvalueisvalid-method"></a><span data-ttu-id="337ce-102">ICorDebugHeapValue::IsValid 方法</span><span class="sxs-lookup"><span data-stu-id="337ce-102">ICorDebugHeapValue::IsValid Method</span></span>
<span data-ttu-id="337ce-103">获取一个值，该值指示此 ICorDebugHeapValue 所表示的对象是否有效。</span><span class="sxs-lookup"><span data-stu-id="337ce-103">Gets a value that indicates whether the object represented by this ICorDebugHeapValue is valid.</span></span>  
  
 <span data-ttu-id="337ce-104">.NET Framework 2.0 版中，此方法已弃用。</span><span class="sxs-lookup"><span data-stu-id="337ce-104">This method has been deprecated in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="337ce-105">语法</span><span class="sxs-lookup"><span data-stu-id="337ce-105">Syntax</span></span>  
  
```cpp  
HRESULT IsValid (  
    [out] BOOL    *pbValid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="337ce-106">参数</span><span class="sxs-lookup"><span data-stu-id="337ce-106">Parameters</span></span>  
 `pbValid`  
 <span data-ttu-id="337ce-107">[out]指向一个布尔值，该值指示在堆上的此值是否有效的指针。</span><span class="sxs-lookup"><span data-stu-id="337ce-107">[out] A pointer to a Boolean value that indicates whether this value on the heap is valid.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="337ce-108">备注</span><span class="sxs-lookup"><span data-stu-id="337ce-108">Remarks</span></span>  
 <span data-ttu-id="337ce-109">如果垃圾回收器回收，则值无效。</span><span class="sxs-lookup"><span data-stu-id="337ce-109">The value is invalid if it has been reclaimed by the garbage collector.</span></span>  
  
 <span data-ttu-id="337ce-110">此方法已被否决。</span><span class="sxs-lookup"><span data-stu-id="337ce-110">This method has been deprecated.</span></span> <span data-ttu-id="337ce-111">在.NET Framework 2.0 中，所有值都是有效期截止日期[icordebugcontroller:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md)调用时，在这段时间的值都是无效。</span><span class="sxs-lookup"><span data-stu-id="337ce-111">In the .NET Framework 2.0, all values are valid until [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) is called, at which time the values are invalidated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="337ce-112">要求</span><span class="sxs-lookup"><span data-stu-id="337ce-112">Requirements</span></span>  
 <span data-ttu-id="337ce-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="337ce-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="337ce-114">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="337ce-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="337ce-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="337ce-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="337ce-116">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="337ce-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
