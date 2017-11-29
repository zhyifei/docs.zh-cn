---
title: "FunctionEnter2 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: FunctionEnter2
api_location: mscorwks.dll
api_type: COM
f1_keywords: FunctionEnter2
helpviewer_keywords: FunctionEnter2 function [.NET Framework profiling]
ms.assetid: ce7a21f9-0ca3-4b92-bc4b-bb803cae3f51
topic_type: apiref
caps.latest.revision: "17"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 0aa1d98021dcbfc38721d7f30ad305065dced605
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="functionenter2-function"></a>FunctionEnter2 函数
控件被传递给函数，并提供帧和函数的自变量的有关堆栈的信息，请通知探查器。 此函数将取代[FunctionEnter](../../../../docs/framework/unmanaged-api/profiling/functionenter-function.md)函数。  
  
## <a name="syntax"></a>语法  
  
```  
void __stdcall FunctionEnter2 (  
    [in]  FunctionID                       funcId,   
    [in]  UINT_PTR                         clientData,   
    [in]  COR_PRF_FRAME_INFO               func,   
    [in]  COR_PRF_FUNCTION_ARGUMENT_INFO  *argumentInfo  
);  
```  
  
#### <a name="parameters"></a>参数  
 `funcId`  
 [in]控件传递到函数的标识符。  
  
 `clientData`  
 [in]重新映射的函数标识符，它通过使用以前指定探查器[FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md)函数。  
  
 `func`  
 [in]A`COR_PRF_FRAME_INFO`值，该值指向有关堆栈帧的信息。  
  
 探查器应将此视为不透明的句柄可以传递回执行引擎[icorprofilerinfo2:: Getfunctioninfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md)方法。  
  
 `argumentInfo`  
 [in]指向的指针[COR_PRF_FUNCTION_ARGUMENT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-info-structure.md)结构，它在内存中函数的参数中指定位置。  
  
 若要访问参数信息，`COR_PRF_ENABLE_FUNCTION_ARGS`必须设置标志。 探查器可以使用[icorprofilerinfo:: Seteventmask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md)方法以设置事件标志。  
  
## <a name="remarks"></a>备注  
 值`func`和`argumentInfo`参数不是有效之后`FunctionEnter2`函数返回，因为值可能会更改或将其销毁。  
  
 `FunctionEnter2`函数为回调; 你必须实现它。 实现必须使用`__declspec`(`naked`) 存储类特性。  
  
 调用此函数之前，执行引擎不保存任何寄存器。  
  
-   在进入时，必须保存所有使用，包括浮点单位 (FPU) 中的寄存器。  
  
-   在退出时，你必须通过弹出已推送由其调用方的所有参数由还原堆栈。  
  
 实现`FunctionEnter2`不应阻止，因为它会将延迟垃圾回收。 实现不应尝试垃圾回收，因为堆栈可能不是在垃圾收集友好状态中。 如果尝试执行垃圾回收，则运行时将阻塞直到`FunctionEnter2`返回。  
  
 此外，`FunctionEnter2`函数不能调用进入托管代码或以任何方式导致托管的内存分配。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorProf.idl  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [FunctionLeave2 函数](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)  
 [FunctionTailcall2 函数](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)  
 [SetEnterLeaveFunctionHooks2 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)  
 [分析全局静态函数](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
