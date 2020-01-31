---
title: ICorDebugExceptionDebugEvent 接口
ms.date: 03/30/2017
ms.assetid: f9ba60d8-b54d-417e-bb3e-fde4b41ca44c
ms.openlocfilehash: 168ba2945608a5b26432c5a0f583e5d406f6ce9b
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76782827"
---
# <a name="icordebugexceptiondebugevent-interface"></a><span data-ttu-id="9737b-102">ICorDebugExceptionDebugEvent 接口</span><span class="sxs-lookup"><span data-stu-id="9737b-102">ICorDebugExceptionDebugEvent Interface</span></span>
<span data-ttu-id="9737b-103">扩展[ICorDebugDebugEvent](icordebugdebugevent-interface.md)接口以支持异常事件。</span><span class="sxs-lookup"><span data-stu-id="9737b-103">Extends the [ICorDebugDebugEvent](icordebugdebugevent-interface.md) interface to support exception events.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9737b-104">方法</span><span class="sxs-lookup"><span data-stu-id="9737b-104">Methods</span></span>  
  
|<span data-ttu-id="9737b-105">方法</span><span class="sxs-lookup"><span data-stu-id="9737b-105">Method</span></span>|<span data-ttu-id="9737b-106">描述</span><span class="sxs-lookup"><span data-stu-id="9737b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9737b-107">GetFlags 方法</span><span class="sxs-lookup"><span data-stu-id="9737b-107">GetFlags Method</span></span>](icordebugexceptiondebugevent-getflags-method.md)|<span data-ttu-id="9737b-108">获取指示是否可拦截异常的标志。</span><span class="sxs-lookup"><span data-stu-id="9737b-108">Gets a flag that indicates whether the exception is can be intercepted.</span></span>|  
|[<span data-ttu-id="9737b-109">GetNativeIP 方法</span><span class="sxs-lookup"><span data-stu-id="9737b-109">GetNativeIP Method</span></span>](icordebugexceptiondebugevent-getnativeip-method.md)|<span data-ttu-id="9737b-110">获取此异常调试事件的本机接口指针。</span><span class="sxs-lookup"><span data-stu-id="9737b-110">Gets the native interface pointer for this exception debug event.</span></span>|  
|[<span data-ttu-id="9737b-111">GetStackPointer 方法</span><span class="sxs-lookup"><span data-stu-id="9737b-111">GetStackPointer Method</span></span>](icordebugexceptiondebugevent-getstackpointer-method.md)|<span data-ttu-id="9737b-112">获取此异常调试事件的堆栈指针。</span><span class="sxs-lookup"><span data-stu-id="9737b-112">Gets the stack pointer for this exception debug event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9737b-113">备注</span><span class="sxs-lookup"><span data-stu-id="9737b-113">Remarks</span></span>  
 <span data-ttu-id="9737b-114">`ICorDebugExceptionDebugEvent` 接口由以下事件类型实现：</span><span class="sxs-lookup"><span data-stu-id="9737b-114">The `ICorDebugExceptionDebugEvent` interface is implemented by the following event types:</span></span>  
  
- [<span data-ttu-id="9737b-115">MANAGED_EXCEPTION_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="9737b-115">MANAGED_EXCEPTION_FIRST_CHANCE</span></span>](cordebugrecordformat-enumeration.md)  
  
- [<span data-ttu-id="9737b-116">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="9737b-116">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span></span>](cordebugrecordformat-enumeration.md)  
  
- [<span data-ttu-id="9737b-117">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span><span class="sxs-lookup"><span data-stu-id="9737b-117">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span></span>](cordebugrecordformat-enumeration.md)  
  
- [<span data-ttu-id="9737b-118">MANAGED_EXCEPTION_UNHANDLED</span><span class="sxs-lookup"><span data-stu-id="9737b-118">MANAGED_EXCEPTION_UNHANDLED</span></span>](cordebugrecordformat-enumeration.md)  
  
> [!NOTE]
> <span data-ttu-id="9737b-119">此接口仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="9737b-119">The interface is available with .NET Native only.</span></span> <span data-ttu-id="9737b-120">尝试调用 `QueryInterface` 来检索接口指针会为 .NET Native 外部的 ICorDebug 方案返回 `E_NOINTERFACE`。</span><span class="sxs-lookup"><span data-stu-id="9737b-120">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9737b-121">需求</span><span class="sxs-lookup"><span data-stu-id="9737b-121">Requirements</span></span>  
 <span data-ttu-id="9737b-122">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9737b-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9737b-123">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9737b-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9737b-124">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9737b-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9737b-125">**.NET Framework 版本：** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9737b-125">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9737b-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9737b-126">See also</span></span>

- [<span data-ttu-id="9737b-127">调试接口</span><span class="sxs-lookup"><span data-stu-id="9737b-127">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="9737b-128">调试</span><span class="sxs-lookup"><span data-stu-id="9737b-128">Debugging</span></span>](index.md)
