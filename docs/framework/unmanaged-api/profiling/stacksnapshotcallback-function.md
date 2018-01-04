---
title: "StackSnapshotCallback 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: StackSnapshotCallback
api_location: mscorwks.dll
api_type: COM
f1_keywords: StackSnapshotCallback
helpviewer_keywords: StackSnapshotCallback function [.NET Framework profiling]
ms.assetid: d0f235b2-91fe-4f82-b7d5-e5c64186eea8
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 32cf21fb5a76fdec4daa322d53a8eb218ae2f2b5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="stacksnapshotcallback-function"></a>StackSnapshotCallback 函数
探查器提供了有关每个托管的帧和非托管的帧每次运行在堆栈上的堆栈审核，启动的过程信息，以及[icorprofilerinfo2:: Dostacksnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md)方法。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT __stdcall StackSnapshotCallback (  
    [in] FunctionID funcId,  
    [in] UINT_PTR ip,  
    [in] COR_PRF_FRAME_INFO frameInfo,  
    [in] ULONG32 contextSize,  
    [in] BYTE context[],  
    [in] void *clientData  
);  
```  
  
#### <a name="parameters"></a>参数  
 `funcId`  
 [in]对于运行的非托管的帧; 如果此值为零，是此回调否则为它是托管函数的标识符，此回调可能会个托管帧。  
  
 `ip`  
 [in]在框架中的本机代码指令指针的值。  
  
 `frameInfo`  
 [in]A`COR_PRF_FRAME_INFO`引用有关堆栈帧的信息的值。 此值可用于使用仅在此回调。  
  
 `contextSize`  
 [in]大小`CONTEXT`结构，这通过引用`context`参数。  
  
 `context`  
 [in]一个指向 Win32`CONTEXT`结构，它表示此帧的 CPU 的状态。  
  
 `context`参数才有效仅当传入的 COR_PRF_SNAPSHOT_CONTEXT 标志`ICorProfilerInfo2::DoStackSnapshot`。  
  
 `clientData`  
 [in]指向客户端数据，这直接通过传递从`ICorProfilerInfo2::DoStackSnapshot`。  
  
## <a name="remarks"></a>备注  
 `StackSnapshotCallback`函数由探查器编写器实现。 你必须限制完成工作的复杂性`StackSnapshotCallback`。 例如，在使用`ICorProfilerInfo2::DoStackSnapshot`以异步方式，此目标线程可能会持有锁。 如果中的代码`StackSnapshotCallback`需要相同的锁定，死锁无法随之发生。  
  
 `ICorProfilerInfo2::DoStackSnapshot`方法调用`StackSnapshotCallback`函数一次每个托管帧或第一次每次运行的非托管的帧。 如果`StackSnapshotCallback`调用探查器可能对于非托管帧的运行时，使用寄存器上下文 (所引用的`context`参数) 来执行其自己的非托管的堆栈审核。 在此情况下，Win32`CONTEXT`结构表示中的非托管帧运行最近推入镇的 CPU 状态。 尽管 Win32`CONTEXT`结构包括所有寄存器的值，但您应依赖于的堆栈指针寄存器、 帧指针寄存器、 指令指针寄存器和非易失的 （即保留） 的值仅整数寄存器。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorProf.idl  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [DoStackSnapshot 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md)  
 [分析全局静态函数](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
