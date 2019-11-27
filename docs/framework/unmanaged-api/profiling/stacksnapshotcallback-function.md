---
title: StackSnapshotCallback 函数
ms.date: 03/30/2017
api_name:
- StackSnapshotCallback
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- StackSnapshotCallback
helpviewer_keywords:
- StackSnapshotCallback function [.NET Framework profiling]
ms.assetid: d0f235b2-91fe-4f82-b7d5-e5c64186eea8
topic_type:
- apiref
ms.openlocfilehash: c0cec9eb7bb8bbc94b255152a9b4d79108bdd1b1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427075"
---
# <a name="stacksnapshotcallback-function"></a>StackSnapshotCallback 函数
在堆栈遍历期间，为探查器提供有关每个托管帧和每个托管帧的每个运行的信息，由[ICorProfilerInfo2：:D ostacksnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md)方法启动。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT __stdcall StackSnapshotCallback (  
    [in] FunctionID funcId,  
    [in] UINT_PTR ip,  
    [in] COR_PRF_FRAME_INFO frameInfo,  
    [in] ULONG32 contextSize,  
    [in] BYTE context[],  
    [in] void *clientData  
);  
```  
  
## <a name="parameters"></a>参数  
 `funcId`  
 中如果此值为零，则此回调适用于非托管帧的运行;否则，它是托管函数的标识符，此回调适用于托管帧。  
  
 `ip`  
 中帧中的本机代码指令指针的值。  
  
 `frameInfo`  
 中一个 `COR_PRF_FRAME_INFO` 值，该值引用有关堆栈帧的信息。 此值仅在此回调期间有效。  
  
 `contextSize`  
 中`context` 参数引用的 `CONTEXT` 结构的大小。  
  
 `context`  
 中指向 Win32 `CONTEXT` 结构的指针，该结构表示此帧的 CPU 状态。  
  
 仅当在 `ICorProfilerInfo2::DoStackSnapshot`中传递了 COR_PRF_SNAPSHOT_CONTEXT 标志时，`context` 参数才有效。  
  
 `clientData`  
 中指向客户端数据的指针，通过从 `ICorProfilerInfo2::DoStackSnapshot`直接传递此数据。  
  
## <a name="remarks"></a>备注  
 `StackSnapshotCallback` 函数由探查器编写器实现。 必须限制 `StackSnapshotCallback`中完成的工作的复杂性。 例如，以异步方式使用 `ICorProfilerInfo2::DoStackSnapshot` 时，目标线程可能会持有锁。 如果 `StackSnapshotCallback` 中的代码需要相同的锁，则可能会不幸死锁。  
  
 `ICorProfilerInfo2::DoStackSnapshot` 方法为每个托管帧调用一次 `StackSnapshotCallback` 函数，或每次运行非托管帧调用一次。 如果调用 `StackSnapshotCallback` 来运行非托管帧，则探查器可能会使用寄存器上下文（由 `context` 参数引用）来执行其自己的非托管堆栈遍历。 在这种情况下，Win32 `CONTEXT` 结构表示在非托管帧运行内最近推送的帧的 CPU 状态。 尽管 Win32 `CONTEXT` 结构包含所有寄存器的值，但你只应依赖堆栈指针寄存器的值、帧指针寄存器、指令指针寄存器和非易失性（即，保留的）整数寄存器的值。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Corprof.idl .idl  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [DoStackSnapshot 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md)
- [分析全局静态函数](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
