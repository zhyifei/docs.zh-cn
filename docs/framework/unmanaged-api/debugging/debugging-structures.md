---
title: "调试结构"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- unmanaged structures [.NET Framework], debugging
- debugging structures [.NET Framework]
- structures [.NET Framework debugging]
ms.assetid: 173ba2c2-ab34-49ae-b6a8-e5c49882bf05
caps.latest.revision: "22"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0293a20f5f735dd38b1d167ebc5057f645fa011a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="debugging-structures"></a><span data-ttu-id="4cbe7-102">调试结构</span><span class="sxs-lookup"><span data-stu-id="4cbe7-102">Debugging Structures</span></span>
<span data-ttu-id="4cbe7-103">本节描述调试 API 使用的非托管结构。</span><span class="sxs-lookup"><span data-stu-id="4cbe7-103">This section describes the unmanaged structures that the debugging API uses.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4cbe7-104">本节内容</span><span class="sxs-lookup"><span data-stu-id="4cbe7-104">In This Section</span></span>  
 [<span data-ttu-id="4cbe7-105">CLR_DEBUGGING_VERSION 结构</span><span class="sxs-lookup"><span data-stu-id="4cbe7-105">CLR_DEBUGGING_VERSION Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-version-structure.md)  
 <span data-ttu-id="4cbe7-106">出于调试目的，定义公共语言运行时 (CLR) 的产品版本。</span><span class="sxs-lookup"><span data-stu-id="4cbe7-106">Defines the product version of the common language runtime (CLR) for debugging purposes.</span></span>  
  
 [<span data-ttu-id="4cbe7-107">CodeChunkInfo 结构 1</span><span class="sxs-lookup"><span data-stu-id="4cbe7-107">CodeChunkInfo Structure1</span></span>](../../../../docs/framework/unmanaged-api/debugging/codechunkinfo-structure.md)  
 <span data-ttu-id="4cbe7-108">表示内存中的单一代码块。</span><span class="sxs-lookup"><span data-stu-id="4cbe7-108">Represents a single chunk of code in memory.</span></span>  
  
 [<span data-ttu-id="4cbe7-109">CorDebugBlockingObject 结构</span><span class="sxs-lookup"><span data-stu-id="4cbe7-109">CorDebugBlockingObject Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md)  
 <span data-ttu-id="4cbe7-110">定义一个阻塞线程的对象以及阻塞线程的原因。</span><span class="sxs-lookup"><span data-stu-id="4cbe7-110">Defines an object that is blocking a thread and the reason why the thread is blocked.</span></span>  
  
 [<span data-ttu-id="4cbe7-111">CorDebugEHClause 结构</span><span class="sxs-lookup"><span data-stu-id="4cbe7-111">CorDebugEHClause Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugehclause-structure.md)  
 <span data-ttu-id="4cbe7-112">表示给定的一段中间语言 (IL) 的异常处理 (EH) 子句。</span><span class="sxs-lookup"><span data-stu-id="4cbe7-112">Represents an exception handling (EH) clause for a given piece of intermediate language (IL).</span></span>  
  
 [<span data-ttu-id="4cbe7-113">CorDebugExceptionObjectStackFrame 结构</span><span class="sxs-lookup"><span data-stu-id="4cbe7-113">CorDebugExceptionObjectStackFrame Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md)  
 <span data-ttu-id="4cbe7-114">表示异常对象中的堆栈帧信息。</span><span class="sxs-lookup"><span data-stu-id="4cbe7-114">Represents stack frame information from an exception object.</span></span>  
  
 [<span data-ttu-id="4cbe7-115">CorDebugExceptionObjectStackFrame 结构</span><span class="sxs-lookup"><span data-stu-id="4cbe7-115">CorDebugExceptionObjectStackFrame Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md)  
 <span data-ttu-id="4cbe7-116">地图[!INCLUDE[wrt](../../../../includes/wrt-md.md)]到其对应的 GUID [ICorDebugType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-interface.md)对象。</span><span class="sxs-lookup"><span data-stu-id="4cbe7-116">Maps a [!INCLUDE[wrt](../../../../includes/wrt-md.md)] GUID to its corresponding [ICorDebugType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-interface.md) object.</span></span>  
  
 <span data-ttu-id="4cbe7-117">COR_ACTIVE_FUNCTION</span><span class="sxs-lookup"><span data-stu-id="4cbe7-117">COR_ACTIVE_FUNCTION</span></span>  
 <span data-ttu-id="4cbe7-118">包含有关在线程框架中当前处于活动状态的函数的信息。</span><span class="sxs-lookup"><span data-stu-id="4cbe7-118">Contains information about the functions that are currently active in a thread's frames.</span></span>  
  
 [<span data-ttu-id="4cbe7-119">COR_ARRAY_LAYOUT 结构</span><span class="sxs-lookup"><span data-stu-id="4cbe7-119">COR_ARRAY_LAYOUT Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cor-array-layout-structure.md)  
 <span data-ttu-id="4cbe7-120">提供有关内存中数组对象的布局的信息。</span><span class="sxs-lookup"><span data-stu-id="4cbe7-120">Provides information about the layout of an array object in memory.</span></span>  
  
 <span data-ttu-id="4cbe7-121">COR_DEBUG_IL_TO_NATIVE_MAP</span><span class="sxs-lookup"><span data-stu-id="4cbe7-121">COR_DEBUG_IL_TO_NATIVE_MAP</span></span>  
 <span data-ttu-id="4cbe7-122">包含用于将 Microsoft 中间语言 (MSIL) 代码映射到本机代码的偏移量。</span><span class="sxs-lookup"><span data-stu-id="4cbe7-122">Contains the offsets that are used to map Microsoft intermediate language (MSIL) code to native code.</span></span>  
  
 <span data-ttu-id="4cbe7-123">COR_DEBUG_STEP_RANGE</span><span class="sxs-lookup"><span data-stu-id="4cbe7-123">COR_DEBUG_STEP_RANGE</span></span>  
 <span data-ttu-id="4cbe7-124">包含代码区域的偏离量信息。</span><span class="sxs-lookup"><span data-stu-id="4cbe7-124">Contains the offset information for a range of code.</span></span>  
  
 [<span data-ttu-id="4cbe7-125">COR_FIELD 结构</span><span class="sxs-lookup"><span data-stu-id="4cbe7-125">COR_FIELD Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md)  
 <span data-ttu-id="4cbe7-126">提供有关对象中的某个字段的信息。</span><span class="sxs-lookup"><span data-stu-id="4cbe7-126">Provides information about a field in an object.</span></span>  
  
 [<span data-ttu-id="4cbe7-127">COR_GC_REFERENCE 结构</span><span class="sxs-lookup"><span data-stu-id="4cbe7-127">COR_GC_REFERENCE Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md)  
 <span data-ttu-id="4cbe7-128">包含有关要进行垃圾回收的对象的信息。</span><span class="sxs-lookup"><span data-stu-id="4cbe7-128">Contains information about an object that is to be garbage-collected.</span></span>  
  
 [<span data-ttu-id="4cbe7-129">COR_HEAPINFO 结构</span><span class="sxs-lookup"><span data-stu-id="4cbe7-129">COR_HEAPINFO Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md)  
 <span data-ttu-id="4cbe7-130">提供有关垃圾回收堆的常规信息，包括它是否是可枚举的。</span><span class="sxs-lookup"><span data-stu-id="4cbe7-130">Provides general information about the garbage collection heap, including whether it is enumerable.</span></span>  
  
 [<span data-ttu-id="4cbe7-131">COR_HEAPOBJECT 结构</span><span class="sxs-lookup"><span data-stu-id="4cbe7-131">COR_HEAPOBJECT Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md)  
 <span data-ttu-id="4cbe7-132">提供有关托管堆上的对象的信息。</span><span class="sxs-lookup"><span data-stu-id="4cbe7-132">Provides information about an object on the managed heap.</span></span>  
  
 <span data-ttu-id="4cbe7-133">COR_IL_MAP</span><span class="sxs-lookup"><span data-stu-id="4cbe7-133">COR_IL_MAP</span></span>  
 <span data-ttu-id="4cbe7-134">指定函数的相对偏移量的更改。</span><span class="sxs-lookup"><span data-stu-id="4cbe7-134">Specifies changes in the relative offset of a function.</span></span>  
  
 [<span data-ttu-id="4cbe7-135">COR_SEGMENT 结构</span><span class="sxs-lookup"><span data-stu-id="4cbe7-135">COR_SEGMENT Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md)  
 <span data-ttu-id="4cbe7-136">包含有关托管堆中的内存区域的信息。</span><span class="sxs-lookup"><span data-stu-id="4cbe7-136">Contains information about a region of memory in the managed heap.</span></span>  
  
 [<span data-ttu-id="4cbe7-137">COR_TYPEID 结构</span><span class="sxs-lookup"><span data-stu-id="4cbe7-137">COR_TYPEID Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md)  
 <span data-ttu-id="4cbe7-138">包含类型标识符。</span><span class="sxs-lookup"><span data-stu-id="4cbe7-138">Contains a type identifier.</span></span>  
  
 [<span data-ttu-id="4cbe7-139">COR_TYPE_LAYOUT 结构</span><span class="sxs-lookup"><span data-stu-id="4cbe7-139">COR_TYPE_LAYOUT Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md)  
 <span data-ttu-id="4cbe7-140">提供有关内存中某个对象的布局的信息。</span><span class="sxs-lookup"><span data-stu-id="4cbe7-140">Provides information about the layout of an object in memory.</span></span>  
  
 <span data-ttu-id="4cbe7-141">COR_VERSION</span><span class="sxs-lookup"><span data-stu-id="4cbe7-141">COR_VERSION</span></span>  
 <span data-ttu-id="4cbe7-142">存储由四个部分组成的公共语言运行时标准版本号。</span><span class="sxs-lookup"><span data-stu-id="4cbe7-142">Stores the standard four-part version number of the common language runtime.</span></span>  
  
 [<span data-ttu-id="4cbe7-143">StackTrace_SimpleContext 结构</span><span class="sxs-lookup"><span data-stu-id="4cbe7-143">StackTrace_SimpleContext Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/stacktrace-simplecontext-structure.md)  
 <span data-ttu-id="4cbe7-144">提供可用于代替完整的 `CONTEXT` 结构的简单上下文。</span><span class="sxs-lookup"><span data-stu-id="4cbe7-144">Provides a simple context that can be used in place of a full `CONTEXT` structure.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="4cbe7-145">相关章节</span><span class="sxs-lookup"><span data-stu-id="4cbe7-145">Related Sections</span></span>  
 [<span data-ttu-id="4cbe7-146">调试组件类</span><span class="sxs-lookup"><span data-stu-id="4cbe7-146">Debugging Coclasses</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-coclasses.md)  
  
 [<span data-ttu-id="4cbe7-147">调试接口</span><span class="sxs-lookup"><span data-stu-id="4cbe7-147">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
  
 [<span data-ttu-id="4cbe7-148">调试全局静态函数</span><span class="sxs-lookup"><span data-stu-id="4cbe7-148">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)  
  
 [<span data-ttu-id="4cbe7-149">调试枚举</span><span class="sxs-lookup"><span data-stu-id="4cbe7-149">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
  
 [<span data-ttu-id="4cbe7-150">调试</span><span class="sxs-lookup"><span data-stu-id="4cbe7-150">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
