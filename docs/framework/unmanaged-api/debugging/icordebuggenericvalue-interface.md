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
ms.workload: dotnet
ms.openlocfilehash: d6c6fb4893edf0bcda9d6f7ddbeea7054f5b4fd5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebuggenericvalue-interface1"></a><span data-ttu-id="23ee3-102">ICorDebugGenericValue 接口 1</span><span class="sxs-lookup"><span data-stu-id="23ee3-102">ICorDebugGenericValue Interface1</span></span>
<span data-ttu-id="23ee3-103">"ICorDebugValue"适用于所有值的一个子类。</span><span class="sxs-lookup"><span data-stu-id="23ee3-103">A subclass of "ICorDebugValue" that applies to all values.</span></span> <span data-ttu-id="23ee3-104">此接口可为值提供 Get 和 Set 方法。</span><span class="sxs-lookup"><span data-stu-id="23ee3-104">This interface provides Get and Set methods for the value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="23ee3-105">方法</span><span class="sxs-lookup"><span data-stu-id="23ee3-105">Methods</span></span>  
  
|<span data-ttu-id="23ee3-106">方法</span><span class="sxs-lookup"><span data-stu-id="23ee3-106">Method</span></span>|<span data-ttu-id="23ee3-107">描述</span><span class="sxs-lookup"><span data-stu-id="23ee3-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="23ee3-108">GetValue 方法</span><span class="sxs-lookup"><span data-stu-id="23ee3-108">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-getvalue-method.md)|<span data-ttu-id="23ee3-109">将值复制到指定的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="23ee3-109">Copies the value into the specified buffer.</span></span>|  
|[<span data-ttu-id="23ee3-110">SetValue 方法</span><span class="sxs-lookup"><span data-stu-id="23ee3-110">SetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-setvalue-method.md)|<span data-ttu-id="23ee3-111">从指定的缓冲区中复制新值。</span><span class="sxs-lookup"><span data-stu-id="23ee3-111">Copies a new value from the specified buffer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="23ee3-112">备注</span><span class="sxs-lookup"><span data-stu-id="23ee3-112">Remarks</span></span>  
 <span data-ttu-id="23ee3-113">`ICorDebugGenericValue`是一个子接口，因为它是非远程操作。</span><span class="sxs-lookup"><span data-stu-id="23ee3-113">`ICorDebugGenericValue` is a sub-interface because it is non-remotable.</span></span>  
  
 <span data-ttu-id="23ee3-114">对于引用类型，则这是引用而不是该引用的内容。</span><span class="sxs-lookup"><span data-stu-id="23ee3-114">For reference types, the value is the reference rather than the contents of the reference.</span></span>  
  
 <span data-ttu-id="23ee3-115">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="23ee3-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="23ee3-116">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="23ee3-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="23ee3-117">惠?</span><span class="sxs-lookup"><span data-stu-id="23ee3-117">Requirements</span></span>  
 <span data-ttu-id="23ee3-118">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="23ee3-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="23ee3-119">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="23ee3-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="23ee3-120">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="23ee3-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="23ee3-121">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="23ee3-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23ee3-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="23ee3-122">See Also</span></span>  
    
 [<span data-ttu-id="23ee3-123">调试接口</span><span class="sxs-lookup"><span data-stu-id="23ee3-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
