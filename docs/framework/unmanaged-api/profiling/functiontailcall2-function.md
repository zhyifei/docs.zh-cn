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
ms.openlocfilehash: 60276327617ae24e9bdcebf958613c21d3808429
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175182"
---
# <a name="functiontailcall2-function"></a>FunctionTailcall2 函数
通知探查器当前执行的函数即将对另一个函数执行尾调用，并提供有关堆栈帧的信息。  
  
## <a name="syntax"></a>语法  
  
```cpp
void __stdcall FunctionTailcall2 (  
    [in] FunctionID         funcId,
    [in] UINT_PTR           clientData,
    [in] COR_PRF_FRAME_INFO func  
);  
```  
  
## <a name="parameters"></a>parameters

- `funcId`

  \[in] 即将进行尾调用的当前执行函数的标识符。

- `clientData`

  \[in] 重新映射的函数标识符，探查器以前通过函数[IDMapper](functionidmapper-function.md)指定，该标识符是当前正在执行的函数，该函数即将进行尾调用。
  
- `func`

  \[in]`COR_PRF_FRAME_INFO`指向有关堆栈帧的信息的值。

  探查器应将此视为不透明句柄，可在[ICorProfilerInfo2 中传回执行引擎：：get功能Info2](icorprofilerinfo2-getfunctioninfo2-method.md)方法。

## <a name="remarks"></a>备注  
 尾调用的目标函数将使用当前堆栈帧，并将直接返回到发出尾调用的函数的调用方。 这意味着不会为作为尾调用目标的函数发出[函数Leave2](functionleave2-function.md)回调。  
  
 函数返回后`FunctionTailcall2`，`func`参数的值无效，因为该值可能会更改或销毁。  
  
 函数`FunctionTailcall2`是回调;你必须实现它。 实现必须使用`__declspec`（`naked`） 存储类属性。  
  
 在调用此函数之前，执行引擎不会保存任何寄存器。  
  
- 进入时，必须保存您使用的所有寄存器，包括浮点单元 （FPU） 中的寄存器。  
  
- 在退出时，必须通过弹出其调用方推送的所有参数来还原堆栈。  
  
 的实现不应`FunctionTailcall2`阻塞，因为它将延迟垃圾回收。 实现不应尝试垃圾回收，因为堆栈可能未处于垃圾回收友好状态。 如果尝试垃圾回收，运行时将阻塞，直到`FunctionTailcall2`返回。  
  
 此外，`FunctionTailcall2`该函数不得调用托管代码，或以任何方式导致托管内存分配。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标题：** 科尔普罗普.伊德尔  
  
 **库：** CorGuids.lib  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [FunctionEnter2 函数](functionenter2-function.md)
- [FunctionLeave2 函数](functionleave2-function.md)
- [SetEnterLeaveFunctionHooks2 方法](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [分析全局静态函数](profiling-global-static-functions.md)
