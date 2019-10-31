---
title: 调试结构
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged structures [.NET Framework], debugging
- debugging structures [.NET Framework]
- structures [.NET Framework debugging]
ms.assetid: 173ba2c2-ab34-49ae-b6a8-e5c49882bf05
ms.openlocfilehash: 05a321d5025f03d6a0378b462178bf06c0291f48
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123024"
---
# <a name="debugging-structures"></a><span data-ttu-id="7ac4c-102">调试结构</span><span class="sxs-lookup"><span data-stu-id="7ac4c-102">Debugging Structures</span></span>

<span data-ttu-id="7ac4c-103">本节描述调试 API 使用的非托管结构。</span><span class="sxs-lookup"><span data-stu-id="7ac4c-103">This section describes the unmanaged structures that the debugging API uses.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="7ac4c-104">本节内容</span><span class="sxs-lookup"><span data-stu-id="7ac4c-104">In This Section</span></span>
 <span data-ttu-id="7ac4c-105">[CLRDATA_ADDRESS_RANGE 结构](../../../../docs/framework/unmanaged-api/debugging/clrdata-address-range-structure.md)定义地址范围。</span><span class="sxs-lookup"><span data-stu-id="7ac4c-105">[CLRDATA_ADDRESS_RANGE Structure](../../../../docs/framework/unmanaged-api/debugging/clrdata-address-range-structure.md) Defines an address range.</span></span>

 <span data-ttu-id="7ac4c-106">[CLRDATA_IL_ADDRESS_MAP 结构](../../../../docs/framework/unmanaged-api/debugging/clrdata-il-address-map-structure.md)定义用于寻址映射的 IL</span><span class="sxs-lookup"><span data-stu-id="7ac4c-106">[CLRDATA_IL_ADDRESS_MAP Structure](../../../../docs/framework/unmanaged-api/debugging/clrdata-il-address-map-structure.md) Defines an IL to address mapping</span></span>

 <span data-ttu-id="7ac4c-107">[CLR_DEBUGGING_VERSION 结构](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-version-structure.md)出于调试目的定义公共语言运行时（CLR）的产品版本。</span><span class="sxs-lookup"><span data-stu-id="7ac4c-107">[CLR_DEBUGGING_VERSION Structure](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-version-structure.md) Defines the product version of the common language runtime (CLR) for debugging purposes.</span></span>

 <span data-ttu-id="7ac4c-108">[CodeChunkInfo 结构](../../../../docs/framework/unmanaged-api/debugging/codechunkinfo-structure.md)表示内存中的单个代码块。</span><span class="sxs-lookup"><span data-stu-id="7ac4c-108">[CodeChunkInfo Structure](../../../../docs/framework/unmanaged-api/debugging/codechunkinfo-structure.md) Represents a single chunk of code in memory.</span></span>

 <span data-ttu-id="7ac4c-109">[COR_ACTIVE_FUNCTION](cor-active-function-structure.md)包含有关线程帧中当前处于活动状态的函数的信息。</span><span class="sxs-lookup"><span data-stu-id="7ac4c-109">[COR_ACTIVE_FUNCTION](cor-active-function-structure.md) Contains information about the functions that are currently active in a thread's frames.</span></span>

 <span data-ttu-id="7ac4c-110">[COR_ARRAY_LAYOUT 结构](../../../../docs/framework/unmanaged-api/debugging/cor-array-layout-structure.md)提供有关内存中数组对象的布局的信息。</span><span class="sxs-lookup"><span data-stu-id="7ac4c-110">[COR_ARRAY_LAYOUT Structure](../../../../docs/framework/unmanaged-api/debugging/cor-array-layout-structure.md) Provides information about the layout of an array object in memory.</span></span>

 <span data-ttu-id="7ac4c-111">[COR_DEBUG_IL_TO_NATIVE_MAP](cor-debug-il-to-native-map-structure.md)包含用于将 Microsoft 中间语言（MSIL）代码映射到本机代码的偏移量。</span><span class="sxs-lookup"><span data-stu-id="7ac4c-111">[COR_DEBUG_IL_TO_NATIVE_MAP](cor-debug-il-to-native-map-structure.md) Contains the offsets that are used to map Microsoft intermediate language (MSIL) code to native code.</span></span>

 <span data-ttu-id="7ac4c-112">[COR_DEBUG_STEP_RANGE](cor-debug-step-range-structure.md)包含一系列代码的偏移信息。</span><span class="sxs-lookup"><span data-stu-id="7ac4c-112">[COR_DEBUG_STEP_RANGE](cor-debug-step-range-structure.md) Contains the offset information for a range of code.</span></span>

 <span data-ttu-id="7ac4c-113">[COR_FIELD 结构](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md)提供有关对象中的字段的信息。</span><span class="sxs-lookup"><span data-stu-id="7ac4c-113">[COR_FIELD Structure](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) Provides information about a field in an object.</span></span>

 <span data-ttu-id="7ac4c-114">[COR_GC_REFERENCE 结构](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md)包含有关要进行垃圾回收的对象的信息。</span><span class="sxs-lookup"><span data-stu-id="7ac4c-114">[COR_GC_REFERENCE Structure](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) Contains information about an object that is to be garbage-collected.</span></span>

 <span data-ttu-id="7ac4c-115">[COR_HEAPINFO 结构](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md)提供有关垃圾回收堆的常规信息，包括是否可枚举。</span><span class="sxs-lookup"><span data-stu-id="7ac4c-115">[COR_HEAPINFO Structure](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) Provides general information about the garbage collection heap, including whether it is enumerable.</span></span>

 <span data-ttu-id="7ac4c-116">[COR_HEAPOBJECT 结构](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md)提供有关托管堆上的对象的信息。</span><span class="sxs-lookup"><span data-stu-id="7ac4c-116">[COR_HEAPOBJECT Structure](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) Provides information about an object on the managed heap.</span></span>

 <span data-ttu-id="7ac4c-117">[COR_IL_MAP](cor-il-map-structure.md)指定函数的相对偏移量中的更改。</span><span class="sxs-lookup"><span data-stu-id="7ac4c-117">[COR_IL_MAP](cor-il-map-structure.md) Specifies changes in the relative offset of a function.</span></span>

 <span data-ttu-id="7ac4c-118">[COR_SEGMENT 结构](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md)包含有关托管堆中的内存区域的信息。</span><span class="sxs-lookup"><span data-stu-id="7ac4c-118">[COR_SEGMENT Structure](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md) Contains information about a region of memory in the managed heap.</span></span>

 <span data-ttu-id="7ac4c-119">[COR_TYPEID 结构](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md)包含一个类型标识符。</span><span class="sxs-lookup"><span data-stu-id="7ac4c-119">[COR_TYPEID Structure](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) Contains a type identifier.</span></span>

 <span data-ttu-id="7ac4c-120">[COR_TYPE_LAYOUT 结构](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md)提供有关内存中对象的布局的信息。</span><span class="sxs-lookup"><span data-stu-id="7ac4c-120">[COR_TYPE_LAYOUT Structure](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md) Provides information about the layout of an object in memory.</span></span>

 <span data-ttu-id="7ac4c-121">[COR_VERSION](cor-version-structure.md)存储公共语言运行时的由四个部分组成的标准版本号。</span><span class="sxs-lookup"><span data-stu-id="7ac4c-121">[COR_VERSION](cor-version-structure.md) Stores the standard four-part version number of the common language runtime.</span></span>

 <span data-ttu-id="7ac4c-122">[CorDebugBlockingObject 结构](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md)定义一个对象，该对象阻止线程，以及线程被阻止的原因。</span><span class="sxs-lookup"><span data-stu-id="7ac4c-122">[CorDebugBlockingObject Structure](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) Defines an object that is blocking a thread and the reason why the thread is blocked.</span></span>

 <span data-ttu-id="7ac4c-123">[CorDebugEHClause 结构](../../../../docs/framework/unmanaged-api/debugging/cordebugehclause-structure.md)表示给定中间语言（IL）部分的异常处理（EH）子句。</span><span class="sxs-lookup"><span data-stu-id="7ac4c-123">[CorDebugEHClause Structure](../../../../docs/framework/unmanaged-api/debugging/cordebugehclause-structure.md) Represents an exception handling (EH) clause for a given piece of intermediate language (IL).</span></span>

 <span data-ttu-id="7ac4c-124">[CorDebugExceptionObjectStackFrame 结构](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md)表示异常对象中的堆栈帧信息。</span><span class="sxs-lookup"><span data-stu-id="7ac4c-124">[CorDebugExceptionObjectStackFrame Structure](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) Represents stack frame information from an exception object.</span></span>

 <span data-ttu-id="7ac4c-125">[CorDebugGuidToTypeMapping 结构](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md)将 Windows 运行时 GUID 映射到其对应的[ICorDebugType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-interface.md)对象。</span><span class="sxs-lookup"><span data-stu-id="7ac4c-125">[CorDebugGuidToTypeMapping Structure](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) Maps a Windows Runtime GUID to its corresponding [ICorDebugType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-interface.md) object.</span></span>

 <span data-ttu-id="7ac4c-126">[DacpGetModuleAddress 结构](../../../../docs/framework/unmanaged-api/debugging/dacpgetmoduleaddress-structure.md)定义模块地址请求的容器。</span><span class="sxs-lookup"><span data-stu-id="7ac4c-126">[DacpGetModuleAddress Structure](../../../../docs/framework/unmanaged-api/debugging/dacpgetmoduleaddress-structure.md) Defines the container for a module address request.</span></span>

 <span data-ttu-id="7ac4c-127">[DacpMethodDescData 结构](../../../../docs/framework/unmanaged-api/debugging/dacpmethoddescdata-structure.md)定义方法的运行时信息的传输缓冲区。</span><span class="sxs-lookup"><span data-stu-id="7ac4c-127">[DacpMethodDescData Structure](../../../../docs/framework/unmanaged-api/debugging/dacpmethoddescdata-structure.md) Defines a transport buffer for a method's runtime information.</span></span>

 <span data-ttu-id="7ac4c-128">[DacpModuleData 结构](../../../../docs/framework/unmanaged-api/debugging/dacpmoduledata-structure.md)定义模块的运行时信息的传输缓冲区。</span><span class="sxs-lookup"><span data-stu-id="7ac4c-128">[DacpModuleData Structure](../../../../docs/framework/unmanaged-api/debugging/dacpmoduledata-structure.md) Defines a transport buffer for a module's runtime information.</span></span>

 <span data-ttu-id="7ac4c-129">[DacpReJitData 结构](../../../../docs/framework/unmanaged-api/debugging/dacprejitdata-structure.md)定义有关给定探查器检测到的方法的基本信息。</span><span class="sxs-lookup"><span data-stu-id="7ac4c-129">[DacpReJitData Structure](../../../../docs/framework/unmanaged-api/debugging/dacprejitdata-structure.md) Defines the basic information about a given profiler-instrumented method.</span></span>

 <span data-ttu-id="7ac4c-130">[StackTrace_SimpleContext 结构](../../../../docs/framework/unmanaged-api/debugging/stacktrace-simplecontext-structure.md)提供一个可用于代替完整 `CONTEXT` 结构的简单上下文。</span><span class="sxs-lookup"><span data-stu-id="7ac4c-130">[StackTrace_SimpleContext Structure](../../../../docs/framework/unmanaged-api/debugging/stacktrace-simplecontext-structure.md) Provides a simple context that can be used in place of a full `CONTEXT` structure.</span></span>

## <a name="related-sections"></a><span data-ttu-id="7ac4c-131">相关章节</span><span class="sxs-lookup"><span data-stu-id="7ac4c-131">Related Sections</span></span>

 [<span data-ttu-id="7ac4c-132">调试组件类</span><span class="sxs-lookup"><span data-stu-id="7ac4c-132">Debugging Coclasses</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-coclasses.md)

 [<span data-ttu-id="7ac4c-133">调试接口</span><span class="sxs-lookup"><span data-stu-id="7ac4c-133">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

 [<span data-ttu-id="7ac4c-134">调试全局静态函数</span><span class="sxs-lookup"><span data-stu-id="7ac4c-134">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)

 [<span data-ttu-id="7ac4c-135">调试枚举</span><span class="sxs-lookup"><span data-stu-id="7ac4c-135">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)

 [<span data-ttu-id="7ac4c-136">调试</span><span class="sxs-lookup"><span data-stu-id="7ac4c-136">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
