---
title: ICorDebugGenericValue Interface1
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
ms.openlocfilehash: ce4c1b73ab806958627bb68bfdcfcae890bc5e67
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54709827"
---
# <a name="icordebuggenericvalue-interface1"></a><span data-ttu-id="192c7-102">ICorDebugGenericValue Interface1</span><span class="sxs-lookup"><span data-stu-id="192c7-102">ICorDebugGenericValue Interface1</span></span>
<span data-ttu-id="192c7-103">适用于所有值的"ICorDebugValue"的子类。</span><span class="sxs-lookup"><span data-stu-id="192c7-103">A subclass of "ICorDebugValue" that applies to all values.</span></span> <span data-ttu-id="192c7-104">此接口可为值提供 Get 和 Set 方法。</span><span class="sxs-lookup"><span data-stu-id="192c7-104">This interface provides Get and Set methods for the value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="192c7-105">方法</span><span class="sxs-lookup"><span data-stu-id="192c7-105">Methods</span></span>  
  
|<span data-ttu-id="192c7-106">方法</span><span class="sxs-lookup"><span data-stu-id="192c7-106">Method</span></span>|<span data-ttu-id="192c7-107">描述</span><span class="sxs-lookup"><span data-stu-id="192c7-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="192c7-108">GetValue 方法</span><span class="sxs-lookup"><span data-stu-id="192c7-108">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-getvalue-method.md)|<span data-ttu-id="192c7-109">将值复制到指定的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="192c7-109">Copies the value into the specified buffer.</span></span>|  
|[<span data-ttu-id="192c7-110">SetValue 方法</span><span class="sxs-lookup"><span data-stu-id="192c7-110">SetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-setvalue-method.md)|<span data-ttu-id="192c7-111">从指定的缓冲区中复制新值。</span><span class="sxs-lookup"><span data-stu-id="192c7-111">Copies a new value from the specified buffer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="192c7-112">备注</span><span class="sxs-lookup"><span data-stu-id="192c7-112">Remarks</span></span>  
 <span data-ttu-id="192c7-113">`ICorDebugGenericValue` 因为它是不可远程处理是一个子接口。</span><span class="sxs-lookup"><span data-stu-id="192c7-113">`ICorDebugGenericValue` is a sub-interface because it is non-remotable.</span></span>  
  
 <span data-ttu-id="192c7-114">对于引用类型，值为引用而不是引用的内容。</span><span class="sxs-lookup"><span data-stu-id="192c7-114">For reference types, the value is the reference rather than the contents of the reference.</span></span>  
  
 <span data-ttu-id="192c7-115">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="192c7-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="192c7-116">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="192c7-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="192c7-117">要求</span><span class="sxs-lookup"><span data-stu-id="192c7-117">Requirements</span></span>  
 <span data-ttu-id="192c7-118">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="192c7-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="192c7-119">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="192c7-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="192c7-120">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="192c7-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="192c7-121">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="192c7-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="192c7-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="192c7-122">See also</span></span>

- [<span data-ttu-id="192c7-123">调试接口</span><span class="sxs-lookup"><span data-stu-id="192c7-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
