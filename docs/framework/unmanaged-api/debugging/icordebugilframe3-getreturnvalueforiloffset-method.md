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
ms.openlocfilehash: 7ac90473a0bf15173683c45abc8e4a840ea7e733
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59088296"
---
# <a name="icordebugilframe3getreturnvalueforiloffset-method"></a><span data-ttu-id="bfeb8-102">ICorDebugILFrame3::GetReturnValueForILOffset 方法</span><span class="sxs-lookup"><span data-stu-id="bfeb8-102">ICorDebugILFrame3::GetReturnValueForILOffset Method</span></span>
<span data-ttu-id="bfeb8-103">获取封装函数的返回值的"ICorDebugValue"对象。</span><span class="sxs-lookup"><span data-stu-id="bfeb8-103">Gets an "ICorDebugValue" object that encapsulates the return value of a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bfeb8-104">语法</span><span class="sxs-lookup"><span data-stu-id="bfeb8-104">Syntax</span></span>  
  
```cpp
HRESULT GetReturnValueForILOffset(  
    ULONG32 ILoffset,   
    [out] ICorDebugValue **ppReturnValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bfeb8-105">参数</span><span class="sxs-lookup"><span data-stu-id="bfeb8-105">Parameters</span></span>  
 `ILOffset`  
 <span data-ttu-id="bfeb8-106">IL 偏移量。</span><span class="sxs-lookup"><span data-stu-id="bfeb8-106">The IL offset.</span></span> <span data-ttu-id="bfeb8-107">请参见“备注”部分。</span><span class="sxs-lookup"><span data-stu-id="bfeb8-107">See the Remarks section.</span></span>  
  
 `ppReturnValue`  
 <span data-ttu-id="bfeb8-108">指向提供有关返回值的函数调用信息"ICorDebugValue"接口对象的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="bfeb8-108">A pointer to the address of an "ICorDebugValue" interface object that provides information about the return value of a function call.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bfeb8-109">备注</span><span class="sxs-lookup"><span data-stu-id="bfeb8-109">Remarks</span></span>  
 <span data-ttu-id="bfeb8-110">此方法使用连同[ICorDebugCode3::GetReturnValueLiveOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md)方法以获取一种方法的返回值。</span><span class="sxs-lookup"><span data-stu-id="bfeb8-110">This method is used along with the [ICorDebugCode3::GetReturnValueLiveOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md) method to get the return value of a method.</span></span> <span data-ttu-id="bfeb8-111">它是在其返回值将被忽略，如以下两个代码示例所示的方法的情况下特别有用。</span><span class="sxs-lookup"><span data-stu-id="bfeb8-111">It is particularly useful in the case of methods whose return values are ignored, as in the following two code examples.</span></span> <span data-ttu-id="bfeb8-112">第一个示例调用<xref:System.Int32.TryParse%2A?displayProperty=nameWithType>方法，但忽略方法的返回值。</span><span class="sxs-lookup"><span data-stu-id="bfeb8-112">The first example calls the <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> method, but ignores the method's return value.</span></span>  
  
 [!code-csharp[Unmanaged.Debugging.MRV#1](../../../../samples/snippets/csharp/VS_Snippets_CLR/unmanaged.debugging.mrv/cs/mrv1.cs#1)]
 [!code-vb[Unmanaged.Debugging.MRV#1](../../../../samples/snippets/visualbasic/VS_Snippets_CLR/unmanaged.debugging.mrv/vb/mrv1.vb#1)]  
  
 <span data-ttu-id="bfeb8-113">第二个示例说明了在调试更常见的问题。</span><span class="sxs-lookup"><span data-stu-id="bfeb8-113">The second example illustrates a much more common problem in debugging.</span></span> <span data-ttu-id="bfeb8-114">由于一种方法用作方法调用中的自变量，因此，仅当调试器单步通过调用的方法，才可访问其返回值。</span><span class="sxs-lookup"><span data-stu-id="bfeb8-114">Because a method is used as an argument in a method call, its return value is accessible only when the debugger steps through the called method.</span></span> <span data-ttu-id="bfeb8-115">在许多情况下，尤其是在调用的方法定义中的外部库时，不能。</span><span class="sxs-lookup"><span data-stu-id="bfeb8-115">In many cases, particularly when the called method is defined in an external library, that is not possible.</span></span>  
  
 [!code-csharp[Unmanaged.Debugging.MRV#2](../../../../samples/snippets/csharp/VS_Snippets_CLR/unmanaged.debugging.mrv/cs/mrv2.cs#2)]
 [!code-vb[Unmanaged.Debugging.MRV#2](../../../../samples/snippets/visualbasic/VS_Snippets_CLR/unmanaged.debugging.mrv/vb/mrv2.vb#2)]  
  
 <span data-ttu-id="bfeb8-116">如果传递[ICorDebugCode3::GetReturnValueLiveOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md)一个 IL 偏移量至函数调用站点的方法，它将返回一个或多个本机偏移量。</span><span class="sxs-lookup"><span data-stu-id="bfeb8-116">If you pass the [ICorDebugCode3::GetReturnValueLiveOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md) method an IL offset to a function call site, it returns one or more native offsets.</span></span> <span data-ttu-id="bfeb8-117">调试程序然后可以在函数中的本机偏移量上设置断点。</span><span class="sxs-lookup"><span data-stu-id="bfeb8-117">The debugger can then set breakpoints on these native offsets in the function.</span></span> <span data-ttu-id="bfeb8-118">当调试器遇到其中一个断点时，然后可以将相同的 IL 偏移量传递给此方法以获取返回值进行传递。</span><span class="sxs-lookup"><span data-stu-id="bfeb8-118">When the debugger hits one of the breakpoints, you can then pass the same IL offset that you passed to this method to get the return value.</span></span> <span data-ttu-id="bfeb8-119">然后调试器应该清除此设置的所有断点。</span><span class="sxs-lookup"><span data-stu-id="bfeb8-119">The debugger should then clear all the breakpoints that it set.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="bfeb8-120">[ICorDebugCode3::GetReturnValueLiveOffset Method](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md)和`ICorDebugILFrame3::GetReturnValueForILOffset`方法，你可以获得仅为引用类型的返回值信息。</span><span class="sxs-lookup"><span data-stu-id="bfeb8-120">The [ICorDebugCode3::GetReturnValueLiveOffset Method](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md) and `ICorDebugILFrame3::GetReturnValueForILOffset` methods allow you to get return value information for reference types only.</span></span> <span data-ttu-id="bfeb8-121">从值类型检索返回值信息 (即，派生的所有类型<xref:System.ValueType>) 不受支持。</span><span class="sxs-lookup"><span data-stu-id="bfeb8-121">Retrieving return value information from value types (that is, all types that derive from <xref:System.ValueType>) is not supported.</span></span>  
  
 <span data-ttu-id="bfeb8-122">指定的 IL 偏移量`ILOffset`参数应在函数调用站点，并应在返回的本机偏移量处设置断点处停止调试对象[ICorDebugCode3::GetReturnValueLiveOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md)方法为相同的 IL 偏移量。</span><span class="sxs-lookup"><span data-stu-id="bfeb8-122">The IL offset specified by the `ILOffset` parameter should be at a function call site, and the debuggee should be stopped at a breakpoint set at the native offset returned by the [ICorDebugCode3::GetReturnValueLiveOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md) method for the same IL offset.</span></span> <span data-ttu-id="bfeb8-123">如果未在指定的 IL 偏移量的正确位置停止调试对象，该 API 将失败。</span><span class="sxs-lookup"><span data-stu-id="bfeb8-123">If the debuggee is not stopped at the correct location for the specified IL offset, the API will fail.</span></span>  
  
 <span data-ttu-id="bfeb8-124">如果函数调用不会返回一个值，该 API 将失败。</span><span class="sxs-lookup"><span data-stu-id="bfeb8-124">If the function call doesn't return a value, the API will fail.</span></span>  
  
 <span data-ttu-id="bfeb8-125">`ICorDebugILFrame3::GetReturnValueForILOffset`方法是仅适用于基于 x86 和 AMD64 系统。</span><span class="sxs-lookup"><span data-stu-id="bfeb8-125">The `ICorDebugILFrame3::GetReturnValueForILOffset` method is available only on x86-based and AMD64 systems.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bfeb8-126">要求</span><span class="sxs-lookup"><span data-stu-id="bfeb8-126">Requirements</span></span>  
 <span data-ttu-id="bfeb8-127">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="bfeb8-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bfeb8-128">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bfeb8-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bfeb8-129">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bfeb8-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bfeb8-130">**.NET Framework 版本：**[!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bfeb8-130">**.NET Framework Versions:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfeb8-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="bfeb8-131">See also</span></span>

- [<span data-ttu-id="bfeb8-132">GetReturnValueLiveOffset 方法</span><span class="sxs-lookup"><span data-stu-id="bfeb8-132">GetReturnValueLiveOffset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md)
- [<span data-ttu-id="bfeb8-133">ICorDebugILFrame3 接口</span><span class="sxs-lookup"><span data-stu-id="bfeb8-133">ICorDebugILFrame3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-interface.md)
