---
title: ICorDebugCode 接口
ms.date: 03/30/2017
api_name:
- ICorDebugCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode
helpviewer_keywords:
- ICorDebugCode interface [.NET Framework debugging]
ms.assetid: 7bd14fb6-8b54-4484-a891-e3c21859c019
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9ca47eb5508907297a78dba1ab2b0a6d2b8ece0d
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2019
ms.locfileid: "56976923"
---
# <a name="icordebugcode-interface"></a><span data-ttu-id="84580-102">ICorDebugCode 接口</span><span class="sxs-lookup"><span data-stu-id="84580-102">ICorDebugCode Interface</span></span>

<span data-ttu-id="84580-103">表示 Microsoft 中间语言 (MSIL) 代码段或本机代码段。</span><span class="sxs-lookup"><span data-stu-id="84580-103">Represents a segment of either Microsoft intermediate language (MSIL) code or native code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="84580-104">方法</span><span class="sxs-lookup"><span data-stu-id="84580-104">Methods</span></span>  
  
|<span data-ttu-id="84580-105">方法</span><span class="sxs-lookup"><span data-stu-id="84580-105">Method</span></span>|<span data-ttu-id="84580-106">描述</span><span class="sxs-lookup"><span data-stu-id="84580-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="84580-107">CreateBreakpoint 方法</span><span class="sxs-lookup"><span data-stu-id="84580-107">CreateBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-createbreakpoint-method.md)|<span data-ttu-id="84580-108">指定的偏移量位置处创建断点。</span><span class="sxs-lookup"><span data-stu-id="84580-108">Creates a breakpoint at the specified offset.</span></span>|  
|[<span data-ttu-id="84580-109">GetAddress 方法</span><span class="sxs-lookup"><span data-stu-id="84580-109">GetAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getaddress-method.md)|<span data-ttu-id="84580-110">获取代码段的相对虚拟地址 (RVA) 这`ICorDebugCode`表示。</span><span class="sxs-lookup"><span data-stu-id="84580-110">Gets the relative virtual address (RVA) of the code segment that this `ICorDebugCode` represents.</span></span>|  
|[<span data-ttu-id="84580-111">GetCode 方法</span><span class="sxs-lookup"><span data-stu-id="84580-111">GetCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getcode-method.md)|<span data-ttu-id="84580-112">获取指定的函数的反汇编格式的所有代码。</span><span class="sxs-lookup"><span data-stu-id="84580-112">Gets all the code for the specified function, formatted for disassembly.</span></span> <span data-ttu-id="84580-113">此方法已弃用;使用[ICorDebugCode2::GetCodeChunks](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md)相反。</span><span class="sxs-lookup"><span data-stu-id="84580-113">This method has been deprecated; use [ICorDebugCode2::GetCodeChunks](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md) instead.</span></span>|  
|[<span data-ttu-id="84580-114">GetEnCRemapSequencePoints 方法</span><span class="sxs-lookup"><span data-stu-id="84580-114">GetEnCRemapSequencePoints Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getencremapsequencepoints-method.md)|<span data-ttu-id="84580-115">未实现。</span><span class="sxs-lookup"><span data-stu-id="84580-115">Not implemented.</span></span>|  
|[<span data-ttu-id="84580-116">GetFunction 方法</span><span class="sxs-lookup"><span data-stu-id="84580-116">GetFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getfunction-method.md)|<span data-ttu-id="84580-117">获取与此相关联"ICorDebugFunction" `ICorDebugCode`。</span><span class="sxs-lookup"><span data-stu-id="84580-117">Gets the "ICorDebugFunction" associated with this `ICorDebugCode`.</span></span>|  
|[<span data-ttu-id="84580-118">GetILToNativeMapping 方法</span><span class="sxs-lookup"><span data-stu-id="84580-118">GetILToNativeMapping Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getiltonativemapping-method.md)|<span data-ttu-id="84580-119">获取表示从 MSIL 偏移量到本机偏移量的映射的"COR_DEBUG_IL_TO_NATIVE_MAP"实例的数组。</span><span class="sxs-lookup"><span data-stu-id="84580-119">Gets an array of "COR_DEBUG_IL_TO_NATIVE_MAP" instances that represent mappings from MSIL offsets to native offsets.</span></span>|  
|[<span data-ttu-id="84580-120">GetSize 方法</span><span class="sxs-lookup"><span data-stu-id="84580-120">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getsize-method.md)|<span data-ttu-id="84580-121">获取用字节表示，这表示的二进制代码大小， `ICorDebugCode`。</span><span class="sxs-lookup"><span data-stu-id="84580-121">Gets the size, in bytes, of the binary code represented by this `ICorDebugCode`.</span></span>|  
|[<span data-ttu-id="84580-122">GetVersionNumber 方法</span><span class="sxs-lookup"><span data-stu-id="84580-122">GetVersionNumber Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getversionnumber-method.md)|<span data-ttu-id="84580-123">获取标识的代码版本的基于 1 的数，此`ICorDebugCode`表示。</span><span class="sxs-lookup"><span data-stu-id="84580-123">Gets the one-based number that identifies the version of the code that this `ICorDebugCode` represents.</span></span>|  
|[<span data-ttu-id="84580-124">IsIL 方法</span><span class="sxs-lookup"><span data-stu-id="84580-124">IsIL Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-isil-method.md)|<span data-ttu-id="84580-125">获取一个值，该值指示是否此`ICorDebugCode`在 MSIL 中编译。</span><span class="sxs-lookup"><span data-stu-id="84580-125">Gets a value that indicates whether this `ICorDebugCode` is compiled in MSIL.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="84580-126">备注</span><span class="sxs-lookup"><span data-stu-id="84580-126">Remarks</span></span>  
 <span data-ttu-id="84580-127">`ICorDebugCode` 可以表示 MSIL 或本机代码。</span><span class="sxs-lookup"><span data-stu-id="84580-127">`ICorDebugCode` can represent either MSIL or native code.</span></span> <span data-ttu-id="84580-128">表示 MSIL 代码的"ICorDebugFunction"对象可以有零个或一个`ICorDebugCode`与它关联的对象。</span><span class="sxs-lookup"><span data-stu-id="84580-128">An "ICorDebugFunction" object that represents MSIL code can have either zero or one `ICorDebugCode` objects associated with it.</span></span> <span data-ttu-id="84580-129">一个表示本机代码的"ICorDebugFunction"对象可以具有任意数量的`ICorDebugCode`与它关联的对象。</span><span class="sxs-lookup"><span data-stu-id="84580-129">An "ICorDebugFunction" object that represents native code can have any number of `ICorDebugCode` objects associated with it.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="84580-130">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="84580-130">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84580-131">要求</span><span class="sxs-lookup"><span data-stu-id="84580-131">Requirements</span></span>  
 <span data-ttu-id="84580-132">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="84580-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84580-133">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="84580-133">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="84580-134">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="84580-134">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="84580-135">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84580-135">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84580-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="84580-136">See also</span></span>

- [<span data-ttu-id="84580-137">ICorDebugCode3 接口</span><span class="sxs-lookup"><span data-stu-id="84580-137">ICorDebugCode3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)
- [<span data-ttu-id="84580-138">调试接口</span><span class="sxs-lookup"><span data-stu-id="84580-138">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
