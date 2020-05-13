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
ms.openlocfilehash: 7c5359ddf2c021f77ad1ea0a8579316c3c773fd5
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209781"
---
# <a name="icordebuggenericvalue-interface"></a><span data-ttu-id="824ee-102">ICorDebugGenericValue 接口</span><span class="sxs-lookup"><span data-stu-id="824ee-102">ICorDebugGenericValue Interface</span></span>

<span data-ttu-id="824ee-103">"ICorDebugValue" 的子类，适用于所有值。</span><span class="sxs-lookup"><span data-stu-id="824ee-103">A subclass of "ICorDebugValue" that applies to all values.</span></span> <span data-ttu-id="824ee-104">此接口可为值提供 Get 和 Set 方法。</span><span class="sxs-lookup"><span data-stu-id="824ee-104">This interface provides Get and Set methods for the value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="824ee-105">方法</span><span class="sxs-lookup"><span data-stu-id="824ee-105">Methods</span></span>  
  
|<span data-ttu-id="824ee-106">方法</span><span class="sxs-lookup"><span data-stu-id="824ee-106">Method</span></span>|<span data-ttu-id="824ee-107">描述</span><span class="sxs-lookup"><span data-stu-id="824ee-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="824ee-108">GetValue 方法</span><span class="sxs-lookup"><span data-stu-id="824ee-108">GetValue Method</span></span>](icordebuggenericvalue-getvalue-method.md)|<span data-ttu-id="824ee-109">将值复制到指定的缓冲区中。</span><span class="sxs-lookup"><span data-stu-id="824ee-109">Copies the value into the specified buffer.</span></span>|  
|[<span data-ttu-id="824ee-110">SetValue 方法</span><span class="sxs-lookup"><span data-stu-id="824ee-110">SetValue Method</span></span>](icordebuggenericvalue-setvalue-method.md)|<span data-ttu-id="824ee-111">从指定的缓冲区复制新值。</span><span class="sxs-lookup"><span data-stu-id="824ee-111">Copies a new value from the specified buffer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="824ee-112">备注</span><span class="sxs-lookup"><span data-stu-id="824ee-112">Remarks</span></span>  
 <span data-ttu-id="824ee-113">`ICorDebugGenericValue`是子接口，因为它是不可远程处理的。</span><span class="sxs-lookup"><span data-stu-id="824ee-113">`ICorDebugGenericValue` is a sub-interface because it is non-remotable.</span></span>  
  
 <span data-ttu-id="824ee-114">对于引用类型，该值是引用而不是引用的内容。</span><span class="sxs-lookup"><span data-stu-id="824ee-114">For reference types, the value is the reference rather than the contents of the reference.</span></span>  
  
 <span data-ttu-id="824ee-115">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="824ee-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="824ee-116">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="824ee-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="824ee-117">要求</span><span class="sxs-lookup"><span data-stu-id="824ee-117">Requirements</span></span>  
 <span data-ttu-id="824ee-118">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="824ee-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="824ee-119">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="824ee-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="824ee-120">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="824ee-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="824ee-121">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="824ee-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="824ee-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="824ee-122">See also</span></span>

- [<span data-ttu-id="824ee-123">调试接口</span><span class="sxs-lookup"><span data-stu-id="824ee-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
