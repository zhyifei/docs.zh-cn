---
title: ICorDebugGenericValue 接口
ms.date: 03/30/2017
api_name:
- ICorDebugGenericValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGenericValue
helpviewer_keywords:
- ICorDebugGenericValue interface [.NET Framework debugging]
ms.assetid: bc14f408-b359-4c8c-ade2-888ccdf7261b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ad2209c6e28c7749bd149902e5b696955ee7f13f
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2019
ms.locfileid: "56981980"
---
# <a name="icordebuggenericvalue-interface"></a><span data-ttu-id="60f65-102">ICorDebugGenericValue 接口</span><span class="sxs-lookup"><span data-stu-id="60f65-102">ICorDebugGenericValue Interface</span></span>

<span data-ttu-id="60f65-103">适用于所有值的"ICorDebugValue"的子类。</span><span class="sxs-lookup"><span data-stu-id="60f65-103">A subclass of "ICorDebugValue" that applies to all values.</span></span> <span data-ttu-id="60f65-104">此接口可为值提供 Get 和 Set 方法。</span><span class="sxs-lookup"><span data-stu-id="60f65-104">This interface provides Get and Set methods for the value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="60f65-105">方法</span><span class="sxs-lookup"><span data-stu-id="60f65-105">Methods</span></span>  
  
|<span data-ttu-id="60f65-106">方法</span><span class="sxs-lookup"><span data-stu-id="60f65-106">Method</span></span>|<span data-ttu-id="60f65-107">描述</span><span class="sxs-lookup"><span data-stu-id="60f65-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="60f65-108">GetValue 方法</span><span class="sxs-lookup"><span data-stu-id="60f65-108">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-getvalue-method.md)|<span data-ttu-id="60f65-109">将值复制到指定的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="60f65-109">Copies the value into the specified buffer.</span></span>|  
|[<span data-ttu-id="60f65-110">SetValue 方法</span><span class="sxs-lookup"><span data-stu-id="60f65-110">SetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-setvalue-method.md)|<span data-ttu-id="60f65-111">从指定的缓冲区中复制新值。</span><span class="sxs-lookup"><span data-stu-id="60f65-111">Copies a new value from the specified buffer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="60f65-112">备注</span><span class="sxs-lookup"><span data-stu-id="60f65-112">Remarks</span></span>  
 <span data-ttu-id="60f65-113">`ICorDebugGenericValue` 因为它是不可远程处理是一个子接口。</span><span class="sxs-lookup"><span data-stu-id="60f65-113">`ICorDebugGenericValue` is a sub-interface because it is non-remotable.</span></span>  
  
 <span data-ttu-id="60f65-114">对于引用类型，值为引用而不是引用的内容。</span><span class="sxs-lookup"><span data-stu-id="60f65-114">For reference types, the value is the reference rather than the contents of the reference.</span></span>  
  
 <span data-ttu-id="60f65-115">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="60f65-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="60f65-116">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="60f65-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="60f65-117">要求</span><span class="sxs-lookup"><span data-stu-id="60f65-117">Requirements</span></span>  
 <span data-ttu-id="60f65-118">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="60f65-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="60f65-119">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="60f65-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="60f65-120">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="60f65-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="60f65-121">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="60f65-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60f65-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="60f65-122">See also</span></span>

- [<span data-ttu-id="60f65-123">调试接口</span><span class="sxs-lookup"><span data-stu-id="60f65-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
