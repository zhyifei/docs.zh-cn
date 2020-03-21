---
title: FunctionIDMapper 函数
ms.date: 03/30/2017
api_name:
- FunctionIDMapper
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionIDMapper
helpviewer_keywords:
- FunctionIDMapper function [.NET Framework profiling]
ms.assetid: b8205b60-1893-4303-8cff-7ac5a00892aa
topic_type:
- apiref
ms.openlocfilehash: 0cf2014d7007593c51868eff0b488fdab136e362
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175169"
---
# <a name="functionidmapper-function"></a>FunctionIDMapper 函数
通知探查器，函数的给定标识符可以重新映射到要用于该函数[的函数Enter2、](functionenter2-function.md)[函数Leave2](functionleave2-function.md)和[函数尾声2](functiontailcall2-function.md)回调中使用的替代 ID。 `FunctionIDMapper` 此外还要使探查器指示它是否想要接收该函数的回调。  
  
## <a name="syntax"></a>语法  
  
```cpp  
UINT_PTR __stdcall FunctionIDMapper (  
    [in]  FunctionID  funcId,
    [out] BOOL       *pbHookFunction  
);  
```  
  
## <a name="parameters"></a>parameters

- `funcId`

  \[in] 要重新映射的函数标识符。

- `pbHookFunction`

  \[out_ 指向探查器`true`在要接收`FunctionEnter2`时`FunctionLeave2`设置的值的指针， `FunctionTailcall2`否则，它将此值设置为`false`。

## <a name="return-value"></a>返回值  
 探查器返回一个执行引擎用作替代函数标识符的值。 返回值不能为 null，除非在 `pbHookFunction` 中返回 `false`。 否则，空返回值将生成不可预知的结果，包括可能停止该过程。  
  
## <a name="remarks"></a>备注  
 该`FunctionIDMapper`函数是回调。 探查器实现了它将函数 ID 重新映射到对探查器更有用的其他标识符。 返回`FunctionIDMapper`用于任何给定函数的备用 ID。 然后，执行引擎通过将此备用 ID（除了传统的函数`clientData`ID）传递给`FunctionEnter2`、`FunctionLeave2`和`FunctionTailcall2`挂钩参数中的探查器来标识为其调用挂钩的功能来响应探查器的请求。  
  
 您可以使用[ICorProfilerInfo：：Set功能IDMapper](icorprofilerinfo-setfunctionidmapper-method.md)方法来指定`FunctionIDMapper`函数的实现。 您只能调用该方法`ICorProfilerInfo::SetFunctionIDMapper`一次，我们建议您在[ICorProfiler 回调：：初始化](icorprofilercallback-initialize-method.md)回调中调用该方法。  
  
 默认情况下，假定使用[ICorProfilerInfo：：setEventMask](icorprofilerinfo-seteventmask-method.md)设置COR_PRF_MONITOR_ENTERLEAVE标志的探查器，并且通过[ICorProfilerInfo 设置挂钩：设置EnterLeave函数Hooks](icorprofilerinfo-setenterleavefunctionhooks-method.md)或[ICorProfilerInfo2：SetEnterLeave函数Hooks2，](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)应接收 每个函数的`FunctionEnter2`、`FunctionLeave2`和`FunctionTailcall2`回调。 但是，探查器可以通过`FunctionIDMapper`设置为`pbHookFunction`有选择地避免接收某些函数的回调`false`。  
  
 探查器应容忍配置文件应用程序的多个线程同时调用同一方法/函数的情况。 在这种情况下，探查器可能会收到同`FunctionIDMapper``FunctionID`一的多个回调。 当同调用多次回调时，探查器应确定应从此回调返回相同的`FunctionID`值。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标题：** 科尔普罗普.伊德尔  
  
 **库：** CorGuids.lib  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [SetFunctionIDMapper 方法](icorprofilerinfo-setfunctionidmapper-method.md)
- [FunctionIDMapper2 函数](functionidmapper2-function.md)
- [FunctionEnter2 函数](functionenter2-function.md)
- [FunctionLeave2 函数](functionleave2-function.md)
- [FunctionTailcall2 函数](functiontailcall2-function.md)
- [分析全局静态函数](profiling-global-static-functions.md)
