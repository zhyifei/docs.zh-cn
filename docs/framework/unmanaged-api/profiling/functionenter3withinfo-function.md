---
title: FunctionEnter3WithInfo 函数
ms.date: 03/30/2017
api_name:
- FunctionEnter3WithInfo
api_location:
- mscorwks.cll
api_type:
- COM
f1_keywords:
- FunctionEnter3WithInfo
helpviewer_keywords:
- FunctionEnter3WithInfo function [.NET Framework profiling]
ms.assetid: 277c3344-d0cb-431e-beae-eb1eeeba8eea
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6a36f9b54ce7ac6a0a5a22b33a4d07150a96f40b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="functionenter3withinfo-function"></a>FunctionEnter3WithInfo 函数
通知探查器正在将控件传递给函数，并提供一个句柄，可以传递给[icorprofilerinfo3:: Getfunctionenter3info 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionenter3info-method.md)检索堆栈帧和函数自变量。  
  
## <a name="syntax"></a>语法  
  
```  
void __stdcall FunctionEnter3WithInfo(  
               [in] FunctionIDOrClientID functionIDOrClientID,  
               [in] COR_PRF_ELT_INFO eltInfo);  
```  
  
#### <a name="parameters"></a>参数  
 `functionIDOrClientID`  
 [in]控件传递到函数的标识符。  
  
 `eltInfo`  
 [in] 表示有关给定堆栈帧的信息的不透明的句柄。 此句柄仅在传递到回调过程有效。  
  
## <a name="remarks"></a>备注  
 `FunctionEnter3WithInfo`回调方法通知探查器，如函数调用，并使探查器使用[icorprofilerinfo3:: Getfunctionenter3info 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionenter3info-method.md)检查自变量值。 若要访问参数信息，请`COR_PRF_ENABLE_FUNCTION_ARGS`标志必须设置。 探查器可以使用[icorprofilerinfo:: Seteventmask 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md)设置事件标志，然后使用[icorprofilerinfo3:: Setenterleavefunctionhooks3withinfo 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)注册你此函数的实现。  
  
 `FunctionEnter3WithInfo`函数为回调; 你必须实现它。 实现必须使用`__declspec(naked)`存储类特性。  
  
 调用此函数之前，执行引擎不保存任何寄存器。  
  
-   在进入时，必须保存所有使用，包括浮点单位 (FPU) 中的寄存器。  
  
-   在退出时，你必须通过弹出已推送由其调用方的所有参数由还原堆栈。  
  
 实现`FunctionEnter3WithInfo`不应阻止，因为它会将延迟垃圾回收。 实现不应尝试的垃圾回收，因为堆栈可能不是在垃圾收集友好状态中。 如果尝试执行垃圾回收，则运行时将阻塞直到`FunctionEnter3WithInfo`返回。  
  
 `FunctionEnter3WithInfo`函数不得调入托管代码或以任何方式导致托管的内存分配。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorProf.idl  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [GetFunctionEnter3Info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionenter3info-method.md)  
 [FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)  
 [FunctionLeave3](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)  
 [分析全局静态函数](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
