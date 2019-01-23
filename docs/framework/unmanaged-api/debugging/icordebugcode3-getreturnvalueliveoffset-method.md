---
title: ICorDebugCode3::GetReturnValueLiveOffset 方法
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugCode3.GetReturnValueLiveOffset
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode3::GetReturnValueLiveOffset
helpviewer_keywords:
- ICorDebugCode3::GetReturnValueLiveOffset method [.NET Framework debugging]
- GetReturnValueLiveOffset method [.NET Framework debugging]
ms.assetid: 8c2ff5d8-8c04-4423-b1e1-e1c8764b36d3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: df50a4f5b0bdd0c1e70d7c47fe115f4a28b9bbc2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54526439"
---
# <a name="icordebugcode3getreturnvalueliveoffset-method"></a><span data-ttu-id="39a69-102">ICorDebugCode3::GetReturnValueLiveOffset 方法</span><span class="sxs-lookup"><span data-stu-id="39a69-102">ICorDebugCode3::GetReturnValueLiveOffset Method</span></span>
<span data-ttu-id="39a69-103">对于指定的 IL 偏移量，获取本机偏移量，以便调试器可以从函数获取返回值应放置一个断点。</span><span class="sxs-lookup"><span data-stu-id="39a69-103">For a specified IL offset, gets the native offsets where a breakpoint should be placed so that the debugger can obtain the return value from a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39a69-104">语法</span><span class="sxs-lookup"><span data-stu-id="39a69-104">Syntax</span></span>  
  
```cpp
HRESULT GetReturnValueLiveOffset(  
    [in] ULONG32 ILoffset,  
    [in] ULONG32 bufferSize,   
    [out] ULONG32 *pFetched,   
    [out, size_is(buffersize), length_is(*pFetched)] ULong32 pOffsets[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="39a69-105">参数</span><span class="sxs-lookup"><span data-stu-id="39a69-105">Parameters</span></span>  
 `ILoffset`  
 <span data-ttu-id="39a69-106">IL 偏移量。</span><span class="sxs-lookup"><span data-stu-id="39a69-106">The IL offset.</span></span> <span data-ttu-id="39a69-107">它必须是函数调用站点，否则函数调用将失败。</span><span class="sxs-lookup"><span data-stu-id="39a69-107">It must be a function call site or the function call will fail.</span></span>  
  
 `bufferSize`  
 <span data-ttu-id="39a69-108">可用来存储的字节数`pOffsets`。</span><span class="sxs-lookup"><span data-stu-id="39a69-108">The number of bytes available to store `pOffsets`.</span></span>  
  
 `pFetched`  
 <span data-ttu-id="39a69-109">指向实际返回的偏移量数的指针。</span><span class="sxs-lookup"><span data-stu-id="39a69-109">A pointer to the number of offsets actually returned.</span></span> <span data-ttu-id="39a69-110">通常情况下，其值为 1，但单个 IL 指令可以映射到多个`CALL`程序集指令。</span><span class="sxs-lookup"><span data-stu-id="39a69-110">Usually, its value is 1, but a single IL instruction can map to multiple `CALL` assembly instructions.</span></span>  
  
 `pOffsets`  
 <span data-ttu-id="39a69-111">本机偏移量的数组。</span><span class="sxs-lookup"><span data-stu-id="39a69-111">An array of native offsets.</span></span> <span data-ttu-id="39a69-112">通常情况下，`pOffsets`包含一个偏移量，尽管单个 IL 指令可以映射到多个映射到多个`CALL`程序集指令。</span><span class="sxs-lookup"><span data-stu-id="39a69-112">Typically, `pOffsets` contains a single offset, although a single IL instruction can map to multiple map to multiple `CALL` assembly instructions.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="39a69-113">备注</span><span class="sxs-lookup"><span data-stu-id="39a69-113">Remarks</span></span>  
 <span data-ttu-id="39a69-114">此方法使用连同[ICorDebugILFrame3::GetReturnValueForILOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md)方法以获取返回引用类型的方法的返回值。</span><span class="sxs-lookup"><span data-stu-id="39a69-114">This method is used along with the [ICorDebugILFrame3::GetReturnValueForILOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md) method to get the return value of a method that returns a reference type.</span></span> <span data-ttu-id="39a69-115">传递 IL 偏移量至函数调用站点，此方法返回一个或多个本机偏移量。</span><span class="sxs-lookup"><span data-stu-id="39a69-115">Passing an IL offset to a function call site to this method returns one or more native offsets.</span></span> <span data-ttu-id="39a69-116">调试程序然后可以在函数中的本机偏移量上设置断点。</span><span class="sxs-lookup"><span data-stu-id="39a69-116">The debugger can then set breakpoints on these native offsets in the function.</span></span> <span data-ttu-id="39a69-117">当调试器遇到其中一个断点时，您可以将传递给此方法的相同的 IL 偏移量[ICorDebugILFrame3::GetReturnValueForILOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md)方法以获取返回值。</span><span class="sxs-lookup"><span data-stu-id="39a69-117">When the debugger hits one of the breakpoints, you can then pass the same IL offset that you passed to this method to the [ICorDebugILFrame3::GetReturnValueForILOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md) method to get the return value.</span></span> <span data-ttu-id="39a69-118">然后调试器应该清除此设置的所有断点。</span><span class="sxs-lookup"><span data-stu-id="39a69-118">The debugger should then clear all the breakpoints that it set.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="39a69-119">`ICorDebugCode3::GetReturnValueLiveOffset`并[ICorDebugILFrame3::GetReturnValueForILOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md)方法，你可以获得仅为引用类型的返回值信息。</span><span class="sxs-lookup"><span data-stu-id="39a69-119">The `ICorDebugCode3::GetReturnValueLiveOffset` and [ICorDebugILFrame3::GetReturnValueForILOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md) methods allow you to get return value information for reference types only.</span></span> <span data-ttu-id="39a69-120">从值类型检索返回值信息 (即，派生的所有类型<xref:System.ValueType>) 不受支持。</span><span class="sxs-lookup"><span data-stu-id="39a69-120">Retrieving return value information from value types (that is, all types that derive from <xref:System.ValueType>) is not supported.</span></span>  
  
 <span data-ttu-id="39a69-121">该函数将返回`HRESULT`下表中显示的值。</span><span class="sxs-lookup"><span data-stu-id="39a69-121">The function returns the `HRESULT` values shown in the following table.</span></span>  
  
|<span data-ttu-id="39a69-122">`HRESULT` 值</span><span class="sxs-lookup"><span data-stu-id="39a69-122">`HRESULT` value</span></span>|<span data-ttu-id="39a69-123">描述</span><span class="sxs-lookup"><span data-stu-id="39a69-123">Description</span></span>|  
|---------------------|-----------------|  
|`S_OK`|<span data-ttu-id="39a69-124">成功。</span><span class="sxs-lookup"><span data-stu-id="39a69-124">Success.</span></span>|  
|`CORDBG_E_INVALID_OPCODE`|<span data-ttu-id="39a69-125">给定的 IL 偏移量的站点不是调用命令，或该函数将返回`void`。</span><span class="sxs-lookup"><span data-stu-id="39a69-125">The given IL offset site is not a call instruction, or the function returns `void`.</span></span>|  
|`CORDBG_E_UNSUPPORTED`|<span data-ttu-id="39a69-126">给定的 IL 偏移量为适当的调用，但返回类型是用于获取返回值不受支持。</span><span class="sxs-lookup"><span data-stu-id="39a69-126">The given IL offset is a proper call, but the return type is unsupported for getting a return value.</span></span>|  
  
 <span data-ttu-id="39a69-127">`ICorDebugCode3::GetReturnValueLiveOffset`方法是仅适用于基于 x86 和 AMD64 系统。</span><span class="sxs-lookup"><span data-stu-id="39a69-127">The `ICorDebugCode3::GetReturnValueLiveOffset` method is available only on x86-based and AMD64 systems.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39a69-128">要求</span><span class="sxs-lookup"><span data-stu-id="39a69-128">Requirements</span></span>  
 <span data-ttu-id="39a69-129">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="39a69-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="39a69-130">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="39a69-130">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="39a69-131">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="39a69-131">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="39a69-132">**.NET Framework 版本：**[!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="39a69-132">**.NET Framework Versions:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39a69-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="39a69-133">See also</span></span>
- [<span data-ttu-id="39a69-134">GetReturnValueForILOffset 方法</span><span class="sxs-lookup"><span data-stu-id="39a69-134">GetReturnValueForILOffset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md)
- [<span data-ttu-id="39a69-135">ICorDebugCode3 接口</span><span class="sxs-lookup"><span data-stu-id="39a69-135">ICorDebugCode3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)
