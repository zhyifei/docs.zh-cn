---
title: ICorProfilerFunctionControl::SetCodegenFlags 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionControl.SetCodegenFlags
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionControl::SetCodegenFlags
helpviewer_keywords:
- ICorProfilerFunctionControl::SetCodegenFlags method [.NET Framework profiling]
- SetCodegenFlags method, ICorProfilerFunctionControl interface [.NET Framework profiling]
ms.assetid: a2d5daa5-b990-4ae5-bf2a-c0862fe58bd7
topic_type:
- apiref
ms.openlocfilehash: 75414ec3d2b30fe8afc5db1e97c81f34b29a3115
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76864669"
---
# <a name="icorprofilerfunctioncontrolsetcodegenflags-method"></a>ICorProfilerFunctionControl::SetCodegenFlags 方法
设置[COR_PRF_CODEGEN_FLAGS](cor-prf-codegen-flags-enumeration.md)枚举中的一个或多个标志，以控制实时（JIT）重新编译函数的代码生成。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT SetCodegenFlags(  
    [in] DWORD flags);  
```  
  
## <a name="parameters"></a>参数  
 `flags`  
 中[COR_PRF_CODEGEN_FLAGS](cor-prf-codegen-flags-enumeration.md)枚举中的一个或多个标志。  
  
## <a name="remarks"></a>备注  
 探查器通过[ICorProfilerCallback4：： GetReJITParameters](icorprofilercallback4-getrejitparameters-method.md)回调获取此接口的实例。 `SetCodegenFlags` 允许探查器控制重新编译函数的代码生成。 与所有其他 JIT 重新编译参数一样，代码生成标志适用于函数的所有实例。  
  
 编译函数时，JIT 编译器会将这些编译标志连同其他源指定的其他标志一起考虑。  其他源包括调试器、启动时探查器设置的全局标志 `COR_PRF_DISABLE_OPTIMIZATIONS``COR_PRF_DISABLE_INLINING` （使用[ICorProfilerInfo：： SetEventMask](icorprofilerinfo-seteventmask-method.md)方法）、探查器的[ICorProfilerCallback：： JITInlining](icorprofilercallback-jitinlining-method.md)回调。  JIT 编译器为请求最小优化量的源提供优先级别。  例如，如果探查器在启动时指定了 `COR_PRF_DISABLE_INLINING`，但没有在[ICorProfilerFunctionControl：： SetCodegenFlags](icorprofilerfunctioncontrol-setcodegenflags-method.md)回调中指定 `COR_PRF_CODEGEN_DISABLE_INLINING`，则仍将禁用内联。  同样，如果探查器未在 `SetCodegenFlags`中指定 `COR_PRF_CODEGEN_DISABLE_INLINING`，而是通过使用[ICorProfilerCallback：： JITInlining](icorprofilercallback-jitinlining-method.md)回调禁用内联，则禁用内联。  
  
## <a name="requirements"></a>需求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [ICorProfilerFunctionControl 接口](icorprofilerfunctioncontrol-interface.md)
