---
title: "调试枚举"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- debugging enumerations [.NET Framework]
- unmanaged enumerations [.NET Framework], debugging
- enumerations [.NET Framework debugging]
ms.assetid: 3af9f584-f1b4-4154-aeaa-8fce7c9f8b50
caps.latest.revision: "27"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a5e294275da45575a3aed457fb2428c4768e78d8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="debugging-enumerations"></a><span data-ttu-id="95abb-102">调试枚举</span><span class="sxs-lookup"><span data-stu-id="95abb-102">Debugging Enumerations</span></span>
<span data-ttu-id="95abb-103">本节介绍了调试 API 使用的非托管枚举。</span><span class="sxs-lookup"><span data-stu-id="95abb-103">This section describes the unmanaged enumerations that the debugging API uses.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="95abb-104">本节内容</span><span class="sxs-lookup"><span data-stu-id="95abb-104">In This Section</span></span>  
 [<span data-ttu-id="95abb-105">CLR_DEBUGGING_PROCESS_FLAGS 枚举</span><span class="sxs-lookup"><span data-stu-id="95abb-105">CLR_DEBUGGING_PROCESS_FLAGS Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-process-flags-enumeration.md)  
 <span data-ttu-id="95abb-106">提供使用的值[iclrdebugging:: Openvirtualprocess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="95abb-106">Provides values that are used by the [ICLRDebugging::OpenVirtualProcess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) method.</span></span>  
  
 [<span data-ttu-id="95abb-107">CLRDataEnumMemoryFlags 枚举</span><span class="sxs-lookup"><span data-stu-id="95abb-107">CLRDataEnumMemoryFlags Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/clrdataenummemoryflags-enumeration.md)  
 <span data-ttu-id="95abb-108">指示的内存区域对的调用[iclrdataenummemoryregions:: Enummemoryregions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md)应包括方法。</span><span class="sxs-lookup"><span data-stu-id="95abb-108">Indicates which memory regions a call to the [ICLRDataEnumMemoryRegions::EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) method should include.</span></span>  
  
 [<span data-ttu-id="95abb-109">COR_PUB_ENUMPROCESS 枚举</span><span class="sxs-lookup"><span data-stu-id="95abb-109">COR_PUB_ENUMPROCESS Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cor-pub-enumprocess-enumeration.md)  
 <span data-ttu-id="95abb-110">标识要枚举的进程的类型。</span><span class="sxs-lookup"><span data-stu-id="95abb-110">Identifies the type of process to be enumerated.</span></span>  
  
 [<span data-ttu-id="95abb-111">CorDebugBlockingReason 枚举</span><span class="sxs-lookup"><span data-stu-id="95abb-111">CorDebugBlockingReason Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingreason-enumeration.md)  
 <span data-ttu-id="95abb-112">指定线程可能在给定对象上受到阻塞的原因。</span><span class="sxs-lookup"><span data-stu-id="95abb-112">Specifies the reasons why a thread may become blocked on a given object.</span></span>  
  
 <span data-ttu-id="95abb-113">CorDebugChainReason</span><span class="sxs-lookup"><span data-stu-id="95abb-113">CorDebugChainReason</span></span>  
 <span data-ttu-id="95abb-114">指示启动调用链的一个或多个原因。</span><span class="sxs-lookup"><span data-stu-id="95abb-114">Indicates the reason or reasons for the initiation of a call chain.</span></span>  
  
 [<span data-ttu-id="95abb-115">CorDebugCodeInvokeKind 枚举</span><span class="sxs-lookup"><span data-stu-id="95abb-115">CorDebugCodeInvokeKind Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugcodeinvokekind-enumeration.md)  
 <span data-ttu-id="95abb-116">描述导出函数如何调用托管代码。</span><span class="sxs-lookup"><span data-stu-id="95abb-116">Describes how an exported function invokes managed code.</span></span>  
  
 [<span data-ttu-id="95abb-117">CorDebugCodeInvokePurpose 枚举</span><span class="sxs-lookup"><span data-stu-id="95abb-117">CorDebugCodeInvokePurpose Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugcodeinvokepurpose-enumeration.md)  
 <span data-ttu-id="95abb-118">描述为何导出的函数会调用托管代码。</span><span class="sxs-lookup"><span data-stu-id="95abb-118">Describes why an exported function calls managed code.</span></span>  
  
 <span data-ttu-id="95abb-119">CorDebugCreateProcessFlags</span><span class="sxs-lookup"><span data-stu-id="95abb-119">CorDebugCreateProcessFlags</span></span>  
 <span data-ttu-id="95abb-120">提供了其他可以在调用中使用的调试选项[icordebug:: Createprocess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="95abb-120">Provides additional debugging options that can be used in a call to the [ICorDebug::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md) method.</span></span>  
  
 [<span data-ttu-id="95abb-121">CorDebugDebugEventKind 枚举</span><span class="sxs-lookup"><span data-stu-id="95abb-121">CorDebugDebugEventKind Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md)  
 <span data-ttu-id="95abb-122">指示由解码获取其信息的事件类型[解码事件](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="95abb-122">Indicates the type of event whose information is decoded by the [DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) method.</span></span>  
  
 [<span data-ttu-id="95abb-123">CorDebugDecodeEventFlagsWindows 枚举</span><span class="sxs-lookup"><span data-stu-id="95abb-123">CorDebugDecodeEventFlagsWindows Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugdecodeeventflagswindows-enumeration.md)  
 <span data-ttu-id="95abb-124">提供关于 Windows 平台上的调试事件的其他信息。</span><span class="sxs-lookup"><span data-stu-id="95abb-124">Provides additional information about debug events on the Windows platform.</span></span>  
  
 <span data-ttu-id="95abb-125">CorDebugExceptionCallbackType</span><span class="sxs-lookup"><span data-stu-id="95abb-125">CorDebugExceptionCallbackType</span></span>  
 <span data-ttu-id="95abb-126">指示的回调中所做的类型[icordebugmanagedcallback2:: Exception](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-exception-method.md)事件。</span><span class="sxs-lookup"><span data-stu-id="95abb-126">Indicates the type of callback that is made from an [ICorDebugManagedCallback2::Exception](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-exception-method.md) event.</span></span>  
  
 [<span data-ttu-id="95abb-127">CorDebugExceptionFlags 枚举</span><span class="sxs-lookup"><span data-stu-id="95abb-127">CorDebugExceptionFlags Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md)  
 <span data-ttu-id="95abb-128">提供有关异常的附加信息。</span><span class="sxs-lookup"><span data-stu-id="95abb-128">Provides additional information about an exception.</span></span>  
  
 <span data-ttu-id="95abb-129">CorDebugExceptionUnwindCallbackType</span><span class="sxs-lookup"><span data-stu-id="95abb-129">CorDebugExceptionUnwindCallbackType</span></span>  
 <span data-ttu-id="95abb-130">指示在展开阶段正由回调发送信号的事件。</span><span class="sxs-lookup"><span data-stu-id="95abb-130">Indicates the event that is being signaled by the callback during the unwind phase.</span></span>  
  
 [<span data-ttu-id="95abb-131">CorDebugGCType 枚举</span><span class="sxs-lookup"><span data-stu-id="95abb-131">CorDebugGCType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebuggctype-enumeration.md)  
 <span data-ttu-id="95abb-132">指示垃圾回收器是在工作站还是服务器上运行。</span><span class="sxs-lookup"><span data-stu-id="95abb-132">Indicates whether the garbage collector is running on a workstation or a server.</span></span>  
  
 [<span data-ttu-id="95abb-133">CorDebugGenerationTypes 枚举</span><span class="sxs-lookup"><span data-stu-id="95abb-133">CorDebugGenerationTypes Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebuggenerationtypes-enumeration.md)  
 <span data-ttu-id="95abb-134">指定托管堆上内存区域的生成。</span><span class="sxs-lookup"><span data-stu-id="95abb-134">Specifies the generation of a region of memory on the managed heap.</span></span>  
  
 <span data-ttu-id="95abb-135">CorDebugHandleType</span><span class="sxs-lookup"><span data-stu-id="95abb-135">CorDebugHandleType</span></span>  
 <span data-ttu-id="95abb-136">指示句柄类型。</span><span class="sxs-lookup"><span data-stu-id="95abb-136">Indicates the handle type.</span></span>  
  
 [<span data-ttu-id="95abb-137">CorDebugIlToNativeMappingTypes 枚举</span><span class="sxs-lookup"><span data-stu-id="95abb-137">CorDebugIlToNativeMappingTypes Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugiltonativemappingtypes-enumeration.md)  
 <span data-ttu-id="95abb-138">指示本机指令的某一特定范围是否与特殊的代码区域相符。</span><span class="sxs-lookup"><span data-stu-id="95abb-138">Indicates whether a particular range of native instructions corresponds to a special code region.</span></span>  
  
 <span data-ttu-id="95abb-139">CorDebugIntercept</span><span class="sxs-lookup"><span data-stu-id="95abb-139">CorDebugIntercept</span></span>  
 <span data-ttu-id="95abb-140">指示可单步执行的代码的类型。</span><span class="sxs-lookup"><span data-stu-id="95abb-140">Indicates the types of code that can be stepped into.</span></span>  
  
 [<span data-ttu-id="95abb-141">CorDebugInterfaceVersion 枚举</span><span class="sxs-lookup"><span data-stu-id="95abb-141">CorDebugInterfaceVersion Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebuginterfaceversion-enumeration.md)  
 <span data-ttu-id="95abb-142">指定 .NET Framework 的版本，或在其中引入了接口的 .NET Framework 的版本。</span><span class="sxs-lookup"><span data-stu-id="95abb-142">Specifies either a version of the .NET Framework, or the version of the .NET Framework in which an interface was introduced.</span></span>  
  
 <span data-ttu-id="95abb-143">CorDebugInternalFrameType</span><span class="sxs-lookup"><span data-stu-id="95abb-143">CorDebugInternalFrameType</span></span>  
 <span data-ttu-id="95abb-144">标识堆栈帧的类型。</span><span class="sxs-lookup"><span data-stu-id="95abb-144">Identifies the type of stack frame.</span></span>  
  
 [<span data-ttu-id="95abb-145">CorDebugJITCompilerFlags 枚举</span><span class="sxs-lookup"><span data-stu-id="95abb-145">CorDebugJITCompilerFlags Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md)  
 <span data-ttu-id="95abb-146">包含影响托管的实时 (JIT) 编译器的行为的值。</span><span class="sxs-lookup"><span data-stu-id="95abb-146">Contains values that influence the behavior of the managed just-in-time (JIT) compiler.</span></span>  
  
 [<span data-ttu-id="95abb-147">CorDebugJITCompilerFlagsDeprecated 枚举</span><span class="sxs-lookup"><span data-stu-id="95abb-147">CorDebugJITCompilerFlagsDeprecated Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflagsdeprecated-enumeration.md)  
 <span data-ttu-id="95abb-148">已过时。</span><span class="sxs-lookup"><span data-stu-id="95abb-148">Obsolete.</span></span> <span data-ttu-id="95abb-149">使用`CORDEBUG_JIT_DEFAULT`的成员[CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md)枚举相反。</span><span class="sxs-lookup"><span data-stu-id="95abb-149">Use the `CORDEBUG_JIT_DEFAULT` member of the [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) enumeration instead.</span></span>  
  
 <span data-ttu-id="95abb-150">CorDebugMappingResult</span><span class="sxs-lookup"><span data-stu-id="95abb-150">CorDebugMappingResult</span></span>  
 <span data-ttu-id="95abb-151">提供如何获取指令指针 (IP) 的值的详细信息。</span><span class="sxs-lookup"><span data-stu-id="95abb-151">Provides the details of how the value of the instruction pointer (IP) was obtained.</span></span>  
  
 [<span data-ttu-id="95abb-152">CorDebugMDAFlags 枚举</span><span class="sxs-lookup"><span data-stu-id="95abb-152">CorDebugMDAFlags Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugmdaflags-enumeration.md)  
 <span data-ttu-id="95abb-153">指定在其上激发托管调试助手 (MDA) 的线程的状态。</span><span class="sxs-lookup"><span data-stu-id="95abb-153">Specifies the status of the thread on which the managed debugging assistant (MDA) is fired.</span></span>  
  
 [<span data-ttu-id="95abb-154">CorDebugNGenPolicy 枚举</span><span class="sxs-lookup"><span data-stu-id="95abb-154">CorDebugNGenPolicy Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugngenpolicy-enumeration.md)  
 <span data-ttu-id="95abb-155">提供用于确定调试器是否从本机映像缓存中加载本机 (NGen) 映像的值。</span><span class="sxs-lookup"><span data-stu-id="95abb-155">Provides a value that determines whether a debugger loads native (NGen) images from the native image cache.</span></span>  
  
 [<span data-ttu-id="95abb-156">CorDebugPlatform 枚举</span><span class="sxs-lookup"><span data-stu-id="95abb-156">CorDebugPlatform Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugplatform-enumeration.md)  
 <span data-ttu-id="95abb-157">提供通过使用的目标平台值[icordebugdatatarget:: Getplatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="95abb-157">Provides target platform values that are used by the [ICorDebugDataTarget::GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) method.</span></span>  
  
 [<span data-ttu-id="95abb-158">CorDebugRecordFormat 枚举</span><span class="sxs-lookup"><span data-stu-id="95abb-158">CorDebugRecordFormat Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)  
 <span data-ttu-id="95abb-159">描述包含本机异常调试事件相关信息的字节数组的数据格式。</span><span class="sxs-lookup"><span data-stu-id="95abb-159">Describes the format of the data in a byte array that contains information about a native exception debug event.</span></span>  
  
 <span data-ttu-id="95abb-160">CorDebugRegister</span><span class="sxs-lookup"><span data-stu-id="95abb-160">CorDebugRegister</span></span>  
 <span data-ttu-id="95abb-161">指定与给定处理器体系结构关联的寄存器。</span><span class="sxs-lookup"><span data-stu-id="95abb-161">Specifies the registers associated with a given processor architecture.</span></span>  
  
 [<span data-ttu-id="95abb-162">CorDebugSetContextFlag 枚举</span><span class="sxs-lookup"><span data-stu-id="95abb-162">CorDebugSetContextFlag Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugsetcontextflag-enumeration.md)  
 <span data-ttu-id="95abb-163">指示上下文是来自堆栈上的活动（或叶）帧，还是已通过从另一个帧展开来进行计算。</span><span class="sxs-lookup"><span data-stu-id="95abb-163">Indicates whether the context is from the active (or leaf) frame on the stack or has been computed by unwinding from another frame.</span></span>  
  
 [<span data-ttu-id="95abb-164">CorDebugStateChange 枚举</span><span class="sxs-lookup"><span data-stu-id="95abb-164">CorDebugStateChange Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugstatechange-enumeration.md)  
 <span data-ttu-id="95abb-165">描述基于进程变化必须删除的缓存数据数量。</span><span class="sxs-lookup"><span data-stu-id="95abb-165">Describes the amount of cached data that must be discarded based on changes to the process.</span></span>  
  
 <span data-ttu-id="95abb-166">CorDebugStepReason</span><span class="sxs-lookup"><span data-stu-id="95abb-166">CorDebugStepReason</span></span>  
 <span data-ttu-id="95abb-167">指示一个单步执行的结果。</span><span class="sxs-lookup"><span data-stu-id="95abb-167">Indicates the outcome of an individual step.</span></span>  
  
 <span data-ttu-id="95abb-168">CorDebugThreadState</span><span class="sxs-lookup"><span data-stu-id="95abb-168">CorDebugThreadState</span></span>  
 <span data-ttu-id="95abb-169">指定用于调试的线程的状态。</span><span class="sxs-lookup"><span data-stu-id="95abb-169">Specifies the state of a thread for debugging.</span></span>  
  
 <span data-ttu-id="95abb-170">\>CorDebugUnmappedStop</span><span class="sxs-lookup"><span data-stu-id="95abb-170">\>CorDebugUnmappedStop</span></span>  
 <span data-ttu-id="95abb-171">指定未映射代码的类型，这些代码可以中断分档器代码执行。</span><span class="sxs-lookup"><span data-stu-id="95abb-171">Specifies the type of unmapped code that can trigger a halt in code execution by the stepper.</span></span>  
  
 <span data-ttu-id="95abb-172">CorDebugUserState</span><span class="sxs-lookup"><span data-stu-id="95abb-172">CorDebugUserState</span></span>  
 <span data-ttu-id="95abb-173">指示线程的用户状态。</span><span class="sxs-lookup"><span data-stu-id="95abb-173">Indicates the user state of a thread.</span></span>  
  
 [<span data-ttu-id="95abb-174">CorGCReferenceType 枚举</span><span class="sxs-lookup"><span data-stu-id="95abb-174">CorGCReferenceType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md)  
 <span data-ttu-id="95abb-175">标识要进行垃圾回收的对象的源。</span><span class="sxs-lookup"><span data-stu-id="95abb-175">Identifies the source of an object to be garbage-collected.</span></span>  
  
 [<span data-ttu-id="95abb-176">ILCodeKind 枚举</span><span class="sxs-lookup"><span data-stu-id="95abb-176">ILCodeKind Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/ilcodekind-enumeration.md)  
 <span data-ttu-id="95abb-177">提供用于指定调试器是否能够访问在探查器 ReJIT 检测中添加的局部变量或代码的值。</span><span class="sxs-lookup"><span data-stu-id="95abb-177">Provides values that specify whether the debugger is able to access local variables or code added in profiler ReJIT instrumentation.</span></span>  
  
 [<span data-ttu-id="95abb-178">LoggingLevelEnum 枚举</span><span class="sxs-lookup"><span data-stu-id="95abb-178">LoggingLevelEnum Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/logginglevelenum-enumeration.md)  
 <span data-ttu-id="95abb-179">指示在托管线程记录事件时写入事件日志的描述性消息的严重级别。</span><span class="sxs-lookup"><span data-stu-id="95abb-179">Indicates the severity level of a descriptive message that is written to the event log when a managed thread logs an event.</span></span>  
  
 [<span data-ttu-id="95abb-180">LogSwitchCallReason 枚举</span><span class="sxs-lookup"><span data-stu-id="95abb-180">LogSwitchCallReason Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/logswitchcallreason-enumeration.md)  
 <span data-ttu-id="95abb-181">指示已对调试/跟踪开关执行的操作。</span><span class="sxs-lookup"><span data-stu-id="95abb-181">Indicates the operation that was performed on a debugging/tracing switch.</span></span>  
  
 [<span data-ttu-id="95abb-182">VariableLocationType 枚举</span><span class="sxs-lookup"><span data-stu-id="95abb-182">VariableLocationType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/variablelocationtype-enumeration.md)  
 <span data-ttu-id="95abb-183">指示变量的本机位置类型。</span><span class="sxs-lookup"><span data-stu-id="95abb-183">Indicates the native location type of a variable.</span></span>  
  
 [<span data-ttu-id="95abb-184">WriteableMetadataUpdateMode 枚举</span><span class="sxs-lookup"><span data-stu-id="95abb-184">WriteableMetadataUpdateMode Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/writeablemetadataupdatemode-enumeration.md)  
 <span data-ttu-id="95abb-185">提供用于指定元数据的内存中更新对调试器是否可见的值。</span><span class="sxs-lookup"><span data-stu-id="95abb-185">Provides values that specify whether in-memory updates to metadata are visible to a debugger.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="95abb-186">相关章节</span><span class="sxs-lookup"><span data-stu-id="95abb-186">Related Sections</span></span>  
 [<span data-ttu-id="95abb-187">调试组件类</span><span class="sxs-lookup"><span data-stu-id="95abb-187">Debugging Coclasses</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-coclasses.md)  
  
 [<span data-ttu-id="95abb-188">调试接口</span><span class="sxs-lookup"><span data-stu-id="95abb-188">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
  
 [<span data-ttu-id="95abb-189">调试全局静态函数</span><span class="sxs-lookup"><span data-stu-id="95abb-189">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)  
  
 [<span data-ttu-id="95abb-190">调试结构</span><span class="sxs-lookup"><span data-stu-id="95abb-190">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
