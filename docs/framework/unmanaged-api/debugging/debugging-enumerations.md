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
ms.openlocfilehash: c24882f2bd9819043bbc786bd2e5f35129a92744
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="debugging-enumerations"></a>调试枚举
本节介绍了调试 API 使用的非托管枚举。  
  
## <a name="in-this-section"></a>本节内容  
 [CLR_DEBUGGING_PROCESS_FLAGS 枚举](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-process-flags-enumeration.md)  
 提供使用的值[iclrdebugging:: Openvirtualprocess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md)方法。  
  
 [CLRDataEnumMemoryFlags 枚举](../../../../docs/framework/unmanaged-api/debugging/clrdataenummemoryflags-enumeration.md)  
 指示的内存区域对的调用[iclrdataenummemoryregions:: Enummemoryregions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md)应包括方法。  
  
 [COR_PUB_ENUMPROCESS 枚举](../../../../docs/framework/unmanaged-api/debugging/cor-pub-enumprocess-enumeration.md)  
 标识要枚举的进程的类型。  
  
 [CorDebugBlockingReason 枚举](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingreason-enumeration.md)  
 指定线程可能在给定对象上受到阻塞的原因。  
  
 CorDebugChainReason  
 指示启动调用链的一个或多个原因。  
  
 [CorDebugCodeInvokeKind 枚举](../../../../docs/framework/unmanaged-api/debugging/cordebugcodeinvokekind-enumeration.md)  
 描述导出函数如何调用托管代码。  
  
 [CorDebugCodeInvokePurpose 枚举](../../../../docs/framework/unmanaged-api/debugging/cordebugcodeinvokepurpose-enumeration.md)  
 描述为何导出的函数会调用托管代码。  
  
 CorDebugCreateProcessFlags  
 提供了其他可以在调用中使用的调试选项[icordebug:: Createprocess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md)方法。  
  
 [CorDebugDebugEventKind 枚举](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md)  
 指示由解码获取其信息的事件类型[解码事件](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md)方法。  
  
 [CorDebugDecodeEventFlagsWindows 枚举](../../../../docs/framework/unmanaged-api/debugging/cordebugdecodeeventflagswindows-enumeration.md)  
 提供关于 Windows 平台上的调试事件的其他信息。  
  
 CorDebugExceptionCallbackType  
 指示的回调中所做的类型[icordebugmanagedcallback2:: Exception](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-exception-method.md)事件。  
  
 [CorDebugExceptionFlags 枚举](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md)  
 提供有关异常的附加信息。  
  
 CorDebugExceptionUnwindCallbackType  
 指示在展开阶段正由回调发送信号的事件。  
  
 [CorDebugGCType 枚举](../../../../docs/framework/unmanaged-api/debugging/cordebuggctype-enumeration.md)  
 指示垃圾回收器是在工作站还是服务器上运行。  
  
 [CorDebugGenerationTypes 枚举](../../../../docs/framework/unmanaged-api/debugging/cordebuggenerationtypes-enumeration.md)  
 指定托管堆上内存区域的生成。  
  
 CorDebugHandleType  
 指示句柄类型。  
  
 [CorDebugIlToNativeMappingTypes 枚举](../../../../docs/framework/unmanaged-api/debugging/cordebugiltonativemappingtypes-enumeration.md)  
 指示本机指令的某一特定范围是否与特殊的代码区域相符。  
  
 CorDebugIntercept  
 指示可单步执行的代码的类型。  
  
 [CorDebugInterfaceVersion 枚举](../../../../docs/framework/unmanaged-api/debugging/cordebuginterfaceversion-enumeration.md)  
 指定 .NET Framework 的版本，或在其中引入了接口的 .NET Framework 的版本。  
  
 CorDebugInternalFrameType  
 标识堆栈帧的类型。  
  
 [CorDebugJITCompilerFlags 枚举](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md)  
 包含影响托管的实时 (JIT) 编译器的行为的值。  
  
 [CorDebugJITCompilerFlagsDeprecated 枚举](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflagsdeprecated-enumeration.md)  
 已过时。 使用`CORDEBUG_JIT_DEFAULT`的成员[CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md)枚举相反。  
  
 CorDebugMappingResult  
 提供如何获取指令指针 (IP) 的值的详细信息。  
  
 [CorDebugMDAFlags 枚举](../../../../docs/framework/unmanaged-api/debugging/cordebugmdaflags-enumeration.md)  
 指定在其上激发托管调试助手 (MDA) 的线程的状态。  
  
 [CorDebugNGenPolicy 枚举](../../../../docs/framework/unmanaged-api/debugging/cordebugngenpolicy-enumeration.md)  
 提供用于确定调试器是否从本机映像缓存中加载本机 (NGen) 映像的值。  
  
 [CorDebugPlatform 枚举](../../../../docs/framework/unmanaged-api/debugging/cordebugplatform-enumeration.md)  
 提供通过使用的目标平台值[icordebugdatatarget:: Getplatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md)方法。  
  
 [CorDebugRecordFormat 枚举](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)  
 描述包含本机异常调试事件相关信息的字节数组的数据格式。  
  
 CorDebugRegister  
 指定与给定处理器体系结构关联的寄存器。  
  
 [CorDebugSetContextFlag 枚举](../../../../docs/framework/unmanaged-api/debugging/cordebugsetcontextflag-enumeration.md)  
 指示上下文是来自堆栈上的活动（或叶）帧，还是已通过从另一个帧展开来进行计算。  
  
 [CorDebugStateChange 枚举](../../../../docs/framework/unmanaged-api/debugging/cordebugstatechange-enumeration.md)  
 描述基于进程变化必须删除的缓存数据数量。  
  
 CorDebugStepReason  
 指示一个单步执行的结果。  
  
 CorDebugThreadState  
 指定用于调试的线程的状态。  
  
 \>CorDebugUnmappedStop  
 指定未映射代码的类型，这些代码可以中断分档器代码执行。  
  
 CorDebugUserState  
 指示线程的用户状态。  
  
 [CorGCReferenceType 枚举](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md)  
 标识要进行垃圾回收的对象的源。  
  
 [ILCodeKind 枚举](../../../../docs/framework/unmanaged-api/debugging/ilcodekind-enumeration.md)  
 提供用于指定调试器是否能够访问在探查器 ReJIT 检测中添加的局部变量或代码的值。  
  
 [LoggingLevelEnum 枚举](../../../../docs/framework/unmanaged-api/debugging/logginglevelenum-enumeration.md)  
 指示在托管线程记录事件时写入事件日志的描述性消息的严重级别。  
  
 [LogSwitchCallReason 枚举](../../../../docs/framework/unmanaged-api/debugging/logswitchcallreason-enumeration.md)  
 指示已对调试/跟踪开关执行的操作。  
  
 [VariableLocationType 枚举](../../../../docs/framework/unmanaged-api/debugging/variablelocationtype-enumeration.md)  
 指示变量的本机位置类型。  
  
 [WriteableMetadataUpdateMode 枚举](../../../../docs/framework/unmanaged-api/debugging/writeablemetadataupdatemode-enumeration.md)  
 提供用于指定元数据的内存中更新对调试器是否可见的值。  
  
## <a name="related-sections"></a>相关章节  
 [调试组件类](../../../../docs/framework/unmanaged-api/debugging/debugging-coclasses.md)  
  
 [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
  
 [调试全局静态函数](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)  
  
 [调试结构](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
