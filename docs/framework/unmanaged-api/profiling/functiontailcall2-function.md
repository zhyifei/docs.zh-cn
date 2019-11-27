---
title: FunctionTailcall2 函数
ms.date: 03/30/2017
api_name:
- FunctionTailcall2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionTailcall2
helpviewer_keywords:
- FunctionTailcall2 function [.NET Framework profiling]
ms.assetid: 249f9892-b5a9-41e1-b329-28a925904df6
topic_type:
- apiref
ms.openlocfilehash: db3c3d38e0200f9849c84d7605a436816d56b813
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427426"
---
# <a name="functiontailcall2-function"></a>FunctionTailcall2 函数
通知探查器，当前正在执行的函数即将对另一个函数执行尾调用，并提供有关堆栈帧的信息。  
  
## <a name="syntax"></a>语法  
  
```cpp
void __stdcall FunctionTailcall2 (  
    [in] FunctionID         funcId,   
    [in] UINT_PTR           clientData,   
    [in] COR_PRF_FRAME_INFO func  
);  
```  
  
## <a name="parameters"></a>参数  
 `funcId`  
 中要进行尾调用的当前正在执行的函数的标识符。  
  
 `clientData`  
 中探查器前面通过[FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md)指定的函数标识符，当前正在执行的函数将进行尾调用。  
  
 `func`  
 中一个 `COR_PRF_FRAME_INFO` 值，该值指向有关堆栈帧的信息。  
  
 探查器应将此视为不透明的句柄，该句柄可传递回[ICorProfilerInfo2：： GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md)方法中的执行引擎。  
  
## <a name="remarks"></a>备注  
 尾调用的目标函数将使用当前堆栈帧，并将直接返回到进行尾调用的函数的调用方。 这意味着将不会为作为尾调用目标的函数发出[FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)回调。  
  
 `FunctionTailcall2` 函数返回后，`func` 参数的值无效，因为该值可能会更改或被销毁。  
  
 `FunctionTailcall2` 函数是回调;必须实现此方法。 实现必须使用 `__declspec`（`naked`）存储类特性。  
  
 在调用此函数之前，执行引擎不会保存任何注册。  
  
- 进入时，必须保存使用的所有寄存器，包括浮点单元（FPU）中的所有寄存器。  
  
- 退出时，必须通过弹出由其调用方推送的所有参数来还原堆栈。  
  
 `FunctionTailcall2` 的实现不应被阻止，因为它将延迟垃圾回收。 实现不应尝试垃圾回收，因为堆栈可能不处于垃圾回收友好状态。 如果尝试垃圾回收，则运行时将被阻止，直到 `FunctionTailcall2` 返回。  
  
 此外，`FunctionTailcall2` 函数不得调入托管代码或以任何方式导致托管的内存分配。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Corprof.idl .idl  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [FunctionEnter2 函数](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)
- [FunctionLeave2 函数](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)
- [SetEnterLeaveFunctionHooks2 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [分析全局静态函数](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
