---
title: "ICorDebugILFrame3::GetReturnValueForILOffset 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- csharp
- vb
api_name:
- ICorDebugILFrame3.GetReturnValueForILOffset
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 06522727-5f64-4391-9331-11386883c352
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: c58319de99bdd8d7cce0ea55ccb3140a31a39bd0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugilframe3getreturnvalueforiloffset-method"></a><span data-ttu-id="f4982-102">ICorDebugILFrame3::GetReturnValueForILOffset 方法</span><span class="sxs-lookup"><span data-stu-id="f4982-102">ICorDebugILFrame3::GetReturnValueForILOffset Method</span></span>
<span data-ttu-id="f4982-103">获取封装函数的返回值的"ICorDebugValue"对象。</span><span class="sxs-lookup"><span data-stu-id="f4982-103">Gets an "ICorDebugValue" object that encapsulates the return value of a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4982-104">语法</span><span class="sxs-lookup"><span data-stu-id="f4982-104">Syntax</span></span>  
  
```cpp
HRESULT GetReturnValueForILOffset(  
    ULONG32 ILoffset,   
    [out] ICorDebugValue **ppReturnValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f4982-105">参数</span><span class="sxs-lookup"><span data-stu-id="f4982-105">Parameters</span></span>  
 `ILOffset`  
 <span data-ttu-id="f4982-106">IL 偏移量。</span><span class="sxs-lookup"><span data-stu-id="f4982-106">The IL offset.</span></span> <span data-ttu-id="f4982-107">请参见“备注”部分。</span><span class="sxs-lookup"><span data-stu-id="f4982-107">See the Remarks section.</span></span>  
  
 `ppReturnValue`  
 <span data-ttu-id="f4982-108">提供有关返回值的函数调用信息"ICorDebugValue"接口对象的地址指向的指针。</span><span class="sxs-lookup"><span data-stu-id="f4982-108">A pointer to the address of an "ICorDebugValue" interface object that provides information about the return value of a function call.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f4982-109">备注</span><span class="sxs-lookup"><span data-stu-id="f4982-109">Remarks</span></span>  
 <span data-ttu-id="f4982-110">此方法使用连同[icordebugcode3:: Getreturnvalueliveoffset](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md)方法以获取方法的返回值。</span><span class="sxs-lookup"><span data-stu-id="f4982-110">This method is used along with the [ICorDebugCode3::GetReturnValueLiveOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md) method to get the return value of a method.</span></span> <span data-ttu-id="f4982-111">它将在其返回值将被忽略，如下面的两个代码示例所示的方法的情况下特别有用。</span><span class="sxs-lookup"><span data-stu-id="f4982-111">It is particularly useful in the case of methods whose return values are ignored, as in the following two code examples.</span></span> <span data-ttu-id="f4982-112">第一个示例调用<xref:System.Int32.TryParse%2A?displayProperty=nameWithType>方法，但将忽略方法的返回值。</span><span class="sxs-lookup"><span data-stu-id="f4982-112">The first example calls the <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> method, but ignores the method's return value.</span></span>  
  
 [!code-csharp[Unmanaged.Debugging.MRV#1](../../../../samples/snippets/csharp/VS_Snippets_CLR/unmanaged.debugging.mrv/cs/mrv1.cs#1)]
 [!code-vb[Unmanaged.Debugging.MRV#1](../../../../samples/snippets/visualbasic/VS_Snippets_CLR/unmanaged.debugging.mrv/vb/mrv1.vb#1)]  
  
 <span data-ttu-id="f4982-113">第二个示例阐释得更加常见调试问题。</span><span class="sxs-lookup"><span data-stu-id="f4982-113">The second example illustrates a much more common problem in debugging.</span></span> <span data-ttu-id="f4982-114">由于方法用作方法调用中的参数，因此，仅当，调试器逐句通过调用的方法，才可访问其返回值。</span><span class="sxs-lookup"><span data-stu-id="f4982-114">Because a method is used as an argument in a method call, its return value is accessible only when the debugger steps through the called method.</span></span> <span data-ttu-id="f4982-115">在许多情况下，尤其是当调用的方法定义在外部的库中，这是不可行。</span><span class="sxs-lookup"><span data-stu-id="f4982-115">In many cases, particularly when the called method is defined in an external library, that is not possible.</span></span>  
  
 [!code-csharp[Unmanaged.Debugging.MRV#2](../../../../samples/snippets/csharp/VS_Snippets_CLR/unmanaged.debugging.mrv/cs/mrv2.cs#2)]
 [!code-vb[Unmanaged.Debugging.MRV#2](../../../../samples/snippets/visualbasic/VS_Snippets_CLR/unmanaged.debugging.mrv/vb/mrv2.vb#2)]  
  
 <span data-ttu-id="f4982-116">如果你通过[icordebugcode3:: Getreturnvalueliveoffset](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md)的 IL 偏移量到函数的调用站点的方法，它将返回一个或多个本机偏移量。</span><span class="sxs-lookup"><span data-stu-id="f4982-116">If you pass the [ICorDebugCode3::GetReturnValueLiveOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md) method an IL offset to a function call site, it returns one or more native offsets.</span></span> <span data-ttu-id="f4982-117">调试器然后可以在这些函数中的本机偏移量上设置断点。</span><span class="sxs-lookup"><span data-stu-id="f4982-117">The debugger can then set breakpoints on these native offsets in the function.</span></span> <span data-ttu-id="f4982-118">当调试器遇到的其中一个断点时，然后可以将相同的 IL 偏移量传递给此方法以获取返回值进行传递。</span><span class="sxs-lookup"><span data-stu-id="f4982-118">When the debugger hits one of the breakpoints, you can then pass the same IL offset that you passed to this method to get the return value.</span></span> <span data-ttu-id="f4982-119">调试器然后应清除它所设置的所有断点。</span><span class="sxs-lookup"><span data-stu-id="f4982-119">The debugger should then clear all the breakpoints that it set.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="f4982-120">[Icordebugcode3:: Getreturnvalueliveoffset 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md)和`ICorDebugILFrame3::GetReturnValueForILOffset`方法，你可以获取仅适用于引用类型的返回值信息。</span><span class="sxs-lookup"><span data-stu-id="f4982-120">The [ICorDebugCode3::GetReturnValueLiveOffset Method](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md) and `ICorDebugILFrame3::GetReturnValueForILOffset` methods allow you to get return value information for reference types only.</span></span> <span data-ttu-id="f4982-121">从值类型检索返回值信息 (即，派生自的所有类型<xref:System.ValueType>) 不支持。</span><span class="sxs-lookup"><span data-stu-id="f4982-121">Retrieving return value information from value types (that is, all types that derive from <xref:System.ValueType>) is not supported.</span></span>  
  
 <span data-ttu-id="f4982-122">指定的 IL 偏移量`ILOffset`参数应在函数调用站点上，并应在返回的本机偏移量处设置断点处停止调试对象[icordebugcode3:: Getreturnvalueliveoffset](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md)方法为相同的 IL 偏移量。</span><span class="sxs-lookup"><span data-stu-id="f4982-122">The IL offset specified by the `ILOffset` parameter should be at a function call site, and the debuggee should be stopped at a breakpoint set at the native offset returned by the [ICorDebugCode3::GetReturnValueLiveOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md) method for the same IL offset.</span></span> <span data-ttu-id="f4982-123">如果在指定的 IL 偏移量的正确位置不停止调试对象，该 API 将失败。</span><span class="sxs-lookup"><span data-stu-id="f4982-123">If the debuggee is not stopped at the correct location for the specified IL offset, the API will fail.</span></span>  
  
 <span data-ttu-id="f4982-124">如果函数调用不返回值，该 API 将失败。</span><span class="sxs-lookup"><span data-stu-id="f4982-124">If the function call doesn't return a value, the API will fail.</span></span>  
  
 <span data-ttu-id="f4982-125">`ICorDebugILFrame3::GetReturnValueForILOffset`方法是仅适用于基于 x86 和 AMD64 系统。</span><span class="sxs-lookup"><span data-stu-id="f4982-125">The `ICorDebugILFrame3::GetReturnValueForILOffset` method is available only on x86-based and AMD64 systems.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f4982-126">惠?</span><span class="sxs-lookup"><span data-stu-id="f4982-126">Requirements</span></span>  
 <span data-ttu-id="f4982-127">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f4982-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4982-128">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f4982-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f4982-129">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f4982-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f4982-130">**.NET framework 版本：**[!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f4982-130">**.NET Framework Versions:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4982-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="f4982-131">See Also</span></span>  
 [<span data-ttu-id="f4982-132">GetReturnValueLiveOffset 方法</span><span class="sxs-lookup"><span data-stu-id="f4982-132">GetReturnValueLiveOffset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md)  
 [<span data-ttu-id="f4982-133">ICorDebugILFrame3 接口</span><span class="sxs-lookup"><span data-stu-id="f4982-133">ICorDebugILFrame3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-interface.md)
