---
title: ICorDebugILFrame3::GetReturnValueForILOffset 方法
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5832ec095ea0e96327f6a9636193da9c0c8a5dd2
ms.sourcegitcommit: 37616676fde89153f563a485fc6159fc57326fc2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2019
ms.locfileid: "69988267"
---
# <a name="icordebugilframe3getreturnvalueforiloffset-method"></a><span data-ttu-id="c6694-102">ICorDebugILFrame3::GetReturnValueForILOffset 方法</span><span class="sxs-lookup"><span data-stu-id="c6694-102">ICorDebugILFrame3::GetReturnValueForILOffset Method</span></span>
<span data-ttu-id="c6694-103">获取一个 "ICorDebugValue" 对象, 该对象封装函数的返回值。</span><span class="sxs-lookup"><span data-stu-id="c6694-103">Gets an "ICorDebugValue" object that encapsulates the return value of a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6694-104">语法</span><span class="sxs-lookup"><span data-stu-id="c6694-104">Syntax</span></span>  
  
```cpp
HRESULT GetReturnValueForILOffset(  
    ULONG32 ILoffset,   
    [out] ICorDebugValue **ppReturnValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c6694-105">参数</span><span class="sxs-lookup"><span data-stu-id="c6694-105">Parameters</span></span>  
 `ILOffset`  
 <span data-ttu-id="c6694-106">IL 偏移量。</span><span class="sxs-lookup"><span data-stu-id="c6694-106">The IL offset.</span></span> <span data-ttu-id="c6694-107">请参见“备注”部分。</span><span class="sxs-lookup"><span data-stu-id="c6694-107">See the Remarks section.</span></span>  
  
 `ppReturnValue`  
 <span data-ttu-id="c6694-108">一个指向 "ICorDebugValue" 接口对象地址的指针, 该对象提供有关函数调用的返回值的信息。</span><span class="sxs-lookup"><span data-stu-id="c6694-108">A pointer to the address of an "ICorDebugValue" interface object that provides information about the return value of a function call.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c6694-109">备注</span><span class="sxs-lookup"><span data-stu-id="c6694-109">Remarks</span></span>  
 <span data-ttu-id="c6694-110">此方法与[ICorDebugCode3:: GetReturnValueLiveOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md)方法一起使用, 以获取方法的返回值。</span><span class="sxs-lookup"><span data-stu-id="c6694-110">This method is used along with the [ICorDebugCode3::GetReturnValueLiveOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md) method to get the return value of a method.</span></span> <span data-ttu-id="c6694-111">这对于返回值被忽略的方法特别有用, 如以下两个代码示例所示。</span><span class="sxs-lookup"><span data-stu-id="c6694-111">It is particularly useful in the case of methods whose return values are ignored, as in the following two code examples.</span></span> <span data-ttu-id="c6694-112">第一个示例调用<xref:System.Int32.TryParse%2A?displayProperty=nameWithType>方法, 但忽略方法的返回值。</span><span class="sxs-lookup"><span data-stu-id="c6694-112">The first example calls the <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> method, but ignores the method's return value.</span></span>  
  
 [!code-csharp[Unmanaged.Debugging.MRV#1](../../../../samples/snippets/csharp/VS_Snippets_CLR/unmanaged.debugging.mrv/cs/mrv1.cs#1)]
 [!code-vb[Unmanaged.Debugging.MRV#1](../../../../samples/snippets/visualbasic/VS_Snippets_CLR/unmanaged.debugging.mrv/vb/mrv1.vb#1)]  
  
 <span data-ttu-id="c6694-113">第二个示例演示了调试中更常见的问题。</span><span class="sxs-lookup"><span data-stu-id="c6694-113">The second example illustrates a much more common problem in debugging.</span></span> <span data-ttu-id="c6694-114">因为方法在方法调用中用作参数, 所以仅当调试器逐步执行调用的方法时, 才能访问其返回值。</span><span class="sxs-lookup"><span data-stu-id="c6694-114">Because a method is used as an argument in a method call, its return value is accessible only when the debugger steps through the called method.</span></span> <span data-ttu-id="c6694-115">在许多情况下, 尤其是在外部库中定义了所调用的方法时, 这是不可能的。</span><span class="sxs-lookup"><span data-stu-id="c6694-115">In many cases, particularly when the called method is defined in an external library, that is not possible.</span></span>  
  
 [!code-csharp[Unmanaged.Debugging.MRV#2](../../../../samples/snippets/csharp/VS_Snippets_CLR/unmanaged.debugging.mrv/cs/mrv2.cs#2)]
 [!code-vb[Unmanaged.Debugging.MRV#2](../../../../samples/snippets/visualbasic/VS_Snippets_CLR/unmanaged.debugging.mrv/vb/mrv2.vb#2)]  
  
 <span data-ttu-id="c6694-116">如果将[ICorDebugCode3:: GetReturnValueLiveOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md)方法传递给函数调用站点的 IL 偏移量, 它将返回一个或多个本机偏移量。</span><span class="sxs-lookup"><span data-stu-id="c6694-116">If you pass the [ICorDebugCode3::GetReturnValueLiveOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md) method an IL offset to a function call site, it returns one or more native offsets.</span></span> <span data-ttu-id="c6694-117">然后, 调试器可以在函数中的这些本机偏移量上设置断点。</span><span class="sxs-lookup"><span data-stu-id="c6694-117">The debugger can then set breakpoints on these native offsets in the function.</span></span> <span data-ttu-id="c6694-118">当调试器遇到其中一个断点时, 您可以传递您传递给此方法的同一 IL 偏移量来获取返回值。</span><span class="sxs-lookup"><span data-stu-id="c6694-118">When the debugger hits one of the breakpoints, you can then pass the same IL offset that you passed to this method to get the return value.</span></span> <span data-ttu-id="c6694-119">调试器随后应清除它所设置的所有断点。</span><span class="sxs-lookup"><span data-stu-id="c6694-119">The debugger should then clear all the breakpoints that it set.</span></span>  
  
> [!WARNING]
> <span data-ttu-id="c6694-120">[ICorDebugCode3:: GetReturnValueLiveOffset 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md)和`ICorDebugILFrame3::GetReturnValueForILOffset`方法仅允许获取引用类型的返回值信息。</span><span class="sxs-lookup"><span data-stu-id="c6694-120">The [ICorDebugCode3::GetReturnValueLiveOffset Method](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md) and `ICorDebugILFrame3::GetReturnValueForILOffset` methods allow you to get return value information for reference types only.</span></span> <span data-ttu-id="c6694-121">不支持从值类型 (即从<xref:System.ValueType>派生的所有类型) 检索返回值信息。</span><span class="sxs-lookup"><span data-stu-id="c6694-121">Retrieving return value information from value types (that is, all types that derive from <xref:System.ValueType>) is not supported.</span></span>  
  
 <span data-ttu-id="c6694-122">`ILOffset`参数指定的 IL 偏移量应位于函数调用站点上, 并且调试对象应在[ICorDebugCode3:: GetReturnValueLiveOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md)方法为同一 IL 偏移量返回的本机偏移量处停止。</span><span class="sxs-lookup"><span data-stu-id="c6694-122">The IL offset specified by the `ILOffset` parameter should be at a function call site, and the debuggee should be stopped at a breakpoint set at the native offset returned by the [ICorDebugCode3::GetReturnValueLiveOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md) method for the same IL offset.</span></span> <span data-ttu-id="c6694-123">如果在指定的 IL 偏移量的正确位置没有停止调试对象, 则 API 将失败。</span><span class="sxs-lookup"><span data-stu-id="c6694-123">If the debuggee is not stopped at the correct location for the specified IL offset, the API will fail.</span></span>  
  
 <span data-ttu-id="c6694-124">如果函数调用不返回值, 则 API 将失败。</span><span class="sxs-lookup"><span data-stu-id="c6694-124">If the function call doesn't return a value, the API will fail.</span></span>  
  
 <span data-ttu-id="c6694-125">`ICorDebugILFrame3::GetReturnValueForILOffset`方法仅适用于基于 x86 的和 AMD64 系统。</span><span class="sxs-lookup"><span data-stu-id="c6694-125">The `ICorDebugILFrame3::GetReturnValueForILOffset` method is available only on x86-based and AMD64 systems.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6694-126">要求</span><span class="sxs-lookup"><span data-stu-id="c6694-126">Requirements</span></span>  
 <span data-ttu-id="c6694-127">**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c6694-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6694-128">**标头：** Cordebug.idl, Cordebug.idl</span><span class="sxs-lookup"><span data-stu-id="c6694-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c6694-129">**类库**CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c6694-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c6694-130">**.NET Framework 版本：** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6694-130">**.NET Framework Versions:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6694-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="c6694-131">See also</span></span>

- [<span data-ttu-id="c6694-132">GetReturnValueLiveOffset 方法</span><span class="sxs-lookup"><span data-stu-id="c6694-132">GetReturnValueLiveOffset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md)
- [<span data-ttu-id="c6694-133">ICorDebugILFrame3 接口</span><span class="sxs-lookup"><span data-stu-id="c6694-133">ICorDebugILFrame3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-interface.md)
