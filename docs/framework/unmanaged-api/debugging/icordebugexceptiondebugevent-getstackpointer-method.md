---
title: "ICorDebugExceptionDebugEvent::GetStackPointer 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: d8f66a1c-16be-4264-afc5-bc2dfbb4a682
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1b9096bbb494036156a528d8f9e940630f555f6a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugexceptiondebugeventgetstackpointer-method"></a><span data-ttu-id="176b2-102">ICorDebugExceptionDebugEvent::GetStackPointer 方法</span><span class="sxs-lookup"><span data-stu-id="176b2-102">ICorDebugExceptionDebugEvent::GetStackPointer Method</span></span>
<span data-ttu-id="176b2-103">获取此异常调试事件的堆栈指针。</span><span class="sxs-lookup"><span data-stu-id="176b2-103">Gets the stack pointer for this exception debug event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="176b2-104">语法</span><span class="sxs-lookup"><span data-stu-id="176b2-104">Syntax</span></span>  
  
```  
HRESULT GetStackPointer(  
   [out]CORDB_ADDRESS *pStackPointer  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="176b2-105">参数</span><span class="sxs-lookup"><span data-stu-id="176b2-105">Parameters</span></span>  
 `pStackPointer`  
 <span data-ttu-id="176b2-106">[out] 指向此异常调试事件的堆栈指针的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="176b2-106">[out] A pointer to the address of the stack pointer for this exception debug event.</span></span> <span data-ttu-id="176b2-107">有关详细信息，请参阅备注部分。</span><span class="sxs-lookup"><span data-stu-id="176b2-107">See the Remarks section for more information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="176b2-108">备注</span><span class="sxs-lookup"><span data-stu-id="176b2-108">Remarks</span></span>  
 <span data-ttu-id="176b2-109">此堆栈指针的含义取决于事件类型，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="176b2-109">The meaning of this stack pointer depends on the event type, as shown in the following table.</span></span>  
  
|<span data-ttu-id="176b2-110">事件类型</span><span class="sxs-lookup"><span data-stu-id="176b2-110">Event type</span></span>|<span data-ttu-id="176b2-111">`pStackPointer` 值的含义</span><span class="sxs-lookup"><span data-stu-id="176b2-111">Meaning of `pStackPointer` value</span></span>|  
|----------------|--------------------------------------|  
|[<span data-ttu-id="176b2-112">MANAGED_EXCEPTION_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="176b2-112">MANAGED_EXCEPTION_FIRST_CHANCE</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)|<span data-ttu-id="176b2-113">引发异常的帧的堆栈指针。</span><span class="sxs-lookup"><span data-stu-id="176b2-113">The stack pointer for the frame that threw the exception.</span></span>|  
|[<span data-ttu-id="176b2-114">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="176b2-114">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)|<span data-ttu-id="176b2-115">与引发的异常点最接近的用户代码帧的堆栈指针。</span><span class="sxs-lookup"><span data-stu-id="176b2-115">The stack pointer for the user-code frame closest to the point of the thrown exception.</span></span>|  
|[<span data-ttu-id="176b2-116">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span><span class="sxs-lookup"><span data-stu-id="176b2-116">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)|<span data-ttu-id="176b2-117">包含 catch 处理程序的帧的堆栈指针。</span><span class="sxs-lookup"><span data-stu-id="176b2-117">The stack pointer for the frame that contains the catch handler.</span></span>|  
|[<span data-ttu-id="176b2-118">MANAGED_EXCEPTION_UNHANDLED</span><span class="sxs-lookup"><span data-stu-id="176b2-118">MANAGED_EXCEPTION_UNHANDLED</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)|<span data-ttu-id="176b2-119">`pStackPointer` 为 null。</span><span class="sxs-lookup"><span data-stu-id="176b2-119">`pStackPointer` is **null**.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="176b2-120">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="176b2-120">This method is available with .NET Native only.</span></span>  
  
 <span data-ttu-id="176b2-121">事件类型是可从[icordebugdebugevent:: Geteventkind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="176b2-121">The event type is available from the [ICorDebugDebugEvent::GetEventKind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="176b2-122">惠?</span><span class="sxs-lookup"><span data-stu-id="176b2-122">Requirements</span></span>  
 <span data-ttu-id="176b2-123">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="176b2-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="176b2-124">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="176b2-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="176b2-125">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="176b2-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="176b2-126">**.NET framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="176b2-126">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="176b2-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="176b2-127">See Also</span></span>  
 [<span data-ttu-id="176b2-128">ICorDebugExceptionDebugEvent 接口</span><span class="sxs-lookup"><span data-stu-id="176b2-128">ICorDebugExceptionDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-interface.md)  
 [<span data-ttu-id="176b2-129">调试接口</span><span class="sxs-lookup"><span data-stu-id="176b2-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
