---
title: "ICorDebugGenericValue 接口 1"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugGenericValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugGenericValue
helpviewer_keywords: ICorDebugGenericValue interface [.NET Framework debugging]
ms.assetid: bc14f408-b359-4c8c-ade2-888ccdf7261b
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 61c159e30efb33dca4043e5b5306c9544acd614a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icordebuggenericvalue-interface1"></a><span data-ttu-id="1bb71-102">ICorDebugGenericValue 接口 1</span><span class="sxs-lookup"><span data-stu-id="1bb71-102">ICorDebugGenericValue Interface1</span></span>
<span data-ttu-id="1bb71-103">"ICorDebugValue"适用于所有值的一个子类。</span><span class="sxs-lookup"><span data-stu-id="1bb71-103">A subclass of "ICorDebugValue" that applies to all values.</span></span> <span data-ttu-id="1bb71-104">此接口可为值提供 Get 和 Set 方法。</span><span class="sxs-lookup"><span data-stu-id="1bb71-104">This interface provides Get and Set methods for the value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1bb71-105">方法</span><span class="sxs-lookup"><span data-stu-id="1bb71-105">Methods</span></span>  
  
|<span data-ttu-id="1bb71-106">方法</span><span class="sxs-lookup"><span data-stu-id="1bb71-106">Method</span></span>|<span data-ttu-id="1bb71-107">描述</span><span class="sxs-lookup"><span data-stu-id="1bb71-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1bb71-108">GetValue 方法</span><span class="sxs-lookup"><span data-stu-id="1bb71-108">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-getvalue-method.md)|<span data-ttu-id="1bb71-109">将值复制到指定的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="1bb71-109">Copies the value into the specified buffer.</span></span>|  
|[<span data-ttu-id="1bb71-110">SetValue 方法</span><span class="sxs-lookup"><span data-stu-id="1bb71-110">SetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-setvalue-method.md)|<span data-ttu-id="1bb71-111">从指定的缓冲区中复制新值。</span><span class="sxs-lookup"><span data-stu-id="1bb71-111">Copies a new value from the specified buffer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1bb71-112">备注</span><span class="sxs-lookup"><span data-stu-id="1bb71-112">Remarks</span></span>  
 <span data-ttu-id="1bb71-113">`ICorDebugGenericValue`是一个子接口，因为它是非远程操作。</span><span class="sxs-lookup"><span data-stu-id="1bb71-113">`ICorDebugGenericValue` is a sub-interface because it is non-remotable.</span></span>  
  
 <span data-ttu-id="1bb71-114">对于引用类型，则这是引用而不是该引用的内容。</span><span class="sxs-lookup"><span data-stu-id="1bb71-114">For reference types, the value is the reference rather than the contents of the reference.</span></span>  
  
 <span data-ttu-id="1bb71-115">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="1bb71-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1bb71-116">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="1bb71-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1bb71-117">要求</span><span class="sxs-lookup"><span data-stu-id="1bb71-117">Requirements</span></span>  
 <span data-ttu-id="1bb71-118">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1bb71-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1bb71-119">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1bb71-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1bb71-120">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1bb71-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1bb71-121">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1bb71-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1bb71-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1bb71-122">See Also</span></span>  
    
 [<span data-ttu-id="1bb71-123">调试接口</span><span class="sxs-lookup"><span data-stu-id="1bb71-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
