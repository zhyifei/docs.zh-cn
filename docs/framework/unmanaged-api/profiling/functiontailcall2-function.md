---
title: "FunctionTailcall2 函数"
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a9d6ccb08bc09bea2ec9e9a49333c92da8cb5695
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="functiontailcall2-function"></a>FunctionTailcall2 函数
当前正在执行的函数，即将执行尾调用给另一个函数，并提供有关堆栈帧的信息，请通知探查器。  
  
## <a name="syntax"></a>语法  
  
```  
void __stdcall FunctionTailcall2 (  
    [in] FunctionID         funcId,   
    [in] UINT_PTR           clientData,   
    [in] COR_PRF_FRAME_INFO func  
);  
```  
  
#### <a name="parameters"></a>参数  
 `funcId`  
 [in]当前正在执行即将进行的尾调用的函数的标识符。  
  
 `clientData`  
 [in]重新映射的函数标识符，它通过以前指定探查器[FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md)，即将进行的尾调用的当前正在执行函数。  
  
 `func`  
 [in]A`COR_PRF_FRAME_INFO`值，该值指向有关堆栈帧的信息。  
  
 探查器应将此视为不透明的句柄可以传递回执行引擎[icorprofilerinfo2:: Getfunctioninfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md)方法。  
  
## <a name="remarks"></a>备注  
 尾调用的目标函数将使用当前的堆栈帧，并且将直接向进行尾调用的函数的调用方返回。 这意味着， [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)回调将不会颁发目标的尾调用的函数。  
  
 值`func`参数不是有效之后`FunctionTailcall2`函数返回，因为值可能会更改或将其销毁。  
  
 `FunctionTailcall2`函数为回调; 你必须实现它。 实现必须使用`__declspec`(`naked`) 存储类特性。  
  
 调用此函数之前，执行引擎不保存任何寄存器。  
  
-   在进入时，必须保存所有使用，包括浮点单位 (FPU) 中的寄存器。  
  
-   在退出时，你必须通过弹出已推送由其调用方的所有参数由还原堆栈。  
  
 实现`FunctionTailcall2`不应阻止，因为它会将延迟垃圾回收。 实现不应尝试垃圾回收，因为堆栈可能不是在垃圾收集友好状态中。 如果尝试执行垃圾回收，则运行时将阻塞直到`FunctionTailcall2`返回。  
  
 此外，`FunctionTailcall2`函数不能调用进入托管代码或以任何方式导致托管的内存分配。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorProf.idl  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [FunctionEnter2 函数](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)  
 [FunctionLeave2 函数](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)  
 [SetEnterLeaveFunctionHooks2 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)  
 [分析全局静态函数](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
