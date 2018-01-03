---
title: "“ICor调试异常调试事件”接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: f9ba60d8-b54d-417e-bb3e-fde4b41ca44c
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 97bbd9374b8a3f938f42b8ddd001049a2e7a324c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugexceptiondebugevent-interface"></a><span data-ttu-id="3783c-102">“ICor调试异常调试事件”接口</span><span class="sxs-lookup"><span data-stu-id="3783c-102">ICorDebugExceptionDebugEvent Interface</span></span>
<span data-ttu-id="3783c-103">扩展[icor 调试调试事件](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md)接口以支持异常事件。</span><span class="sxs-lookup"><span data-stu-id="3783c-103">Extends the [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) interface to support exception events.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3783c-104">方法</span><span class="sxs-lookup"><span data-stu-id="3783c-104">Methods</span></span>  
  
|<span data-ttu-id="3783c-105">方法</span><span class="sxs-lookup"><span data-stu-id="3783c-105">Method</span></span>|<span data-ttu-id="3783c-106">描述</span><span class="sxs-lookup"><span data-stu-id="3783c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3783c-107">GetFlags 方法</span><span class="sxs-lookup"><span data-stu-id="3783c-107">GetFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-getflags-method.md)|<span data-ttu-id="3783c-108">获取指示是否可拦截异常的标志。</span><span class="sxs-lookup"><span data-stu-id="3783c-108">Gets a flag that indicates whether the exception is can be intercepted.</span></span>|  
|[<span data-ttu-id="3783c-109">GetNativeIP 方法</span><span class="sxs-lookup"><span data-stu-id="3783c-109">GetNativeIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-getnativeip-method.md)|<span data-ttu-id="3783c-110">获取此异常调试事件的本机接口指针。</span><span class="sxs-lookup"><span data-stu-id="3783c-110">Gets the native interface pointer for this exception debug event.</span></span>|  
|[<span data-ttu-id="3783c-111">GetStackPointer 方法</span><span class="sxs-lookup"><span data-stu-id="3783c-111">GetStackPointer Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-getstackpointer-method.md)|<span data-ttu-id="3783c-112">获取此异常调试事件的堆栈指针。</span><span class="sxs-lookup"><span data-stu-id="3783c-112">Gets the stack pointer for this exception debug event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3783c-113">备注</span><span class="sxs-lookup"><span data-stu-id="3783c-113">Remarks</span></span>  
 <span data-ttu-id="3783c-114">`ICorDebugExceptionDebugEvent` 接口由以下事件类型实现：</span><span class="sxs-lookup"><span data-stu-id="3783c-114">The `ICorDebugExceptionDebugEvent` interface is implemented by the following event types:</span></span>  
  
-   [<span data-ttu-id="3783c-115">MANAGED_EXCEPTION_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="3783c-115">MANAGED_EXCEPTION_FIRST_CHANCE</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)  
  
-   [<span data-ttu-id="3783c-116">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="3783c-116">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)  
  
-   [<span data-ttu-id="3783c-117">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span><span class="sxs-lookup"><span data-stu-id="3783c-117">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)  
  
-   [<span data-ttu-id="3783c-118">MANAGED_EXCEPTION_UNHANDLED</span><span class="sxs-lookup"><span data-stu-id="3783c-118">MANAGED_EXCEPTION_UNHANDLED</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)  
  
> [!NOTE]
>  <span data-ttu-id="3783c-119">此接口仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="3783c-119">The interface is available with .NET Native only.</span></span> <span data-ttu-id="3783c-120">尝试调用 `QueryInterface` 来检索接口指针会为 .NET Native 外部的 ICorDebug 方案返回 `E_NOINTERFACE`。</span><span class="sxs-lookup"><span data-stu-id="3783c-120">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3783c-121">惠?</span><span class="sxs-lookup"><span data-stu-id="3783c-121">Requirements</span></span>  
 <span data-ttu-id="3783c-122">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3783c-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3783c-123">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3783c-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3783c-124">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3783c-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3783c-125">**.NET framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3783c-125">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3783c-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="3783c-126">See Also</span></span>  
 [<span data-ttu-id="3783c-127">调试接口</span><span class="sxs-lookup"><span data-stu-id="3783c-127">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="3783c-128">调试</span><span class="sxs-lookup"><span data-stu-id="3783c-128">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
