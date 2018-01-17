---
title: "FunctionTailcall 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: FunctionTailcall
api_location: mscorwks.dll
api_type: COM
f1_keywords: FunctionTailcall
helpviewer_keywords: FunctionTailcall function [.NET Framework profiling]
ms.assetid: 66347e03-9a97-41e8-8f9d-89b80803f7b5
topic_type: apiref
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 223f112ba405e29b800456adca2f83e0cef6e7b8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="functiontailcall-function"></a>FunctionTailcall 函数
通知探查器当前正在执行的函数来执行对另一个函数的结尾调用。  
  
> [!NOTE]
>  `FunctionTailcall`函数已弃用.NET Framework 2.0 版中。 它将继续工作，但将会导致性能下降。 使用[FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)函数。  
  
## <a name="syntax"></a>语法  
  
```  
void __stdcall FunctionTailcall (  
    [in] FunctionID funcID  
);  
```  
  
#### <a name="parameters"></a>参数  
 `funcID`  
 [in]当前正在执行即将进行的尾调用的函数的标识符。  
  
## <a name="remarks"></a>备注  
 尾调用的目标函数将使用当前的堆栈帧，并且将直接向进行尾调用的函数的调用方返回。 这意味着， [FunctionLeave](../../../../docs/framework/unmanaged-api/profiling/functionleave-function.md)回调将不会颁发目标的尾调用的函数。  
  
 `FunctionTailcall`函数为回调; 你必须实现它。 实现必须使用`__declspec`(`naked`) 存储类特性。  
  
 调用此函数之前，执行引擎不保存任何寄存器。  
  
-   在进入时，必须保存所有使用，包括浮点单位 (FPU) 中的寄存器。  
  
-   在退出时，你必须通过弹出已推送由其调用方的所有参数由还原堆栈。  
  
 实现`FunctionTailcall`不应阻止，因为它会将延迟垃圾回收。 实现不应尝试垃圾回收，因为堆栈可能不是在垃圾收集友好状态中。 如果尝试执行垃圾回收，则运行时将阻塞直到`FunctionTailcall`返回。  
  
 此外，`FunctionTailcall`函数不能调用进入托管代码或以任何方式导致托管的内存分配。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorProf.idl  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：** 1.1、 1.0  
  
## <a name="see-also"></a>请参阅  
 [FunctionEnter2 函数](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)  
 [FunctionLeave2 函数](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)  
 [SetEnterLeaveFunctionHooks2 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)  
 [分析全局静态函数](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
