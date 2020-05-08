---
title: ICorDebugExceptionDebugEvent::GetStackPointer 方法
ms.date: 03/30/2017
ms.assetid: d8f66a1c-16be-4264-afc5-bc2dfbb4a682
ms.openlocfilehash: 4f84183dfc23ebc0d0fee9feeb21329c217b9cca
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976013"
---
# <a name="icordebugexceptiondebugeventgetstackpointer-method"></a><span data-ttu-id="0c702-102">ICorDebugExceptionDebugEvent::GetStackPointer 方法</span><span class="sxs-lookup"><span data-stu-id="0c702-102">ICorDebugExceptionDebugEvent::GetStackPointer Method</span></span>
<span data-ttu-id="0c702-103">获取此异常调试事件的堆栈指针。</span><span class="sxs-lookup"><span data-stu-id="0c702-103">Gets the stack pointer for this exception debug event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c702-104">语法</span><span class="sxs-lookup"><span data-stu-id="0c702-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStackPointer(  
   [out]CORDB_ADDRESS *pStackPointer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0c702-105">参数</span><span class="sxs-lookup"><span data-stu-id="0c702-105">Parameters</span></span>  
 `pStackPointer`  
 <span data-ttu-id="0c702-106">[out] 指向此异常调试事件的堆栈指针的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="0c702-106">[out] A pointer to the address of the stack pointer for this exception debug event.</span></span> <span data-ttu-id="0c702-107">有关详细信息，请参阅“备注”部分。</span><span class="sxs-lookup"><span data-stu-id="0c702-107">See the Remarks section for more information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0c702-108">备注</span><span class="sxs-lookup"><span data-stu-id="0c702-108">Remarks</span></span>  
 <span data-ttu-id="0c702-109">此堆栈指针的含义取决于事件类型，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="0c702-109">The meaning of this stack pointer depends on the event type, as shown in the following table.</span></span>  
  
|<span data-ttu-id="0c702-110">事件类型</span><span class="sxs-lookup"><span data-stu-id="0c702-110">Event type</span></span>|<span data-ttu-id="0c702-111">`pStackPointer` 值的含义</span><span class="sxs-lookup"><span data-stu-id="0c702-111">Meaning of `pStackPointer` value</span></span>|  
|----------------|--------------------------------------|  
|[<span data-ttu-id="0c702-112">MANAGED_EXCEPTION_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="0c702-112">MANAGED_EXCEPTION_FIRST_CHANCE</span></span>](cordebugrecordformat-enumeration.md)|<span data-ttu-id="0c702-113">引发异常的帧的堆栈指针。</span><span class="sxs-lookup"><span data-stu-id="0c702-113">The stack pointer for the frame that threw the exception.</span></span>|  
|[<span data-ttu-id="0c702-114">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="0c702-114">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span></span>](cordebugrecordformat-enumeration.md)|<span data-ttu-id="0c702-115">与引发的异常点最接近的用户代码帧的堆栈指针。</span><span class="sxs-lookup"><span data-stu-id="0c702-115">The stack pointer for the user-code frame closest to the point of the thrown exception.</span></span>|  
|[<span data-ttu-id="0c702-116">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span><span class="sxs-lookup"><span data-stu-id="0c702-116">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span></span>](cordebugrecordformat-enumeration.md)|<span data-ttu-id="0c702-117">包含 catch 处理程序的帧的堆栈指针。</span><span class="sxs-lookup"><span data-stu-id="0c702-117">The stack pointer for the frame that contains the catch handler.</span></span>|  
|[<span data-ttu-id="0c702-118">MANAGED_EXCEPTION_UNHANDLED</span><span class="sxs-lookup"><span data-stu-id="0c702-118">MANAGED_EXCEPTION_UNHANDLED</span></span>](cordebugrecordformat-enumeration.md)|<span data-ttu-id="0c702-119">`pStackPointer` 为 **null**。</span><span class="sxs-lookup"><span data-stu-id="0c702-119">`pStackPointer` is **null**.</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="0c702-120">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="0c702-120">This method is available with .NET Native only.</span></span>  
  
 <span data-ttu-id="0c702-121">可以从[ICorDebugDebugEvent：： GetEventKind](icordebugdebugevent-geteventkind-method.md)方法获取事件类型。</span><span class="sxs-lookup"><span data-stu-id="0c702-121">The event type is available from the [ICorDebugDebugEvent::GetEventKind](icordebugdebugevent-geteventkind-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c702-122">要求</span><span class="sxs-lookup"><span data-stu-id="0c702-122">Requirements</span></span>  
 <span data-ttu-id="0c702-123">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0c702-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c702-124">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0c702-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0c702-125">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0c702-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0c702-126">**.NET Framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c702-126">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c702-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0c702-127">See also</span></span>

- [<span data-ttu-id="0c702-128">“ICor调试异常调试事件”接口</span><span class="sxs-lookup"><span data-stu-id="0c702-128">ICorDebugExceptionDebugEvent Interface</span></span>](icordebugexceptiondebugevent-interface.md)
- [<span data-ttu-id="0c702-129">调试接口</span><span class="sxs-lookup"><span data-stu-id="0c702-129">Debugging Interfaces</span></span>](debugging-interfaces.md)
