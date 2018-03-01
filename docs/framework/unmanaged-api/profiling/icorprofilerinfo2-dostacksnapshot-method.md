---
title: "ICorProfilerInfo2::DoStackSnapshot 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorProfilerInfo2.DoStackSnapshot
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::DoStackSnapshot
helpviewer_keywords:
- ICorProfilerInfo2::DoStackSnapshot method [.NET Framework profiling]
- DoStackSnapshot method [.NET Framework profiling]
ms.assetid: 287b11e9-7c52-4a13-ba97-751203fa97f4
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5548254eb160547643a874fd2e31a085ec6f3ecb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo2dostacksnapshot-method"></a>ICorProfilerInfo2::DoStackSnapshot 方法
上的指定线程的堆栈遍历托管的帧并将信息发送到通过回调探查器。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT DoStackSnapshot(  
    [in] ThreadID thread,  
    [in] StackSnapshotCallback *callback,  
    [in] ULONG32 infoFlags,  
    [in] void *clientData,  
    [in, size_is(contextSize), length_is(contextSize)] BYTE context[],  
    [in] ULONG32 contextSize);  
```  
  
#### <a name="parameters"></a>参数  
 `thread`  
 [in]目标线程的 ID。  
  
 传入 null`thread`会生成当前线程的快照。 如果`ThreadID`的传递不同的线程，公共语言运行时 (CLR) 将该线程挂起、 执行快照，并恢复。  
  
 `callback`  
 [in]指向的实现的[StackSnapshotCallback](../../../../docs/framework/unmanaged-api/profiling/stacksnapshotcallback-function.md)方法，由 CLR 探查器提供每个托管的帧和每次运行的非托管帧的信息。  
  
 `StackSnapshotCallback`方法由探查器编写器实现。  
  
 `infoFlags`  
 [in]值为[COR_PRF_SNAPSHOT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-snapshot-info-enumeration.md)枚举，指定要返回为每个帧传递的数据量`StackSnapshotCallback`。  
  
 `clientData`  
 [in]指向客户端数据，这直接通过传递给`StackSnapshotCallback`回调函数。  
  
 `context`  
 [in]一个指向 Win32`CONTEXT`结构，用于设定种子堆栈审核。 Win32`CONTEXT`结构包含的 CPU 寄存器的值，表示在特定时刻的 CPU 的状态。  
  
 种子可帮助确定从何处着手堆栈审核，堆栈的顶部是非托管帮助器代码; 如果 CLR否则，将忽略种子。 必须为异步审核提供种子。 如果你正在进行同步的审核，没有种子是必需的。  
  
 `context`参数才有效仅当传入的 COR_PRF_SNAPSHOT_CONTEXT 标志`infoFlags`参数。  
  
 `contextSize`  
 [in]大小`CONTEXT`结构，这通过引用`context`参数。  
  
## <a name="remarks"></a>备注  
 传递 null`thread`会生成当前线程的快照。 仅当目标线程挂起时，可以其他线程拍摄快照。  
  
 当探查器想要遍历堆栈时，它将调用`DoStackSnapshot`。 从该调用中返回 CLR 之前，它将调用你`StackSnapshotCallback`几次，一次每个托管帧 （或运行非托管帧） 堆栈上。 当遇到非托管的帧时，你必须自己逐步它们。  
  
 在其中遍历堆栈的顺序是如何帧已推送到堆栈上的反向： 上次叶 （上一次推送） 首先，主要 （第一个推送） 框架。  
  
 有关如何进行编程以审核托管的堆栈探查器的详细信息，请参阅[.NET Framework 2.0 中的探查器堆栈审核： 基础知识和扩展](http://go.microsoft.com/fwlink/?LinkId=73638)。  
  
 下列部分中所述，可以同步或异步，堆栈审核。  
  
## <a name="synchronous-stack-walk"></a>同步堆栈审核  
 同步堆栈审核涉及对回调的响应中的审核当前线程的堆栈。 它不需要设置种子或挂起。  
  
 你进行同步时，调用以响应调用的探查器的某个 CLR [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) (或[ICorProfilerCallback2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)) 调用的方法，`DoStackSnapshot`遍历的堆栈当前线程。 这是有用的当你想要查看堆栈如下所示在通知如[icorprofilercallback:: Objectallocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md)。 你只需调用`DoStackSnapshot`中你`ICorProfilerCallback`方法，传入 null`context`和`thread`参数。  
  
## <a name="asynchronous-stack-walk"></a>异步堆栈审核  
 异步堆栈审核要求审核的另一个线程，堆栈或不在响应回调，但通过劫持当前线程的指令指针步行当前线程的堆栈。 异步审核要求的种子如果堆栈的顶部是不是一个平台的一部分的非托管的代码调用 (PInvoke) 或 COM 调用，但在 CLR 自行的帮助器代码。 例如，执行在实时 (JIT) 编译或垃圾收集的代码是帮助器代码。  
  
 通过直接停用此目标线程获取种子和你自己，直到你找到的最顶层的遍历其堆栈托管帧。 此目标线程已挂起后，获取目标线程的当前寄存器上下文。 接下来，确定是否寄存器上下文指向非托管代码通过调用[icorprofilerinfo:: Getfunctionfromip](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getfunctionfromip-method.md) -如果它返回`FunctionID`等于零，框架的非托管的代码。 现在，遍历堆栈，直到到达第一个托管的帧，然后计算基于该框架的寄存器上下文在种子上下文。  
  
 调用`DoStackSnapshot`与你的种子上下文开始异步堆栈审核。 如果未提供种子，`DoStackSnapshot`可能会跳过堆栈顶部的托管的帧，因此，将为你提供完整的堆栈审核。 如果你提供种子，则它必须指向 JIT 编译或本机映像生成器 (Ngen.exe)-生成的代码;否则为`DoStackSnapshot`返回失败代码，CORPROF_E_STACKSNAPSHOT_UNMANAGED_CTX。  
  
 异步堆栈审核可轻松会导致死锁或访问冲突，除非您遵循这些指导原则：  
  
-   直接挂起线程时，请记住仅从未运行托管的代码的线程可以挂起另一个线程。  
  
-   始终块中，在你[icorprofilercallback:: Threaddestroyed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threaddestroyed-method.md)回调完成此线程的堆栈审核之前。  
  
-   不保持锁定，而你的探查器调入可以触发垃圾回收的 CLR 函数。 如果拥有的线程可能会使触发垃圾回收的调用，即，并持有锁。  
  
 此外，还有死锁风险如果调用`DoStackSnapshot`从你的探查器已创建，以便你可以遍历的单独目标线程堆栈的线程。 第一次你创建的线程进入某些`ICorProfilerInfo*`方法 (包括`DoStackSnapshot`)，CLR 将执行每个线程，该线程上的特定于 CLR 的初始化。 如果你的探查器已暂停目标线程尝试引导，其堆栈和该目标线程发生拥有锁所需执行此每个线程初始化，将发生死锁。 若要避免这种死锁，进行初始调用`DoStackSnapshot`从您探查器创建的线程遍历单独目标线程，但首先未挂起此目标线程。 此初始调用可确保每个线程初始化，可以在不死锁的情况下完成。 如果`DoStackSnapshot`成功，并且报告至少一个帧，此后，它将该探查器创建线程在可以挂起任何目标线程和调用安全`DoStackSnapshot`遍历该目标线程的堆栈。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICorProfilerInfo 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [ICorProfilerInfo2 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
