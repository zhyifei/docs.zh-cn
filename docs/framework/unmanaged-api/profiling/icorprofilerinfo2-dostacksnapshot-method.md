---
title: ICorProfilerInfo2::DoStackSnapshot 方法
ms.date: 03/30/2017
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
ms.openlocfilehash: 64bcf6ee58d743a26e31c49a425f36cc808b5080
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74426836"
---
# <a name="icorprofilerinfo2dostacksnapshot-method"></a>ICorProfilerInfo2::DoStackSnapshot 方法
遍历指定线程的堆栈上的托管帧，并通过回调将信息发送到探查器。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT DoStackSnapshot(  
    [in] ThreadID thread,  
    [in] StackSnapshotCallback *callback,  
    [in] ULONG32 infoFlags,  
    [in] void *clientData,  
    [in, size_is(contextSize), length_is(contextSize)] BYTE context[],  
    [in] ULONG32 contextSize);  
```  
  
## <a name="parameters"></a>参数  
 `thread`  
 中目标线程的 ID。  
  
 在 `thread` 中传递 null 会生成当前线程的快照。 如果传递了不同线程的 `ThreadID`，则公共语言运行时（CLR）会挂起该线程，执行快照并恢复。  
  
 `callback`  
 中指向[StackSnapshotCallback](../../../../docs/framework/unmanaged-api/profiling/stacksnapshotcallback-function.md)方法的实现的指针，CLR 调用此方法为探查器提供有关每个托管帧以及每次运行非托管帧的信息。  
  
 `StackSnapshotCallback` 方法由探查器编写器实现。  
  
 `infoFlags`  
 中一个[COR_PRF_SNAPSHOT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-snapshot-info-enumeration.md)枚举的值，该值指定要通过 `StackSnapshotCallback`为每个帧传递回的数据量。  
  
 `clientData`  
 中指向客户端数据的指针，它将直接传递到 `StackSnapshotCallback` 回调函数。  
  
 `context`  
 中指向 Win32 `CONTEXT` 结构的指针，该结构用于对堆栈审核进行种子设定。 Win32 `CONTEXT` 结构包含 CPU 寄存器的值，表示特定时刻的 CPU 状态。  
  
 如果堆栈顶部是非托管的帮助程序代码，则 seed 有助于 CLR 确定开始堆栈审核的位置;否则，将忽略种子。 必须为异步审核提供种子。 如果执行同步审核，则不需要种子。  
  
 仅当在 `infoFlags` 参数中传递了 COR_PRF_SNAPSHOT_CONTEXT 标志时，`context` 参数才有效。  
  
 `contextSize`  
 中`context` 参数引用的 `CONTEXT` 结构的大小。  
  
## <a name="remarks"></a>备注  
 为 `thread` 传递 null 会生成当前线程的快照。 仅当目标线程在此时挂起时，才能对其他线程执行快照操作。  
  
 当探查器需要遍历堆栈时，它将调用 `DoStackSnapshot`。 在 CLR 从该调用返回之前，它将为堆栈上的每个托管帧（或运行非托管帧）调用 `StackSnapshotCallback` 几次。 如果遇到非托管帧，则必须自行对其进行演练。  
  
 遍历堆栈的顺序与帧被推送到堆栈上的顺序相反：叶（上传）帧优先于最后一个（第一个推送的）帧。  
  
 有关如何对探查器进行编程以遍历托管堆栈的详细信息，请参阅[.NET Framework 2.0：基础和更高版本中的探查器堆栈遍历](https://go.microsoft.com/fwlink/?LinkId=73638)。  
  
 堆栈审核可以是同步的，也可以是异步的，如以下各节所述。  
  
## <a name="synchronous-stack-walk"></a>同步堆栈遍历  
 同步堆栈审核包括遍历当前线程的堆栈以响应回调。 它不需要进行种子设定或暂停。  
  
 当你在响应调用某个探查器的[ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) （或[ICorProfilerCallback2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)）方法的 CLR 时进行同步调用，你可以调用 `DoStackSnapshot` 来遍历当前线程的堆栈。 当你想要在通知（如[ICorProfilerCallback：： ObjectAllocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md)）上查看堆栈的外观时，这非常有用。 只需从 `ICorProfilerCallback` 方法中调用 `DoStackSnapshot`，在 `context` 和 `thread` 参数中传递 null。  
  
## <a name="asynchronous-stack-walk"></a>异步堆栈遍历  
 异步堆栈审核需要遍历不同线程的堆栈，或遍历当前线程的堆栈，而不是响应回调，但通过劫持当前线程的指令指针。 如果堆栈顶部是非托管代码，而不是平台调用（PInvoke）或 COM 调用的一部分，而是 CLR 本身中的帮助程序代码，则异步审核需要种子。 例如，执行实时（JIT）编译或垃圾回收的代码是帮助器代码。  
  
 您可以通过直接挂起目标线程并自己遍历其堆栈来获取种子，直到找到最顶层的托管帧。 挂起目标线程后，获取目标线程的当前注册上下文。 接下来，通过调用[ICorProfilerInfo：： GetFunctionFromIP](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getfunctionfromip-method.md)确定寄存器上下文是否指向非托管代码，如果它返回的 `FunctionID` 等于零，则该框架为非托管代码。 现在，遍历堆栈直至到达第一个托管帧，然后基于该帧的注册上下文计算种子上下文。  
  
 用种子上下文调用 `DoStackSnapshot`，开始异步堆栈遍历。 如果未提供种子，`DoStackSnapshot` 可能会跳过堆栈顶部的托管帧，因此，将为您提供不完整的堆栈审核。 如果提供了种子，则它必须指向 JIT 编译的或本机图像生成器（Ngen.exe）生成的代码;否则，`DoStackSnapshot` 将返回失败代码 CORPROF_E_STACKSNAPSHOT_UNMANAGED_CTX。  
  
 异步堆栈审核可能会导致死锁或访问冲突，除非你遵循以下准则：  
  
- 当你直接挂起线程时，请记住，只有从未运行托管代码的线程才能挂起另一个线程。  
  
- 始终在[ICorProfilerCallback：： ThreadDestroyed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threaddestroyed-method.md)回调中阻止，直到该线程的堆栈遍历完成。  
  
- 当探查器调入可触发垃圾回收的 CLR 函数时，不要持有锁。 也就是说，如果拥有的线程可能发出调用来触发垃圾回收，则不要持有锁。  
  
 如果从探查器已创建的线程调用 `DoStackSnapshot`，以便可以遍历单独目标线程的堆栈，还会发生死锁的风险。 第一次创建的线程会输入某些 `ICorProfilerInfo*` 方法（包括 `DoStackSnapshot`），CLR 将在该线程上执行每个线程特定于 CLR 的初始化。 如果探查器已挂起要尝试遍历其堆栈的目标线程，并且如果该目标线程发生了对每个线程初始化执行所需的锁，则会发生死锁。 若要避免这种死锁，请在探查器创建的线程中初始调用 `DoStackSnapshot`，以遍历单独的目标线程，但不要首先挂起目标线程。 此初始调用可确保在发生死锁的情况下，每个线程的初始化都可以完成。 如果 `DoStackSnapshot` 成功并报告了至少一个帧，则在该点之后，此探查器创建的线程将会挂起任何目标线程，并调用 `DoStackSnapshot` 来遍历该目标线程的堆栈。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [ICorProfilerInfo 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [ICorProfilerInfo2 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
