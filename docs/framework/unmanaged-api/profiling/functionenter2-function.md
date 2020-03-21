---
title: FunctionEnter2 函数
ms.date: 03/30/2017
api_name:
- FunctionEnter2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionEnter2
helpviewer_keywords:
- FunctionEnter2 function [.NET Framework profiling]
ms.assetid: ce7a21f9-0ca3-4b92-bc4b-bb803cae3f51
topic_type:
- apiref
ms.openlocfilehash: 9aeb7a294beb10f9c2968e6161c72fdc362c4991
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177054"
---
# <a name="functionenter2-function"></a>FunctionEnter2 函数
通知探查器控件正在传递到函数，并提供有关堆栈帧和函数参数的信息。 此函数取代[函数Enter](functionenter-function.md)函数。  
  
## <a name="syntax"></a>语法  
  
```cpp  
void __stdcall FunctionEnter2 (  
    [in]  FunctionID                       funcId,
    [in]  UINT_PTR                         clientData,
    [in]  COR_PRF_FRAME_INFO               func,
    [in]  COR_PRF_FUNCTION_ARGUMENT_INFO  *argumentInfo  
);  
```  
  
## <a name="parameters"></a>parameters

- `funcId`

  \[in] 传递给控件的函数的标识符。

- `clientData`

  \[in] 重新映射的函数标识符，探查器以前使用[函数 IDMapper](functionidmapper-function.md)函数指定该标识符。
  
- `func`

  \[in]`COR_PRF_FRAME_INFO`指向有关堆栈帧的信息的值。
  
  探查器应将此视为不透明句柄，可在[ICorProfilerInfo2 中传回执行引擎：：get功能Info2](icorprofilerinfo2-getfunctioninfo2-method.md)方法。  
  
- `argumentInfo`

  \[in] 指向[COR_PRF_FUNCTION_ARGUMENT_INFO](cor-prf-function-argument-info-structure.md)结构的指针，用于指定函数参数的内存中的位置。

  为了访问参数信息，`COR_PRF_ENABLE_FUNCTION_ARGS`必须设置标志。 探查器可以使用[ICorProfilerInfo：：SetEventMask](icorprofilerinfo-seteventmask-method.md)方法设置事件标志。

## <a name="remarks"></a>备注  
 `func`和`argumentInfo`参数的值在`FunctionEnter2`函数返回后无效，因为值可能会更改或被销毁。  
  
 函数`FunctionEnter2`是回调;你必须实现它。 实现必须使用`__declspec`（`naked`） 存储类属性。  
  
 在调用此函数之前，执行引擎不会保存任何寄存器。  
  
- 进入时，必须保存您使用的所有寄存器，包括浮点单元 （FPU） 中的寄存器。  
  
- 在退出时，必须通过弹出其调用方推送的所有参数来还原堆栈。  
  
 的实现不应`FunctionEnter2`阻塞，因为它将延迟垃圾回收。 实现不应尝试垃圾回收，因为堆栈可能未处于垃圾回收友好状态。 如果尝试垃圾回收，运行时将阻塞，直到`FunctionEnter2`返回。  
  
 此外，`FunctionEnter2`该函数不得调用托管代码，或以任何方式导致托管内存分配。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标题：** 科尔普罗普.伊德尔  
  
 **库：** CorGuids.lib  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [FunctionLeave2 函数](functionleave2-function.md)
- [FunctionTailcall2 函数](functiontailcall2-function.md)
- [SetEnterLeaveFunctionHooks2 方法](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [分析全局静态函数](profiling-global-static-functions.md)
