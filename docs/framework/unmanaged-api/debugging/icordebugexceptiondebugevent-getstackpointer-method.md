---
title: ICorDebugExceptionDebugEvent::GetStackPointer 方法
ms.date: 03/30/2017
ms.assetid: d8f66a1c-16be-4264-afc5-bc2dfbb4a682
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 47f60b151166804d612292fb32b7ff154e417342
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69928207"
---
# <a name="icordebugexceptiondebugeventgetstackpointer-method"></a><span data-ttu-id="e0481-102">ICorDebugExceptionDebugEvent::GetStackPointer 方法</span><span class="sxs-lookup"><span data-stu-id="e0481-102">ICorDebugExceptionDebugEvent::GetStackPointer Method</span></span>
<span data-ttu-id="e0481-103">获取此异常调试事件的堆栈指针。</span><span class="sxs-lookup"><span data-stu-id="e0481-103">Gets the stack pointer for this exception debug event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0481-104">语法</span><span class="sxs-lookup"><span data-stu-id="e0481-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStackPointer(  
   [out]CORDB_ADDRESS *pStackPointer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e0481-105">参数</span><span class="sxs-lookup"><span data-stu-id="e0481-105">Parameters</span></span>  
 `pStackPointer`  
 <span data-ttu-id="e0481-106">[out] 指向此异常调试事件的堆栈指针的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="e0481-106">[out] A pointer to the address of the stack pointer for this exception debug event.</span></span> <span data-ttu-id="e0481-107">有关详细信息，请参阅备注部分。</span><span class="sxs-lookup"><span data-stu-id="e0481-107">See the Remarks section for more information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e0481-108">备注</span><span class="sxs-lookup"><span data-stu-id="e0481-108">Remarks</span></span>  
 <span data-ttu-id="e0481-109">此堆栈指针的含义取决于事件类型，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="e0481-109">The meaning of this stack pointer depends on the event type, as shown in the following table.</span></span>  
  
|<span data-ttu-id="e0481-110">事件类型</span><span class="sxs-lookup"><span data-stu-id="e0481-110">Event type</span></span>|<span data-ttu-id="e0481-111">`pStackPointer` 值的含义</span><span class="sxs-lookup"><span data-stu-id="e0481-111">Meaning of `pStackPointer` value</span></span>|  
|----------------|--------------------------------------|  
|[<span data-ttu-id="e0481-112">MANAGED_EXCEPTION_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="e0481-112">MANAGED_EXCEPTION_FIRST_CHANCE</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)|<span data-ttu-id="e0481-113">引发异常的帧的堆栈指针。</span><span class="sxs-lookup"><span data-stu-id="e0481-113">The stack pointer for the frame that threw the exception.</span></span>|  
|[<span data-ttu-id="e0481-114">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="e0481-114">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)|<span data-ttu-id="e0481-115">与引发的异常点最接近的用户代码帧的堆栈指针。</span><span class="sxs-lookup"><span data-stu-id="e0481-115">The stack pointer for the user-code frame closest to the point of the thrown exception.</span></span>|  
|[<span data-ttu-id="e0481-116">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span><span class="sxs-lookup"><span data-stu-id="e0481-116">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)|<span data-ttu-id="e0481-117">包含 catch 处理程序的帧的堆栈指针。</span><span class="sxs-lookup"><span data-stu-id="e0481-117">The stack pointer for the frame that contains the catch handler.</span></span>|  
|[<span data-ttu-id="e0481-118">MANAGED_EXCEPTION_UNHANDLED</span><span class="sxs-lookup"><span data-stu-id="e0481-118">MANAGED_EXCEPTION_UNHANDLED</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)|<span data-ttu-id="e0481-119">`pStackPointer` 为 null。</span><span class="sxs-lookup"><span data-stu-id="e0481-119">`pStackPointer` is **null**.</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="e0481-120">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="e0481-120">This method is available with .NET Native only.</span></span>  
  
 <span data-ttu-id="e0481-121">可以从[ICorDebugDebugEvent:: GetEventKind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md)方法获取事件类型。</span><span class="sxs-lookup"><span data-stu-id="e0481-121">The event type is available from the [ICorDebugDebugEvent::GetEventKind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0481-122">要求</span><span class="sxs-lookup"><span data-stu-id="e0481-122">Requirements</span></span>  
 <span data-ttu-id="e0481-123">**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e0481-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0481-124">**标头：** Cordebug.idl, Cordebug.idl</span><span class="sxs-lookup"><span data-stu-id="e0481-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e0481-125">**类库**CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e0481-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e0481-126">**.NET Framework 版本：** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e0481-126">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0481-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="e0481-127">See also</span></span>

- [<span data-ttu-id="e0481-128">ICorDebugExceptionDebugEvent 接口</span><span class="sxs-lookup"><span data-stu-id="e0481-128">ICorDebugExceptionDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-interface.md)
- [<span data-ttu-id="e0481-129">调试接口</span><span class="sxs-lookup"><span data-stu-id="e0481-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
