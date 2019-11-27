---
title: FunctionLeave 函数
ms.date: 03/30/2017
api_name:
- FunctionLeave
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionLeave
helpviewer_keywords:
- FunctionLeave function [.NET Framework profiling]
ms.assetid: 18e89f45-e068-426a-be16-9f53a4346860
topic_type:
- apiref
ms.openlocfilehash: 774a5d4e48f00ea8c28977f3f685dcd5a8da3199
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440585"
---
# <a name="functionleave-function"></a>FunctionLeave 函数
通知探查器某个函数将要返回到调用方。  
  
> [!NOTE]
> `FunctionLeave` 函数在 .NET Framework 2.0 中已弃用。 它将继续运行，但会导致性能下降。 改为使用[FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)函数。  
  
## <a name="syntax"></a>语法  
  
```cpp  
void __stdcall FunctionLeave (  
    [in] FunctionID funcID  
);  
```  
  
## <a name="parameters"></a>参数  
 `funcID`  
 中返回的函数的标识符。  
  
## <a name="remarks"></a>备注  
 `FunctionLeave` 函数是回调;必须实现此方法。 实现必须使用 `__declspec`（`naked`）存储类特性。  
  
 在调用此函数之前，执行引擎不会保存任何注册。  
  
- 进入时，必须保存使用的所有寄存器，包括浮点单元（FPU）中的所有寄存器。  
  
- 退出时，必须通过弹出由其调用方推送的所有参数来还原堆栈。  
  
 `FunctionLeave` 的实现不应被阻止，因为它将延迟垃圾回收。 实现不应尝试垃圾回收，因为堆栈可能不处于垃圾回收友好状态。 如果尝试垃圾回收，则运行时将被阻止，直到 `FunctionLeave` 返回。  
  
 此外，`FunctionLeave` 函数不得调入托管代码或以任何方式导致托管的内存分配。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Corprof.idl .idl  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** 1.1、1。0  
  
## <a name="see-also"></a>另请参阅

- [FunctionEnter2 函数](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)
- [FunctionLeave2 函数](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)
- [FunctionTailcall2 函数](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)
- [SetEnterLeaveFunctionHooks2 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [分析全局静态函数](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
